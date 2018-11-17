# Namaz vakitleri
Türkiye namaz vakitlerini gösteren bir shell script'i. Vakitleri "http://namazvakitleri.diyanet.gov.tr" üzerinden çekmektedir.  
```
$ namaz
ISTANBUL NAMAZ VAKİTLERİ
İMSAK GÜNEŞ ÖĞLE İKİNDİ AKŞAM YATSI
05:25 06:53 13:17 16:43 19:29 20:50
```
# Kurulum
`namaz` ve `sehirler` dosyalarını bilgisayarınıza indirdikten sonra `chmod +x namaz` ile scripte çalıştırılabilir (executable) haklarını vermeniz gerekmektedir.  

Tercihen `sudo cp namaz /usr/bin/` şeklinde script'i binary dosyaların saklandığı bir klasöre taşımanız daha sonra kullanımızı kolaylaştıracaktır.  

`sehirler` dosyasını ise `cp sehirler $HOME/.sehirler` şeklinde ana dizininize kopyalamanız gerekmektedir. Bu dosyada şehirlerin kodları saklanmaktadır, dilerseniz `namaz` bash script'inde de yazdığı gibi güncelleyebilirsiniz.
  
Bu script `curl`e ihtiyaç duymaktadır. Eğer bilgisayarınızda `curl` programı yüklü değilse `sudo apt install curl` (Ubuntu) gibi `curl`ü kurmanız gerekmektedir.

# Kullanım
Eğer `/usr/bin` gibi bir klasöre kopyaladıysanız bir terminal üzerinde: `namaz istanbul`  
Diğer türlü: `./namaz istanbul` şeklinde çalıştırabilirsiniz. Size tavsiyemiz ilk defa çalıştırdıktan bir gidip "http://namazvakitleri.diyanet.gov.tr" adresindeki vakit bilgileriyle sonuçları karşılaştırmanız. Eğer sonuçlar farklı gözüküyorsa şehir ismini BÜYÜK HARFLERLE yazın ve tekrar deneyin. İşletim sisteminin dilinden kaynaklı büyük İ'nin I'ya dönüşmesi benzeri sebeplerle bu yaşanabilmektedir. 
  
Sadece `namaz` (veya `./namaz`) şeklinde de çalıştırabilir ve varsayılan şehre (hatta ilçeye) ait sonuçları alabilirsiniz. Varsayılan şehir İstanbul'dur. Bunu script'in içindeki ilgili satırı düzenleyerek değiştirebilirsiniz. Tüm ilçe isimleri için "http://namazvakitleri.diyanet.gov.tr" sitesindeki şehrinizin kaydedilmiş ilçe isimlerine bakabilirsiniz.

# Örnekler
```
$ namaz
ISTANBUL NAMAZ VAKİTLERİ
İMSAK GÜNEŞ ÖĞLE İKİNDİ AKŞAM YATSI
05:25 06:53 13:17 16:43 19:29 20:50
```
```
$ namaz bursa
BURSA NAMAZ VAKİTLERİ
İMSAK GÜNEŞ ÖĞLE İKİNDİ AKŞAM YATSI
05:26 06:53 13:17 16:43 19:29 20:48
```
```
$ namaz bbbb
NOT: BBBB için namaz vakitlerine
ulaşılamamaktadır. Lütfen internet
bağlantınızı kontrol edin ve şehir
ismini küçük İngilizce karakterker-
lerle "/usr/bin/namaz kahramanmaraş" şek-
yazdığınızdan emin olun.

Bu sonuçlar en son çalıştırma sıra-
sında kaydedilmiştir.

BURSA NAMAZ VAKİTLERİ
İMSAK GÜNEŞ ÖĞLE İKİNDİ AKŞAM YATSI
05:26 06:53 13:17 16:43 19:29 20:48

Kayıt tarihi: Sun Mar 25 18:21:59 EAT 2018
```
