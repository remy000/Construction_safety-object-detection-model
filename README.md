# Workplace Safety Object Detection using YOLOv8 (Trained from Scratch)

This project presents a computer vision solution for detecting whether individuals are wearing helmets, vest as essential part of Personal Protective Equipment (PPE).
It leverages the YOLOv8 object detection architecture and is trained from scratch on a custom dataset.

## Dataset

- **Name:** roboflow construction safety dataset 
- **Format:** YOLO format (images and labels)  
- **Link:** [Robflow Dataset - PPE Object Detection](https://universe.roboflow.com/roboflow-100/construction-safety-gsnvb/dataset/2/download/yolov5pytorch)  
- **Classes:**  
  - `helmet`  
  - `no_helmet`
  - `no-vest`
  - `vest`
  - `person` 
Sample structure of the `data.yaml` used:

```yaml
train: images/train
val: images/val

nc: 5
names: ['helmet', 'no-helmet', 'no-vest', 'person', 'vest']
```

---

## Model

- **Architecture:** YOLOv8n  
- **Config used:** `yolov8n.yaml`  
- **Framework:** PyTorch (via [Ultralytics YOLOv8](https://docs.ultralytics.com))  
- **Training setup:**  
  - No pre-trained weights (training from scratch)  
  - 50 epochs  
  - Image size: 640  
  - Batch size: 32  


## Improvements

- The model initially struggled to distinguish **hair** from **helmets**
- Improvements included:
  - Additional samples of hair vs helmet
  - Clearer annotation guidelines
  - Potential for adding a third class: `hair`
