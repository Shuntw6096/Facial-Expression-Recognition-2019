# Facial-Expression-Recognition-2019
這個專題利用fer2013資料集(from kaggle)訓練CNN，在fer2013資料集已預先劃分成一個訓練集與兩個測試集．
資料集介紹
------
資料預處理
------
![number of data in a predefined data set](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/master/img/number_ds.JPG)  
對訓練集做資料清洗，將不包含人臉的圖片過濾．  
![clean](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/readme/img/clean.JPG)  
利用Dlib預先訓練好的人臉偵測器完成過濾．  
![detector](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/readme/img/detector.JPG)  
訓練集過濾後各類別的資料數量．  
![after cleaning](https://github.com/Shuntw6096/Facial-Expression-Recognition-2019/blob/readme/img/after_cleaning.JPG)  



