# 🧠 Interactive MCQ Generator using sBERT Model And Gemini API and Streamlit

A smart MCQ (Multiple Choice Question) generator powered by **Google Gemini 1.5 Pro**, designed to extract text from uploaded files and generate relevant paragraph-based or aptitude-based MCQs. It also includes an interactive quiz interface with performance analytics, visual feedback, and topic-wise insights.

---

## 📑 Table of Contents

- [📘 Introduction](#-introduction)
- [📜 Overview](#-overview)
- [📐 Architecture Diagram](#-architecture-diagram)
- [🛠️ Technologies Used](#-technologies-used)
- [📊 Dataset Requirements](#-dataset-requirements)
- [📂 Repository Setup](#-repository-setup)
- [📦 Dependencies](#-dependencies)
- [📸 Results](#-results)

---

## 📘 Introduction

This project enables educators, trainers, and students to generate MCQs from any textual or tabular data (PDF, DOCX, TXT, CSV) using **LLM capabilities**. It supports two types of MCQs:
- Paragraph-Based: Derived from descriptive text
- Aptitude-Based: Logical/numerical questions from datasets

Built with **Streamlit** for an intuitive UI and integrated with **Google Gemini API** for content generation.

---

## 📜 Overview

- Upload multiple files (PDF, TXT, DOCX, CSV)
- Choose between aptitude or paragraph-based MCQ generation
- Auto-generate questions with answer options
- Interactive quiz interface to attempt and submit answers
- Get performance analytics including:
  - Correct vs Incorrect breakdown
  - Question review
  - Topic-wise attempt analysis

---

## 📐 Architecture Diagram

### 📊 Architecture Flowchart

+-----------------------------------------+
|          🧑‍💻 User Interface (Streamlit)          |
+-------------------------+---------------+
                          |
                          v
+-----------------------------------------+
|      📄 Dataset Upload / Web Scraping         |
|     (CSV or Paragraph Input Collection)  |
+-------------------------+---------------+
                          |
                          v
+-----------------------------------------+
|        🧹 Data Preprocessing Module           |
|  (Cleaning, Tokenization - Pandas/NLTK) |
+-------------------------+---------------+
                          |
                          v
+------------------------+----------------+
|         🧠 Question Type Decision Module       |
+------------------+---------------------+
                   |                     
     +-------------+-------------+       
     |                           |       
     v                           v       
+-------------+         +------------------+
| Paragraph   |         | Aptitude-Based   |
| Based MCQs  |         | MCQs Generator   |
+------+------+         +--------+---------+
       |                          |
       v                          v
+--------------------+   +------------------------+
| SBERT Embeddings   |   | Rule-Based Logic       |
| Distractor Gen     |   | (Arithmetic/Logical)   |
+----------+---------+   +------------------------+
           \                  /
            \                /
             v              v
         +------------------------+
         |    🧪 MCQ Evaluation Module    |
         +--------------+---------------+
                        |
                        v
         +------------------------------+
         |   📄 PDF Generator (FPDF)       |
         +------------------------------+


---

## 🛠️ Technologies Used

The MCQ Generator System leverages a variety of technologies to automate the generation of multiple-choice questions:

- **Python** – Core programming language for logic and data handling.
- **BeautifulSoup & Requests** – Used for web scraping to collect paragraph and aptitude question datasets from online sources.
- **Pandas & NumPy** – For efficient data processing and manipulation.
- **FPDF** – To generate downloadable PDF files of generated questions and answers.
- **Streamlit** – For building the interactive web-based user interface.
- **Regex** – For extracting questions and answers from unstructured text formats.
- **scikit-learn** – For text similarity scoring and optional classification metrics.
- **SentenceTransformer (SBERT)** – Used to compute sentence embeddings and perform semantic similarity for generating context-aware MCQs.
- **google.generativeai** – Gemini API for language generation tasks.
- **matplotlib** – For visual representation of performance metrics.
- **seaborn** – To generate heatmaps and advanced visual insights.
- **random** – For shuffling options and selections.
- **json, os** – For handling file I/O and storage
---

## 📦 Dataset Requirements

This system uses a **custom-built dataset**, created via web scraping from educational websites:

- **Paragraph-based datasets**: Extracted from blogs, articles, and textbooks containing educational passages.
- **Aptitude-based datasets**: Scraped from online test prep sites and question banks containing math, reasoning, and logic-based questions.

The scraped content is cleaned, structured, and formatted into `.csv` files for processing.

> 📌 Note: Proper scraping practices are followed with respect to robots.txt and website terms of use.

---

## 📦 Repository Cloning & Setup

Follow the steps below to clone the repository and set up the environment:

### Clone the repository
git clone https://github.com/Raghunadha-Charyulu/MCQ_GENERATOR_AND_PERFORMANCE_ANALYSIS_USING_SBERT_GEMINI_API_INTEGRATION

### Navigate to the project directory
- cd mcq-generator

### (Optional) Create and activate a virtual environment
- python -m venv venv
- source venv/bin/activate        # (On macOS/Linux)
- venv\Scripts\activate           (# On Windows)

### Install required dependencies
- pip install -r requirements.txt

---

