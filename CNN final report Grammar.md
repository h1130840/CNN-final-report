# 臺北市私立薇閣高級中學114學年度第1學期工程專題
####  班級：二辛   	座號：49   	姓名：楊皓宇
## 一、主題：Transfer Learning with Deep Network Designer
在這次課程中，透過不同的網路神經系統來測試不同種類圖片的判別，探討他們的使用方法以及運作的方式，並且比較它們的不同之處，而這次我選擇用SqueezeNet與GoogLeNet這兩種網路神經系統。
| 項目 | SqueezeNet | GoogLeNet |
| :--- | :--- | :--- |
| 圖片 | <img width="714" height="418" alt="image" src="https://github.com/user-attachments/assets/2ba7b13b-26f9-4b25-a546-c2bd3dc98195" /> | <img width="1419" height="503" alt="image" src="https://github.com/user-attachments/assets/4e3b1cc8-6a87-44ec-b4c4-a87e004a39bc" /> |

參考資料：https://cloud.tencent.com/developer/article/1016524
          https://tigercosmos.xyz/post/2020/10/ai/googlenet/
## 二、收集資料：
收集四種交通工具的圖片，每種各五十張，並分別存入四個資料夾。</br>
<img width="1167" height="661" alt="image" src="https://github.com/user-attachments/assets/9bf64469-6f5f-4361-8783-7830ff0be99f" />
為符合後面資料的限制，將圖片統一轉換成全彩、調整大小為227*227、命名每種交通工具並存進新的資料夾裡分類。</br>
<img width="629" height="681" alt="image" src="https://github.com/user-attachments/assets/bc43bd96-1a30-497c-a4ed-5304a46f275c" />
## 三、建立模型挖掘資料：
選擇網路神經系統(SqueezeNet與GoogLeNet)，將先前收集的圖片資料輸入進去並調整數值，其中，AUGMENTATION OPTION可以用來增強影像資料的訓練，像是在這次的測試中，新增影像對x軸的隨機反射、在 90 ~ -90 度隨機旋轉與隨機縮放 1 ~ 2 倍，用以讓輸入的圖片進行隨機增強。</br>
<img width="1077" height="537" alt="image" src="https://github.com/user-attachments/assets/2082a185-a314-4502-babc-8cf3d97bfe09" />
而在 50 張圖片中，選擇將 70% 用來訓練，30% 用來驗證，以下為訓練圖片的圖示。</br>
<img width="1078" height="566" alt="image" src="https://github.com/user-attachments/assets/4d25fad8-8607-4c65-a195-b3f6a72dc855" />
最後調整符合訓練模型的資料，以SqueezeNet舉例，將檔案大小改成 (1,1)，資料總數改成 4，將WeightLearnRateFactor與BiasLearnRateFactor改為10，以及修改最後的output layer為classificationLayer。</br>
<img width="1097" height="692" alt="image" src="https://github.com/user-attachments/assets/6074ba90-5cd2-4b8a-af5f-7b48ab650fac" />
## 四、實驗結果：
<img width="361" height="637" alt="image" src="https://github.com/user-attachments/assets/bd512445-ecda-4c05-85d9-ed541503b573" />

| 項目 | EX1 | EX2 |
| :--- | :--- | :--- |
| 圖片 | <img width="872" height="175" alt="image" src="https://github.com/user-attachments/assets/afd020b1-8f50-4964-a902-86aa91c9a61a" /> | <img width="874" height="171" alt="image" src="https://github.com/user-attachments/assets/805b3ea7-1d7f-4d56-a5d8-4435cad72c0c" /> |
- $\color{red}{\text{符合兩種訓練模型的圖片大小不同}}$</br>
### SqueezeNet :
<img width="890" height="477" alt="image" src="https://github.com/user-attachments/assets/73de16d9-a4dd-41fa-9fe8-5079db4f7956" />

| motorcycle 100% | train 100% |
| :--- | :--- |
| <img width="379" height="302" alt="image" src="https://github.com/user-attachments/assets/1db68f01-b505-48a3-8286-6d19bbe3940b" />| <img width="382" height="303" alt="image" src="https://github.com/user-attachments/assets/1d523b44-9cb6-4a58-a8b6-925ad165d0f0" /> |
| car 85.9% | bus 87.8% |
| <img width="389" height="311" alt="image" src="https://github.com/user-attachments/assets/59594cec-29ef-415f-b80c-2c2f8d4efcde" /> | <img width="390" height="310" alt="image" src="https://github.com/user-attachments/assets/8b1ebc99-eb72-4a2a-b23b-d367f850d51d" /> |
