dado la siguiente plantilla de diseño:

```code
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="24dp"
        android:text="@string/question_text" />
		<LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/boton_verdadero" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/boton_falso" />

    </LinearLayout>
</LinearLayout>
```

Se pide crear una aplicación para Android que simule un juego de preguntas y respuestas con las siguientes especificaciones:

- El juego constará de tres preguntas organizadas en tres "Activity".
- Deberá controlar el numero de preguntas acertadas mediante el envío de extras entre actividades.
- Al finalizar el juego habrá una cuarta "activity" donde mostrará el número de preguntas acertadas.
- OPCIONAL: se puede mostrar un snackbar en cada activity diciendo si has acertado o no y la cuenta de preguntas acertadas.


## VERSION 2
La vesrión incluye solo una activitiy y cambiaremos el enlace entre el codigo y el layout por LayoutInflate

La linea 
`setContentView(R.layout.activity_main)`

debe ser reemplazada por:

```java
binding = ActivityMainBinding.inflate(layoutInflater)
setContentView(binding.root)
```

Y el acceso a los elementos del layout se hace de la siguiente manera:
1. Eliminados las referencias de `findViewById`
   `botonVerdadero = findViewById(R.id.boton_verdadero)`
   `botonFalso = findViewById(R.id.boton_falso)`
2. Y en el clickListner accedemos directamente al elemento por bindeo:
    Reemplazamos `botonVerdadero.setOnClickListener {`  por
    `binding.botonVerdadero.setOnClickListener { `.

La lista de preguntas es recomendable que se guarde en HashMap o en una lista:

```
private val bancoPreguntas = listOf(
	Question(R.string.pregunta1, true),
	Question(R.string.pregunta2, true),
	Question(R.string.pregunta3, false),
	Question(R.string.pregunta4, false),
	Question(R.string.pregunta5, true),
	Question(R.string.pregunta16, true))
```
#### RECURSOS
https://jarroba.com/inflate-en-android-inflar-y-adjuntar-views/

https://developer.android.com/topic/libraries/view-binding#java

https://devexperto.com/view-binding/

https://developer.android.com/guide/topics/resources/layout-resource

## VERSION 3

Vamos a implementar las preguntas y respuestas en un ViewModel, de tal manera que implementaremos la capa de modelo para la gestión de datos.

#### RECURSOS
https://developer.android.com/topic/libraries/architecture/viewmodel?hl=es-419#java

https://developer.android.com/jetpack/androidx/releases/lifecycle#groovy

https://medium.com/androiddevelopers/viewmodels-a-simple-example-ed5ac416317e
