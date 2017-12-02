# MCUXPresso Kullanımı


## MCUXpresso

Kullandığımız [MCUXpresso IDE](https://www.nxp.com/support/developer-resources/run-time-software/mcuxpresso-software-and-tools/mcuxpresso-integrated-development-environment-ide:MCUXpresso-IDE?tab=Design_Tools_Tab)' sini linkten indirebilirsiniz.

Kurulumu basit, kurduktan sonra JLink de içerisinde gelmektedir. Aksi durumla karşılaşırsanız [JLink](https://www.segger.com/downloads/jlink/) linkinden indirip kurabilirsiniz.

### Proje oluşturulması


#### Proje Import Edilmesi

* İlk olarak projemiz de kullanacağımız nxp kütüphanelerini import edeceğiz. Yeni projelere bunları ekleyeceğimiz için workspace'imiz de bulunmalı.

    **LPC1768** için **CMSISv1p30_LPC17xx**

    **LPC11xx** için **CMSISv2p00_LPC11xx**

kullanıyoruz. İsterseniz bunları değiştirebilirsiniz.

Öncelikle yukarıda belirttiğimiz 2 projeyi de çalıştığımız **workspace** klasörü içerisine atıyoruz. 
Ardından bu projeleri import ediyoruz.

**Project Exploer** sekmesinin bulunduğu yerde sağ click yapıp açılan pencereden **Import** sekmesini seçiyoruz.

<p align="center">
    <img src="img/import.png">
</p>


**Import** sekmesini seçtikten sonra karşımıza çıkan ekrandan **Existing Projects into Workspace** sekmesini seçiyoruz.

<p align="center">
    <img src="img/existing_project.png">
</p>


**Existing Projects into Workspace** sekmesini seçtikten sonra karşımıza çıkan ekrandan **Select root directory** labelinde **Browse** kısımından projenin olduğu klasörü seçiyoruz.

<p align="center">
    <img src="img/select_pro.png">
</p>


Projeyi aşağıdaki çıkan ekrandan seçebiliriz.

<p align="center">
    <img src="img/select_pro2.png">
</p>


Proje formatına uygun eklenebilecek bir proje var ise gösterdiğiniz yol da aşağıda ki resimden de anlaşılacağı gibi projenin seçilmiş halini gösterir. Birden fazla proje de olabilir ama siz istediğinizi seçerek projeyi ekleyebilirsiniz. Seçimimizi yaptıktan sonra **Finish** butonuna basarak devam ediyoruz.

<p align="center">
    <img src="img/select_pro3.png">
</p>


Bu işlemlerin ardından projelerimizi **Project Explorer** üzerinde eklenmiş halini görebiliriz.

<p align="center">
    <img src="img/lib_eklendi.png">
</p>

Bu işlemleri yaptıktan sonra eklenmiş projeyi **Build** edebiliriz. Aşağıdaki gibi projenin üzerinde sağa tıklayarak rahatlıkla *Build** alabiiriz.


<p align="center">
    <img src="img/build_pro.png">
</p>

### Yeni Proje Oluşturma

Yeni proje oluşturmak için izlenen adımlar aşağıda sıralanmıştır.

Kütüphanelerimizi ekledikten sonra **Project Explorer** panelinde sağa tıklayarak açılan pencereden **New** sekmesini seçiyoruz ve ardından **Project** sekmesini seçiyoruz.

<p align="center">
    <img src="img/build_pro.png">
</p>

Açılan sekmeden **New C/C++ Project** sekmesini seçiyoruz.

<p align="center">
    <img src="img/yeni_pro2.png">
</p>

İşlemci tipini ve model numarasına göre seçimimizi yapıyoruz.

<p align="center">
    <img src="img/yeni_pro3.png">
</p>

 Açılan pencereden hangi dilde geliştirme yapmak istiyorsak seçimimizi yapıyoruz ve **Next** butonuna basıyoruz.

<p align="center">
    <img src="img/yeni_pro4.png">
</p>

Yeni Projemize ismini veriyoruz ve **Next** butonuna tıklıyoruz.

<p align="center">
    <img src="img/yeni_pro5.png">
</p>

>Asıl önemli kısım şimdi başlamaktadır. Projeye ekleyeceğimiz **CMSIS Core Library** yi aşağıdaki ekrandan seçiyoruz. Ancak ekrandan seçtiğimiz kütüphanenin **Project Explorer**'a eklenmiş olması gerekmektedir. Bu ekleme işlemini ilk proje kütüphaneleri import ederken yaptığımız için o kütüphane hangisi ise O'nu seçmeliyiz.

<p align="center">
    <img src="img/yeni_pro6.png">
</p>

Seçimimizi yaptıktan sonra karşımıza çıkan ekran dan **None** bölümünü seçerek **Next** tuşuna basabiliriz. Projenin oluşturulma evresi tamamlanmıştır. Oluşan projeyi **Project Explorer**'da görebilirsiniz.

<p align="center">
    <img src="img/yeni_pro7.png">
</p>

Oluşturulan Proje aşağıdaki gibi **Project Explorer**'da görülmektedir.

<p align="center"> 
    <img src="img/yeni_pro8.png">
</p>

Oluşturulan projenin tamamlanmasının ardından **Build** işlemini gerçekleştirebiliriz.

<p align="center">
    <img src="img/yeni_pro9.png">
</p>

Bu adımların sonunda proje oluşturulmuş ve eklediğimiz libraryler **(CMSIS)** projemize eklenmiştir.


### Projeye External Kütüphane Ekleme

>Projeniz için external libraryler geliştirmiş olabilirsiniz. Bunları projenize nasıl ekleyeceğiniz konusunda bilgilendireceğim. Bu adımlar external bir kütüphane eklemek için kullanılır. Yukarıdaki adımlar sizin işinizi görüyor ise bu adımı atlayabilirsiniz.

**Project Explorer** içerisinde ki oluşturduğumuz projemizin üzerine gelip **Properties** sekmesini seçiyoruz ve ardından açılan **C/C++ Build** sekmesinin altındaki **Settings** 



Properties             |  C/C++ Build
:-------------------------:|:-------------------------:
![Alt text](img/yeni_pro8.png) | ![Alt text](img/yeni_pro10.png)

**Settings** bölümünden seçilen sekmede **Tool Settings** bölümündeki **Include** sekmesine **Include paths (-l)** bölümüne **Add** ile ekleme yapıyoruz. Include dosyalarımızın bulunduğu path bilgilerini ekliyoruz.

<p align="center">
    <img src="img/yeni_pro11.png">
</p>

<p align="center">
    <img src="img/yeni_pro12.png">
</p>

<p align="center">
    <img src="img/yeni_pro13.png">
</p>

<p align="center">
    <img src="img/yeni_pro14.png">
</p>


Ekleme işlemleri bittikten sonra projeyi **Build** edebilirsiniz.

### Projenin Debug Edilmesi


Oluşturulan projenin debug edilebilmesi için **Project Explorer**'da bulunan projemizi seçiyoruz ve ardından **Quick Start** panelinde bulunan **Debug** sekmesine tıklıyoruz ve ardından **Jlink**'in çalışmasını bekliyoruz.

<p align="center">
    <img src="img/yeni_pro15.png">
</p>


İlk çalıştırmamız da JLink ekranı gelecektir seçip devam ediyoruz ve çıkan ekrandan **Accept** butonuna tıklayarak kullanıma hazır ediyoruz.
Programın yüklenebilmesi için devremizin enerjisinin verilmesi gerekmektedir.

<p align="center">
    <img src="img/yeni_pro16.png">
</p>

Debug başarılı olursa **main** fonksiyonun da **breakpoint** e düşecektir. Ardından altta bulunan **Resume All Debug** butonuna basarak projeyi çalıştırabilirsiniz.

<p align="center">
    <img src="img/yeni_pro17.png">
</p>
