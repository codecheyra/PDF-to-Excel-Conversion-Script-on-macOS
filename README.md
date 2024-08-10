# PDF to Excel Conversion Script on macOS

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Step 1: Setup the Virtual Environment](#step-1-setup-the-virtual-environment)
3. [Step 2: Install Dependencies](#step-2-install-dependencies)
4. [Step 3: Python Script for PDF to Excel Conversion](#step-3-python-script-for-pdf-to-excel-conversion)
5. [Step 4: Directory Structure](#step-4-directory-structure)
6. [Step 5: Running the Script](#step-5-running-the-script)
7. [Expected Output](#expected-output)
8. [Note](#note)

## Prerequisites
- Python 3.12.4
- Homebrew

## Step 1: Setup the Virtual Environment
1. **Open your terminal.**

2. **Navigate to your project directory:**
    ```sh
    cd /path/to/my_project
    ```

3. **Create a virtual environment:**
    ```sh
    python3 -m venv venv
    ```

4. **Activate the virtual environment:**
    ```sh
    source venv/bin/activate
    ```

## Step 2: Install Dependencies
1. **Create a `requirements.txt` file in your project directory with the following content:**
    ```text
    pandas==2.2.0
    tabula_py==1.4.2
    ```

2. **Install the dependencies listed in `requirements.txt`:**
    ```sh
    pip install -r requirements.txt
    ```

3. **Install additional dependencies and set up Java for tabula-py:**
    ```sh
    brew install openjdk
    export JAVA_HOME=$(/usr/libexec/java_home)
    source ~/.bash_profile
    pip install tabula-py
    pip install --upgrade tabula-py
    pip install openpyxl
    pip install jpype1
    pip install setuptools
    ```

## Step 3: Directory Structure
Ensure your project directory (`my_project`) has the following structure:
```
my_project
├── requirements.txt
├── pdftoexcel.py
└── *.pdf (all PDF files to be converted)
```

## Step 4: Running the Script
1. **Make sure you are in the project directory and the virtual environment is activated.**

2. **Run the script:**
    ```sh
    python3 pdf2excel.py
    ```

## Expected Output
For each PDF file in the directory, an Excel file with the same name (but with an `.xlsx` extension) will be created in the same directory.

## Note
- The script assumes all PDF files are in the same directory as `pdftoexcel.py`.
- The conversion process will print messages indicating the status of each PDF file conversion.

By following these steps, you should be able to successfully convert PDF files to Excel files on macOS.

### Advantages/Pros:
- It can extract multiple tables.
- It can extract data from multiple pages.
- It can work on multiple PDF files.

### Disadvantages/Cons:
- Data from imaged PDFs cannot be extracted.
- Every PDF must contain at least one table.
