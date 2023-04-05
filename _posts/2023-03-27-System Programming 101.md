---
layout: post
comments: true
title: System Programming 101
categories: [System Programming]
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
sudo apt install build-essential  # ana paketlerin yüklenmesi (bazı distrolarda kurulu olarak gelebilmekte)
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

##Bellek Yapisi ve Isleyisi
