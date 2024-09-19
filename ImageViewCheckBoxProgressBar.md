Proje 1: Resim Görüntüleme ve Gizleme
Bu projede bir ImageView kullanıcının seçimine göre CheckBox ile gösterilip gizlenecek.

XML (activity_main.xml)
```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <ImageView
        android:id="@+id/imageViewExample"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@drawable/example_image"
        android:layout_gravity="center" />

    <CheckBox
        android:id="@+id/checkBoxToggleImage"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Resmi Göster"
        android:checked="true"
        android:layout_gravity="center"
        android:layout_marginTop="16dp" />
</LinearLayout>
```

MainActivity.java
```java
public class MainActivity extends AppCompatActivity {

    private ImageView imageView;
    private CheckBox checkBoxToggleImage;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageViewExample);
        checkBoxToggleImage = findViewById(R.id.checkBoxToggleImage);

        checkBoxToggleImage.setOnCheckedChangeListener((buttonView, isChecked) -> {
            if (isChecked) {
                imageView.setVisibility(View.VISIBLE);
            } else {
                imageView.setVisibility(View.GONE);
            }
        });
    }
}
```
Proje 2: Onaylama ve İlerlemenin Gösterilmesi
Bu projede, bir ProgressBar kullanıcıya tamamlanan bir işlemi gösterecek. CheckBox işaretlenirse işlem tamamlanmış kabul edilecek.

XML (activity_main.xml)
```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <ProgressBar
        android:id="@+id/progressBarExample"
        style="?android:attr/progressBarStyleHorizontal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:max="100"
        android:progress="50" />

    <CheckBox
        android:id="@+id/checkBoxComplete"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="İşlemi Tamamla"
        android:layout_gravity="center"
        android:layout_marginTop="16dp" />
</LinearLayout>
```

MainActivity.java
```java
public class MainActivity extends AppCompatActivity {

    private ProgressBar progressBar;
    private CheckBox checkBoxComplete;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        progressBar = findViewById(R.id.progressBarExample);
        checkBoxComplete = findViewById(R.id.checkBoxComplete);

        checkBoxComplete.setOnCheckedChangeListener((buttonView, isChecked) -> {
            if (isChecked) {
                progressBar.setProgress(100);
            } else {
                progressBar.setProgress(50);
            }
        });
    }
}
```

