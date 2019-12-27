# ⭐ GroupLayout Örnekleri

## 🎈 Basit Bir Örnek

Alt taraftaki gibi bir çıktı almak istediğimiz zaman, adım adım yatay ve dikey olarak inceleme yapmamız gerekmekte; \(gl = GroupLayout, b1 = buton1, b2 = buton2

![](../../.gitbook/assets/image%20%2814%29.png)

### ⏩ Yatay Olarak İncelersek

Buton1 ve Buton2 birbirlerine seri \(ardışık\) durmakta.

```java
gl.setHorizontalGroup(
    gl.createSequentialGroup()
    .addComponent(b1)
    .addComponent(b2)
    );
);
```

### ⏬ Dikey Olarak İncelersek

Buton1 ve Buton2 birbirlerine paralel durmakta.

```java
gl.setVerticalGroup(
    gl.createParallelGroup()
    .addComponent(b1)
    .addComponent(b2)
    );
);
```

### ⭐ Detaylı Resim İle Açıklama

![](../../.gitbook/assets/image%20%2813%29.png)

## 🪁 Biraz Daha Zor Bir Örnek

Alt taraftaki gibi bir çıktı almak istediğimiz zaman, adım adım yatay ve dikey olarak inceleme yapmamız gerekmekte; \(gl = GroupLayout, b1 = buton1, b2 = buton2\)

![](../../.gitbook/assets/image%20%2815%29.png)

### ⏩ Yatay Olarak İncelersek

Buton1 ve Buton2 birbirlerine seri \(ardışık\) durmakta.

* Yatayda 10px boşluk var.
* İnceleme 1'de alt kısımdaki yeri bulup, b1 ve b2 arasına .addGap\(10\) eklemen yeterli.

```java
gl.setHorizontalGroup(
    gl.createSequentialGroup()
    .addComponent(b1)
    .addGap(10) // Boşluk
    .addComponent(b2)
    );
);
```

### ⏬ Dikey Olarak İncelersek

Dikeyde boşluk bulunmamakta.

![](../../.gitbook/assets/image%20%282%29.png)

```java
gl.setVerticalGroup(
    gl.createParallelGroup()
    .addComponent(b1)
    .addComponent(b2)
    );
);
```

### ⭐ Ek Örnek Daha

![](../../.gitbook/assets/image%20%288%29.png)

## 

