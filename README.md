# Utility Invoice Data Extraction

This project automates the extraction of data from utility invoices in PDF format, using AI to parse and structure invoice information into a standardized format for analysis and record keeping.

## Overview

The Utility Invoice Data Extraction tool allows you to:

- Connect to Google Drive to download utility invoice PDFs
- Process PDFs using AI to extract structured data
- Extract key invoice information including:
  - Invoice numbers, dates, and due dates
  - Vendor information and GST numbers
  - Billing periods and consumption quantities
  - Cost breakdowns and tax amounts
- Export extracted data to Excel for further analysis

## Features

- **Google Drive Integration**: Securely access and download invoice PDFs from specified folders
- **Document Validation**: Automatically validate file types, sizes, and page counts
- **AI-Powered Extraction**: Leverages advanced AI models to extract structured data from unstructured documents
- **Batch Processing**: Process multiple invoices concurrently for efficient data extraction
- **Structured Output**: Organizes extracted data into standardized formats with proper typing
- **Excel Reporting**: Generates detailed Excel reports with multiple sheets for different data views

## Prerequisites

- Python 3.8+
- Google Cloud Service Account with Drive API access
- API keys for Gemini and/or OpenAI (as needed)

## Installation

1. Clone this repository
2. Install the required packages:

```bash
pip install py-zerox pydantic langchain langchain-google-vertexai langchain-openai langchain-community python-dotenv google-api-python-client PyPDF2 openpyxl tqdm nest_asyncio pandas pillow
```

## Configuration

Create a `.env` file in the root directory with the following variables:

```
GEMINI_API_KEY="your-gemini-api-key"
OPENAI_API_KEY="your-openai-api-key"
GOOGLE_SERVICE_ACCOUNT_FILE_PATH="path/to/service-account-key.json"
GOOGLE_FOLDER_ID="your-google-drive-folder-id"
DOWNLOAD_FOLDER_PATH="path/to/download/folder"
```

## Usage

The project is structured as a Jupyter notebook that guides you through the entire workflow:

1. **Setup & Authentication**: Configure API credentials and connect to Google Drive
2. **Download Invoices**: Retrieve PDF files from the specified Google Drive folder
3. **Process Documents**: Convert PDFs to markdown and extract structured data
4. **Data Extraction**: Parse invoice details using AI models into standardized formats
5. **Generate Reports**: Export all extracted data to formatted Excel reports

To run the complete pipeline, execute all cells in the notebook or run specific sections as needed.

## Data Model

The extraction process produces structured data in the following format:

- **UtilityInvoice**: Main invoice information including vendor, dates, and amounts
- **UtilityInvoiceItem**: Detailed consumption data with quantities, dates, and costs

## Output

The final output is an Excel file with three sheets:

1. **Documents**: Overview of all processed files with status and link information
2. **Utility Invoices**: Main invoice data with financial and vendor information
3. **Invoice Items**: Detailed consumption data by utility type

## License

MIT

## Acknowledgments

- This project uses [py-zerox](https://github.com/kreneskyp/zx) for PDF processing
- Powered by Gemini and/or OpenAI language models
