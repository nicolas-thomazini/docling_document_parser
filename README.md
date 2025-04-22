# 📄 docling_document_parser

docling_document_parser
Project for converting and extracting structured information from PDF documents using [Docling](https://github.com/IBM/docling). Full support for both digital and scanned documents (via OCR).

## 🚀 Features

- Convert PDFs to JSON or Markdown
- Layout recognition with pre-trained models (DocLayNet)
- Table detection using TableFormer
- OCR support for scanned documents
- Export text, tables, and images
- Fully local (offline) execution

## ⚙️ CPU vs GPU for PDF Processing

The project runs by default on CPU, which is ideal for small files and quick tests. However, heavier tasks (such as batch OCR, TableFormer, and NLP) are significantly faster when using a GPU.

**CPU**: easy to use, but slower for large volumes.  
**GPU**: recommended for multiple PDFs, scanned OCR, and intensive AI tasks.

**💡 Tip (Colab):**  
If you don’t have a local GPU, you can run the project for free with hardware acceleration using **Google Colab**.

- Open the notebook on Colab
- Go to _Runtime > Change runtime type_
- Select **GPU**
- Run the notebook normally

This ensures faster and more efficient execution without needing to install drivers or configure CUDA manually.

## 🧰 Requirements

- Python 3.10+
- Pip
- Git

## 📦 Installation

Clone this repository and install the dependencies in a virtual environment:

```bash
git clone https://github.com/seu-usuario/docling_document_parser.git
cd docling_document_parser

python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

pip install -r requirements.txt
```

⚠️ The requirements.txt file can be generated automatically with:

```bash
pip freeze > requirements.txt
```

## 📝 Execution

### 🧪 Run the notebook

Open Jupyter Notebook (or Jupyter Lab) and run the file:

```bash
jupyter notebook extract_and_ocr.ipynb
```

## 📂 Expected structure

Place your .pdf files at the root of the project or in a subfolder, and adjust the paths in the notebook if necessary:

```
.
├── extract_and_ocr.ipynb
├── scanned_bill.pdf
├── sample_doc.pdf
├── venv/
└── ...
```

### 📤 Output

Ao rodar o notebook, serão extraídos:

- Text: with positions and page numbers
- Tables: exportable in HTML or JSON
- Images: with metadata and location
- OCR: automatically performed for scanned PDFs

## 🧠 About Docling

Docling is an IBM library for layout analysis and structured document extraction, with AI models trained on datasets such as DocLayNet. This project uses these capabilities to efficiently process and structure PDFs.

### 🐛 Common issues

❌ Data format error when opening scanned PDFs: the file may be corrupted or improperly structured. Try using a different viewer or re-scan the document.

⚠️ Use of deprecated functions (export_to_html()...): you may need to explicitly pass the doc argument in future versions of the library.

## 🛠️ TODO

This project will soon be dockerized to improve portability and ease of execution.

✅ What's planned:

- Create a Dockerfile with a Python environment + Docling + OCR

- Allow running the notebook inside the container

- Support volumes for input/output of PDFs and JSONs

- Run OCR + extraction with a single Docker command

## 📃 License

MIT License. See the LICENSE file for more information.
