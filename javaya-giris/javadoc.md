---
description: 'Java kod dokümanları, yorum satırları ve kod açıklamaları'
---

# 📝 JavaDoc

## 🔰 Yapıyı Tanıyalım

* 📝 Metotların hemen üstüne `/**` karakteri ile açılan yorum satırlarıdır
* 📃 Bu doküman, metodun üzerine imleç ile geldiğinizde karşınıza çıkan popup ekranını belirler
* 📈 Birden fazla kişinin çalıştığı projelerde kodun anlaşılabilirliğini artırır

> ⏲ Tek çalışıyorsanız da, uzun süre sonra koda baktığınızda hatırlamanızı sağlar

![](../.gitbook/assets/image%20%2815%29.png)

## 🧱 Temel Anahtarlar

| 💎 Anahtar | 📝 Açıklama |
| :--- | :--- |
| `@param` | Metodun aldığı parametreleri açıklar |
| `@return` | Metodun döndürdüğü değeri açıklar |
| `@see <metin>` | Kodu anlamamız için bakmamız gereken alanları gösterir |
| `{@link <metin>}` | Kod ile alakalı değişken, metot ya da class objesi belirtir |

```java
/**
 * Gets URL
 * @return Generated {@link #URL_TEMPLATE} with a random {@link #API_KEYS}
 */
private static String generateURL() {
    int ix = new Random().nextInt(API_KEYS.length);
    return String.format(URL_TEMPLATE, API_KEYS[ix]);
}
```

