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

- El juego debe tener entre 15 y 20 preguntas.
- (1 punto) El juego constará de tres tres "Activity": Una para la pantalla inicial, otra para la pantalla de las preguntas y otra para mostrar los resultados. 
- (1 punto) Para gestionar los elementos de la aplicación, se utilizará el método de `binding`. 
- (2 puntos) Es estado del juego (pregunta actual, aciertos, nombre usuario, ...) se almacenará en la estructura que el alumno considere pero implementada en un `ViewModel`. 
- (2 puntos) Las preguntas se obtendrán de una colección de elementos de [Google firestore](https://console.firebase.google.com/u/0/). Cada pregunta será un objeto que modelizará el elemento de la colección descargado de Firestore. 
  - El objeto que modele la pregunta debe tener, al menos, los siguientes atributos: id(sera un indice con el número de orden de la pregunta), textoPregunta, respUno, respDos, respTres, respCuatro, respCorrecta.
- (1 punto) Se debe mostrar un `snackbar` en cada activity diciendo si has acertado o no y la cuenta de preguntas acertadas.
- (2 puntos) Incluir imágenes, sonidos y/o videos en las preguntas.
- (2 puntos) En la pantalla de inicio, se debe pedir un nombre, y una vez finalizado el juego, se suben a firestore los resultados junto con la puntuación para llevar un registro de participantes.

### RECURSOS
- https://jarroba.com/inflate-en-android-inflar-y-adjuntar-views/
- https://developer.android.com/topic/libraries/view-binding#java
- https://devexperto.com/view-binding/
- https://developer.android.com/guide/topics/resources/layout-resource
- https://developer.android.com/topic/libraries/architecture/viewmodel?hl=es-419#java
- https://developer.android.com/jetpack/androidx/releases/lifecycle#groovy
- https://medium.com/androiddevelopers/viewmodels-a-simple-example-ed5ac416317e
