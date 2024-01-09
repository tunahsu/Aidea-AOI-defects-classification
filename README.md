# Aidea-AOI

此專案為藉由AOI影像訓練深度學習模型辨識產品表面瑕疵，使用框架為 TensorFlow。結果顯示預訓練 DenseNet 模型的測試準確達到99.4%

## 資料集

來源: https://aidea-web.tw/topic/a49e3f76-69c9-4a4a-bcfc-c882840b3f27

官方提供之影像資料包含 6 個類別(正常類別 + 5 種瑕疵類別)下載資料 aoi_data.zip 檔案包含：

* train_images.zip：訓練所需的影像資料共計 2528 張
* train.csv：包含 2 個欄位 ID 和 Label
* ID：影像的檔名
* Label：瑕疵分類類別(0 表示 normal, 1 表示 void, 2 表示 horizontal defect, 3 表示 vertical defect, 4 表示 edge defect, 5 表示 particle)
* test_images.zip：測試所需的影像資料共計 10142 張
* test.csv：包含 2 個欄位ID 和 Label。
* ID：影像的檔名
* Label：瑕疵分類類別(其值只能是下列其中之一： 0, 1, 2, 3, 4, 5)

## 資料前處理

* 影像水平、垂直平移 0.05
* 影像隨機旋轉 15 度
* 影像大小縮為 224 x 224

## 訓練環境

* Python 3.10.12
* CUDA Toolkit 12.2
* Tensorflow 2.15.0
* OpenCV 4.8.0

## 模型 & 超參數

* DenseNet169
* Batch size: 32
* Epochs: 50(early stopping)
* Optimizer: Adam
* Dynamic learning rate: 0.0001
