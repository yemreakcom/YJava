---
description: Java'da değişkenler koşullar ve döngüler
---

# 👮‍♀️ Koşul Yapıları

### 🚀 Yeni Switch Case

```java
String test = switch (type) {
    case "formatCode" -> data.formatCode;
    case "extension" -> data.extension;
    case "type" -> data.type;
    case "resolution" -> data.resolution;
    case "size" -> data.size;
    default -> "";
}
```

## 💫 Döngüler

```java
// For each
for (<type> num : <iterable>) {}
<arr>.foreach(<eleman> -> {<işlemler>});
```

* `<iterable>` İçerisinde çok veri barındıran obje
  * Array, Arraylist vs..

