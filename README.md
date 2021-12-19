<h2 style ="text-align": center; "markdown="1"> ComputerVision-YoloV5 </h2>
Google Colab kullanılarak yapılmıştır.
<br> <br>

<h2 style ="text-align": center; "markdown="1"> Kod </h2>

#### Setup
```python

!git clone https://github.com/ultralytics/yolov5
%cd yolov5

```

#### Datanın yüklenmesi ve zip dosyasından çıkarılması
```python

!unzip -q ../coco128.zip -d ../

```


#### Training
```python
!python train.py --img 640 --batch 16 --epochs 3 --data coco128.yaml --weights yolov5s.pt --cache
```

#### Test
```python
!python detect.py --weights yolov5s.pt --img 640 --conf 0.25 --source dosyaDizini
```

#### Output'u görüntülemek
![image](https://user-images.githubusercontent.com/56040583/146684483-fb450571-6ce7-4209-976a-cd608f1777d1.png)

<br>
<h2 style ="text-align": center; "markdown="1"> Sunum </h2>

* Yolo v5'in Avantajları ve Dezavantajları:
   * YOLOv4'ten yaklaşık %88 daha küçüktür. (27 MB vs 244 MB)
   * YOLOv4'ten yaklaşık %180 daha hızlıdır. (140 FPS vs 50 FPS)

   * YOLOv5'in dejavantajı ise: Diğer YOLO sürümleri gibi resmi bir belge yayınlanmamış olmasıdır.   Ayrıca, YOLO v5 hala geliştirme aşamasındadır ve ultralytics'ten sık sık güncellemeler almaktadır.

<br>

![image](https://user-images.githubusercontent.com/59237081/146679876-5e74d28d-2f1b-46e7-86f0-cfeb027db991.png)

<p align="center">
    YOLOV5'in diğer versiyonlarına göre performans farkı
</p>

<br>

Biz projemizde YoloV5 kullandık. 
Projemizin başında Drone fotoğrafı datasını kullandık (Data'ya [buradan](https://www.kaggle.com/mcagriaksoy/amateur-unmanned-air-vehicle-detection-dataset) ulaşabilirsiniz) <br>
Ancak istediğimiz başarıyı data'nın iyi bir data olmamasından dolayı elde edemedik. <br>
Bu yüzden elimizde olan datalardan iyi durumda olanları etiketleyip YoloV5 ile eğitip hızlıca bir sonuç aldık.

<br>

![image](https://user-images.githubusercontent.com/59237081/146680190-c98ab4ca-65fc-480d-8852-d536e99d604a.png)

<p align="center">
    Drone Fotoğrafı Datasının Eğitim Sonucu
</p>

<br>

Ardından daha iyi bir sonuç alabilmek için COCO128 datasını kullandık (Data'ya [buradan](https://www.kaggle.com/ultralytics/coco128 ) ulaşabilirsiniz)

Bu data, 2017 COCO treninin ilk 128 görüntüsünü içerir. YOLOV5 için öğretici bir data olarak kullanılır: https://github.com/ultralytics/yolov5

Bu data, eğitmek ve test etmek için aynı 128 görüntüyü kullanır. Daha büyük bir datayı eğitmeden önce böyle küçük bir data'da sonuçlar gösterilerek performansın ölçülmesi amaçlanmıştır.

<br> <br>

<p align="center">
    <strong> Coco128 Datasının Eğitim Sonuçları </strong>
</p>

<br>

![image](https://user-images.githubusercontent.com/59237081/146680420-0db703ed-7451-4cb9-a9a6-9895ee3279ce.png)

![image](https://user-images.githubusercontent.com/59237081/146680430-3049d94b-bd15-4fec-b97c-51d72b3b4404.png)
