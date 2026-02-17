📂 Application Manager

A desktop utility built with Python + Tkinter (ttkbootstrap) to scan folders, detect duplicate files using SHA-256 hashing, categorize files based on custom keyword rules, and generate structured reports.

Designed for simple, fast local file management.

✨ Features

🔍 Recursive folder scanning

🔐 Duplicate detection using SHA-256 hashing

🗂️ Keyword-based file categorization

✏️ GUI-based rule editor

🧹 Duplicate file removal

📝 Automatic report generation

📜 Logging system

🌙 Dark-themed UI

🛠️ Requirements

Python 3.8+

ttkbootstrap

Install dependency:

pip install ttkbootstrap

▶️ Running the Application
python main.py


The GUI window will open.

⚙️ How It Works
1️⃣ Folder Scanning

When you select a folder and click Scan, the application:

Recursively walks through all files

Calculates SHA-256 hash for each file

Detects duplicate files by comparing hashes

If two files have identical hashes → they are marked as duplicates.

2️⃣ File Categorization

Each file name is checked against keyword rules stored in:

rules.json


Example:

{
  "Games": ["game", "steam", "play"],
  "Development": ["code", "editor", "vscode"],
  "Utilities": ["setup", "tool"],
  "Media": ["music", "video"]
}


If a filename contains a keyword:

It is placed in that category

If no match is found → it goes to Uncategorized

Rules can be edited directly from the GUI.

3️⃣ Report Generation

After every scan:

A detailed session report is saved in:

/reports/session_report_<timestamp>.txt


The report includes:

Total duplicate files

Duplicate file paths

Categorized file lists

4️⃣ Logging

Application activity is logged in:

/logs/app_log.log


This includes scan completion and report creation events.

5️⃣ Duplicate Cleaning

Click Clean Duplicates to remove detected duplicate files.

⚠️ Files are permanently deleted using os.remove().

📁 Project Structure
Application-Manager/
│
├── main.py
├── rules.json
│
├── logs/
│   └── app_log.log
│
├── reports/
│   └── session_report_<timestamp>.txt
│
└── README.md

🔧 Core Logic Overview
Duplicate Detection
hashlib.sha256()


Files are read in chunks and hashed.
Matching hashes = duplicate files.

Categorization

Simple keyword match:

if keyword in filename.lower():
