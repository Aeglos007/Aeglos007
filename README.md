### Hi there 👋

Emlak Uygulaması 








1)a Emlakçıların Verileri 

while True: 

`    `danisman\_Sayisi = int(input("Kaç danışman çalışıyor")) ![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.001.png)

if danisman\_Sayisi > 0: 

break 

for i in range(danisman\_Sayisi): 

`    `danisman\_toplam\_komisyon = 0 

danisman\_toplam\_bedel=0 

cevap = "e" 

ad\_soyad = input("danışmanın adı soyadı nedir") ![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.002.png)

while cevap in "eE": 

while True: 

`        `maas = float(input("maaş giriniz.Asgari ücrete eşit ya da fazla olmalıdır")) 

if maas >= asgari: 

break 

`        `else: 

print("Asgari ücrete eşit ya da fazla olmalıdır") 

`    `kota = maas \* 10 ![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.003.png)

1a)Ekran Görüntüsü 

![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.004.png)

1a)Açıklama 

Danışman sayısının 0 altında olmaması kaydıyla input değeri giriyoruz.Sonrasında her danışmanın ismini öğreniyoruz. Buraya her danışman değişikliğinde sıfırlanacak birkaç sabit ekliyorum. 

2)Emlak Tipi Ve İşlem Öğrenme 

emlak\_tipi = input("emlak tipini girin.Konut, İş yeri, Arsa (K/k/İ/i/A/a karakterleri)") 

while emlak\_tipi not in "KkİiAa": 

print("hatalı giriş (K/k/İ/i/A/a karakterleri)") 

`    `emlak\_tipi = input("emlak tipini girin.Konut, İş yeri, Arsa (K/k/İ/i/A/a karakterleri)") 

if emlak\_tipi in "kK": 

`    `islem = input("Satış mı yaptı kiralama mı (S/s/K/k karakterleri)") 

while islem not in "SsKk": 

print("belirtilen harfleri giriniz.(S/s/K/k karakterleri)") 

`        `islem = input("Satış mı yaptı kiralama mı (S/s/K/k karakterleri)") 

if islem in "Ss": 

`        `bedel = float(input("Bedeli nedir")) 

while bedel < 0: 

print("0dan büyük bir sayı giriniz") 

`            `bedel = float(input("Bedeli nedir")) 

`            `satilan\_konut\_topfiyat += bedel 

`            `satilan\_konut\_sayisi += 1 

elif islem in "Kk": 

`        `bedel = float(input("Bedeli nedir")) 

while bedel < 0: 

print("0dan büyük bir sayı giriniz") 

`            `bedel = float(input("Bedeli nedir")) 

`            `kiralanan\_konut\_sayisi += 1 

kiralanan\_konut\_topfiyat += bedel 

if bedel > asgari: 

`                `asgariden\_yuksek\_kiralik\_konut += 1 ![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.005.png)

elif emlak\_tipi in "İi": 

`    `islem = input("Satış mı yaptı kiralama mı (S/s/K/k karakterleri)") 

while islem not in "SsKk": 

print("belirtilen harfleri giriniz.(S/s/K/k karakterleri)") 

`        `islem = input("Satış mı yaptı kiralama mı (S/s/K/k karakterleri)") 

if islem in "Ss": 

`        `satilan\_isyeri\_sayisi += 1 

bedel = float(input("Bedeli nedir")) 

while bedel < 0: 

print("0dan büyük bir sayı giriniz") 

`            `bedel = float(input("Bedeli nedir")) 

`            `satilan\_isyeri\_topfiyat += bedel 

if islem in "Kk": 

`        `kiralanan\_isyeri\_sayisi += 1 

bedel = float(input("Bedeli nedir")) 

while bedel < 0: 

print("0dan büyük bir sayı giriniz") 

`            `bedel = input("Bedeli nedir") 

`            `kiralanan\_isyeri\_topfiyat += bedel 

elif emlak\_tipi in "Aa": ![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.006.png)

`    `islem = input("Satış mı yaptı kiralama mı (S/s/K/k karakterleri)") 

while islem not in "SsKk": 

print("belirtilen harfleri giriniz.(S/s/K/k karakterleri)") 

`        `islem = input("Satış mı yaptı kiralama mı (S/s/K/k karakterleri)") 

if islem in "Ss": 

`        `satilan\_arsa\_sayisi += 1 

bedel = float(input("Bedeli nedir")) 

while bedel < 0: 

print("0dan büyük bir sayı giriniz") 

`            `bedel = float(input("Bedeli nedir")) 

`            `satilan\_arsa\_topfiyat += bedel 

elif islem in "Kk": 

`        `kiralanan\_arsa\_sayisi += 1 

bedel = float(input("Bedeli nedir")) 

while bedel < 0: 

print("0dan büyük bir sayı giriniz") 

`            `bedel = float(input("Bedeli nedir")) 

`            `kiralanan\_arsa\_topfiyat += bedel 

2)Ekran Görüntüsü

![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.007.png)

2)Açıklama 

Burda satıcının hangi tip emlak ilgili işlem yaptığını if else bloklarıyla emlak tipini yönlendiriyorum 

Seçtiği emlak tipine göre bir satma ya da kiralama yapması bekleniyor. Her seçim yaptığında ilgili emlak tipinin sayısı artıyor.Bedeli 0 olmayacak şekilde girdikten sonra her bir tipin satın alma ya da kiralanma durumuna göre bedel sayacı çalışıyor ve o tiplerin kiralama satın alma bilgileri tutuluyor. 

3)Göze çarpan verileri kaydetme 

if islem in "Ss": 

if bedel > satilan\_en\_yuksek\_bedel\_emlak: 

`            `satilan\_en\_yuksek\_bedel\_emlak = bedel 

`            `satilan\_en\_yuksek\_bedel\_emlakci = ad\_soyad         komisyon = bedel \* 0.04 

elif islem in "Kk": 

if bedel > en\_yuksek\_kira: 

`            `en\_yuksek\_kira = bedel 

`            `en\_yuksek\_kiraci = ad\_soyad 

`        `komisyon = bedel 

`    `danisman\_toplam\_komisyon += komisyon 

`    `danisman\_toplam\_bedel += bedel 

if kiralanan\_Sayisi > 10 or bedel > 25000: 

`        `ya10ya25000 += 1 ![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.008.png)

cevap = input("başka satış var mı (e/h)") toplam\_komisyon+=danisman\_toplam\_komisyon toplam\_bedel+=danisman\_toplam\_bedel 

if bedel > kota: 

`    `kota\_durum="geçti" 

kota\_dolduran\_sayi += 1 

elif bedel<kota: 

`    `kota\_durum="geçemedi" 

prim = danisman\_toplam\_komisyon \* 0.1 ![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.008.png)if prim > maas: 

`    `primi\_maasdan\_yuksek += 1 

if prim > max\_prim\_alan\_kisi: 

`    `max\_prim\_alan\_kisi = prim 

if prim < min\_prim\_alan\_kisi: 

`    `min\_prim\_alan\_kisi = prim 

3)açıklama 

Burada en iyi ve en kötü değerleri bulmaya çalışıyorum. Bazı işlemler emlağın satılık ya da kiralık olmasına göre değişiyor.Bu sırada elde edilen toplam geliri alıp bununla komisyonu buluyorum.Satıcının kazandırmış olduğu toplam komisyonu ile primini hesaplıyorum. Bu arada kotayı doldurmuş arkadaşları da saymış oluyorum. 


4)Elde ettiğim verilerin toplanıp düzenli bir hale getirilmesi 

if kota\_durum=="geçti": 

`    `ikramiye=asgari/2 

elif kota\_durum=="geçemedi": 

`    `ikramiye=0 

aylik\_toplam\_ucret=maas+prim+ikramiye 

acente\_toplam\_komisyon = komisyon 

satilan\_emlak\_adet = satilan\_arsa\_sayisi + satilan\_isyeri\_sayisi + satilan\_konut\_sayisi 

satilan\_emlak\_oran = (satilan\_emlak\_adet / toplam\_satis) \* 100 satilan\_toplam\_fiyat = satilan\_konut\_topfiyat + satilan\_arsa\_topfiyat + satilan\_isyeri\_topfiyat ![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.001.png)

kiralanan\_oran = (kiralanan\_Sayisi / toplam\_satis) \* 100 kira\_ort = kiralama\_toplam\_fiyat / kiralanan\_Sayisi kiralama\_toplam\_fiyat = kiralanan\_konut\_topfiyat + kiralanan\_isyeri\_topfiyat + kiralanan\_arsa\_topfiyat toplam\_satis = satilan\_emlak\_adet + kiralanan\_Sayisi 

4)Açıklama 

Burada kota durumuna ikramiye kazanıp kazanmadığını buluyorum ve bunla beraber kişinin alacağı aylık ücret etkileniyor.Sonra daha önce aldığım emlak tipine göre nicelikleri bir yerde topluyorum .Aynı şekilde emlak tipiyle yaptığım işleme göre elde ettiğim gelirleri de toplamış oluyorum.Bütün bu veriler 1 kişi bittikten sonra en aşağıda derlenmiş hale geliyor 

5)Kişinin bilgilerinin yansıtılması 

print("adı soyadı", ad\_soyad) 

print("Sattığı emlak adedi:{:.2f} kiraladığı emlak sayısı:{:.2f} ".format(satilan\_emlak\_adet,kiralanan\_Sayisi)) 

print("sattığı emlak oranı:{:.2f} kiraladığı emlak oranı: {:.2f}".format(satilan\_emlak\_oran,kiralanan\_oran)) 

print("toplam satılan bedelleri konut:{:.2f}(TL)/n iş yeri,arsa:{:.2f}(TL)/n iş yeri:{:.2f}(TL) ".format(satilan\_konut\_topfiyat,satilan\_arsa\_topfiyat,satilan\_isyeri\_topfiy at)) 

print("kira ortalaması:{:.2f}(TL)".format(kira\_ort)) print("maaş(TL)",maas) 

print("prim(TL)",prim) 

print("kota(TL)",kota) 

print("o ay acenteye kazandırdığı toplam komisyon tutarı (TL)",danisman\_toplam\_komisyon) 

print("o ay kotasını doldurup dolduramadığı",kota\_durum) 

print("o ay kotasını doldurduysa alacağı ikramiye (TL)",ikramiye) 

print("o ay toplam ücreti (TL){:.2f}".format(aylik\_toplam\_ucret)) 

5)Ekran Görüntüle

![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.009.jpeg)

![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.010.png)

5)Açıklama 


Kişinin daha önce aldığım ismini ,maaşasını, işlemine göre topladığımız verileri,emlak tipleriyle olan istatistiklerin hepsini tek tek yansıtıyoruz.Burada format işlemi ile daha düzenli bir görüntü yakalıyoruz.En son kısımda artık yeni danışmana geçiliyor. 

6)Şirketin Bilgilerini Yansıtma 

print("satılan toplam konut:{:.2f}/n iş yeri:{:.2f}/n arsa:{:.2f}".format(satilan\_konut\_sayisi,satilan\_isyeri\_sayisi,satilan\_arsa \_sayisi)) 

toplam\_emlak=satilan\_emlak\_adet+kiralanan\_Sayisi 

print("satılan emlak oranları: konut{:.2f}%/n işyeri {:.2f}%/n arsa {:.2f}%".format((satilan\_konut\_sayisi/toplam\_emlak)\*100,(satilan\_isyeri\_say isi/toplam\_emlak)\*100,(satilan\_arsa\_sayisi/toplam\_emlak)\*100)) print("kiralanan toplam konut:{:.2f}/n iş yeri:{:.2f}/n arsa:{:.2f}".format(kiralanan\_konut\_sayisi,kiralanan\_isyeri\_sayisi,kiralana n\_arsa\_sayisi)) 

print("kiralanan emlak oranları: konut{:.2f}%/n işyeri {:.2f}%/n arsa {:.2f}%".format((kiralanan\_konut\_sayisi/toplam\_emlak)\*100,(kiralanan\_isyeri \_sayisi/toplam\_emlak)\*100,(kiralanan\_arsa\_sayisi/toplam\_emlak)\*100)) print("toplam satma bedeli konut:{:.2f}/n iş yeri:{:.2f}/n arsa:{:.2f}".format(satilan\_konut\_topfiyat,satilan\_isyeri\_topfiyat,satilan\_ arsa\_topfiyat)) 

print("toplam kiralama bedeli konut:{:.2f}/n iş yeri:{:.2f}/n arsa:{:.2f}".format(kiralanan\_konut\_topfiyat,kiralanan\_isyeri\_topfiyat,kira lanan\_arsa\_topfiyat)) 

print("o ay en yüksek bedelle kiralanan konutun kira bedeli {:.2f}(TL), kiralayan danışmanın adısoyadı:{}".format(en\_yuksek\_kira,en\_yuksek\_kiraci)) print("o ay kiralanan konutlardan kira bedeli, aylık asgari net ücretten yüksek olan konutların sayısı:{:.2f}/n oranları:%{:.2f}".format(asgariden\_yuksek\_kiralik\_konut,(asgariden\_yuksek\_k iralik\_konut/kiralanan\_Sayisi)\*100)) 

print("o ay hiç satış yapamayan danışmanların sayısı ve tüm danışmanlar içindeki oranı:%".format(0,0)) 

print("en çok satış adedi yapan :{}sattığı emlak sayısı :{} toplam satış bedeli:{:.2f}".format("",0,0)) 

print("en çok satış bedeli yapan:{}sattığı emlak sayısı :{} toplam satış bedeli:{:.2f}".format("",0,0)) 

print("o ay kotasını dolduran danışmanların sayısı {:.2f}/n tüm danışmanlar içindeki oranı:%{:.2f}".format(kota\_dolduran\_sayi,(kota\_dolduran\_sayi/danisman\_Sayis i)\*100)) 

print("o ay primi maaşından yüksek olan danışmanların sayısı:{}/n  tüm danışmanlar içindeki oranı:%{:.2f}".format(primi\_maasdan\_yuksek,(primi\_maasdan\_yuksek/danisman\_S ayisi)\*100)) 

print("o ay en az 10 adet veya en az 25000 TL tutarında emlak kiralayan danışmanların sayısı",ya10ya25000) 

print("o ay en yüksek prim alan ve en düşük prim alan danışmanların adı soyadı, maaşı, primi ve aylık toplam ücreti") 

print("o ay tüm emlak danışmanlarına ödenecek toplam ücretlerin toplamı (TL) ve ortalaması") 

print("o ay acentenin kazandığı toplam komisyon (TL)") 

6)Ekran Görüntüsü 

![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.011.jpeg)

![](Aspose.Words.caaf4ef3-6e46-4484-9cc2-b06146c01826.012.jpeg)

6)Açıklama 

Bütün emlakçılardan elde ettiğimiz istatistikleri burada bastırıyoruz.Sayılarla olan işlemlerimizde sayının virgülden sonra 2 basamak kaymasına izin veriyoruz ve bunu da tekrardan format işlemi kullanarak uyarlıyoruz.Oran istiyen yerlerde ifadeleri 100 ile çarptık.Bazı yerlerde verileri yan yana yazdırdım. 


