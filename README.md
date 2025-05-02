# 🏥 Medical Report Generator with Gemini API

This project provides two FastAPI-based APIs for generating **medical reports in PDF format** based on user-provided **questions and answers**. It supports **Arabic** and **English** outputs, utilizing Google's **Gemini API** to enrich and explain medical Q&A content.

---

## ✨ Features

- ✅ Multi-language support (Arabic & English)
- ✅ Uses Google Gemini (1.5 Pro) for content enhancement
- ✅ Generates clean, styled PDF reports
- ✅ Lightweight FastAPI service

---

## 📦 Installation

```bash
git clone https://github.com/AhmedSofi/medical_report_generator_with_gemini_api.git
cd medical-report-generator
pip install -r requirements.txt
```

### Requirements

- `fastapi`
- `uvicorn`
- `google-generativeai`
- `reportlab`
- `arabic_reshaper` *(Arabic version only)*
- `python-bidi` *(Arabic version only)*

---

## 🚀 Running the API

Start the FastAPI server with:

```bash
uvicorn main:app --reload
```

Then access it at: `http://127.0.0.1:8000`

---

## 🇸🇦 Arabic Report API

**Endpoint**: `/generate_pdf/`  
**Method**: `GET`

### 🔸 Query Parameters

| Name     | Type   | Description                         |
|----------|--------|-------------------------------------|
| question | list   | Arabic questions                    |
| answer   | list   | Corresponding Arabic answers        |

### 🧪 Example

```http
GET /generate_pdf/?question=ما هي أعراض السكر؟&answer=تشمل العطش والتبول المتكرر
```

### 📝 Description

- Generates a medical summary from Arabic questions/answers.
- Text is reshaped for proper RTL display.
- Arabic-friendly font (`Amiri-Regular.ttf`) is used in the PDF.

---

## 🇬🇧 English Report API

**Endpoint**: `/generate_pdf/`  
**Method**: `GET`

### 🔸 Query Parameters

| Name     | Type   | Description                         |
|----------|--------|-------------------------------------|
| question | list   | English questions                   |
| answer   | list   | Corresponding English answers       |

### 🧪 Example

```http
GET /generate_pdf/?question=What are symptoms of diabetes?&answer=Increased thirst and frequent urination
```

### 📝 Description

- English-only medical content analysis.
- PDF formatting with headings, highlights, and readable layout.
- No special font handling needed.

---

## 📂 File Structure

```
main.py                  # FastAPI app (Arabic and English APIs)
Amiri-Regular.ttf        # Arabic font file
README.md                # Project documentation
```

---

## 🔐 Gemini API Key

Add your API key inside the `gemini()` function:

```python
genai.configure(api_key='YOUR_API_KEY')
```

Get your API key from [Google AI Studio](https://makersuite.google.com/).

---


## 🤝 Contributing

Pull requests are welcome! If you have suggestions or want to improve the formatting, logic, or features, feel free to fork and contribute.

---


