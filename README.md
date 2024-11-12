
# YOLOv5 Setup and Training Guide

1. **Clone YOLOv5 Repository**
   ```bash
   git clone https://github.com/ultralytics/yolov5


2. **Install Requirements**
   ```bash
   cd yolov5
   pip install -r requirements.txt
   ```

3. **Set Up Datasets**
   - Ensure `train`, `test`, and `val` folders are correctly structured.

4. **Edit `data.yaml`**
   - Specify the paths and number of classes:
     ```yaml
     train: (path to train folder)
     val: (path to val folder)
     test: (path to test folder)
     nc: (number of labeled classes)
     ```

5. **Modify Model Config File**
   - Go to `yolov5/models` and edit the `.yaml` file for your chosen model (eg. `yolov5n.yaml`) to match the number of classes:
     ```yaml
     nc: (same number of classes as in data.yaml)
     ```

6. **Train the Model**
   ```bash
   python train.py --device cpu --img 640 --batch 16 --epochs 100 --data data.yaml --cfg ./models/yolov5n.pt --weights yolov5n.pt
   ```
     ###### * (options) refer to parse_opt() in train.py
   
8. **Test the Model**
   ```bash
   python val.py --data data.yaml --weights runs/train/exp/weights/best.pt --batch-size 16 --imgsz 640 --device cpu --task test
   ```
```
