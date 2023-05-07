# -LSTM-model-for-binary-classification

목적 : CNN-LSTM모델로 학습을 할 수 있는지 확인하기위한 작업

1차 데이터 수집 : YOLO v5를 이용하여 사람객체 탐지 후 탐지된 객체의 바운딩박스 이미지를 사용

원본 이미지 : ![img900](https://user-images.githubusercontent.com/47483492/236686105-d1e68916-f5be-47b6-8a90-f49ececc8e5c.jpg)

탐지된 객체 이미지 : ![img900](https://user-images.githubusercontent.com/47483492/236686044-4393992a-96ab-4c30-9393-07b0383999ed.jpg)


2차 데이터 수집 : 1차에서 수집한 데이터를 CNN-LSTM모델에 사용하기위해 넘어지는 행위를 1 일반적으로 걷는 행위를 0으로 지정하여 분류한 후 각각 저장


데이터 전처리 방법 : 
- resize_image함수를 사용하여 이미지를 64x64크기로 조정하고 픽셀값을 [0,1]범위로 스케일링(이렇게 조정된 이미지는 시계열 데이터로 구성된 입력 시퀀스를 만들기 위함)

- load_data함수를 사용하여 데이터를 로드하고 Numpy배열로 변환 data_path변수에 지정된 경로에 있는 이미지 데이터를 불러오고 sequence_length변수에 지정된 길이를 갖는 이미지 시퀀스를를생성후 라벨 0에 대해서는 900번부터 1093번까지의 이미지를 사용, 라벨 1에 대해서는 1093번 부터 1148번까지의 이미지를 사용


전처리 후 이미지 : ![img900](https://user-images.githubusercontent.com/47483492/236686345-d0c29b1b-55e6-4e63-aef0-a2e32dc5ef2f.jpg)


