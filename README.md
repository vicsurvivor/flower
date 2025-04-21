## 圖像分類
目標:使用TensorFlow模型框架建立分類模型，以花卉照片訓練並使用驗證集產出模型準確率95%以上/混淆矩陣，將模型驗證結果整理。

## 圖片檢視
人工檢視訓練資料集，將不清楚、分類不正確、單圖包含多個分類的資料排除

## 模型選擇
根據ImageNet評分高且支援於tensorflow.keras.applications優先測試
選取EfficientNetV2S, EfficientV2L與ConvNeXtBase,ConvNeXtLarge

## EfficientNetV2S:
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 efficientnetv2-s (Function  (None, 7, 7, 1280)        20331360  
 al)                                                             
                                                                 
 global_average_pooling2d (  (None, 1280)              0         
 GlobalAveragePooling2D)                                         
                                                                 
 dense (Dense)               (None, 256)               327936    
                                                                 
 dropout (Dropout)           (None, 256)               0         
                                                                 
 dense_1 (Dense)             (None, 5)                 1285      
                                                                 
=================================================================
Total params: 20660581 (78.81 MB)
Trainable params: 329221 (1.26 MB)
Non-trainable params: 20331360 (77.56 MB)
_________________________________________________________________

## EfficientNetV2M:
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 efficientnetv2-m (Function  (None, 7, 7, 1280)        53150388  
 al)                                                             
                                                                 
 global_average_pooling2d_1  (None, 1280)              0         
  (GlobalAveragePooling2D)                                       
                                                                 
 dense_2 (Dense)             (None, 256)               327936    
                                                                 
 dropout_1 (Dropout)         (None, 256)               0         
                                                                 
 dense_3 (Dense)             (None, 5)                 1285      
                                                                 
=================================================================
Total params: 53479609 (204.01 MB)
Trainable params: 329221 (1.26 MB)
Non-trainable params: 53150388 (202.75 MB)
_________________________________________________________________

## EfficientNetV2L:
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 efficientnetv2-l (Function  (None, 7, 7, 1280)        117746848 
 al)                                                             
                                                                 
 global_average_pooling2d_2  (None, 1280)              0         
  (GlobalAveragePooling2D)                                       
                                                                 
 dense_4 (Dense)             (None, 256)               327936    
                                                                 
 dropout_2 (Dropout)         (None, 256)               0         
                                                                 
 dense_5 (Dense)             (None, 5)                 1285      
                                                                 
=================================================================
Total params: 118076069 (450.42 MB)
Trainable params: 329221 (1.26 MB)
Non-trainable params: 117746848 (449.17 MB)
_________________________________________________________________
## ConvNeXtTiny:
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 convnext_tiny (Functional)  (None, 7, 7, 768)         27820128  
                                                                 
 global_average_pooling2d_3  (None, 768)               0         
  (GlobalAveragePooling2D)                                       
                                                                 
 dense_6 (Dense)             (None, 256)               196864    
                                                                 
 dropout_3 (Dropout)         (None, 256)               0         
                                                                 
 dense_7 (Dense)             (None, 5)                 1285      
                                                                 
=================================================================
Total params: 28018277 (106.88 MB)
Trainable params: 198149 (774.02 KB)
Non-trainable params: 27820128 (106.13 MB)
_________________________________________________________________
## ConvNeXtSmall:
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 convnext_small (Functional  (None, 7, 7, 768)         49454688  
 )                                                               
                                                                 
 global_average_pooling2d_4  (None, 768)               0         
  (GlobalAveragePooling2D)                                       
                                                                 
 dense_8 (Dense)             (None, 256)               196864    
                                                                 
 dropout_4 (Dropout)         (None, 256)               0         
                                                                 
 dense_9 (Dense)             (None, 5)                 1285      
                                                                 
=================================================================
Total params: 49652837 (189.41 MB)
Trainable params: 198149 (774.02 KB)
Non-trainable params: 49454688 (188.65 MB)
_________________________________________________________________
## ConvNeXtBase:
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 convnext_base (Functional)  (None, 7, 7, 1024)        87566464  
                                                                 
 global_average_pooling2d_5  (None, 1024)              0         
  (GlobalAveragePooling2D)                                       
                                                                 
 dense_10 (Dense)            (None, 256)               262400    
                                                                 
 dropout_5 (Dropout)         (None, 256)               0         
                                                                 
 dense_11 (Dense)            (None, 5)                 1285      
                                                                 
=================================================================
Total params: 87830149 (335.05 MB)
Trainable params: 263685 (1.01 MB)
Non-trainable params: 87566464 (334.04 MB)
_________________________________________________________________
## 參數設定
optimizer = Adam(learning_rate=0.0005)
loss='categorical_crossentropy'

## 模型訓練

## 驗證指標與混淆矩陣

## 總結

