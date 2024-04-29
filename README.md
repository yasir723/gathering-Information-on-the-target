# Hedef ile İlgili Bilgi Toplama Saldırısı (Gathering Information on the Target)

Bir hacker için ilk adım genellikle hedef hakkında bilgi toplamaktır. Bir cihazı veya sistemi hacklemek istiyorsak, öncelikle o sistem hakkında mümkün olduğunca fazla bilgi edinmemiz gerekir. Web siteleri hedef alındığında, bu bilgi toplama sürecine "Gathering Information on the Target" adı verilir.

Bir web geliştiricinin sıkça yaptığı hatalardan biri, yorumların yanlış bir şekilde kullanılmasıdır. HTML kodunda yapılan yorumlar, tarayıcı tarafından görülebilir. Bu durum, bir hacker için web sitesi hakkında bilgi edinme fırsatı sunabilir.

Web sitelerindeki yazılan yorumlara ulaşmak için, tarayıcıda `view page source` seçeneğine tıkladıktan sonra açılan HTML kodun içinde `Ctrl + F` kısa yolu kullanarak arama kutusuna `<!--` yazarak yorumların yerlerini tespit edebiliriz. Bu yöntemle, web sitesinin kaynak kodunda yazılan yorumları kolayca bulabilir ve önemli bilgilere ulaşabiliriz.

Her yorum işimize yaramayabilir, bu yüzden değerlendirip işimize gelenleri not alıyoruz. Böylece, saldırı gerçekleştirirken ihtiyacımız olan bilgilere daha kolay erişebiliriz.

<div align="center">
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/87feec64-fa76-4008-a259-eda57cbf655f">
</div>
<br></br>

Diğer yorum satırlarına baktığımızda, karşımıza böyle bir yorum çıkabilir:

<div align="center">
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/743d2623-f15d-4aef-af44-6a2eeb40bcaa">
</div>
Bu genellikle geliştiricinin test amacıyla eklediği ancak sonrasında silmeyi unuttuğu bir yorumdur. Bu yorumdaki bilgileri kullanarak yönetici yetkileriyle giriş yapabiliriz.
<br></br>
Bir diğer hamlemiz, JavaScript kodlarındaki yorumları da inceleyebiliriz. Bunları bulmak için "//" işaretini arayabiliriz. Kodun çalışıp çalışmadığını kontrol etmek için URL içinde error parametresine bir değer vererek bu durumu kontrol edebiliriz


<div align="center">
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/dbfb190a-c584-4f7d-8162-d7bc4bfa19f3">
</div>
<br></br>

Yukarıdaki resimdeki JavaScript yorumlarında yazılan kod parçasından anladığımız şu ki, get isteğiyle gönderilen herhangi bir hata parametresi, alert fonksiyonu kullanılarak kullanıcıya bir bildirim olarak gösterilir.

<div align="center">
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/757bb28d-34ff-4a22-97ed-389ead639fa7">
</div>
<br></br>

URL'ye `login.php?error=100` parametresini ekleyip Enter tuşuna bastığımızda, alert fonksiyonu aracılığıyla kullanıcıya 100 olarak bildirim gösterilecektir. Bu durumu daha sonra anlatacağımız `Erişim Saldırısı (Access Attack)`nda kullanacağız.
