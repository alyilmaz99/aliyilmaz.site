---
layout: post
comments: true
title: System Programming 101
categories: [System Programming]
---

### Sistem Programlama Nedir?

Sozluk anlami olarak Sistem; "_Düzen; bir şeyi, aygıtı oluşturan düzen, düzenek, tertibat_" olarak gecmekte olup bizim kullanicagimiz sekliyle bilgisayar bilesenlerinden olusan yapidir. Bir sistem ana hatlariyla 5 elementten olusur. Bunlar:

- Architecture
- Modules
- Components
- Interface
- Data

olarak gecer.

**Sistem Programlama** ise bilesenlerin en alt seviyesine erisilerek, gelistirme yaparak, sisteme daha yakin duzeyde yapilan yazilim modeline karsilik gelir. Bir diger deyisle donanimin ve kullanicinin birbiriyle erisimini saglamak icin programci tarafindan tasarlanan, gelistirilen ve sistemde efektif bir sekilde calismasinin kontrolunu iceren modele denir.

Sistem programlama yaparken genelde **Low Level** seviye denilen programlama dilleri tercih edilir. Gunumuzde, piyasada agirlikla **C,C++,Assembly** gibi diller sistem programlama yapilirken cokca tercih edilir.Ilerleyen surecte gelistirecegimiz ve yazacagimiz program ve yazilimlarda cokca **C** dilinden faydalanacagiz.

### C Dili Nedir ve Syntax'i Nasildir?

C dili, **UNIX** Isletim Sistemi'ni gelistirmek icin **B** dilinden turetilmis Low Level bir programlama dilidir. AT&T Bell de, Dennis Ritchie ve Ken Thompson tarafindan, 1972 yilindan beri gelistirilmektedir._Ken Thompson ayni zamanda 2006 yilindan itibaren Google da **Go** dilinin gelistirilmesinde gorev almaktadir._ Gelisimini 2000 yilinda yayinlanan **C99** ile genel hattiyla tamamlayan C, ANSI(Amerikan Ulusal Standartlar Enstitusu) tarafindan da kabul gorulerek benimsenmistir. C guvenlik olarak ve memory yonetimi olarak guclu olsa da object orienting programming konusundaki eksikliginden dolayi C++ olarak gelisimine devam etmistir. Gunumuzde bilinen bir cok isletim sisteminin gelistirilmesinde %95 lere varan etkisi olan C 2023 yilinda da en cok kullanilan ve tercih edilen diller arasinda yer almaya devam etmektedir. Syntax yapisi olarak gayet basit olan C dilini ogrenilmesi en kolay dillerden birisi olarak dusundugumden ve baslangic icin en ideal dillerden birisidir benim icin.

C gelistirme ortamini kurmak icin linux isletim sisteminde:

```bash
sudo apt-get update  // sistem guncellemesi
sudo apt install build-essential  // ana paketlerin yuklenmesi
(bazi distrolarda kurulu olarak gelebilmekte)
gcc --version   // gcc kurulumu gerceklestiyse version kontrolunu saglama
```

komutlarini calistirmak yeterli olacaktir.

C programi yasam dongusune main fonksiyonu ile baslayip main fonksiyonu ile bitirir diyebiliriz. Bir cok fonksiyonun taniminin oldugu ve en cok kullanilan kutuphanelerden birisi olan stdio.h ile tanimlama yapildiktan sonra main fonksiyonumuz olusturulup program yasam dongusune baslatilir. **main()** fonksiyonu integer veri tipinde yani bir tam sayi turunde geriye '0' veya '1' gibi basarili veya basarisiz anlamina gelen sayi return eder. 'dosya_adi.c' seklinde olusturdugumuz ve icerisinde C dili bulunan bir dosyayi compile etmek istedigimizde '**gcc dosya_adi.c**' komutunu dosya dizininde yazmamiz yeterli olacaktir.

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

| Veri Tipi  | &nbsp;Bellek Boyutu | &nbsp;Tanimi                                                         |
| :--------- | :------------------ | :------------------------------------------------------------------- |
| **int**    | 4 bytes             | Tam sayili degeler icin kullanilmakta                                |
| **float**  | 4 bytes             | Ondalikli sayilar icin kullanilmakta                                 |
| **char**   | 1 byte              | Tek karakterler icin kullanilmakta                                   |
| **double** | 8 bytes             | 15 decimal degerler icin kullanilmakta                               |
| **bool**   | 1 byte              | true - false degiskenler icin _stdbool.h_ kutuphanesi ile kullanilir |
