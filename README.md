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

CNN模型
------
|Layer|Output Shape|Activate Function/Kernel Size/Stride|Drop Rate|
|---|----|----|:---:|
|Input|(48,48,1)|N.A.|	N.A.|
|2D-Convolution|(46,46,64)|Relu/(3,3)/(1,1)|N.A.|
|2D-Convolution|(46,46,64)|Relu/(3,3)/(1,1)|N.A.|
|Batch Normalization|(46,46,64)|N.A.|N.A.|
|Max pooling|(23,23,64)|N.A./(2,2)/(2,2)|N.A.|
|2D-Convolution|(23,23,128)|Relu/(3,3)/(1,1)|N.A.|
|Batch Normalization|(23,23,128)|N.A.|N.A.|
|2D-Convolution|(23,23,128)|Relu/(3,3)/(1,1)|N.A.|
|Batch Normalization|(23,23,128)|N.A.|N.A.|
|Max pooling|(11,11,128)|N.A./(2,2)/(2,2)|N.A.|
|2D-Convolution|(11,11,256)|Relu/(3,3)/(1,1)|N.A.|
|Batch Normalization|(11,11,256)|N.A.|N.A.|
|2D-Convolution|(11,11,256)|Relu/(3,3)/(1,1)|N.A.|
|Batch Normalization|(11,11,256)|N.A.|N.A.|
|Max pooling|(5,5,256)|N.A./(2,2)/(2,2)|N.A.|
|2D-Convolution|(5,5,512)|Relu/(3,3)/(1,1)|N.A.|
|Batch Normalization|(5,5,512)|N.A.|N.A.|
|2D-Convolution|(5,5,512)|Relu/(3,3)/(1,1)|N.A.|
|Batch Normalization|(5,5,512)|N.A.|N.A.|
|Max pooling|(2,2,512)|N.A./(2,2)/(2,2)|N.A.|
|Flatten|2048|N.A.|N.A.|
|Fully-Connected|512|Relu|0.4|
|Fully-Connected|256|Relu|0.4|
|Fully-Connected|128|Relu|0.4|
|Fully-Connected|7|Softmax|N.A.|

Total Parameters：5,905,863  



