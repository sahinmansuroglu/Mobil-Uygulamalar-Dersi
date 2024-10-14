#ListBox kullanımı:

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <ListView
        android:id="@+id/listViewItems"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:dividerHeight="1dp"/>
</LinearLayout>

```


```java

public class MainActivity extends AppCompatActivity {

    private ListView listViewItems;
    private ArrayList<String> items;
    private ArrayAdapter<String> adapter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        listViewItems = findViewById(R.id.listViewItems);

        // Liste için örnek veriler
        items = new ArrayList<>();
        items.add("Öğe 1");
        items.add("Öğe 2");
        items.add("Öğe 3");
        items.add("Öğe 4");
        items.add("Öğe 5");

        // Adapter oluşturma ve listeyi bağlama
        adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, items);
        listViewItems.setAdapter(adapter);
    }
}

```

Açıklama:
XML Layout:

LinearLayout: Ana düzen.
ListView: Liste öğelerini görüntülemek için.
Java Kodu:

ArrayList: Liste öğelerini saklamak için.
ArrayAdapter: ListView'ye veri eklemek için.
Örnek veriler ekleyerek ListView'ye bağladık.
ListView Kullanımı:
ListView öğeleri kaydırarak görüntülemenize olanak tanır.
ArrayAdapter ile kolayca veri bağlayabilirsiniz.
Kullanıcı bir öğeye tıkladığında olay dinleyicileri ekleyerek farklı işlemler gerçekleştirebilirsiniz.

Tıklama Olayı Ekleme
Öğelere tıkladığınızda bir mesaj göstermek için bir OnItemClickListener ekleyebilirsiniz:

```java
listViewItems.setOnItemClickListener((parent, view, position, id) -> {
    String selectedItem = items.get(position);
    Toast.makeText(MainActivity.this, "Seçilen: " + selectedItem, Toast.LENGTH_SHORT).show();
});

```




```xml
```


```java
```



```xml
```


```java
```



```xml
```


```java
```
