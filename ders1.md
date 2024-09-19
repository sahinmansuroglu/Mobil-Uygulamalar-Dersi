Android'deki Activity Yaşam Döngüsü, bir uygulamanın ekranı açıldığında, kullanıldığında, arka plana alındığında veya kapandığında hangi süreçlerden geçtiğini belirler. Android, bu yaşam döngüsünü kontrol etmek için çeşitli geri çağrı (callback) yöntemlerini kullanır. İşte temel aşamaları:

onCreate(): Aktivite ilk kez oluşturulduğunda çağrılır. Genellikle kullanıcı arayüzünü başlatmak ve etkinliğe ait değişkenleri tanımlamak için kullanılır.

Örnek kullanım: setContentView(R.layout.main_activity);
onStart(): Aktivite görünür hale gelir ancak henüz kullanıcı ile etkileşimde değildir. Aktivitenin ekranda belirmesi bu aşamada olur.

onResume(): Aktivite kullanıcının etkileşime geçebileceği duruma gelir. Aktivite artık ön plandadır ve kullanıcı ile doğrudan etkileşime girebilir.

onPause(): Kullanıcı aktiviteden çıkarken (örneğin, bir başka uygulamaya geçerken) bu aşama devreye girer. Aktivite ön plandan kaybolurken bu durumda geçici olarak askıya alınır. Bu aşamada kritik olmayan işlemler durdurulabilir.

onStop(): Aktivite artık görünür değildir. Arka planda kalır ancak tamamen kapatılmamıştır. Genellikle bu aşamada, kullanıcı verileri saklanabilir.

onRestart(): Aktivite durdurulduktan sonra tekrar başlatıldığında çağrılır. Yalnızca onStop() ardından gelir.

onDestroy(): Aktivite tamamen yok edilmeden hemen önce çağrılır. Bu, uygulamanın veya aktivitenin sona erdiği andır.

https://learn.microsoft.com/tr-tr/previous-versions/xamarin/android/app-fundamentals/activity-lifecycle/images/image2.png#lightbox
