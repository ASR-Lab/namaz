# Namaz vakitleri
Türkiye namaz vakitlerini gösteren bir shell script'i. Vakitleri "haberler.com" üzerinden çekmektedir.  
```
$ namaz
ISTANBUL NAMAZ VAKİTLERİ
İMSAK GÜNEŞ ÖĞLE İKİNDİ AKŞAM YATSI
05:25 06:53 13:17 16:43 19:29 20:50
```
# Kurulum
`namaz` dosyasını bilgisayarınıza indirdikten sonra `chmod +x namaz` ile scripte çalıştırılabilir (executable) haklarını vermeniz gerekmektedir.  
Tercihen `sudo cp namaz /usr/bin/` şeklinde script'i binary dosyaların saklandığı bir klasöre taşımanız daha sonra kullanımızı kolaylaştıracaktır.

# Kullanım
Eğer `/usr/bin` gibi bir klasöre kopyaladıysanız bir terminal üzerinde: `namaz istanbul`  
Diğer türlü: `./namaz istanbul` şeklinde çalıştırabilirsiniz.  
  
Sadece `namaz` (veya `./namaz`) şeklinde de çalıştırabilir ve varsayılan şehre ait sonuçları alabilirsiniz. Varsayılan şehir İstanbul'dur. Bunu script'in içindeki ilgili satırı düzenleyerek değiştirebilirsiniz.

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
lerle "/usr/bin/namaz kahramanmaras" şek-
yazdığınızdan emin olun.

Bu sonuçlar en son çalıştırma sıra-
sında kaydedilmiştir.

BURSA NAMAZ VAKİTLERİ
İMSAK GÜNEŞ ÖĞLE İKİNDİ AKŞAM YATSI
05:26 06:53 13:17 16:43 19:29 20:48

Kayıt tarihi: Sun Mar 25 18:21:59 EAT 2018
```
