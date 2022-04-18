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

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson89/screenshot/app-lesson84.PNG)


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

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson89/screenshot/app-lesson85.PNG)


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

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson89/screenshot/app-lesson86.PNG)


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

3. Resultado, ao clicar no botão é exibido um calendário:

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson89/screenshot/app-lesson87.PNG)


<h2>Lição 88 - Exibindo a data</h2>

1. Inserindo ID no componente TextView que exibe a data:

``` xml
<TextView
    android:id="@+id/tvSelectedDate"
    ...
    />
```

2. Dentro do metódo clickDatePicker():

``` java
    fun clickDatePicker(){
            val myCalendar = Calendar.getInstance()
            val year = myCalendar.get(Calendar.YEAR)
            val month = myCalendar.get(Calendar.MONTH)
            val day = myCalendar.get(Calendar.DAY_OF_MONTH)

            DatePickerDialog(this, DatePickerDialog.OnDateSetListener{view,selectedYear,selectedMonth,selectedDayOfMonth ->
                //Toast.makeText(this,"btnDatePicker pressed", Toast.LENGTH_LONG).show()

                val selectedDate = "$selectedDayOfMonth/${selectedMonth+1}/$selectedYear"
                tvSelectedDate?.text = selectedDate

                val sdf = SimpleDateFormat("dd/MM/yyyy",Locale.ENGLISH)

                val theDate = sdf.parse(selectedDate)

            },
            year,
            month,
            day).show()
    }
```

3. Resutlado, após selecionar a data no calendário o componente TextView será preenchido:

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson89/screenshot/app-lesson88.png)

<h2>Lição 89 - Calculo da data</h2>

1. Os componente tvSelectedDate recebe a data selecionada no data picker.
   Já o componente tvAgeInMinutes recebe o calculo realizado no metódo clickDatePicker().
   E o componente btnDatePicker acessa o metódo clickDatePicker().
   O metódo clickDatePicker(), utiliza a classe Calendar e DatePickerDialog para


``` java
private fun clickDatePicker(){
        val myCalendar = Calendar.getInstance()
        val year = myCalendar.get(Calendar.YEAR)
        val month = myCalendar.get(Calendar.MONTH)
        val day = myCalendar.get(Calendar.DAY_OF_MONTH)
        val dpd = DatePickerDialog(this, DatePickerDialog.OnDateSetListener{_,selectedYear,selectedMonth,selectedDayOfMonth ->

            val selectedDate = "$selectedDayOfMonth/${selectedMonth+1}/$selectedYear"
            tvSelectedDate?.text = selectedDate

            val sdf = SimpleDateFormat("dd/MM/yyyy",Locale.ENGLISH)

            val theDate = sdf.parse(selectedDate)

            theDate?.let{
                val selectedDateInMinutes = theDate.time / 60000

                val currentDate = sdf.parse(sdf.format(System.currentTimeMillis()))

                currentDate?.let{
                    val currentDateInMinutes = currentDate.time / 60000

                    val differenceInMinutes = currentDateInMinutes - selectedDateInMinutes

                    tvAgeInMinutes?.text = differenceInMinutes.toString()
                }
            }
        },
        year,
        month,
        day)
        dpd.datePicker.maxDate = System.currentTimeMillis() - 86400000
        dpd.show()
    }
```

2. Resultado:

O usuário utiliza o botão "Selected Date" para exibir o Calendário.
O usuário seleciona uma data e clica em OK.
O aplicativo calcula a diferença da data selecionada e a data corrente.
A diferença é calculada em minutos.

![ScreenShot App](https://github.com/fabiocaettano/android-calculate-age/blob/lesson89/screenshot/app-lesson89.png)


<h1>Referência</h1>

![Curso Udemy](https://www.udemy.com/share/102Jgo3@-7uk2kJOfwYBE8siVK-4NfFoSO3KPB3dU29_XberNQ51o0o1xaOTFN57QIxXlJdD/)