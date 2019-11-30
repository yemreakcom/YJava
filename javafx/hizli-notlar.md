---
description: JavaFX 12 için hızlı notlar
---

# 🏃‍♂️ Hızlı Notlar

## 🧱 Proje Dizin Yapısı

JavaFX için önerilen dizin yapısı aşağıdaki gibidir. \([kaynak](https://stackoverflow.com/a/24948550/9770490)\)

* Çalışmaları gruplandırmak için `com/yemreak/myproject` yapısı kullanılmakta
  * Maven veya gradle yapısı olarak da geçmektedir
* `controllers`, FXML dosyalarını kontrol eden kodlar
* `services`, Harici hizmetler \(veya tüm hizmetler\)
  * Eğer çok fazla hizmet varsa, yerel hizmetleri farklı dizine alabilirsin
* `utility`, Dahili hizmetler
* `resources`, Tüm kod dışı kaynaklar \(images, css, html vs.\)
* `views`, FXML tasarımları

```text
src/main
  ├──java/com/yemreak/myproject (ya da sadece myproject)
     ├── controllers
        ├──Screen1controller.java
        ├──Screen2controller.java
     ├── services
        ├──Service1.java
     ├── applications
        ├── SaveProducts.java
  ├──resources
     ├──views
        ├──screen1.fxml
        ├──screen2.fxml
     ├──css
        ├──style.css
     ├──images
        ├──img1.jpg
        ├──img2.jpg
```

> Örnek olacak [proje](https://github.com/badarshahzad/JFX-Browser) için buraya bakabilirsin

### 👷‍♂️ Dosyaları Yapılandırma

Dizinleri IDE üzerinden yapılandırak daha verimli çalışabilirsin.

* `Project Structure` - `Project Settings` - `Modules`
* `Source` sekmesinden `src/res` dizinini `Resources` olarak tanıt
* `out`, `lib` ve `res` dosyalarını `Excluded` olarak tanıt

![jetbrains\_project\_structures](https://github.com/yedhrab/YWiki/tree/169abadfd1b8862c004399268f6ca1f9f9359d61/1%20-%20Programlama%20Notları/res/jetbrains_project_structures.png)

> [Kaynak](https://stackoverflow.com/a/24948550)

## 💨 Hızlı Notlar

* İlk önce `Controller` clasına ekle sonra `Scene Builder` tarafında `fx:id`'ye eşle
* `drive.png` okunmuyor ama `google_drive.png` okunuyor
  * Refactor ile ismi yenilenirse de düzeliyor
  * Resimlerin herbiri **src dizinininin altında** olmalı
* Üst üste tasarımlar için tasarım yapacağın paneli `Hierarchy` kısmından en alta alırsan, diğerlerinin üstüne gelir ve karışmaz
* Ya da visible değerini `false` yaparsın
* En alta alınan program çalıştığında ilk görülendir
* [Arkaplanı görünmez yapma](https://stackoverflow.com/a/48404925/9770490)

## 📦 JPackage ile Çıkarma

* İlk olarak [buradan](https://jdk.java.net/jpackage/) JPackage'ı indirmen lazım.

> [MSPaint](https://wiki.ms-paint-i.de/developing#prerequesits) adlı yazılım JPackage ile çıkarılmış \(?\)

## Kod Notları



## Listeners \(Eylem Yönetimi\)

### Ekranı Taşıma İşlemi

```java
public class Main extends Application {

    private double xOffset;
    private double yOffset;

    @Override
    public void start(Stage primaryStage) throws Exception{
        Parent root = FXMLLoader.load(getClass().getResource("sample.fxml"));

        primaryStage.setTitle("Hello World");
        primaryStage.setScene(new Scene(root));
        primaryStage.show();

        root.setOnMousePressed(mouseEvent -> {
            xOffset = mouseEvent.getSceneX();
            yOffset = mouseEvent.getSceneY();
        });

        root.setOnMouseDragged(mouseEvent -> {
            primaryStage.setX(mouseEvent.getScreenX() - xOffset);
            primaryStage.setY(mouseEvent.getScreenY() - yOffset);
        });
    }


    public static void main(String[] args) {
        launch(args);
    }
}
```

## Harici Bağlantılar

* [JavaFX ImageView'i Dosya İle Değiştirme](https://stackoverflow.com/questions/7830951/how-can-i-load-computer-directory-images-in-javafx)
* [JavaFX Executable File](https://www.youtube.com/watch?v=_KHCHiH2RZ0)
* [JavaFX Drag and Drop for Internal and External Communication](https://www.youtube.com/watch?v=f7KGXUrAH0g)
* [JavaFX Settings UI Design - Scene builder and Netbeans](https://youtu.be/gJYXctDSIl8?list=PLniX3R2-dwS90WpmHq-hD7g_3xnkTwB6w)
* [JPackage Tools](http://jdk.java.net/jpackage/)
* [Listener Yönetimi](https://www.javacodegeeks.com/2015/01/dont-remove-listeners-use-listenerhandles.html)
* [JavaFX Jar çıkarma - Intellij]()

