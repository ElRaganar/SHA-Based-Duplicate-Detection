# 📂 Application Manager

A lightweight desktop utility built with **Python + Tkinter (ttkbootstrap)** to:

- 🔍 Scan folders recursively  
- 🔐 Detect duplicate files using SHA-256 hashing  
- 🗂️ Categorize files using customizable keyword rules  
- 📝 Generate structured scan reports  
- 🧹 Clean duplicate files  

---

## 🚀 Features

- 🔍 Recursive folder scanning  
- 🔐 SHA-256 based duplicate detection  
- 🗂️ Keyword-based file categorization  
- ✏️ Editable rules via GUI  
- 📄 Automatic report generation  
- 📜 Logging system  
- 🌙 Dark themed UI (ttkbootstrap)  

---

## 🛠 Requirements

- 🐍 Python 3.8+
- 🎨 ttkbootstrap

Install dependency:

```bash
pip install ttkbootstrap
```

---

## ▶️ Run

```bash
python main.py
```

---

## ⚙️ How It Works

### 🔐 Duplicate Detection

Each file is read in chunks and hashed using:

```python
hashlib.sha256()
```

If two files produce the same hash → they are marked as duplicates.

---

### 🗂️ File Categorization

Files are categorized based on keywords stored in:

```
rules.json
```

Example:

```json
{
  "Games": ["game", "steam", "play"],
  "Development": ["code", "editor", "vscode"],
  "Utilities": ["setup", "tool"],
  "Media": ["music", "video"]
}
```

If no keyword matches → file is placed in `Uncategorized`.

Rules can be modified directly from the GUI.

---

### 📝 Reports

After every scan:

Reports are saved in:

```
reports/session_report_<timestamp>.txt
```

Each report contains:

- 📊 Total duplicates  
- 📂 Duplicate file paths  
- 🗂️ Categorized file list  

---

### 📜 Logging

Application logs are stored in:

```
logs/app_log.log
```

---

## 📁 Project Structure

```bash
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
```

> 📌 Note: `logs/` and `reports/` folders are created automatically if they do not exist.

---
