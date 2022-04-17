<h1>Curso Udemy - Android 12 & Kotlin Development Masterclass</h1>
<h3> Instrutor Denis Panjuta </h3>

<h1>App Calculate Age</h1>

<h2>Lesson 84 - Setting up the UI</h2>

1. No arquivo <u>src>>main>>res>>values>>colors.xml</u> foi incluida duas referências de cores.

``` xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    ...
    <color name="textBlue">#264653</color>
    <color name="bgColor">#e9c46a</color>
</resources>

```

2. No arquivo <u>src>>main>>res>>layout>>activity.main.xml</u> a estrutura foi alterada para <b>LinearLayout</b>.
   E foi incluido as configurações: orientation, background e gravity.
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    ...
    android:orientation="vertical"
    android:background="@color/bgColor"
    android:gravity="center_horizontal">
```
3. Ainda no arquivo <u>activit.main.xml</u> foi configurado o componente TextView:

``` xml
<TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="CALCULATE YOUR"
        android:textColor="@color/textBlue"
        android:textSize="25sp"
        android:textStyle="bold"/>
```

4. Resultado:

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/main/app/src/main/res/drawable/screenshot/app-lesson84.PNG)



