<h1>Curso Udemy - Android 12 & Kotlin Development Masterclass</h1>
<h3> Instrutor Denis Panjuta </h3>

<h1>App Calculate Age</h1>

<h2>Lição 84 - Configurando a Interface</h2>

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
3. Ainda no arquivo <u>activity.main.xml</u> foi configurado o componente TextView:

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

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson85/screenshot/app-lesson84.PNG)


<h2>Lição 85 - Adicionando mais TextViews e entendo SP, DP e pixels.</h2>

## px : corresponde ao pixel atual da tela;
## dp: é uma unidade fixa; recomendado para posicionar e dimensionar os componentes;
## sp: é escalável conforme o phone; recomendado para utilizar com fonts.


No arquivo <u>src>>main>>res>>layout>>activity.main.xml</u>

1. No arquivo <u>src>>main>>res>>values>>colors.xml</u> foi incluido o background
do botão

``` xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    ...
    <color name="btnBgColor">#2a9d8f</color>
</resources>

```

2. No arquivo <u>activity.main.xml</u> inserido mais 03 componentes:

``` xml
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="AGE"
        android:padding="10dp"
        android:background="@color/textBlue"
        android:textColor="@color/white"
        android:textSize="25sp"
        android:textStyle="bold"/>

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="IN MINUTES"
        android:textColor="@color/textBlue"
        android:textSize="25sp"
        android:textStyle="bold"/>

    <Button
        android:id="@+id/button3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Button"
        android:textColor="@color/black"
        android:backgroundTint="@color/white"/>
```

3. Ainda no arquivo <u>activity.main.xml</u> foi inserido um "padding" para os componentes:

``` xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    ...
    android:padding="16dp">
```

4. Resultado:

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson85/screenshot/app-lesson85.PNG)


