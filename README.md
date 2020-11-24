# ML_HouseRegression
[![Work in Repl.it](https://classroom.github.com/assets/work-in-replit-14baed9a392b3a25080506f3b7b6d57f295ec2978f6f33ec97e36a161684cbe9.svg)](https://classroom.github.com/online_ide?assignment_repo_id=3634384&assignment_repo_type=AssignmentRepo)

#   機器學習 – HouseRegression
##  房屋銷售價格預測挑戰
##	一、做法說明
### 1.選擇框架
### 2.資料集預處理
### 3.建立模型
### 4.模型訓練
### 5.測試模型
### 6.輸出結果
##	二、程式流程圖與寫法
![機器學習模型訓練流程圖](https://github.com/t109318121/ML_HouseRegression/blob/main/FlowChart.jpg)
##	三、訓練與驗證損失
### 使用Model 1
超參數設計：設計Learning Rate = 0.001 , Epochs = 200 , 並分別測試Batch_Size 為 64與256。
### ➤Batch_Size = 64
![Batch_Size = 64](https://github.com/t109318121/ML_HouseRegression/blob/main/M1_loss_64.png)
### ➤Batch_Size = 256
![Batch_Size = 256](https://github.com/t109318121/ML_HouseRegression/blob/main/M1_loss_256.png)

由上面兩張圖得知，經由所設計的模型訓練後，Train Loss從原本的450000降至80000左右，Validation Loss從原本的180000降至60000～70000左右。觀察Loss曲線，在Batch_Size較大時，Validation Loss下降較為平緩，震盪情況比較不明顯。
### 使用Model 2
超參數設計：設計Learning Rate = 0.001 , Epochs = 1000 , Batch_Size = 5000。
![Batch_Size = 5000](https://github.com/MachineLearningNTUT/regression-t109318121/blob/main/M2_loss_5000.png)

由上圖得知，經由所設計的模型訓練後，Train Loss與Validation Loss從原本約500000降至70000左右，此時已無震盪情況發生。

##   四、Loss分析與改進
在資料預處理的過程可能沒有注意到空值，缺失值，異常值，或者可能需移除較不重要的欄位。
在梯度下降的優化中，當學習率太高時會導致loss值不收斂，太低則下降緩慢，對於超參數的調整也是尤其重要。


