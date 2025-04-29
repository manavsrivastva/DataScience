# DataScience
A FastAPI service that extracts lab test names, values, and reference ranges from lab report images, flags out-of-range results, and returns structured JSON using OCR and intelligent parsing.

🧪 Lab Report Analyzer API
A FastAPI-based solution to extract structured data from lab report images using OCR and intelligent parsing. This API identifies lab test names, their values, and bio-reference ranges from lab report images and returns the results in a structured JSON format. It also flags tests that fall outside the normal reference range.

🚀 Features
Accepts lab report images via /get-lab-tests POST endpoint

Extracts:

Lab Test Name

Test Value

Bio-Reference Range

Out-of-Range Indicator

Returns structured JSON response

Calculates if a test result is out of the reference range

Deployable as a FastAPI microservice

Designed to be scalable and accurate

📦 Tech Stack
Python

FastAPI

OCR (Tesseract / EasyOCR)

Regex / NLP-based parsing

Pydantic for data validation

🖼️ Dataset
Lab report image dataset used to build and test the model:
Download here

📤 API Endpoint
POST /get-lab-tests
Input: Image file (lab report)
Output:

json
Copy
Edit
{
  "is_success": true,
  "lab_results": [
    {
      "test_name": "Hemoglobin",
      "value": "13.2",
      "reference_range": "13.5 - 17.5",
      "lab_test_out_of_range": true
    },
    ...
  ]
}
🛠️ Installation
bash
Copy
Edit
git clone https://github.com/your-username/lab-report-analyzer.git
cd lab-report-analyzer
pip install -r requirements.txt
uvicorn main:app --reload
