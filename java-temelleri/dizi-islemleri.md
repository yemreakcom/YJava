# 📇 Dizi İşlemleri

## 🧱 Temel Yapısı

```java
// Dizi tanımlaması
new <arr>[]{"a", "b", "c"}

// Diziyi listeye ekleme
Collections.addAll(<arrlist>, <arr>);
<arrlist>.addAll(<arr>);
<arrlist>.addAll(<index>, <arr>); // Belirli indeksten sonrasına ekleme

// Diziyi parçalama
Arrays.asList(<arr>).subList(<n>, <m>) // n'den m'e kadar (m dahil değil)

// Dizi parçasını ekleme
Collections.addAll(<arrlist>, <arr>);
<arrlist>.addAll(Arrays.asList(<arr>).subList(0, <arr>.length - 2));

// Dönüşümler (generic için çalışmaz)
<arr> = <arrlist>.toArray(<type>::new)
<arrlist> = new ArrayList<>(<arr>)
```

* `<arr>` Array, String\[\] vs...
* `<arrlist>` ArrayList, ArrayList vs...
* `<type>` String, Integer vs.

