🌾 Rice Quality Grading System (NCT Standard)

An automated computer vision system that grades rice according to the National Cooperative Testing (NCT) Manual used in the Philippines.
It uses a custom-trained YOLOv11 model to classify grain defects and a Python-based grading engine to compute the final NCT quality grade.

📌 Features
🔍 Automated Grain Detection

Detects and classifies the following six classes:

Whole (Head Rice)

Broken

Chalky

Discolored / Damaged

Immature

Foreign Object

📘 NCT-Compliant Grading

Assigns the final official grade (Premium, Grade 1–3) using:

Head Rice Recovery (%)

Chalkiness (%)

Immaturity (%)

Discoloration (%)

Foreign Matter (Count)

Uses limiting-factor logic, meaning the worst-performing parameter determines the final grade.

📊 Reporting

Outputs:

Annotated images

Detailed text report

Percentage breakdown for each defect type

🛠️ Tech Stack
Component	Technology
Model Architecture	YOLOv11 (Ultralytics)
Language	Python 3.x
Key Libraries	ultralytics, opencv-python, numpy, matplotlib
Hardware Used for Training	Google Colab (T4 GPU)
📘 NCT Grading Standard
NCT Quality Table
Grade	Head Rice %	Chalky %	Immature %	Discolored %	Foreign Matter
Premium	≥ 57.0%	< 2.0%	< 2.0%	≤ 0.5%	None
Grade 1	48.0–56.9%	2.0–5.0%	2.0–5.0%	≤ 2.0%	None
Grade 2	39.0–47.9%	5.1–10.0%	5.1–10.0%	–	Allowed
Grade 3	30.0–38.9%	10.1–15.0%	10.1–15.0%	–	Allowed
🚀 Installation
1️⃣ Clone the repository
git clone https://github.com/your-username/rice-grading-system.git
cd rice-grading-system

2️⃣ Install dependencies
pip install ultralytics opencv-python matplotlib numpy

3️⃣ Add the trained model

Place your model file here:

/rice-grading-system/grain_quality_detector.pt

💻 Usage
Step 1 — Set the paths

Edit your script (e.g., grade_rice.py):

IMAGE_DIR = "./test_images/"
MODEL_PATH = "grain_quality_detector.pt"

Step 2 — Run the system
python grade_rice.py

Step 3 — View results

You will get:

Terminal report

Annotated detection images

📄 Sample Output Report
========================================
      NCT RICE QUALITY ANALYSIS REPORT
========================================
Total Objects Detected: 145
----------------------------------------
HEAD RICE (Whole):      110  (75.86%)
BROKEN RICE:            20   (13.79%)
CHALKY GRAINS:          10   (6.90%)
IMMATURE GRAINS:        3    (2.07%)
DISCOLORED/DAMAGED:     2    (1.38%)
FOREIGN MATTER:         0    (Count)
----------------------------------------
OFFICIAL GRADE:         GRADE 2
========================================

🧠 Model Training Summary

Training Images: 4,200

Validation Images: 480

Test Images: 172

Epochs: 50

Image Size: 640×640

Classes: Whole, Broken, Chalky, Discolored, Immature, Foreign Object

🤝 Contributing

Pull Requests are welcome!
Feel free to open Issues for improvements, bugs, or new feature suggestions.

📜 License

This project can include any license you prefer (MIT recommended).
Add your LICENSE file if needed.
