Android'deki Activity Yaşam Döngüsü, bir uygulamanın ekranı açıldığında, kullanıldığında, arka plana alındığında veya kapandığında hangi süreçlerden geçtiğini belirler. Android, bu yaşam döngüsünü kontrol etmek için çeşitli geri çağrı (callback) yöntemlerini kullanır. İşte temel aşamaları:

onCreate(): Aktivite ilk kez oluşturulduğunda çağrılır. Genellikle kullanıcı arayüzünü başlatmak ve etkinliğe ait değişkenleri tanımlamak için kullanılır.

Örnek kullanım: setContentView(R.layout.main_activity);
onStart(): Aktivite görünür hale gelir ancak henüz kullanıcı ile etkileşimde değildir. Aktivitenin ekranda belirmesi bu aşamada olur.

onResume(): Aktivite kullanıcının etkileşime geçebileceği duruma gelir. Aktivite artık ön plandadır ve kullanıcı ile doğrudan etkileşime girebilir.

onPause(): Kullanıcı aktiviteden çıkarken (örneğin, bir başka uygulamaya geçerken) bu aşama devreye girer. Aktivite ön plandan kaybolurken bu durumda geçici olarak askıya alınır. Bu aşamada kritik olmayan işlemler durdurulabilir.

onStop(): Aktivite artık görünür değildir. Arka planda kalır ancak tamamen kapatılmamıştır. Genellikle bu aşamada, kullanıcı verileri saklanabilir.

onRestart(): Aktivite durdurulduktan sonra tekrar başlatıldığında çağrılır. Yalnızca onStop() ardından gelir.

onDestroy(): Aktivite tamamen yok edilmeden hemen önce çağrılır. Bu, uygulamanın veya aktivitenin sona erdiği andır.


![image](https://learn.microsoft.com/tr-tr/previous-versions/xamarin/android/app-fundamentals/activity-lifecycle/images/image2.png)

```java
package com.example.myapp;

import android.os.Bundle;
import android.util.Log;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private static final String TAG = "MainActivity";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Log.d(TAG, "onCreate() çağrıldı.");
    }

    @Override
    protected void onStart() {
        super.onStart();
        Log.d(TAG, "onStart() çağrıldı.");
    }

    @Override
    protected void onResume() {
        super.onResume();
        Log.d(TAG, "onResume() çağrıldı.");
    }

    @Override
    protected void onPause() {
        super.onPause();
        Log.d(TAG, "onPause() çağrıldı.");
    }

    @Override
    protected void onStop() {
        super.onStop();
        Log.d(TAG, "onStop() çağrıldı.");
    }

    @Override
    protected void onRestart() {
        super.onRestart();
        Log.d(TAG, "onRestart() çağrıldı.");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Log.d(TAG, "onDestroy() çağrıldı.");
    }
}

```


