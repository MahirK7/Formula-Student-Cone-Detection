Formula Student Cone Detection with YOLOv8

🔍 Computer Vision project using Python and PyTorch to detect and classify cones in Formula Student Driverless racing. The project leverages YOLOv8 for object detection, with experiments on different optimizers and hyperparameters to evaluate accuracy, efficiency, and per-class performance.

📌 Project Overview

In Formula Student Driverless, cone detection is crucial for track boundary recognition and autonomous navigation. This project implements a YOLOv8-based object detection model trained on cone images across five classes:

Blue cone

Yellow cone

Small orange cone

Large orange cone

Unknown cone

Experiments were conducted with different optimizers (SGD, Adam, RMSProp) and hyperparameters (learning rate, batch size, epochs) to identify the best-performing setup.

⚙️ Technologies & Frameworks

Python 3

PyTorch

Ultralytics YOLOv8

Pandas, Matplotlib (analysis & visualization)

Google Colab (training environment)

📊 Results Summary
Optimizer	Learning Rate	Epochs	Batch Size	mAP@50	mAP@50–95	Avg Time per Epoch (s)
Adam	0.001	20	16	54.5%	37.3%	37.5
SGD	0.001	20	16	49.0%	32.2%	36.9
RMSProp	0.001	20	16	44.9%	29.3%	37.6

Adam achieved the highest detection accuracy, while SGD provided stable convergence.

RMSProp underperformed, especially on the unknown cone class.

Confusion matrix analysis confirmed strong recognition of blue, orange, and yellow cones, but highlighted weaknesses in underrepresented classes.

🚀 How to Run

Clone the repo

git clone https://github.com/YourUsername/formula-student-cone-detection.git
cd formula-student-cone-detection


Install dependencies

pip install -r requirements.txt


Train the model

yolo detect train data=data.yaml model=yolov8s.pt epochs=20 batch=16 lr0=0.001 optimizer=Adam


Validate and generate results

yolo detect val model=runs/detect/exp/weights/best.pt data=data.yaml

📈 Visualizations

📊 Training & validation curves (loss, precision, recall, mAP)

🔎 Confusion matrix for per-class accuracy

🟦🟧🟨 Cone detection examples on test images

✅ Future Work

Data augmentation (rotation, scaling, translation) to improve generalization

Balancing underrepresented classes (e.g., unknown cones)

Testing deeper YOLO architectures (YOLOv5, YOLOv9) for improved accuracy

Deployment as a real-time inference pipeline for Formula Student Driverless vehicles

📬 Contact

Developed as part of a Formula Student Driverless Computer Vision project.
For questions, feel free to reach out via LinkedIn
 or open an issue in this repo.
