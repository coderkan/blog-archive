# Hex Dosyasının MCU üzerine yüklenmesi

Burada kullanacağımız program **Jlink** ile beraber gelen **JFlash-Lite** programıdır.

Programı arama sekmesinden arayıp çalıştırıyoruz.

<p align="center">
    <img src="img/arama.png">
</p>

Açılan uygulama aşağıdaki gibidir.

<p align="center">
    <img src="img/program.png">
</p>

Buradan işlemcinin marka ve modelini seçiyoruz. 

<p align="center">
    <img src="img/select_mcu.png">
</p>

Seçilen işlemcinin ardından hangi **Interface** üzerinden programlanmmasının yapılacağı bilgisi seçiliyor.

<p align="center">
    <img src="img/select_interface.png">
</p>

Seçilen interface den sonra **Ok** butonuna basarak yükleme uygulamasını çalıştırmış oluyoruz. 

<p align="center">
    <img src="img/open_part.png">
</p>

Yüklemek için **.hex .axf** formatında ki dosyaları seçiyoruz. 

<p align="center">
    <img src="img/select_hex.png">
</p>

Hex dosyamızı da yükledikten sonra **Erase Chip** ya da **Program Device** butonlarına basarak ister chip in hafızasını sileriz istersek hex dosyamızı chip hafızasına kaydederiz.

<p align="center">
    <img src="img/finish_prog.png">
</p>