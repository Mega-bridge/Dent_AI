1. YOLOv5 Clone
     git clone https://github.com/ultralytics/yolov5

2. requirements.txt 설치
     cd yolov5
     pip install -r requirements.txt
3. Datasets 세팅 확인
    (train/test/valid folders)
4. data.yaml 확인
     train: (train 폴더 경로)
     val: (val 폴더 경로)
     test : (test 폴더 경로)

     nc : (라벨링 Classes 개수)
     ...
6. cfg 수정
     >> yolov5/models 폴더 >> 사용할 model 파일 이름의 yaml 파일 nc: (yaml nc와 동일하게 수정)

7. Dataset 학습
     python train.py --device cpu --img 640 --batch 16 --epochs 100 --data data.yaml --cfg ./models/yolov5n.pt --weights yolov5n.pt
     (default)
   
