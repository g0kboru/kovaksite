# kovak
KOVAK 
TEKNİK YETERLİLİK RAPORU

Yarışmaya Katılacak Olan Hava Aracının Özellikleri
KOVAK Projesi, tamamen özgün tasarıma sahip sabit kanatlı bir SİHA’dır. Hava aracımız, kompozit malzemelerden üretilmiş olup hafif ve dayanıklı bir gövde yapısına sahiptir. Kanat profili olarak NACA 23012 tercih edilmiş ve 1.1 metre kanat açıklığı ile kanard sistemi, yüksek manevra kabiliyeti sağlamıştır. Aerodinamik yapısı, uzun süreli uçuş ve hızlı manevra kabiliyeti göz önünde bulundurularak optimize edilmiştir. Hava aracımızın uzunluğu 1.4 metredir. Eni ise kanatçıklar olmadan 300 mm, kanatçıklarla 700 mm, bir kanattan diğerine mesafe 1100 mm’dir. Hava aracımızda 6S 2 adet 10.000 mAh Li-Po batarya kullanılmaktadır. Batarya, ihtiyaç duyulan güç kapasitesini karşılamakta ve tam güç ile 20 dakikalık uçuş süresi sağlamaktadır.

Uçağın Kalkış Sistemi
Uçağın kalkış ağırlığı 10.000 gramdır. Hava aracımız, kalkış için üç tekerlekli sabit iniş takımı ile donatılmıştır. Kalkış için yaklaşık 15 metre koşu mesafesi gerekmektedir. İHA, 50 km/s hıza ulaştığında yeterli kaldırma kuvvetini oluşturarak havalanır.

Uçağın İniş Sistemi
Hava aracımızın inişi için 3 derecelik bir glide slope açısı kullanılmaktadır. İniş takımları, darbe emici süspansiyon sistemi ile donatılmıştır. Gövde altında bulunan koruyucu kızak, iniş takımı hasarı durumunda gövdeyi korumak için tasarlanmıştır. İniş, yaklaşık 40-50 km/s hız aralığında kontrollü bir şekilde sağlanmaktadır.

Uçağımızın Mimarisi
Mimarimizde Pixhawk Cube Orange+ otopilot sistemi merkezi konumdadır. NVIDIA Jetson Nano ise yardımcı bilgisayardır ve görüntü işleme, karar mekanizmaları ve haberleşme sistemlerini yönetmektedir. Telemetri için RFD900+ kullanılmakta olup uzun menzil sağlamaktadır. Ana güç dağıtım kartından ESC, servo motorlar ve elektronik sistemlere güç dağıtılmaktadır. Kamera sistemi, CSI üzerinden Jetson Nano'ya bağlanmakta ve işlenen görüntü verileri Orange Cube+ üzerinden yer istasyonuna aktarılmaktadır.




Uçağımızın Güç Sistemi
Güç sistemi, ana batarya üzerinden Power Module aracılığıyla kontrol edilmektedir. Ana güç kaynağı olarak 2 adet 6S 10.000 mAh batarya, 25C deşarj oranı ile yüksek akım gerektiren manevralar için yeterli performansı sağlamaktadır. Batarya tam şarj ve tam performans ile 20 dakika uçuş süresi sunmaktadır. Şarj işlemi, özel LiPo şarj cihazı ile 2C hızda güvenli bir şekilde gerçekleştirilmektedir.

Uçağımızda Kullanılacak İtki Sistemi
Hava aracımızda Dr. Mad Thrust 90mm 12-Blade Alloy EDF 1600KV Ducted Fan ve 15x6 inç karbon fiber pervane kombinasyonu kullanılmaktadır. Bu motor, 24V beslemeyle 4.5 kg statik itki sağlamaktadır. Yüksek verimliliği sayesinde görev süresi boyunca istikrarlı güç ve uzun uçuş süresi sunmaktadır. ESC olarak T-Motor 60A OPTO kullanılmaktadır.

Uçağımızdaki Otopilot Sistemi
Hava aracımızda otopilot sistemi olarak Pixhawk Cube Orange tercih edilmiştir. İşlemci olarak STM32F7 çalışmaktadır ve üçlü IMU yedekliği sunmaktadır. ArduPilot (PX4) firmware kullanılmakta ve özel olarak geliştirdiğimiz uçuş modları ile donatılmıştır. İHA'nın stabilitesi için PID kontrolcüleri ayrıntılı bir şekilde ayarlanmıştır. Sistem, GPS, pusula, barometre ve airspeed sensörleri ile entegre çalışmaktadır.

Uçağımızda Kullanılacak Görüntüleme Sistemi
Hava aracımızda görüntüleme sistemi olarak Sony IMX477 sensörlü 12MP Raspberry Pi HQ kamera kullanılmaktadır. 1/2.3" sensör boyutu ve 1.55μm piksel boyutu ile yüksek çözünürlüklü görüntü sağlamaktadır. 160° görüş açısına sahip geniş açı lens kullanılarak geniş görüş alanı elde edilmiştir. Kamera dijital olup HDMI üzerinden ana bilgisayara bağlanmaktadır.


Uçağımızdaki RF Cihazları
Uçağımızda telemetri haberleşmesi için RFD900+ uzun menzil telemetri modülü kullanılmaktadır. 902-928 MHz frekans bandında çalışan bu sistem, frekans hopping özelliği ile farklı kanallarda çalışabilmektedir. 20 km'ye kadar haberleşme menzili sunmaktadır. Kumanda olarak FrSky Taranis X9D Plus kullanılacak olup 2.4 GHz bandında çalışmakta ve frekans ayarlaması yapılabilmektedir.

Uçağımızdaki Yer Kontrol İstasyonu
Yer kontrol istasyonu olarak QGroundControl ve özel olarak geliştirdiğimiz KOVAK Control Interface yazılımları kullanılmaktadır. QGroundControl, uçuş planlaması, telemetri takibi ve uçuş parametrelerinin izlenmesi için kullanılırken, KOVAK Control Interface yazılımı görüntü işleme, hedef takibi ve kamikaze görevi için özel olarak geliştirilmiştir. Yazılımlar Python ve C++ dilleri kullanılarak geliştirilmiş olup Linux işletim sistemi üzerinde çalışmaktadır.

Uçağımızın Görüntü İşleme ve Aktarım Sistemleri
Görüntü işleme için OpenCV kütüphanesi ve YOLO v5 derin öğrenme algoritması kullanılmaktadır. Hedef tespiti için özel olarak eğitilmiş CNN modeli geliştirilmiştir. Rakip İHA'lar, farklı ışık koşullarında ve mesafelerde yüksek doğrulukla tespit edilebilmektedir. Görüntü işleme Raspberry Pi 4 üzerinde gerçekleştirilmekte ve Intel Movidius Neural Compute Stick 2 ile hızlandırılmaktadır. Görüntü verileri, 5.8 GHz WiFi sistemi üzerinden yer istasyonuna aktarılmaktadır.

Kamikaze Görevinin Yapımı
Kamikaze görevi için çok aşamalı bir algoritma tasarlanmıştır. İlk aşamada hedef, YOLOv5 algoritması ile tespit edilir ve 3D konumu hesaplanır. İntikal aşamasında, PID tabanlı bir takip kontrolcüsü ile hedefe yaklaşılır. Dalış aşamasında, optimum yaklaşma açısı dinamik olarak hesaplanır ve aerodinamik verimlilik gözetilerek dalış gerçekleştirilir. Hız ve mesafe sürekli olarak değerlendirilir. Hedefin kaçınma manevrası yapması durumunda prediktif takip algoritması devreye girer. Acil durumlar için pas geçme algoritması, belirli bir mesafeye ulaşıldığında otomatik olarak aktifleştirilir.

Rakip Hava Aracına Yaklaşma ve Takip Görevinin Yapımı
Rakip İHA'ya yaklaşma ve takip için hibrit bir kontrol algoritması geliştirilmiştir. Görüntü işleme ile tespit edilen rakip İHA'nın piksel konumu, gerçek dünya koordinatlarına dönüştürülür. Kalman filtresi kullanılarak rakip İHA'nın gelecek konumu tahmin edilir. PD kontrolcü, mesafeyi 30-50 m aralığında tutacak şekilde tasarlanmıştır. Rakip kaybedilirse spiral arama algoritması devreye girer.


Uçuşa Yasaklı Alanlardan Kaçış Görevinin Yapımı
Uçuşa yasaklı alanlardan kaçış için çok katmanlı bir güvenlik yapısı tasarlanmıştır. Yapay potansiyel alan metoduna dayalı kaçınma algoritması devreye girer ve acil durumlarda güvenli bölgeye dönüş algoritması uygulanır
