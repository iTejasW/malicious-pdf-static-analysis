# 🛡️ Malicious PDF Static Analysis (Malware Forensics)

## 📌 Overview
This project presents a **static malware analysis of a malicious PDF file (`evil.pdf`)**, focusing on identifying embedded threats without executing the sample.

The analysis follows an **industry-style forensic workflow**, including:
- PDF structure inspection
- JavaScript detection
- Object-level parsing
- Payload decoding
- IOC extraction
- MITRE ATT&CK mapping

---

## 🎯 Objective
To demonstrate a **repeatable and professional approach** to analyzing document-based malware using static techniques.

---

## 🧪 Sample Details

| Attribute | Value |
|----------|------|
| File Name | evil.pdf |
| File Type | PDF 1.3 |
| Size | 2.69 KB |
| Pages | 0 |
| Classification | **Malicious (High Confidence)** |

---

## 🔍 Key Findings

- Presence of **/OpenAction** → automatic execution on file open
- Embedded **JavaScript**
- **FlateDecode compressed payload** (obfuscation)
- Use of **unescape()** → shellcode-like behavior
- Suspicious outbound URL: hxxp://78.109.30.5/count/load.php

- - Invalid **xref table** → possible tampering

---

## ⚠️ Indicators of Compromise (IOCs)

| Type | Value |
|------|------|
| MD5 Hash | 2264dd0ee26d8e3fbdf715dd0d807569 |
| URL | http://78.109.30.5/count/load.php |
| JS Function | zfnvkWYOKv() |

---

## 🧠 MITRE ATT&CK Mapping

| Technique | Description |
|----------|------------|
| T1204.002 | User Execution: Malicious File |
| T1059.007 | JavaScript Execution |
| T1027 | Obfuscated Files |
| T1071.001 | Web-based C2 Communication |

---

## 🛠️ Tools Used

- `pdfid.py`
- `pdf-parser.py`
- `peepdf`
- `exiftool`
- `CyberChef`

---

## 🧬 Analysis Workflow

1. File identification (`file`, `exiftool`)
2. PDF triage (`pdfid.py`)
3. Object inspection (`pdf-parser.py`)
4. Stream extraction & decoding
5. JavaScript analysis
6. IOC extraction
7. Threat classification

---

## 🚨 Risk Assessment

**Severity: High to Critical**

The sample contains:
- Automatic execution mechanisms
- Obfuscated payload
- External network indicator

This strongly suggests **malicious intent and potential exploitation capability**.

---

## 🛡️ Recommendations

- Disable JavaScript in PDF readers where possible
- Block PDFs with `/OpenAction` or embedded scripts at gateway
- Use sandbox environments for unknown files
- Share IOCs with detection systems (SIEM, EDR)

---

## ⚠️ Disclaimer

This analysis is performed **strictly for educational and research purposes**.  
The sample was analyzed using **static techniques only** and was not executed.

---

## 📄 Report

👉 Full detailed report available here:  
`Malicious_PDF_Static_Analysis_Industry_Report.docx`

---

## 👨‍💻 Author

**Tejas Wakodkar**  
Cybersecurity Analyst | Malware Analysis | SOC | VAPT  

---

## ⭐ If you found this useful
Consider giving a star ⭐ to support the project!
