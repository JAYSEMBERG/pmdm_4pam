La práctica consiste en crear un nuevo proyecto llamado Proyecto1, con dominio
android.ejemplo.es y la ubicación tu carpeta home (UBUNTU) o raiz (Windows). 

Seleccionaremos como dispositivo base API 21: Android 5 (Lollipop), y añadiremos  una actividad vacía (Empty Activity) con nombre Actividad1 y el nombre de su vista activity_actividad1.

A continuación, crea una segunda actividad denominada Actividad2 (lo mas sencillo es copiar, pegar  y renombrar Actividad1, dentro del explorador de proyectos). Igualmente debes hacer con el fichero XML de la vista (renómbralo con activity_actividad2.xml). Ahora asocia en la segunda actividad la vista a este fichero. 

Retoca el objeto de texto de segunda actividad y sustituye el "Hello World!"
por otra cadena distinta. 

A continuación, añade el siguiente código al método onDestroy de la clase Actividad1.
```java
Intent ejemplo = new Intent (this.Actividad2.class):
startActivity(ejemplo);
```

Al ejecutarla en el emulador, si pulsamos el botón Atrás del teléfono, provocaremos  la destrucción de la Actividad1 y debería abrirse la Actividad2, pero la aplicación y da error, esto es debido a que no has declarado esta segunda actividad en el Manifest. Soluciona el problema agregando las lineas necesarias en dicho archivo.

Retoca ahora el código de Actividad2 y  añade el siguiente código al método `onDestroy`:

```java
Intent ejemplo= new Intent (Intent.ACTION VIEW);
ejemplo.setdata(ur1.parse"https://www.ieslosalbares.es")):
startActivity(ejemplo);
```

Te saltará un error de librerías no existentes. Para cargar las librerías tan solo debes colocar el ratón sobre los elementos desconocidos y pulsar Alt+Intro).

Prueba que la aplicación se ha ejecutado correctamente.

