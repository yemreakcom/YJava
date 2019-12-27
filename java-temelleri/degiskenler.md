# 💎 Değişkenler

## 🧱 Temel Bilgiler

* 🎳 `Final`, değiştirilemez \(const\) anlamına gelir 
* 🏗️ Final olursa constructer'da tanımlanması gerekir
* ⭐ `Static` değişkenler 1 kez tanımlanırlar
* [Hashmap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)
  * Key ve değer'e göre veri oluşturur
  * `<hashmap>.get("A");`
  * Örn: `"A"` için `1`, `"B"` için `2` değeri verir.

## 💫 Değişken Dönüşümleri

```java
double kesir = 0.0;
int sayi = 1;
String metin = "metin";

sayi = (int) kesir;
metin =
```

## ➗ Kesirli Sayıları Formatlama

```java
public static String formatDecimal(Double decimal, int digitNum) {
    if (decimal == 0) return "0." + "0".repeat(digitNum - 1);

    int lvl = (int) Math.log10(decimal);
    String format = lvl >= 0 ? "#".repeat(lvl + 1) : "";
    format += lvl - digitNum >= -1 ? "" : "." + "#".repeat(digitNum - lvl - 1);

    return new DecimalFormat(format).format(decimal);
}
```

> [How to round a number to n decimal places in Java](https://stackoverflow.com/a/153785/9770490)

## 💡 Değişkenin Tipi Hakkında Bilgi Alma

* `<degisken>.getClass()` İle sınıf bilgilerini alabilirsin
* `<arr | arrlist>.getClass().getComponentType()` İle alt objelerinin sınıf bilgilerini alabilirsin

