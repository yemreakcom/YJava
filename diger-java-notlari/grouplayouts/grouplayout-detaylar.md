---
description: GroupLayout'u daha iyi anlamak isteyenler için
---

# 🤯 GroupLayout Detaylar

## 🥅 Karmaşık Bir Örnek

![](../../.gitbook/assets/image%20%289%29.png)

### ⏩ Yatay Olarak İncelersek \(Kırmızı Çizgiler\)

Buton1 ve Buton2 birbirlerine seri \(ardışık\) durmakta. \( Dikey konumlarını göz ardı ediyoruz, tek boyut olarak inceliyoruz.\)

```java
gl.setHorizontalGroup(
    gl.createSequentialGroup()
    .addComponent(b1)
    .addComponent(b2)
    );
);
```

### ⏬ Dikey Olarak İncelersek \(Mor Çizgiler\)

Buton1 ve Buton2 birbirlerine seri durmakta. \(Yatay konumlarını göz ardı ediyoruz, tek boyut olarak inceliyoruz.\)

```java
gl.setVerticalGroup(
    gl.createSequentialGroup()
    .addComponent(b1)
    .addComponent(b2)
    );
);
```

### 🚀 Sonuç Resmi

![](../../.gitbook/assets/image%20%2813%29.png)

## ⭐ Hızlı Örnekler

![](../../.gitbook/assets/image%20%286%29.png)

### **⏩ Yatay Olarak İncelersek:**

* Buton1, Buton2 ve Buton3 'e paralel.
* Buton2 ve Butom3 birbirlerine seri.

### **⏬ Dikey Olarak:**

* Buton1, Buton2 ve Buton3 'e seri.
* Buton2 ve Buton3 paralel.

## 🌗 Son Örnek

![](../../.gitbook/assets/image%20%281%29.png)

### **⏩ Yatay Olarak İncelersek \(Kırmızılar\):**

* 1, 5 paralel
* 2, 4 paralel
* 3,  \(2, 4\), \(1, 5\) seri

### **⏬ Dikey Olarak;**

* 4, 3 paralel
* 1, 2, \(4, 3\), 5 seri

![](../../.gitbook/assets/image%20%283%29.png)

a

