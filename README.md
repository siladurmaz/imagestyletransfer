# VGG19 ile Görsel Stil Transferi Web Uygulaması

Bu proje, bir içerik görüntüsüne farklı bir stil görüntüsünün sanatsal özelliklerini aktaran bir web uygulamasıdır. Derin öğrenme için VGG19 modeli kullanılmış, web arayüzü Flask ile geliştirilmiş ve Google Colab üzerinde çalışacak şekilde tasarlanmıştır.
arayüz bu şekildedir
![image](https://github.com/user-attachments/assets/699ee733-5f8e-4989-8e22-6be3d35430bc)

## Temel Özellikler

*   *Sinirsel Stil Transferi:* İçerik resminin yapısını korurken stil resminin dokusunu ve renklerini uygular.
*   *VGG19 Modeli:* Özellik çıkarımı için ImageNet üzerinde eğitilmiş VGG19 ağı kullanılır.
*   *Web Arayüzü:* Kullanıcıların kendi resimlerini yükleyip sonucu görmelerini sağlayan basit ve interaktif bir arayüz (Flask ile).
*   *Colab Uyumluluğu:* Google Colab notebook'u olarak çalıştırılabilir ve pyngrok ile geçici olarak internete açılabilir.

## Kullanılan Ana Teknolojiler

*   Python 3
*   TensorFlow & Keras
*   Flask
*   NumPy, Pillow
*   pyngrok
*   HTML, CSS

## Nasıl Çalıştırılır (Google Colab)

1.  *Notebook'u Açın:* Projenin .ipynb dosyasını Google Colab'da açın.
2.  *Token & Kurulum:* İlk kod hücresini çalıştırarak gerekli kütüphaneleri yükleyin ve Ngrok Auth Token'ınızı ayarlayın.
3.  *HTML Şablonu:* %%writefile templates/index.html içeren hücreyi çalıştırarak web arayüzünü oluşturun.
4.  *Uygulamayı Başlatın:* Ana Flask uygulamasını içeren Python kod hücresini çalıştırın.
5.  *Erişim:* Çıktıda verilen https://<id>.ngrok-free.app benzeri Ngrok URL'sini tarayıcınızda açın.

## Çalışma Prensibi

Uygulama, içerik ve stil resimlerinden VGG19 ağı aracılığıyla özellikler çıkarır. Bu özellikler kullanılarak bir kayıp fonksiyonu (içerik kaybı, stil kaybı, toplam varyasyon kaybı) tanımlanır. İçerik resmi kopyası, bu kayıp fonksiyonunu minimize edecek şekilde Adam optimizatörü ile iteratif olarak güncellenerek stilize edilmiş sonuç görüntüsü elde edilir.

## Proje Yapısı

*   colab_notebook.ipynb: Ana Colab dosyası.
*   templates/index.html: Web arayüzü şablonu.
*   static/uploads/: Yüklenen resimler.
*   static/results/: Oluşturulan stilize resimler.

---
