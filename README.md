# ComputerVision-YoloV5

*Yolo v5'in Avantajları ve Dezavantajları:
   *YOLOv4'ten yaklaşık %88 daha küçüktür. (27 MB vs 244 MB)
   *YOLOv4'ten yaklaşık %180 daha hızlıdır. (140 FPS vs 50 FPS)

YOLOv5 için asıl sorun: diğer YOLO sürümleri gibi resmi bir belge yayınlanmamış olmasıdır. Ayrıca, YOLO v5 hala geliştirme aşamasındadır ve ultralytics'ten sık sık güncellemeler almaktadır.


![image](https://user-images.githubusercontent.com/59237081/146679876-5e74d28d-2f1b-46e7-86f0-cfeb027db991.png)
&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp YOLOV5'in diğer versiyonlarına göre performans farkı


Biz projemizde YoloV5 kullandık. 
Projemizin başında Drone verisi kullandık ancak istediğimiz başarıyı verinin tam olarak güzel olmasından dolayı elde edemedik.Bu yüzden elimizde olan verilerden iyi durumda olanları etiketleyip YoloV5 ile eğitip hızlıca bir sonuç aldık.

Drone Veri Seti: https://www.kaggle.com/mcagriaksoy/amateur-unmanned-air-vehicle-detection-dataset

Drone verisinin eğitim sonucu:
![image](https://user-images.githubusercontent.com/59237081/146680190-c98ab4ca-65fc-480d-8852-d536e99d604a.png)

Ardından daha iyi bir sonuç almak için COCO128 verisini kullandık: https://www.kaggle.com/ultralytics/coco128 

Bu veri kümesi, 2017 COCO treninin ilk 128 görüntüsünü içerir. YOLOv5 için öğretici veri kümesi olarak kullanılır: https://github.com/ultralytics/yolov5

Veri kümesi, eğitmek ve test etmek için aynı 128 görüntüyü kullanır. Daha büyük bir veri kümesini eğitmeden önce küçük bir veri kümesinde fazla takmayı göstererek bir eğitim hattını doğrulamak amaçlanmıştır.

COCO128 verisinin eğitiminden sonra tespit yapabilmesi için verdiğimiz fotoğraflarda beklediğimizin üstünde olumlu sonuç elde ettik.

Coco128 verisinin eğitim sonuçları:

![image](https://user-images.githubusercontent.com/59237081/146680420-0db703ed-7451-4cb9-a9a6-9895ee3279ce.png)

![image](https://user-images.githubusercontent.com/59237081/146680430-3049d94b-bd15-4fec-b97c-51d72b3b4404.png)

Başlamak için :

!git clone https://github.com/ultralytics/yolov5  # clone

%cd yolov5

%pip install -qr requirements.txt  # install

import torch

from yolov5 import utils

display = utils.notebook_init()  # checks

