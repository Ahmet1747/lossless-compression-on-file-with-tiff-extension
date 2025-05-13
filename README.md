# lossless compression on file with tiff extension
 Bu proje, TIFF (Tagged Image File Format) uzantılı bir görüntüyü kaypsız sıkıştırma yöntemleri kullanarak optimize etmeyi amaçlamaktadır. TIFF formatı, yüksek kaliteli görüntüleri saklamak için yaygın olarak kullanılır ve kayıpsız sıkıştırma seçenekleri sunar. Bu projede, LZW (Lempel–Ziv–Welch) algoritması kullanılarak görüntü sıkıştırma işlemi gerçekleştirilmiştir.
Kayıpsız Sıkıştırma: Görüntünün herhangi bir kalite kaybı olmaksızın boyutunun azaltıldığı
 sıkıştırmadır. 

Kullanılan Formatlar ve Yöntemler

1.PNG ( Portable Network Graphics )

Deflate (LZ77 + Huffman kodlama) ile görüntüyü sıkıştırır.



2. TIFF (Tagged Image File Format)

TIFF görüntüsünde LZW sıkıştırma kullanarak tekrar eden görüntü verilerinin karakter dizilerini daha kısa bir şekilde temsil ederek dosya boyutunu küçültür. Deflate, PackBits algoritmaları da kullanılabilir. Tıpta özellikle kullanılır.

3.Bitmap

4.GIF

Kayıpsız Sıkıştırma Avantajları

- Veri kaybı olmaz.
- Orijinal kalite korunur.
- Veri Bütünlüğü korunur.
- Yedekleme ve Arşivleme için ideal

Dezavantajları

- Yüksek çözünürlükteki görüntüler için daha az sıkıştırma oranı sağlar.
- Kayıplı sıkıştırmaya göre daha büyük boyut
- Görüntüler için daha çok kayıplı sıkıştırma tercih edilir.
- Sistem açısından daha fazla bellek ve güç kullanımı olur.


 ![image](https://github.com/user-attachments/assets/3bedffe9-7044-44c6-9c03-747bed2efa70)
 LZW algoritması ile  görüntü verisinin piksel değerleri bir byte dizisi haline getirilir. Örnek olarak [120,120,120,80,120] gibi. LZW algoritması bu tekrar eden  desenleri yani pikselleri tanır ve sıkça tekrarlayanlara karşılık gelen kısa kodlar atar. Algoritma piksel değerlerini okurken, 120'den sonra tekrar 120 gelirse 120120 olarak ikili örüntü oluşturur. Bu şekilde tekrar eden piksel desenleri kodlara dönüştürülür ve daha az yer kaplayan bir sayı dizisi elde edilir. Ne kadar çok tekrar eden piksel değeri varsa o kadar sıkıştırma yapılmış olur.
 
Bu kodlara karşılık gelen piksel dizileri çözülür. Her yeni kodla birlikte sözlük genişletilerek orijinal görüntü geri getirilmiş olur.
![image](https://github.com/user-attachments/assets/ff2497db-9241-41ba-88a8-bd4fdd50533a)

Görüntüyü gri tonlamaya çevirdik. Çünkü tek kanal üstünde sıkıştırma yapmak daha kolaydır. Oluşturulan LZW algoritmaları ile görüntüyü sıkıştırdık. 

 ![image](https://github.com/user-attachments/assets/2645b705-1696-4fe9-8058-b62d81b428d1)

 ![image](https://github.com/user-attachments/assets/216a342c-d17e-4d58-9dd7-ad8c05e4f2cd)
![image](https://github.com/user-attachments/assets/ac3c69b7-203e-4060-a672-f46c9f1a8e6c)

Burada da büyük bir sıkıştırma oranı gözlemleniyor.137 MB boyutlu bir görüntü dosyasını 13 MB' a indirildi. Ve kayıpsız bir şekilde yapıldı.

![image](https://github.com/user-attachments/assets/31a00ef8-848a-47e7-8106-4d581acf222a)

