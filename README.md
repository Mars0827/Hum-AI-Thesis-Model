# 🌾 Rice Quality Grading System (NCT Standard)

An automated computer vision system that grades rice according to the **National Cooperative Testing (NCT) Manual** used in the Philippines.  
The system uses a **custom-trained YOLOv11 model** to classify grain defects and a Python-based grading engine to compute the final NCT quality grade.

---

## 📌 Features

### 🔍 Automated Grain Detection
Detects and classifies the following six rice grain categories:
- Whole (Head Rice)
- Broken
- Chalky
- Discolored / Damaged
- Immature
- Foreign Object

### 📘 NCT-Compliant Grading
Implements official NCT grading logic based on:
- Head Rice Recovery (%)
- Chalkiness (%)
- Immaturity (%)
- Discoloration (%)
- Foreign Matter (count)

Uses a **limiting-factor approach**, meaning the lowest standard met determines the final grade.

### 📊 Visual & Textual Reporting
- Annotated output images  
- Percentage breakdown per grain class  
- Official NCT-grade decision

---

## 🛠️ Tech Stack

| Component         | Technology                                   |
|------------------|-----------------------------------------------|
| Model Architecture | YOLOv11 (Ultralytics)                        |
| Language          | Python 3.x                                    |
| Key Libraries     | ultralytics, opencv-python, numpy, matplotlib |
| Training Hardware | Google Colab (T4 GPU)                         |

---

## 📘 NCT Grading Standard

### Official NCT Quality Table

| Grade       | Head Rice % | Chalky %    | Immature % | Discolored % | Foreign Matter |
|-------------|--------------|-------------|------------|---------------|----------------|
| **Premium** | ≥ 57.0%      | < 2.0%      | < 2.0%     | ≤ 0.5%        | None           |
| **Grade 1** | 48.0–56.9%   | 2.0–5.0%    | 2.0–5.0%   | ≤ 2.0%        | None           |
| **Grade 2** | 39.0–47.9%   | 5.1–10.0%   | 5.1–10.0%  | –             | Allowed        |
| **Grade 3** | 30.0–38.9%   | 10.1–15.0%  | 10.1–15.0% | –             | Allowed        |

---

## 🚀 Installation

### 1️⃣ Clone the repository

```bash
git clone https://github.com/your-username/rice-grading-system.git
cd rice-grading-system
