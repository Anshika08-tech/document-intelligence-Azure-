# document-intelligence-Azure-
Document Intelligence (often referred to as Intelligent Document Processing, or IDP) is the application of Artificial Intelligence (AI) and Machine Learning (ML) to automatically read, understand, and extract actionable information from complex documents.

Key features:
- Automated Data Extraction: Pulls specific information (names, dates, amounts) as key-value pairs without manual entry.
- Pre-built Models: Offers out-of-the-box support for common documents like ID cards, tax forms, and invoices.
- Validation & Verification: Cross-references extracted data against external databases to ensure accuracy.
- Optical Character Recognition (OCR): Converts printed, handwritten, or scanned text into machine-readable digital data.

## 🛠️ Tech Stack

**Languages**
* Python: Primary language for API integration and data manipulation.

**Cloud & AI Services**
* Microsoft Azure AI Document Intelligence: For extracting text, key-value pairs, and structures from documents.
* Azure AI Language: For natural language processing, sentiment analysis, and text summarization.

**Libraries & Frameworks**
* azure-ai-documentintelligence: Official Python SDK for interacting with the service.
* azure-ai-textanalytics: For NLP capabilities.
* Pandas & NumPy: For structuring and analyzing the extracted data.

**Tools & Version Control**
* Git & GitHub: Source code management.
* Jupyter Notebook: For interactive testing and visualization of extracted data.

document-intelligence-project/
│
├── data/                   # Store your sample files here
│   ├── raw/                # Unprocessed documents (PDFs, JPEGs, invoices)
│   └── processed/          # Extracted JSON outputs or CSVs

│
├── notebooks/              # Jupyter notebooks for testing and visualizing
│   └── exploration.ipynb   # Good for prototyping API calls
│

├── src/                    # Your main Python source code
│   ├── __init__.py
│   ├── config.py           # Loads API keys and endpoints
│   ├── extract.py          # Functions calling Azure Document Intelligence
│   └── process.py          # Functions to clean and structure the data (Pandas)
│
├── tests/                  # Unit tests to ensure your code works
│   └── test_extraction.py

│
├── .env                    # Your actual API keys (NEVER upload to GitHub)
├── .env.example            # A template showing what keys are needed
├── .gitignore              # Tells Git which files to ignore
├── requirements.txt        # List of Python dependencies
└── README.md               # Your project description and instructions

1. Clone the Repository
Open your terminal or command prompt and run:
```bash
git clone [https://github.com/Anshika08-tech/](https://github.com/Anshika08-tech/)[repository-name].git
cd [repository-name]

2. Create a Virtual Environment (Recommended)
It is best practice to use a virtual environment to manage your project dependencies and avoid conflicts.

# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate

3. Install Dependencies

Once your virtual environment is activated, install the required Python libraries:
pip install -r requirements.txt

4. Configure Environment Variables

To connect to Azure, you must provide your secure API credentials.

In the root directory, locate the .env.example file.

Rename it to .env (or create a new file named .env).

Open the .env file and add your Azure endpoint and key:

AZURE_DOCUMENT_INTELLIGENCE_ENDPOINT="your_azure_endpoint_url_here"
AZURE_DOCUMENT_INTELLIGENCE_KEY="your_azure_api_key_here"
Security Warning: Never hardcode your API keys directly into your Python scripts, and ensure your .env file is listed in your .gitignore so your keys are not accidentally uploaded to GitHub.

5. Run the Project

Place a sample document (PDF, PNG, or JPEG) inside the data/raw/ directory.

Execute the extraction script:
python src/extract.py

API endpoints

POST: To submit documents for analysis or to command Azure to build/compose a new custom model.  
GET: To retrieve the analysis results, list your models, or check the status of a job.
