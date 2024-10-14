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
# TODO LİST


Tabii ki! Aşağıda bir ListView kullanarak öğeleri ekleyip çıkarabileceğiniz bir To-Do List uygulaması örneği veriyorum. Bu örnekte kullanıcı, yeni görevler ekleyebilir ve mevcut görevleri kaldırabilir.

1. Layout Tasarımı
XML (activity_main.xml)
```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <EditText
        android:id="@+id/editTextTask"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Yeni görev ekleyin" />

    <Button
        android:id="@+id/buttonAddTask"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Görev Ekle" />

    <ListView
        android:id="@+id/listViewTasks"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:dividerHeight="1dp" />

    <Button
        android:id="@+id/buttonRemoveTask"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Görev Sil" />
</LinearLayout>

```

2. Java Kodu
Java (MainActivity.java)

```java
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ListView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
import java.util.ArrayList;

public class MainActivity extends AppCompatActivity {

    private EditText editTextTask;
    private Button buttonAddTask, buttonRemoveTask;
    private ListView listViewTasks;
    private ArrayList<String> taskList;
    private ArrayAdapter<String> adapter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextTask = findViewById(R.id.editTextTask);
        buttonAddTask = findViewById(R.id.buttonAddTask);
        buttonRemoveTask = findViewById(R.id.buttonRemoveTask);
        listViewTasks = findViewById(R.id.listViewTasks);

        taskList = new ArrayList<>();
        adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, taskList);
        listViewTasks.setAdapter(adapter);

        // Görev ekleme butonu tıklama olayı
        buttonAddTask.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String task = editTextTask.getText().toString().trim();
                if (!task.isEmpty()) {
                    taskList.add(task);
                    adapter.notifyDataSetChanged();
                    editTextTask.setText("");
                } else {
                    Toast.makeText(MainActivity.this, "Lütfen bir görev girin.", Toast.LENGTH_SHORT).show();
                }
            }
        });

        // Görev silme butonu tıklama olayı
        buttonRemoveTask.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                int position = listViewTasks.getCheckedItemPosition();
                if (position != ListView.INVALID_POSITION) {
                    taskList.remove(position);
                    adapter.notifyDataSetChanged();
                } else {
                    Toast.makeText(MainActivity.this, "Silmek için bir görev seçin.", Toast.LENGTH_SHORT).show();
                }
            }
        });
    }
}

```


Açıklama:
XML Layout:

EditText: Kullanıcıdan görev girişi almak için.
Button (Görev Ekle): Yeni görev eklemek için.
ListView: Görevlerin listeleneceği alan.
Button (Görev Sil): Seçilen görevi silmek için.
Java Kodu:

ArrayList: Görevleri saklamak için.
ArrayAdapter: ListView'ye veri eklemek için.
Kullanıcı, EditText alanına görev yazdıktan sonra "Görev Ekle" butonuna tıkladığında, görev listeye eklenir.
"Görev Sil" butonuna tıklandığında, ListView'de seçilen görev kaldırılır.
Kullanım:
Kullanıcı görev eklemek için metin kutusuna bir görev yazar ve "Görev Ekle" butonuna tıklar.
Liste görünümünden bir görev seçip "Görev Sil" butonuna basarak seçilen görevi kaldırabilir.


```xml
```


```java
```



```xml
```


```java
```
