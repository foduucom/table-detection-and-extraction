# **Table-detection-and-extraction**

## Model Summary
  The YOLOv8s Table Detection model is an object detection model based on the YOLO (You Only Look Once) framework. It is designed to detect tables, whether they are bordered or borderless, in images. The model has been fine-tuned on a vast dataset and achieved high accuracy in detecting tables and distinguishing between bordered and borderless ones.

## Model Details

## Model Description
  The YOLOv8s Table Detection model serves as a versatile solution for precisely identifying tables within images, whether they exhibit a bordered or borderless design. Notably, this model's capabilities extend beyond mere detection – it plays a crucial role in addressing the complexities of unstructured documents. By employing advanced techniques such as bounding box delineation, the model enables users to isolate tables of interest within the visual content.

What sets this model apart is its synergy with Optical Character Recognition (OCR) technology. This seamless integration empowers the model to not only locate tables but also to extract pertinent data contained within. The bounding box information guides the cropping of tables, which is then coupled with OCR to meticulously extract textual data, streamlining the process of information retrieval from unstructured documents.

We invite you to explore the potential of this model and its data extraction capabilities. For those interested in harnessing its power or seeking further collaboration, we encourage you to reach out to us at info@foduu.com. Whether you require assistance, customization, or have innovative ideas, our collaborative approach is geared towards addressing your unique challenges. Additionally, you can actively engage with our vibrant community section for valuable insights and collective problem-solving. Your input drives our continuous improvement, as we collectively pave the way towards enhanced data extraction and document analysis.

## Developed by: FODUU AI
## Model type: Object Detection
## Task: Table Detection (Bordered and Borderless)
  Furthermore, the YOLOv8s Table Detection model is not limited to table detection alone. It is a versatile tool that contributes to the processing of unstructured documents. By utilizing advanced bounding box techniques, the model empowers users to isolate tables within the document's visual content. What sets this model apart is its seamless integration with Optical Character Recognition (OCR) technology. The combination of bounding box information and OCR allows for precise data extraction from the tables. This comprehensive approach streamlines the process of information retrieval from complex documents.

User collaboration is actively encouraged to enrich the model's capabilities. By contributing table images of different designs and types, users play a pivotal role in enhancing the model's ability to detect a diverse range of tables accurately. Community participation can be facilitated through our platform or by reaching out to us at info@foduu.com. We value collaborative efforts that drive continuous improvement and innovation in table detection and extraction.


## Supported Labels
  ['bordered', 'borderless'] 



## Training Data
  The model is trained on a diverse dataset containing images of tables from various sources. The dataset includes examples of both bordered and borderless tables, capturing different designs and styles.

## Training Procedure
  The training process involves extensive computation and is conducted over multiple epochs. The model's weights are adjusted to minimize detection loss and optimize performance.

# Metrics
  mAP@0.5 (box):
  All: 0.962
  Bordered: 0.961
  Borderless: 0.963
## Model Architecture and Objective
  The YOLOv8s architecture employs a modified CSPDarknet53 as its backbone, along with self-attention mechanisms and feature pyramid networks. These components contribute to the model's ability to detect and classify tables accurately, considering variations in size, design, and style.



## Recommendations
  Users should be informed about the model's limitations and potential biases. Further testing and validation are advised for specific use cases to evaluate its performance accurately.

# How to Get Started with the Model
  To begin using the YOLOv8s Table Detection model, follow these steps:
```
pip install ultralyticsplus==0.0.28 ultralytics==8.0.43

## Load model and perform prediction

  from ultralyticsplus import YOLO, render_result

## load model

model = YOLO('foduucom/table-detection-and-extraction')

## set model parameters
  model.overrides['conf'] = 0.25  # NMS confidence threshold
  model.overrides['iou'] = 0.45  # NMS IoU threshold
  model.overrides['agnostic_nms'] = False  # NMS class-agnostic
  model.overrides['max_det'] = 1000  # maximum number of detections per image

## set image
  image = '/path/to/your/document/images'

## perform inference
  results = model.predict(image)

## observe results
  print(results[0].boxes)
  render = render_result(model=model, image=image, result=results[0])
  render.show()
```
