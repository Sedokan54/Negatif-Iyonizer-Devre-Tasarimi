Yüksek Gerilim Negatif İyonizer Devresi

Bu repo, Sakarya Üniversitesi Elektrik-Elektronik Mühendisliği Yüksek Gerilim Tekniği dersi kapsamında tasarlanmış ve gerçekleştirilmiş olan, 220V AC şebeke geriliminden ~12.7 kV DC negatif gerilim üreten trafosuz bir negatif iyonizer projesinin tüm teknik dokümantasyonunu içermektedir.



Projenin temel amacı, 3mm'den daha büyük bir hava aralığında ark oluşturabilecek bir yüksek gerilim kaynağı tasarlamaktır.    





Projenin tamamlanmış ve kutulanmış hali.



⚠️ HAYATİ GÜVENLİK UYARISI ⚠️

BU DEVRE ÖLÜMCÜLDÜR. Devre, şebeke elektriğinden galvanik olarak izole DEĞİLDİR. Bu, devrenin "toprak" veya "nötr" ucu dahil HERHANGİ BİR NOKTASININ şebeke potansiyelinde olduğu ve dokunulması halinde ölümcül elektrik şokuna neden olabileceği anlamına gelir.    



Devre çalışırken ASLA dokunmayın.    



Devrenin fişini çektikten sonra bile, kapasitörler uzun bir süre boyunca ölümcül bir yük depolamaya devam eder. Devreye dokunmadan önce deşarj olması için en az 1 dakika bekleyin ve bir voltmetre ile gerilimin sıfırlandığını teyit edin.    



Bu projeyi yeniden üretirken tüm sorumluluk size aittir. Yalıtkan bir çalışma ortamı ve koruyucu gözlük kullanımı zorunludur.    



Teknik Özellikler

Özellik	Değer

Giriş Gerilimi	220V AC, 50Hz

Çıkış Gerilimi (Boşta)	Yaklaşık -12.7 kV DC

Devre Mimarisi	20 Kademeli Tam Dalga Cockcroft-Walton Çoklayıcı

PCB Boyutları	20cm x 6cm

Koruma Devreleri	500mA Gecikmeli Sigorta (T Tipi), 10Ω NTC Termistör

Çıkış Akım Limiti	~4 mA (3MΩ direnç ile)



E-Tablolar'a aktar

Çalışma Prensibi

Devre iki ana bölümden oluşur: Yüksek gerilim üretimi ve iyonizasyon.



1\. Yüksek Gerilim Üretimi (Cockcroft-Walton Çoklayıcı)

Devre, 220V AC şebeke gerilimini, bir dizi diyot ve kapasitörden oluşan Cockcroft-Walton gerilim çoklayıcı merdiveni kullanarak yükseltir.  Bu yapı, bir "yük pompası" gibi çalışarak, AC sinyalinin her bir döngüsünde elektrik yükünü kapasitörler boyunca kademeli olarak yukarı taşır ve her kademede gerilimi artırır.    



Yüksüz durumda, n kademeli bir çoklayıcının ideal çıkış gerilimi şu formülle hesaplanır:

$$V\_{çıkış} \\approx 2 \\cdot n \\cdot V\_{tepe}$$Bu proje için (n=20, V 

tepe

​

&nbsp;≈311V):



V 

c

\\c

​

&nbsp;ıkı 

s

\\c

​

&nbsp;

​

&nbsp;≈2⋅20⋅311V≈12,440V

2\. Negatif İyon Üretimi (Korona Deşarjı)

Üretilen yüksek negatif DC gerilimi, devrenin çıkışındaki sivri bir iğneye (emiter) uygulanır. Bu sivri uçta oluşan aşırı yoğun elektrik alanı, havanın dielektrik dayanımını (yaklaşık 30 kV/cm) aşar.  Bu durum, çevredeki hava moleküllerinden elektronların koparılmasına ve bir zincirleme reaksiyonla plazma oluşumuna yol açar. Bu olaya Korona Deşarjı denir. Negatif potansiyel, oluşan bu elektronları ve negatif iyonları (O 

2

−

​

&nbsp;) elektrottan uzağa iterek ortama bir negatif iyon akışı yayar.    



Mühendislik Tasarım Kararları

Bu projenin tasarımında, güvenlik ve kararlılığı sağlamak için bir dizi kritik mühendislik kararı alınmıştır.



Komponent Seçimi

Kapasitörler (150nF 1000V DC): Devredeki her bir kapasitör, giriş tepe geriliminin iki katı olan ~622V'luk bir DC gerilim stresine maruz kalır. Bu nedenle, şebeke dalgalanmalarına karşı geniş bir güvenlik payı sunan 1000V DC dayanımına sahip kapasitörler seçilmiştir.    



Koruma Elemanları (Sigorta ve NTC): Giriş katına, devreyi ilk açılışta oluşan yüksek "ani akım" (inrush current) şokundan korumak için 10Ω NTC Termistör eklenmiştir. Olası bir katastrofik arıza durumunda yangın tehlikesini önlemek için ise 500mA Gecikmeli (T Tipi) Sigorta kullanılmıştır.    



Çıkış Dirençleri (3 x 1MΩ): Çıkışa seri bağlanan toplam 3MΩ'luk dirençler, ark anında akımı ~4mA ile sınırlar ve devre kapatıldığında kapasitörlerde depolanan enerjiyi güvenli bir şekilde deşarj eder. Gerilimi bölmek için üç adet direnç seri bağlanmıştır.    



Baskı Devre (PCB) Tasarımı

Yüksek gerilim devrelerinde PCB tasarımı, devrenin en önemli yalıtım elemanıdır.



Yüksek Gerilim İzolasyonu (Clearance): Tasarımın en kritik güvenlik özelliği, yüksek potansiyel farkına sahip üst ve alt bakır yollar arasına bırakılan 6 cm (60 mm)'lik mesafedir. Bu mesafe, hesaplanan minimum güvenlik mesafesi olan ~1cm'nin 6 katı olup, nem ve toz gibi dış etkenler altında bile ark atlama riskini fiziksel olarak imkansız hale getirir.



Yol Geometrisi (Köşe Yumuşatma): Yüksek gerilim, iletkenlerin keskin köşelerinde yoğunlaşma eğilimindedir. Bu durum, istenmeyen enerji sızıntılarına (korona deşarjı) ve ark atlama riskine yol açar.  Bu riski minimize etmek için, tüm 90 derecelik keskin köşeler manuel olarak düzenlenmiş ve 45 derecelik yumuşak dönüşler kullanılmıştır.   



Proje Dosyaları

Bu repoda projenin yeniden üretilmesi için gerekli tüm dosyalar bulunmaktadır:



/design\_files: Proteus'ta hazırlanmış orijinal şematik (.DSN) ve PCB layout (.LYT) dosyaları.



/manufacturing\_files: PCB'nin profesyonel olarak üretilmesi için gereken Gerber ve Delim Dosyaları (.zip) ve ütü yöntemiyle evde üretim için 1:1 ölçekli, aynalı PDF dosyası.



/documentation: Projenin detaylı teorik analizini içeren ödev raporu (.pdf) ve malzeme listesi (BOM).



/images: Projenin bitmiş halinin fotoğrafları ve çalışma videoları.



Lisans

Bu proje, CERN Open Hardware Licence Version 2 - Permissive (CERN-OHL-P v2) lisansı altında lisanslanmıştır. Detaylar için LICENSE dosyasına bakınız.

