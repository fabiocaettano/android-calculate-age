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

2. No arquivo <u>src>>main>>res>>layout>>activity_main.xml</u> a estrutura foi alterada
para <b>LinearLayout</b>. E foi incluido as configurações: orientation, background e gravity.

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    ...
    android:orientation="vertical"
    android:background="@color/bgColor"
    android:gravity="center_horizontal">
```

3. Ainda no arquivo <u>activity_main.xml</u> foi configurado o componente TextView:

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

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson86/screenshot/app-lesson84.PNG)


<h2>Lição 85 - Adicionando mais TextViews e entendo SP, DP e pixels.</h2>

1. Conceitos:

<ul>
<li> px : corresponde ao pixel atual da tela;</li>

<li> dp: é uma unidade fixa; recomendado para posicionar e dimensionar os componentes; </li>

<li> sp: é escalável conforme o phone; recomendado para utilizar com fonts. </li>
</ul>

2. No arquivo <u>app >> src >> main >> res >> values >> colors.xml</u> foi incluido o background
do botão

``` xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    ...
    <color name="btnBgColor">#2a9d8f</color>
</resources>
```

3. No arquivo <u>src>>main>>res>>layout>>activity_main.xml</u> inserido mais 03 componentes:

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

4. Ainda no arquivo <u>activity_main.xml</u> foi inserido um "padding" para os componentes:

``` xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    ...
    android:padding="16dp">
```

5. Resultado:

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson86/screenshot/app-lesson85.PNG)


<h2>Lição 86 - Finaliando Interface</h2>


1. Alterado a cor primária do tema, no arquivo <u>src >> main >> res >> values >> themes.xml</ul>:

``` xml
<resources xmlns:tools="http://schemas.android.com/tools">
    <style name="Theme.DOBCalc" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
        ...
        <item name="colorPrimary">@color/textBlue</item>
        ...
    </style>
</resources>
```

2. No arquivo <u>app >> src >> main >> res >> values >> colors.xml</u> alterada a cor do background:

``` xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    ...
    <color name="bgColor">#F3E2B9</color>
    ...
</resources>
```

3. Alterado o titulo da aplicação no arquivo <u>app >> src >> main >> res >> values >> strings.xml</u>

``` xml
<resources>
    <string name="app_name">Age In Minutes</string>
</resources>
```

4. No arquivo <u>src>>main>>res>>layout>>activity_main.xml</u> foi alterado o componente Button.
   Incluído novos componentes:

``` xml
    <Button
        android:id="@+id/button3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="SELECT DATE"
        android:textSize="18sp"
        android:textColor="@color/LightGrey"
        android:backgroundTint="@color/btnBgColor"/>

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="04/11/1974"
        android:textColor="@color/textBlue"
        android:textSize="25sp"
        android:textStyle="bold"/>
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="Selected Date"
        android:textColor="@color/LightGrey"
        android:textSize="20sp"
        android:textStyle="bold"/>

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="14000000"
        android:textColor="@color/textBlue"
        android:textSize="35sp"
        android:textStyle="bold"/>
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="Selected Date"
        android:textColor="@color/LightGrey"
        android:textSize="20sp"
        android:textStyle="bold"/>
```

5. Resultados:

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson86/screenshot/app-lesson86.PNG)


<h2>Lição 87 - Date Picker Dialog</h2>

1. No arquivo <u>src>>main>>res>>layout>>activity_main.xml</u> foi configurado o id do Botão.

``` xml
    <Button
    android:id="@+id/btnDatePicker"
    ...
    />
```

2. No arquivo <ul>app >> src >> main >> java >> com.fabiocaettano74.dobcalc >> MainActivity</ul>
configurar ação do botão para interagir com o componente DatePicker:

``` java
    fun clickDatePicker(){
        val myCalendar = Calendar.getInstance()
        val year = myCalendar.get(Calendar.YEAR)
        val month = myCalendar.get(Calendar.MONTH)
        val day = myCalendar.get(Calendar.DAY_OF_MONTH)

        DatePickerDialog(this, DatePickerDialog.OnDateSetListener{view,year,month,dayOfMonth ->
            Toast.makeText(this,"btnDatePicker pressed", Toast.LENGTH_LONG).show()
        },
        year,
        month,
        day).show()
    }
```

