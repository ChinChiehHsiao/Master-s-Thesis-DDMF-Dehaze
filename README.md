# (2025) Master's Thesis : DDMF-Dehaze<br> A Study on Image Dehazing via Deep-Learning-Based Depth Estimation and Multiscale Fusion
![Python](https://img.shields.io/badge/python-3.6.13-blue)
![tensorflow](https://img.shields.io/badge/tensorflow-2.1.0-green)
---

<img width="2182" height="1440" alt="螢幕擷取畫面 2025-08-03 175937" src="https://github.com/user-attachments/assets/fa533527-5ace-46fd-bec4-4f40c3ed92ab" /><br><br>


## 實驗結果
### 去霧與深度圖
![showgithub (cones)](https://github.com/user-attachments/assets/9d8565ae-87e5-47fd-b992-1a7b210584ab)
![showgithub (forest2)](https://github.com/user-attachments/assets/bb15d563-c816-42d3-8a93-20da62f5dbdd)
![showgithub (bear1)](https://github.com/user-attachments/assets/aeac6bb7-661f-4f86-b337-5457aba21859)
![showgithub (03125946_64f412c2409657785)](https://github.com/user-attachments/assets/88ba271b-08d4-4323-b216-e93f207dba9b)
![showgithub (plane)](https://github.com/user-attachments/assets/050957ed-d36a-4127-b190-752e0724d152)<br><br>

### 其他去霧方法比較
<img width="2442" height="1002" alt="螢幕擷取畫面 2025-07-14 143934" src="https://github.com/user-attachments/assets/72a5ff0e-f216-4b4c-97cd-48823e2ca8aa" /><br><br>

### 去霧技術對於物件辨識之效益 (YOLO11x) 
![image](https://github.com/user-attachments/assets/551ae849-9892-4e51-a0b3-38dc6f5d1953)
![image](https://github.com/user-attachments/assets/5a2b432c-8e73-4e47-891e-22ed6466724a)
![image](https://github.com/user-attachments/assets/774eaa86-eb54-4858-a9b3-7d8b955b9292)<br><br>

### 實際去霧影片
 - bear : [(hazy, dehaze, depth)](https://www.youtube.com/watch?v=pj-x6Am7u2Y)、[(hazy, dehaze)](https://www.youtube.com/watch?v=EKMQU_VUEKw)
 - dashcam 1 : [(hazy, dehaze, depth)](https://www.youtube.com/watch?v=ZS3uBpWSmKA)、[(hazy, dehaze)](https://www.youtube.com/watch?v=R2hlng8gy6A)
 - dashcam 7 : [(hazy, dehaze, depth)](https://www.youtube.com/watch?v=kNjC4ndUewU)、[(hazy, dehaze)](https://www.youtube.com/watch?v=hHgnHUj8PEI)
 - dashcam 3 : [(hazy, dehaze, depth)](https://www.youtube.com/watch?v=lZ08_eqMd_0)、[(hazy, dehaze)](https://www.youtube.com/watch?v=h8caJTe-wEI)
 - dashcam 4 : [(hazy, dehaze, depth)](https://www.youtube.com/watch?v=EVcq2cnNCWQ)、[(hazy, dehaze)](https://www.youtube.com/watch?v=yT34_U8t2r4)
 - dashcam 5 : [(hazy, dehaze, depth)](https://www.youtube.com/watch?v=ZtSpRZ7tBPM)、[(hazy, dehaze)](https://www.youtube.com/watch?v=VK3VpuHD0Fs)
 - dashcam 6 : [(hazy, dehaze, depth)](https://www.youtube.com/watch?v=8ZyHo0kDyBs)、[(hazy, dehaze)](https://www.youtube.com/watch?v=ISlnVbWr1qE)
 - dashcam 8 : [(hazy, dehaze, depth)](https://www.youtube.com/watch?v=l5XBZAJMqyY)、[(hazy, dehaze)](https://www.youtube.com/watch?v=8FuxsAphz-I)<br><br>
 


## 訓練與測試
### 訓練
- 您可以在 Kaggle 上下載原始資料集來源 [無霧影像](https://www.kaggle.com/datasets/innominate817/pexels-110k-512p-min-jpg/data)、[深度影像](https://www.kaggle.com/datasets/innominate817/pexels-110k-512p-min-jpg-depth/data)，並執行 `generate hazy image.ipynb` 檔案合成人造有霧影像，同時會存下一個大氣光 `A.csv` 檔案用於後續訓練；或是直接在 [Google Drive](https://drive.google.com/drive/folders/1BqCzjmvuyd-YitLEH-FKEsslsphNciWf?usp=drive_link) 上下載我們已合成的人造有霧影像訓練資料 `image/`、`depth/`、`hazy_image/` 與大氣光 `A.csv` 檔案。
- 使用 `training code.ipynb` 檔案進行訓練，即可得到自行訓練完畢之模型與權重 `model+weights.h5`<br>

### 測試
- 若想測試影像去霧效果，您可以在 [Google Drive](https://drive.google.com/drive/folders/1BqCzjmvuyd-YitLEH-FKEsslsphNciWf?usp=drive_link) 上下載預訓練模型 `model+weights.h5`，並將圖片放進 `data/` 資料夾，執行 `run dehaze.ipynb` 檔案即可，去霧結果將儲存在 `dehaze result/` 資料夾中。<br><br>
- 若想測試去霧後 YOLO 偵測效果，您可以在 [Google Drive](https://drive.google.com/drive/folders/1BqCzjmvuyd-YitLEH-FKEsslsphNciWf?usp=drive_link) 上下載預訓練模型 `model+weights.h5` 與 YOLO11x 模型 `yolo11x.pt`，並將圖片放進 `data/` 資料夾，執行 `run dehaze and YOLO detection.ipynb` 檔案即可，去霧後 YOLO 辨識結果將儲存在 `dehaze and YOLO result/` 資料夾中。<br><br>




環境版本
---
- Python 3.6.13 
- Tensorflow 2.1.0
- Memory : 128 GB
- OS : windows11
- CPU : AMD Ryzen Threadripper 2990WX 32-Core Processor
- GPU : NVIDIA TITAN RTX (24GB)<br><br>



---
關於
---

- 聯繫 : jayabc321@gmail.com
- 機構 : Feng Chia University, Master's Program of Data Science (逢甲大學 數據科學碩士學位學程)
- 作者 : Chin-Chieh Hsiao (蕭晉杰)
- 指導教授 : Cheng-Shu You (游承書 博士)
- 建立時間 : 2025.04.27
- 最後更新 : 2025.08.13
