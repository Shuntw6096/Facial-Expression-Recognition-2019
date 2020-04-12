# Facial-Expression-Recognition-2019
這個專題利用fer2013資料集(from kaggle)訓練CNN．  

資料集介紹
------
* 解析度為48×48的灰階圖片．  
- 預先劃分成一個訓練集與兩個測試集．  
* 總共7個類別，Angry、Disgust、Fear、Happiness、Sadness、Surprise、Neutral．  
![number of data in a predefined data set](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/master/img/number_ds.JPG)  

資料預處理
------
|#|說明|圖片|
|---|----|:---:|
|1|對訓練集做資料清洗，將不包含人臉的圖片過濾|![clean](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/readme/img/clean.JPG)|
|2|利用Dlib預先訓練好的人臉偵測器完成過濾．|![detector](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/readme/img/detector.JPG)|
|3|訓練集過濾後各類別的資料數量．|![after cleaning](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/readme/img/after_cleaning.JPG)|
|4|利用直方圖均衡化對圖片灰階完成歸一化．|![histogram equalization](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/readme/img/hist_equali.JPG)|
|5|透過將原本圖片放大至70 × 70的長寬尺寸，然後對齊圖片四個角落和中間位置剪裁出48 × 48的圖片大小．|![cropping](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/readme/img/cropping.JPG)|
|6|利用對圖片的小角度旋轉增強網路對人臉角度的適應性．|![rotation](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/readme/img/rotation.JPG)|


