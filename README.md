# Object-Detection-with-X-ray scan
 
## 진행기간 
- 2022.08.19 ~ 2022.09.02

## 목적
- **YOLO 모델을 활용하여 출국시간은 단축하면서 저장매체를 따로 빼줘야 하는 불편함을 해소할 수 있는 Object Detection Model 생성**  
          
## 코드 설명

   
코드     | 코드 링크   | 
:-------:|:-----------:|
Image Preprocessing |[X-ray image preprocessing](https://github.com/AliceecilA93/Object-Detection-with-X-ray-scan/blob/main/Prepare%20before%20putting%20darknet/X-ray%20image%20preprocessing.ipynb)|  
Make XML to TXT | [Make XML to TXT](https://github.com/AliceecilA93/Object-Detection-with-X-ray-scan/blob/main/Prepare%20before%20putting%20darknet/Make%20XML%20to%20TXT.ipynb)|
Split dataset| [Split dataset](https://github.com/AliceecilA93/Object-Detection-with-X-ray-scan/blob/main/Prepare%20before%20putting%20darknet/Split%20dataset.ipynb)| 
Check bbox| [Check bbox](https://github.com/AliceecilA93/Object-Detection-with-X-ray-scan/blob/main/Prepare%20before%20putting%20darknet/Check%20bbox.ipynb) |
YOLOv3| [YOLOv3](https://github.com/AliceecilA93/Object-Detection-with-X-ray-scan/blob/main/Model/YOLOv3.ipynb)|    
YOLOv4| [YOLOv4](https://github.com/AliceecilA93/Object-Detection-with-X-ray-scan/blob/77aa339eea488fc769cf608345438f41f2c5080d/Model/YOLOv4.ipynb)|   
Inference| [X-ray scan YOLOv4 inference](https://github.com/AliceecilA93/Object-Detection-with-X-ray-scan/blob/77aa339eea488fc769cf608345438f41f2c5080d/Model/X-ray%20scan%20YOLOv4%20inference.ipynb)|    


## 사용된 데이터  

- AI Hub 위해물품 엑스레이 이미지 (https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=233)

## 사용된 모델 

- YOLOv3
- YOLOv4

## 과정  

 1. 개발환경 : Python, Tensorflow, Colab , Visual Studio 
 
 2. 데이터 전처리
  2-1. Darknet에 필요한 Image, TXT 파일 생성 
  
     * Image preprocessing
     - Image resize  
     
     ![image](https://user-images.githubusercontent.com/112064534/207084566-f05379a8-c943-442c-83d4-b6702a82bdad.png)
  
     - Coordinate transformation (좌표변경) 
     
     ![image](https://user-images.githubusercontent.com/112064534/207085042-370979bc-f1e6-4f71-9dc8-e66343da2565.png)
     
     - Image cropping
     
     ![image](https://user-images.githubusercontent.com/112064534/207085385-e45fdc0d-40ec-4a7e-ae9b-17de493f1788.png)
      

 3. 데이터셋
 
 * 분류해야 할 데이터셋 종류
 
 ![image](https://user-images.githubusercontent.com/112064534/207084020-cf21c75a-a3d2-4991-be09-cec364bff075.png)

 4. 데이터셋 분석 
 
 * 데이터의 양 
 
 ![image](https://user-images.githubusercontent.com/112064534/207084226-1dfc797c-a4eb-4329-aec3-92044995195f.png)

 5. 모델 분석 
 
 ![image](https://user-images.githubusercontent.com/112064534/207086072-b2119740-59f9-40cd-96e8-e890deb6204e.png)

 
 ==> Cropping을 했을 때 작은 객체를 더 잘 잡아줌으로써 mAP가 상승된 것을 알 수 있으며, 
     하나의 이미지에 Annotation이 1개인 것 보다 Annotation이 n개 였을 때가 성능이 더 좋다는 것을 알 수 있습니다. 
     


 6. Inference video 
 ['BEST mAP Inference'] (https://www.youtube.com/watch?v=_O-fLSeARNE)
 
 

## 결과
- Object Detection의 경우 이미지의 해상도가 높으면 높을수록 객체를 잘 잡아낼 수 있기 때문에 
  한정된 컴퓨터 자원 안에서 이미지를 원본 사이즈와 비슷하게 Cropping하면서 mAP를 끌어올릴 수 있었고 
  하나의 이미지에 Annotation 1개인 것을 학습시키는 것보다는 하나의 이미지에 Annotation n개인 것을   학습시키는 것이 성능이 더 좋은 것으로 보아 하나의 이미지당 여러개의 객체가 잡힌다면 한 장만으로도   가치가 높다는 것을 알 수 있었다. 
    

## 참조

- REDMON, Joseph; FARHADI, Ali. Yolov3: An incremental improvement. arXiv preprint arXiv:1804.02767, 2018.
https://doi.org/10.48550/arXiv.1804.02767

- BOCHKOVSKIY, Alexey; WANG, Chien-Yao; LIAO, Hong-Yuan Mark. Yolov4: Optimal speed and accuracy of object detection. arXiv preprint arXiv:2004.10934, 2020
https://doi.org/10.48550/arXiv.2004.10934



