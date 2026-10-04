# Lab 1.2 — End-to-End Project Description  
**Project:** Intelligent Information System for Student Performance Monitoring  
**Student:** Giuseppe Badan Orsatti  
**Course:** Intelligent Information Systems  
**Institution:** Vilnius Tech  

---

## 1. End-to-End Solution Description

The project **“Intelligent Information System for Student Performance Monitoring”** is designed as a complete end‑to‑end AI pipeline that receives student performance data (X), processes it through several intelligent stages, and produces a final prediction (y) indicating the student’s academic risk level.

Although the thesis focuses on structured educational data, the laboratory exercises introduce multimodal AI pipelines (video → audio → text → image → LLM reasoning) to help students understand how end‑to‑end systems operate in real-world AI applications. These concepts are later adapted to the educational context of the thesis.

### Pipeline Stages (Thesis Context)

1. **Data Collection (X)**  
   Student features such as attendance rate, assignment grades, exam results, participation score, and late submissions.

2. **Data Understanding**  
   Cleaning, validation, feature selection, and preparation for inference.

3. **AI Reasoning (Gemini)**  
   Zero‑shot and few‑shot prompting to interpret student behavior and contextual factors.

4. **Inference (Machine Learning Model)**  
   A lightweight ML model predicts the student’s risk level: **low**, **medium**, or **high**.

5. **Output Generation (y)**  
   The system produces the predicted risk level along with explanations and recommended actions.

---

## 2. Examples of (X, y)

Stored in: `/data/examples.csv`

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

## 3. Explanation of Colab Documents

The professor provided two Colab notebooks that demonstrate multimodal AI pipelines.  
Below is a detailed explanation of each one.

---

## **Colab 1 — Video Data Processing Pipeline**

**Purpose:**  
This notebook extracts multiple data modalities from video files and prepares them for downstream AI tasks.

**Dataset:**  
Kaggle — Emotional Video Data

### **Pipeline Steps**

#### **Step 1 — Download Dataset from Kaggle**
Uses `kagglehub` to download a video dataset and copy it into the Colab environment.

#### **Step 2 — Extract Audio from Videos**
Uses `moviepy` to:
- load each `.mp4` video  
- extract the audio track  
- save it as `.mp3`  

This demonstrates **feature extraction** from raw media.

#### **Step 3 — Install Whisper**
Installs OpenAI Whisper for speech-to-text transcription.

#### **Step 4 — Transcribe Audio to Text**
Whisper converts each audio file into a `.txt` transcription.  
This shows **AI-based text extraction** from audio.

#### **Step 5 — Extract Middle Frame from Each Video**
Uses `moviepy` to:
- load each video  
- capture the middle frame  
- save it as `.jpg`  

This demonstrates **image extraction** from video.

#### **Step 6 — Zip and Save Outputs to Google Drive**
Creates:
- `text-data.zip`  
- `frame-data.zip`  

This prepares the data for the next Colab.

### **Relation to the Thesis**
Although the thesis uses structured educational data, this Colab teaches:

- multimodal data extraction  
- preprocessing pipelines  
- preparing data for AI models  

These concepts are directly transferable to building an end‑to‑end educational monitoring system.

---

## **Colab 2 — Image Description Generation Pipeline**

**Purpose:**  
This notebook processes the extracted video frames and generates text descriptions using Google Gemini/Gemma LLM models.

**Input:**  
`frame-data.zip` (from Colab 1)

**Output:**  
`image-descriptions.zip`

### **Pipeline Steps**

#### **Setup — Install Dependencies and Configure API**
Installs:
- `google`  
- `google.genai`  

Loads Gemini API key from Colab Secrets.

#### **Step 1 — Extract Frame Images**
Unzips `frame-data.zip` into `/content/frame-data/`.

#### **Step 2 — Generate Image Descriptions Using LLM**
For each image:
- loads the image bytes  
- sends them to the Gemma/Gemini model  
- receives a natural-language description  
- saves it as `.txt`

This demonstrates **vision-language AI**, where an LLM interprets an image.

#### **Step 3 — Archive Descriptions**
Creates `image-descriptions.zip` and saves it to Google Drive.

### **Relation to the Thesis**
This Colab teaches:

- how LLMs interpret visual data  
- how multimodal AI pipelines operate  
- how to integrate LLM reasoning into an end‑to‑end system  

These skills are essential for building intelligent educational systems that rely on AI reasoning.

---

## 4. Preliminary Process Model (Pipeline Diagram)

### Process Stages (Thesis Context)

1. Input Data (X)  
2. Data Understanding  
3. AI Reasoning (Gemini)  
4. ML Inference  
5. Output Generation (y)

---

## 5. Hand-Drawn Diagram (ASCII Version)

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
