---
description: JavaFx snippets ve kod notları
---

# 👨‍💻 Kod Notları  \| JavaFX

## 🎨 Kod Tarafında CSS Değiştirme

```java
buttonDownload.setStyle("-fx-background-image: url('/images/verified.png')");
```

## 🚧 Thread ile Kodlama

JavaFX'de oluşturulan Thread, FX'in threadına uyumsuz olarak ilerleyebilmekte, bu durumda `Not on FX application thread; currentThread = JavaFX Application Thread error?` hatası gelemektedir.

* FX \(arayüzden\) bağımsız Thread'lerdee sorun oluşmaz.
* Arayüzü bağımlı Thread'lerde `Platform.runAfter{() -> {}}` yapısı kullanılır
* Thread'i platformdan sonra başlat anlamına gelmektedir

```java
new Thread(() -> {
    Image resim = uzunSürenBirİşlem();
    imageView.setImage(resim); // Bu udurmda thread ile FX yapısı kesişir ve hata verir
}).start();

new Thread(() -> {
    Image resim = uzunSürenBirİşlem();
    Platform.runAfter(() -> imageView.setImage(resim)); // Yapısı ile FX hazır olduktan sonra işlem yapılır
}).start();
```

## ✨ CSS ile Stil Oluşturma

* Buton gibi alt öğrelere `.buton` css class'ı ile özellik tanımlayabilirsin
* Her eleman içinde bulunduğu panelin css özelliğini taşır

> * [CSS ile arkaplana resim ekleme](https://stackoverflow.com/questions/9738146/javafx-how-to-set-scene-background-image)
> * [CSS ile özel buton ayarlama](https://stackoverflow.com/questions/10518458/javafx-create-custom-button-with-image)
> * [How to refer to an anchor pane in css?](https://stackoverflow.com/a/28751561/9770490)
> * [JavaFX Button with transparent background](https://stackoverflow.com/a/36566444/9770490)

## 🧱 FXML'de Kod Yapısı

```markup
<TextField prefWidth="50" text="${speedSlider.value}"/> <!-- Inline code -->
<Slider fx:id="speedSlider" orientation="HORIZONTAL" prefWidth="300"
        min="60" max="100000" blockIncrement="100"/>
```

> [Slider'a göre Label'ı güncelleme](https://stackoverflow.com/a/40053895/9770490)

## 🍢 Slider Listener \(Kaydırmalı çubuğun değişikliğine göre tepki verme\)

Silder objesinden herhangi bir özelliği \(`...Property`\) alıp ona uygun listener ekleyebiliriz.

```java
// Listener örneği
sliderQuality.valueProperty().addListener((observableValue, number, t1) -> {
    updateFileSize();
});
```

> [Slider'a göre Label'ı güncelleme](https://stackoverflow.com/a/40053895/9770490)

## 🔳 Çerçeveleri Kaldırma

```java
primaryStage.initStyle(StageStyle.TRANSPARENT);
```

## 👁‍🗨 Arkaplanı Transparant Yapma

* İlk olarak `.fxml` dosyasındaki gerekli objeye `style="-fx-background-color: transparent ;"` özelliği ekleyin
* Ardından kod tarafında alttaki düzeltmeyi yapın

```java
primaryStage.setScene(new Scene(root));
primaryStage.getScene().setFill(Color.TRANSPARENT);
```

## 📋 Clipboard \(Pano\) İşlemleri

```java
private void putClipboard(String clipboardString) {
    StringSelection stringSelection = new StringSelection(clipboardString);
    Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();
    clipboard.setContents(stringSelection, null);
}

String getClipboard() throws IOException, UnsupportedFlavorException {
    Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();
    return (String) clipboard.getData(DataFlavor.stringFlavor);
}
```

## 🎴 ImageView Resmi Değiştirme

Bu işlem için `resource` dizini **IntelliJ**'de işaretlemeniz gerekmektedir.

```java
import javafx.scene.image.Image;

// load an image in background, displaying a placeholder while it's loading
// (assuming there's an ImageView node somewhere displaying this image)
// The image is located in default package of the classpath
Image image1 = new Image("/flower.png", true);

// load an image and resize it to 100x150 without preserving its original
// aspect ratio
// The image is located in my.res package of the classpath
Image image2 = new Image("my/res/flower.png", 100, 150, false, false);

// load an image and resize it to width of 100 while preserving its
// original aspect ratio, using faster filtering method
// The image is downloaded from the supplied URL through http protocol
Image image3 = new Image("http://sample.com/res/flower.png", 100, 0, false, false);

// load an image and resize it only in one dimension, to the height of 100 and
// the original width, without preserving original aspect ratio
// The image is located in the current working directory
Image image4 = new Image("file:flower.png", 0, 100, false, false);
```

> Oracle'ın [resmi sitesinden](https://docs.oracle.com/javafx/2/api/javafx/scene/image/Image.html) alınmıştır.

## 📂 Dosya Sürükle Bırak İşlemleri

```java
@FXML
private ImageView imageView;

@FXML
void handleDragOver(DragEvent event) {
    if (event.getDragboard().hasFiles()) {
        event.acceptTransferModes(TransferMode.ANY);
    }
}

@FXML
void handleDragDropped(DragEvent event) throws FileNotFoundException {
    List<File> files = event.getDragboard().getFiles();
    Image img = new Image(new FileInputStream(files.get(0)));
    imageView.setImage(img);
}
```

