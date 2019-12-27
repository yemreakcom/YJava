---
description: 'Java kod dokümanları, yorum satırları ve kod açıklamaları'
---

# 📝 JavaDoc

## 🔰 Yapıyı Tanıyalım

* 📝 Metotların hemen üstüne `/**` karakteri ile açılan yorum satırlarıdır
* 📃 Metodun üzerine imleç ile geldiğinizde karşınıza çıkan popup ekranının içeriğini belirler
* 📈 Birden fazla kişinin çalıştığı projelerde kodun anlaşılabilirliğini artırır

> ⏲ Tek çalışıyorsanız da, uzun süre sonra koda baktığınızda hatırlamanızı sağlar

## 👀 Popup Ekrana Bakış

![](.gitbook/assets/ezgif-1-72be658495e1.gif)

## 🧱 Temel Anahtarlar

| 💎 Anahtar | 📝 Açıklama |
| :--- | :--- |
| `@param` | Metodun aldığı parametreleri açıklar |
| `@return` | Metodun döndürdüğü değeri açıklar |
| `@see <metin>` | Kodu anlamamız için bakmamız gereken alanları gösterir |
| `{@link <metin>}` | Kod ile alakalı değişken, metot ya da class objesi belirtir |

{% hint style="info" %}
‍🧙‍♂ `@See` anahtarı, html etiketlerini desteklemektedir
{% endhint %}

```java
/**
 * Gets URL
 * @see <a href="https://android.yemreak.com/temel/http-istekleri">HTTPS istekleri ~ YEmreAk</a>
 * @return Generated {@link #URL_TEMPLATE} with a random {@link #API_KEYS}
 */
private static String generateURL() {
    int ix = new Random().nextInt(API_KEYS.length);
    return String.format(URL_TEMPLATE, API_KEYS[ix]);
}
```

## 🐣 Erişim Operatörleri

* 📌 Class objelerine direkt olarak bağlantı verebilirsin
* 💎 Değişkenlere veya metotlara bağlantı vermek için `#` operatörü kullanılır
* 💠 Metotlar doküman içerisinde prototipleri ile gösterilirler

![](.gitbook/assets/image%20%289%29.png)

