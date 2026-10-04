# Lab 1.2 — End-to-End Project Description  
**Project:** Intelligent Information System for Student Performance Monitoring  
**Student:** Giuseppe Badan Orsatti  
**Course:** Intelligent Information Systems  
**Institution:** Vilnius Tech  

---

## 1. End-to-End Solution Description

The project **“Intelligent Information System for Student Performance Monitoring”** is designed as a complete end‑to‑end AI pipeline that receives student performance data (X), processes it through several intelligent stages, and produces a final prediction (y) indicating the student’s academic risk level.

The system begins by collecting structured data such as attendance rate, assignment grades, exam results, participation score, and number of late submissions. These variables form the input vector **X**.

### Pipeline Stages

1. **Data Understanding**  
   The system validates the data, checks for missing values, and identifies relevant features.

2. **AI Reasoning (Gemini)**  
   Using zero‑shot and few‑shot prompting, the AI agent interprets the student’s academic behavior and contextual factors.

3. **Inference (Machine Learning Model)**  
   A lightweight ML model (e.g., Decision Tree or Logistic Regression) predicts the student’s risk level: **low**, **medium**, or **high**.

4. **Output Generation**  
   The system produces the predicted risk level (y) along with an explanation and recommended actions (e.g., tutoring, study plan, monitoring).

This end‑to‑end solution integrates data processing, AI reasoning, ML inference, and actionable feedback, forming a complete intelligent information system aligned with modern educational analytics.

---

## 2. Examples of (X, y)

These examples are stored in the GitHub directory:  
`/data/examples.csv`

| attendance_rate | avg_assignment_grade | exam_grade | late_submissions | participation_score | risk_level |
|-----------------|----------------------|------------|------------------|----------------------|------------|
| 0.65 | 58 | 52 | 3 | 2 | high |
| 0.90 | 82 | 78 | 0 | 4 | low |
| 0.75 | 70 | 65 | 1 | 3 | medium |
| 0.50 | 40 | 38 | 5 | 1 | high |
| 0.88 | 79 | 80 | 0 | 5 | low |
| 0.72 | 68 | 60 | 2 | 3 | medium |
| 0.95 | 85 | 90 | 0 | 5 | low |
| 0.60 | 55 | 50 | 4 | 2 | high |
| 0.78 | 74 | 70 | 1 | 4 | medium |
| 0.83 | 77 | 75 | 0 | 4 | low |

---

## 3. Preliminary Process Model (Pipeline Diagram)

### Process Stages

1. Input Data (X)  
2. Data Understanding  
3. AI Reasoning (Gemini)  
4. ML Inference  
5. Output Generation (y)

---

## 4. Hand-Drawn Diagram (ASCII Version)

+----------------------+
|   Input Data (X)     |
+----------------------+
|
v
+----------------------+
|  Data Understanding  |
+----------------------+
|
v
+------------------------------+
|   AI Reasoning (Gemini)      |
|  Zero-shot / Few-shot prompts|
+------------------------------+
|
v
+----------------------+
|   ML Inference       |
|  (Risk Prediction y) |
+----------------------+
|
v
+------------------------------+
| Output: Risk Level + Advice |
+------------------------------+

---

# End of Lab 1.2
