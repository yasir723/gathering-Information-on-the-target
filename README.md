# Hedef ile İlgili Bilgi Toplama Saldırısı (Gathering Information on the Target)

Bir hacker için ilk adım genellikle hedef hakkında bilgi toplamaktır. Bir cihazı veya sistemi hacklemek istiyorsak, öncelikle o sistem hakkında mümkün olduğunca fazla bilgi edinmemiz gerekir. Web siteleri hedef alındığında, bu bilgi toplama sürecine "Gathering Information on the Target" adı verilir.


## HTML Yorumları
Bir web geliştiricinin sıkça yaptığı hatalardan biri, yorumların yanlış bir şekilde kullanılmasıdır. HTML kodunda yapılan yorumlar, tarayıcı tarafından görülebilir. Bu durum, bir hacker için web sitesi hakkında bilgi edinme fırsatı sunabilir.

Web sitelerindeki yazılan yorumlara ulaşmak için, tarayıcıda `view page source` seçeneğine tıkladıktan sonra açılan HTML kodun içinde `Ctrl + F` kısa yolu kullanarak arama kutusuna `<!--` yazarak yorumların yerlerini tespit edebiliriz. Bu yöntemle, web sitesinin kaynak kodunda yazılan yorumları kolayca bulabilir ve önemli bilgilere ulaşabiliriz.

Her yorum işimize yaramayabilir, bu yüzden değerlendirip işimize gelenleri not alıyoruz. Böylece, saldırı gerçekleştirirken ihtiyacımız olan bilgilere daha kolay erişebiliriz.

### 1. Sonuç
<div align="center">
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/87feec64-fa76-4008-a259-eda57cbf655f">
</div>
<br></br>

### 2. Sonuç
Diğer yorum satırlarına baktığımızda, karşımıza böyle bir yorum çıkabilir:

<div align="center">
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/743d2623-f15d-4aef-af44-6a2eeb40bcaa">
</div>
Bu genellikle geliştiricinin test amacıyla eklediği ancak sonrasında silmeyi unuttuğu bir yorumdur. Bu yorumdaki bilgileri kullanarak yönetici yetkileriyle giriş yapabiliriz.
<br></br>

## JavaScript Yorumları
Bir diğer hamlemiz, JavaScript kodlarındaki yorumları da inceleyebiliriz. 

### Arama Yapmak
JavaScript kodundaki yazılan yorumları bulmak için "//" işaretini arayabiliriz. 
<div align="center">
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/31c8c97c-45ae-4b75-bba5-718b27ec0e08">
</div>

Kodun çalışıp çalışmadığını kontrol etmek için URL içinde error parametresine bir değer vererek bu durumu kontrol edebiliriz


### Yorumlardan anladığımız JavaScript Komutu Çalışma Kontrolü
Yukarıdaki resimdeki JavaScript yorumlarında yazılan kod parçasından anladığımız şu ki, get isteğiyle gönderilen herhangi bir hata parametresi, alert fonksiyonu kullanılarak kullanıcıya bir bildirim olarak gösterilir.

<div align="center">
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/b1a16226-e156-45a2-ac46-3ff800625ee7" width=49% >
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/ee472d38-feb2-4ff7-aad3-0bbcda8b8070" width=49% >
</div>
<br></br>

URL'ye `login.php?error=100` veya `login.php?error=merhaba dünya` parametreleri ekleyip Enter tuşuna bastığımızda, alert fonksiyonu aracılığıyla kullanıcıya yazdığımız parametre `100 veya merhaba dünya` bildirim olarak gösterilecektir. Bu durumu daha sonra anlatacağımız `Erişim Saldırısı (Access Attack)`nda kullanacağız.
