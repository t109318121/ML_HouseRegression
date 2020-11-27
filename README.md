# ML_HouseRegression
[![Work in Repl.it](https://classroom.github.com/assets/work-in-replit-14baed9a392b3a25080506f3b7b6d57f295ec2978f6f33ec97e36a161684cbe9.svg)](https://classroom.github.com/online_ide?assignment_repo_id=3634384&assignment_repo_type=AssignmentRepo)

#   機器學習 – HouseRegression
##  房屋銷售價格預測挑戰

##  目錄
1.  [一、做法說明](#一、做法說明)

2.  [程式流程圖與寫法](#二、程式流程圖與寫法)

3.  [訓練與驗證損失](#三、訓練與驗證損失)

4.  [Loss分析與改進](#四、Loss分析與改進)
-----
##	一、做法說明
### 1.選擇框架
### 2.資料集預處理
### 3.建立模型
### 4.模型訓練
### 5.測試模型
### 6.輸出結果
##	二、程式流程圖與寫法
![機器學習模型訓練流程圖](https://github.com/t109318121/ML_HouseRegression/blob/main/FlowChart.jpg)

-----
##	三、訓練與驗證損失
### 使用Model 1
超參數設計：設計Learning Rate = 0.001 , Epochs = 200 , 並分別測試Batch_Size 為 64與256。
### ➤Batch_Size = 64
![Batch_Size = 64](https://github.com/t109318121/ML_HouseRegression/blob/main/M1_loss_64.png)
### ➤Batch_Size = 256
![Batch_Size = 256](https://github.com/t109318121/ML_HouseRegression/blob/main/M1_loss_256.png)

由上面兩張圖得知，經由所設計的模型訓練後，Train Loss從原本的450000降至80000左右，Validation Loss從原本的180000降至60000～70000左右。觀察Loss曲線，在Batch_Size較大時，Validation Loss下降較為平緩，震盪情況比較不明顯。
### 使用Model 2
超參數設計：設計Learning Rate = 0.001 , Epochs = 2000 , Batch_Size = 5000。
![Batch_Size = 5000](https://github.com/t109318121/ML_HouseRegression/blob/main/M2_loss_5000.png)

由上圖得知，經由所設計的模型訓練後，Train Loss與Validation Loss從原本約500000降至60000左右，此時已無震盪情況發生。

-----
##   四、Loss分析與改進
####    ➤資料本身的特徵中可能夾雜一些較不重要的資訊，透過在資料預處理的過程挑選比較具有指標性的特徵並移除較不重要的欄位。空值，缺失值，異常值也須更仔細檢查，在預處理過程中減少loss降不下去的潛在因素。訓練中，在梯度下降的優化中，當學習率太高時會導致loss值不收斂，太低則下降緩慢，對於超參數的調整也是尤其重要。如果出現過擬合的現象可能是特徵數太少，丟棄太多資訊，須調整篩選特徵，也可以適時在神經網絡使用dropout，於神經網路中隨機丟棄部分神經元。在訓練時，dropout可可使得每次只有部分網路結構得到更新，高效的將神經網絡模型平均化。



