Proje 1: Kullanıcı Adı ve Hoşgeldin Mesajı
Bu projede kullanıcı bir EditText’e adını yazacak ve butona basınca, bir TextView’da hoşgeldin mesajı gösterilecek.

XML (activity_main.xml)

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <EditText
        android:id="@+id/editTextName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Adınızı girin" />

    <Button
        android:id="@+id/buttonGreet"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hoşgeldin Deyin"
        android:layout_gravity="center"
        android:layout_marginTop="16dp" />

    <TextView
        android:id="@+id/textViewGreeting"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text=""
        android:textSize="18sp"
        android:layout_gravity="center"
        android:layout_marginTop="16dp" />
</LinearLayout>

```
MainActivity.java
```java
public class MainActivity extends AppCompatActivity {

    private EditText editTextName;
    private TextView textViewGreeting;
    private Button buttonGreet;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextName = findViewById(R.id.editTextName);
        textViewGreeting = findViewById(R.id.textViewGreeting);
        buttonGreet = findViewById(R.id.buttonGreet);

        buttonGreet.setOnClickListener(v -> {
            String name = editTextName.getText().toString();
            textViewGreeting.setText("Hoşgeldin, " + name + "!");
        });
    }
}
```

Proje 2: Basit Hesap Makinesi
Kullanıcı iki sayı girecek ve butona basınca sonuç TextView’da gösterilecek.

XML (activity_main.xml)
```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <EditText
        android:id="@+id/editTextNumber1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Birinci sayıyı girin"
        android:inputType="number" />

    <EditText
        android:id="@+id/editTextNumber2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="İkinci sayıyı girin"
        android:inputType="number"
        android:layout_marginTop="8dp" />

    <Button
        android:id="@+id/buttonCalculate"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Topla"
        android:layout_gravity="center"
        android:layout_marginTop="16dp" />

    <TextView
        android:id="@+id/textViewResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text=""
        android:textSize="18sp"
        android:layout_gravity="center"
        android:layout_marginTop="16dp" />
</LinearLayout>
```
MainActivity.java
```java
public class MainActivity extends AppCompatActivity {

    private EditText editTextNumber1, editTextNumber2;
    private TextView textViewResult;
    private Button buttonCalculate;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextNumber1 = findViewById(R.id.editTextNumber1);
        editTextNumber2 = findViewById(R.id.editTextNumber2);
        textViewResult = findViewById(R.id.textViewResult);
        buttonCalculate = findViewById(R.id.buttonCalculate);

        buttonCalculate.setOnClickListener(v -> {
            String num1 = editTextNumber1.getText().toString();
            String num2 = editTextNumber2.getText().toString();

            if (!num1.isEmpty() && !num2.isEmpty()) {
                int sum = Integer.parseInt(num1) + Integer.parseInt(num2);
                textViewResult.setText("Sonuç: " + sum);
            }
        });
    }
}

```java
Proje 3: Şifre Giriş Sistemi
Bu projede kullanıcı şifresini girecek ve butona basarak şifresinin doğru olup olmadığını TextView’da görecek.

XML (activity_main.xml)
```xml

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <EditText
        android:id="@+id/editTextPassword"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Şifrenizi girin"
        android:inputType="textPassword" />

    <Button
        android:id="@+id/buttonLogin"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Giriş Yap"
        android:layout_gravity="center"
        android:layout_marginTop="16dp" />

    <TextView
        android:id="@+id/textViewLoginResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text=""
        android:textSize="18sp"
        android:layout_gravity="center"
        android:layout_marginTop="16dp" />
</LinearLayout>
```
```java
public class MainActivity extends AppCompatActivity {

    private EditText editTextPassword;
    private TextView textViewLoginResult;
    private Button buttonLogin;
    private final String correctPassword = "12345";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextPassword = findViewById(R.id.editTextPassword);
        textViewLoginResult = findViewById(R.id.textViewLoginResult);
        buttonLogin = findViewById(R.id.buttonLogin);

        buttonLogin.setOnClickListener(v -> {
            String enteredPassword = editTextPassword.getText().toString();
            if (enteredPassword.equals(correctPassword)) {
                textViewLoginResult.setText("Giriş başarılı!");
            } else {
                textViewLoginResult.setText("Şifre yanlış.");
            }
        });
    }
}
```
