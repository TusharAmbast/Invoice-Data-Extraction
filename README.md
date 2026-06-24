# Invoice Data Extraction

A Python-based invoice processing system that extracts structured information from PDF invoices using `pdfplumber` and Large Language Models (LLMs). The project converts unstructured invoice text into clean JSON output for further processing, analysis, or integration with business workflows.

## Features

- Extract text from PDF invoices
- Process invoice content using OpenAI LLMs
- Convert invoice information into structured JSON
- Handle multiple invoice formats
- Store extracted data for downstream applications
- Easy to extend for additional invoice fields

---

## Project Structure

```text
Invoice-Data-Extraction/
│
├── Invoices/
│   ├── Invoice.pdf
│   ├── invoice-2.pdf
│   └── invoice-3.pdf
│
├── Output/
│   ├── invoice_data.json
│   ├── invoice_data_2.json
│   └── invoice_data_3.json
│
├── .env
├── .gitignore
├── requirements.txt
└── invoice-extraction.ipynb
```

---

## How It Works

### Step 1: Read Invoice PDF

The invoice PDF is loaded and text is extracted using `pdfplumber`.

### Step 2: Send Data to LLM

The extracted invoice text is sent to the OpenAI API with a prompt instructing the model to identify and extract relevant invoice details.

### Step 3: Generate Structured Output

The LLM returns the extracted information in a predefined JSON format.

### Step 4: Save Results

The structured data is stored inside the `Output/` directory as JSON files.

---

## Extracted Fields

Depending on the invoice format, the system can extract:

- Invoice Number
- Invoice Date
- Vendor/Supplier Name
- Customer Information
- Billing Address
- Line Items
- Quantity
- Unit Price
- Tax Details
- Subtotal
- Total Amount
- Payment Terms

---

## Installation

### Clone Repository

```bash
git clone https://github.com/TusharAmbast/Invoice-Data-Extraction.git
cd Invoice-Data-Extraction
```

### Create Virtual Environment

```bash
python -m venv venv
```

Activate:

**Windows**

```bash
venv\Scripts\activate
```

**Linux / macOS**

```bash
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Environment Variables

Create a `.env` file in the root directory:

```env
OPENAI_API_KEY=your_api_key_here
```

---

## Usage

Place invoice PDFs inside the `Invoices/` folder.

Run the notebook:

```bash
jupyter notebook
```

Open:

```text
invoice-extraction.ipynb
```

Execute all cells.

The extracted JSON files will be generated inside the `Output/` folder.

---

## Sample Output

```json
{
  "invoice_number": "INV-1001",
  "invoice_date": "2025-06-20",
  "vendor_name": "ABC Corporation",
  "total_amount": 1250.00,
  "tax_amount": 225.00
}
```

---

## Technologies Used

- Python
- pdfplumber
- OpenAI API
- JSON
- Jupyter Notebook

---

## Author

**Tushar Ambast**

GitHub: https://github.com/TusharAmbast


---
