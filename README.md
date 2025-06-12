# OCR Processing with Mistral AI

A complete pipeline demonstrating how to perform OCR on **PDF documents** and **image files** using Mistral AI models. The output is formatted as both Markdown and structured JSON for easy downstream use.

---

## Features

* ✅ PDF OCR Processing with signed URLs
* ✅ Image OCR Processing via Base64 encoding
* ✅ Extraction of Markdown-formatted output
* ✅ Conversion of OCR output into structured JSON using Mistral chat models

---

## Project Structure

```
.
├── PDF Processing
│   ├── Upload PDF and generate signed URL
│   ├── Process PDF with OCR model
│   ├── Render PDF OCR as Markdown
│   └── Convert OCR result to structured JSON
│
├── Image Processing
│   ├── Encode image to Base64
│   ├── Process image with OCR model
│   ├── Render Image OCR as Markdown
│   └── Convert OCR result to structured JSON
└── README.md
```

---

## 1. PDF Processing

### Steps:

1. **Upload PDF**
   PDF files are uploaded to Mistral AI storage and a **signed URL** is generated.

2. **OCR Processing**
   The PDF is processed using the `mistral-ocr-latest` model to extract text and inline images.

3. **Markdown Rendering**
   The extracted content is converted to Markdown with **embedded Base64 images** for display.

4. **JSON Conversion**
   OCR Markdown output is passed to Mistral's chat model (`ministral-8b-latest`) for structured **JSON output generation**.

---

## 2. Image Processing

### Steps:

1. **Base64 Encoding**
   Image files (e.g., PNG, JPG) are read and converted to a **Base64-encoded string**.

2. **OCR Processing**
   The Base64-encoded image is processed using the `mistral-ocr-latest` model.

3. **Markdown Rendering**
   The OCR result is displayed as Markdown with **embedded inline images**.

4. **JSON Conversion**
   Extracted text in Markdown is passed to the chat model to produce **structured JSON output**.

---

## Sample Output (JSON)

```json
{
    "vendor": "Example Store",
    "date": "2025-06-10",
    "total": "23.50",
    "items": [
        {"name": "Milk", "price": "3.00"},
        {"name": "Bread", "price": "2.50"}
    ]
}
```

---

## Requirements

* Python 3.10+
* `mistralai` SDK
* `IPython`
* `pathlib`
* `base64`
* Jupyter / Google Colab environment

---

## Notes

* Make sure to replace `client` with a valid authenticated Mistral AI client instance.
* Ensure API keys and environment variables are securely set.
* Tested with **Mistral OCR Latest** and **Ministral-8b Chat models**.
