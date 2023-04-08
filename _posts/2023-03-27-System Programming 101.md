---
layout: post
comments: true
title: System Programming 101
categories: [System Programming, C Lang]
---

### Sistem Programlama Nedir?

Sözlük anlamı olarak Sistem; _"Düzen; bir şeyi, aygıtı oluşturan düzen, düzenek, tertibat"_ olarak geçmekte olup bizim kullanacağımız şekliyle bilgisayar bileşenlerinden oluşan yapıdır. Bir sistem ana hatlarıyla 5 elementten oluşur. Bunlar:

Mimari (Architecture)
Modüller (Modules)
Bileşenler (Components)
Arayüz (Interface)
Veri (Data)
olarak geçer.

**Sistem Programlama** ise bilesenlerin en alt seviyesine erisilerek, gelistirme yaparak, sisteme daha yakin duzeyde yapilan yazilim modeline karsilik gelir. Bir diger deyisle donanimin ve kullanicinin birbiriyle erisimini saglamak icin programci tarafindan tasarlanan, gelistirilen ve sistemde efektif bir sekilde calismasinin kontrolunu iceren modele denir.

Sistem programlama yaparken genelde **Low Level** seviye denilen programlama dilleri tercih edilir. Gunumuzde, piyasada agirlikla **C,C++,Assembly** gibi diller sistem programlama yapilirken cokca tercih edilir.Ilerleyen surecte gelistirecegimiz ve yazacagimiz program ve yazilimlarda cokca **C** dilinden faydalanacagiz.

### C Dili Nedir ve Syntax'i Nasildir?

**Sistem Programlama**, bileşenlerin en alt seviyesine erişilerek, geliştirme yaparak, sisteme daha yakın düzeyde yapılan yazılım modeline karşılık gelir. Bir diğer deyişle, donanımın ve kullanıcının birbiriyle erişimini sağlamak için programcı tarafından tasarlanan, geliştirilen ve sistemin etkin bir şekilde çalışmasının kontrolünü içeren modele denir.

Sistem programlama yaparken genellikle **Low Level** seviye denilen programlama dilleri tercih edilir. Günümüzde, piyasada ağırlıklı olarak **C**, **C++**, **Assembly** gibi diller sistem programlama yaparken çokça tercih edilir. İlerleyen süreçte geliştireceğimiz ve yazacağımız program ve yazılımlarda da sıklıkla C dilinden faydalanacağız.

C gelistirme ortamini kurmak icin linux isletim sisteminde:

```bash
sudo apt-get update  # sistem güncellemesi
sudo apt install build-essential  # ana paketlerin yüklenmesi bazı distrolarda kurulu olarak gelebilmekte)
gcc --version   # gcc kurulumu gerçekleştiyse version kontrolünü sağlama

```

komutlarini calistirmak yeterli olacaktir.

C programı yaşam döngüsüne **main()** fonksiyonu ile başlayıp yine **main()** fonksiyonu ile sonlandırılır. Birçok fonksiyonun tanımının yapıldığı ve en çok kullanılan kutuphanelerden birisi olan **stdio.h** ile tanımlama yapıldıktan sonra, **main()** fonksiyonumuz oluşturulup program yaşam döngüsüne başlatılır. main() fonksiyonu, integer veri tipinde yani bir tam sayı türünde geriye **0** veya **1** gibi başarılı veya başarısız anlamına gelen sayı return eder. 'dosya_adi.c' şeklinde oluşturduğumuz ve içerisinde C dili bulunan bir dosyayı compile etmek istediğimizde, dosya dizininde **'gcc dosya_adi.c'** komutunu yazmamız yeterli olacaktır.

```c

#include <stdio.h>

int main() {
  printf("System Programming 101!");
  return 0;
}

```

Yukardaki komutumuzun ciktisi:

```c
System Programming 101!
```

seklinde olacaktir.

Veri tipleri olarak C:

| Veri Tipi  | &nbsp;Bellek Boyutu | &nbsp;Tanimi                                                            |
| :--------- | :------------------ | :---------------------------------------------------------------------- |
| **int**    | 4 bytes             | Tam sayı değerleri için kullanılır                                      |
| **float**  | 4 bytes             | Ondalıklı sayılar için kullanılır                                       |
| **char**   | 1 byte              | Tek karakterler için kullanılır                                         |
| **double** | 8 bytes             | Çift hassasiyetli ondalıklı sayılar için kullanılır                     |
| **bool**   | 1 byte              | stdbool.h kütüphanesiyle kullanılarak true veya false değerlerini alır. |

---

### Döngüler

C'de döngüler 3'e ayrılmaktadır ve bunlar:

- For
- While
- Do-While
  olarak adlandırılırlar.

**For** döngüsünün genel yapısı:

```c
for (baslangic; kosul; artis) {
    // Dongu icerisinde kullanicak kodlar
}
```

Şeklinde kullanılır. Burada başlangıç kısmında bir değer verilir ve bu değer orta kısımda yer alan koşulumuza göre kontrol edilir. 3 değerimiz ise artış veya azalış için kullanacağımız değer olarak tanımlanır.

Örnek bir kullanım olarak:

```c
for(int i= 0; i <10; i++){
  printf("Degerimiz: %d\n", i);
  // burda ekranda asagiya dogru 0 dan 9 a kadar sayilari bastiracaktir,
}
```

gösterilebilir.

**While** döngüsü ise kullanım açısından daha kolay ve mantık olarak yine for döngüsüne benzerdir. Genel şablonu:

```c
while (kosul) {
    // Dongu icerisinde kullanicak kodlar
}

```

"Seklinde" olup, örnek olarak:

```c
int count = 0;
while (count < 10) {
    printf("Degerimiz: %d\n", count);
    count++;
    // burda ekranda asagiya dogru 0 dan 9 a kadar sayilari bastiracaktir,
}
```

gösterilebilir.

**Do-While** döngüsü, normal bir while döngüsüne benzemektedir. Farkı, do kısmında bir kez çalıştırılan kod bloğunu, daha sonra while kısmını kontrol ederek devam etmektedir. Yani do kısmında yazacağımız kod çalıştırıldıktan sonra, while kısmına geçecektir. Genel şablonu şu şekildedir:

```c
do {
    // Dongu icerisinde kullanicak kodlar
} while (kosul);
```

Şeklinde olup, örnek bir kod göstermek istersek:

```c
int count = 0;
do {
    printf("Degerimiz: %d\n", count);
    count++;
} while (count < 10);
// burda ekranda asagiya dogru 0 dan 9 a kadar sayilari bastiracaktir,
```

seklindedir.

---

### Kosullar

C'de koşullar **if-else** ve **switch-case** kullanılarak yapılmaktadır. Genel mantık olarak ikisi de benzer olsa da kullanım açıları ve kolaylıkları bazında düşünüldüğünde, ikisinin kullanıldığı yerler farklılık gösterecektir.

Sablon olarak:

```c
if (kosul) {
    // Kosul saglanirsa burasi calisir
} else {
    // Kosul saglanmazsa burasi calisir
}

switch (degisken) {
    case deger1:
        // Degisken degeri 1 icin yapilacaklar burda yer alir
        break;
    case deger2:
       // Degisken degeri 2 icin yapilacaklar burda yer alir
        break;
    default:
        // Degisken degeri 1 ve 2 degilse burasi calisir.
}

```

Şeklinde olup mantığı ve kullanımı gayet basittir. Örnek bir kod ile daha da detaylandırmak isterseniz;

```c
int check = -3;
if (check > 0) {
   printf("Check degeri 0 dan buyuk\n");
} else {
   printf("Check degeri 0 veya 0 dan kucuk\n");
}

int checkSwitch = 2;
switch (checkSwitch) {
    case 1:
        printf("CheckSwitch degeri 1 dir.\n");
        break;
    case 2:
        printf("CheckSwitch degeri 2 dir\n");
        break;
    default:
        printf("checkSwitch degeri 1 veya 2 degildir\n");
}


```

seklinde kullanimlari mevcuttur.

---

### Fonksiyonlar

C'de fonksiyonlar, belirli bir işlemi gerçekleştirmek için kullanılan kod bloklarıdır. Bu bloklar sayesinde kodumuz yeniden kullanılabilir ve daha işlevsel hale getirilebilir. Fonksiyonların şablonu aşağıdaki gibidir:

```c
veriTipi fonksiyonAdi(parametre degerleri) {
    // Fonksiyonla yapilacak islemlerin yer aldigi kisim
    // ...
    // Fonksiyon sonunda veri tipi void den farkli ise bir veri tipi dondurmesi gerekir
    return donusDegeri;
}

int main(){
    veriTipi deger;
    fonksiyonAdi(deger);
    return 0;
}

```

Genel C syntax'ımızın sonuna geldik. C programlama dilinin temel yapı taşlarını ve önemli kavramlarını öğrendik. Bu temel bilgiler sayesinde C dilinde kod yazmaya başlayabilir, fonksiyonlar, döngüler, koşullar gibi yapıları kullanarak kodlarımızı daha karmaşık hale getirebiliriz.

Ancak, C dilinde daha ayrıntılı konular bulunmaktadır. İlerleyen yazılarda bu konuları daha detaylı bir şekilde inceleyeceğiz. Örneğin, fonksiyonların daha karmaşık kullanımları, bellek yönetimi, dosya işlemleri, işaretçiler gibi konuları ele alacağız. C dilini daha iyi anlamak için pratik yapmaya ve kod yazmaya devam edeceğiz.

Bu süreçte herhangi bir sorunuz olursa sormaktan çekinmeyin. Yardımcı olmaktan mutluluk duyarım. Okuduğunuz için tekrar teşekkür ederim ve bir sonraki yazımızda görüşmek üzere!
