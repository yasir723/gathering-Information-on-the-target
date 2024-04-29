# Hedef ile İlgili Bilgi Toplama Saldırısı (Gathering Information on the Target)

Bir hacker'in aklına ilk gelen saldırı gerçekleştirmek için target hakkında bilgi toplamaktır, bir cihazı veya bir sistemi hacklemek istersek bu sistem hakkında bilgi edinmemiz gerek. Bir web siteesi hakkında bilgi toplamak için kullanılan yöntemlerden biri olan `Gathering Information on the Target` saldırısı. Bir web developer'ın yaptığı en yaygın hatalardan biri olan yolrumları yanlış kullanmaktır. Bildiğimiz gibi html kodunda yazılan yorumlar tarayıcıdan gözükebilir bu da biz hacker olarak web sitesi hakkında bilgi toplamak için bize bir fırsat sunar. 

web sitesindeki yazılan yorumlara ulaşmak için `view page source` tıklayarak html kodunda (Ctrl + F) tıklayınca arama kutusunda `<!--` yazarak yazılan yorumların yerlerini tespit edebiliyoruz. web site örneğimizde uygulama yaparsak bu şekilde önemli bilgiler görebiliriz

Tüm yorumlar işimize gelmeyebilir o yüzden değerlendirip hangisi işimize gelenleri not olarak yazıyoruz saldırı gerçekleştirirken onları kullanmak için
<div align="center">
    <h3> Önemsiz Bilgi </h3>
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/87feec64-fa76-4008-a259-eda57cbf655f">
</div>

Başka bir yorum satırlara baktığımızda böyle bir yorum ile karşılaşabiliriz

<div align="center">
    <h3> Önemli Bilgi </h3>
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/743d2623-f15d-4aef-af44-6a2eeb40bcaa">
</div>

Bu genelde developer bunu test için yazmıştır ve silmeyi unutmuştur, onu kullanarak admin yetki ile giriş yapabiliriz.

Öte yandan Javascript kodlarındaki yorumlara da bakabiliriz `//` aratırarak bulabiliriz

<div align="center">
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/dbfb190a-c584-4f7d-8162-d7bc4bfa19f3">
</div>

Bu yukarıdaki koddan anlayacağımız şey, get olarak error parametresiyle gönderilen her şey alert fonksiyonu kullanarak kullanıcıya bildirim olarak gösterilir. bu olay ileri anlatacağımız saldırılarda `erişim saldırı (access attack)` gerçekleşitrmek için kullanacağız. Peki bu durumu kontrol etmek için url içinde error olarak parametreye değer vererek kodun çalışıp çalışmadığını kontrol edebiliriz

<div align="center">
    <h3>URL'da ?error = 100 ekleyerek enter tıklarsak alert fonksiyonu dolayından bildirim olarak görebiliriz</h3>
    <img src="https://github.com/yasir723/hedef-ile-ilgili-bilgi-toplama/assets/111686779/757bb28d-34ff-4a22-97ed-389ead639fa7">
</div>

