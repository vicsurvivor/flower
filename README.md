## 圖像分類
目標:使用TensorFlow模型框架建立分類模型，以花卉照片訓練並使用驗證集產出模型準確率95%以上/混淆矩陣，將模型驗證結果整理。  

## 圖片檢視
人工檢視訓練資料集，將不清楚、分類不正確、單圖包含多個分類的資料 
![bad_image](https://github.com/user-attachments/assets/7174ef9b-f0dc-451d-9719-d01c19ba9198)

排除 daisy: 0 dandelion: 1 roses: 41 sunflower:1 tulips: 68, total = 111張
最後Training Data使用2952張
## 模型選擇
根據ImageNet評分高且支援於tensorflow.keras.applications優先測試  
選取EfficientNetV2S, EfficientV2L與ConvNeXtTiny, ConvNeXtSmall, ConvNeXtBase測行測試  
|Model Architecture | Inference Accuracy|
| ------------- | ------------- |
|3-layer Convolutional Net | ~80%|
|EfficientNetV2S / V2L | ~90%|
|ConvNeXt-Tiny / Small | ~91%|
|ConvNeXt-Base | ~97%|
## 參數設定
optimizer = Adam(learning_rate=0.0005)  
loss='categorical_crossentropy'  

## 模型訓練  
IMG_HEIGHT = 224  
IMG_WIDTH = 224  
BATCH_SIZE = 16  
EPOCHS = 500  

Data Augmentation:      
image = tf.image.random_flip_left_right(image)  
image = tf.image.random_brightness(image, max_delta=0.2)  
image = tf.image.random_contrast(image, 0.8, 1.2)  

Preprocess:
label = tf.one_hot(label, num_classes)

data_split:
k-fold = 2
## 驗證指標與混淆矩陣
![Loss and Acc](https://github.com/user-attachments/assets/0bfbeaa4-fb2d-4cc2-9370-92d0034c5f10)
![Confusion_metrix](https://github.com/user-attachments/assets/b55f91e9-f077-4bfa-bfcf-2421fd043094)
![wrong_predict](https://github.com/user-attachments/assets/5d5af46e-bfef-4e21-a1d7-8fc22c513a03)

