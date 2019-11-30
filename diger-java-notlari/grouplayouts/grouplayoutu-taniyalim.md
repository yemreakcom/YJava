---
description: GroupLayout kullanımı ve açıklaması
---

# 🔰 GroupLayout'u Tanıyalım

## 🔰 Tanıtım

İnternet'te pek kaynağı bulunmayan ve diğer layoutlara nazaran daha zor olan `GroupLayout`, doğru yerlerde kullanıldığında oldukça kullanışlı olmakta. 

{% hint style="info" %}
🧙‍ Video yok mu dersen \(ki bu yazıda çok detaylı bir şekilde ele aldım\) [buraya](https://www.youtube.com/watch?v=vA9ZSgaLaJs&t=317s) tıklayarak farklı bir kaynağa bakabilirsin :\(
{% endhint %}

## 🏃‍♀️ Kısaca GroupLayout

* Hem yatay, hem de dikey olarak özel tasarlanmış bir layout oluşturmamıza olanak sağlamakta.
* Bu layout diğer layoutların aksine, new GroupLayout\(...\) şeklinde kullanılmamakta, bunu kullanmak için GroupLayout gl = new GroupLayout\(component\); şeklinde nesnesini oluşturup özelleştirmemiz gerekmekte.
  * compenent ; Layout'u kullanacak olan compenent.
* Özelleştirmeyi yaparken, soldan sağa \(horizontal\) ve yukarıdan aşağı \(vertical\) olarak componentlerin konumlarını ayarlamamız gerekmekte. Ayrıca girilen kodların birbiri ile uyumlu olması gerekmekte, aksi halde kod hata verecektir.

## 🧱 Ana GroupLayout Metotları

* setHorizontalGroup\(Group grup\); Componentlerin yatay konumlarını bu metodu kullanarak ayarlayacağız.
* setVerticalGroup\(Group grup\); Componentlerin dikey konumlarını ayarlamak için.
* Bu iki metodun içerisine;
  * createSequentialGroup\(\); Ardışık olarak compenent eklemek için oluşturulan grup.
  * createParallelGroup\(\); Paralel olarak component eklemek için oluşturulan grup.
* Bu metodların ardından da
  * addComponent\(component\); ile componentlerimizi ekleyeceğiz.
  * addGap\(...\); ile gerekirse boşluk ekleyeceğiz.

## 👷‍♂️ Temel Yapılış Şekli

* Yatay İnceleme için hayali dikey çizgiler
* Dikey İnceleme için hayali yatay çizgiler çiziyoruz
* Aynı çizgide olanlar paralel, farklı çizgilerde olanlar seridir.

![](../../.gitbook/assets/image.png)

