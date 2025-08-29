# 🛡️ PII Detector & Redactor  

A Python 3 tool to automatically **detect and redact Personally Identifiable Information (PII)** such as phone numbers, Aadhaar numbers, passports, emails, UPI IDs, and addresses from CSV datasets.  

This is useful for ensuring **data privacy, compliance, and anonymization** before storing, sharing, or processing sensitive information.  

---

## ✨ Features

- Detects **phone numbers, Aadhaar numbers, passport numbers, UPI IDs**
- Detects **combinational identifiers** (name + email, address + pin, IP + device ID, etc.)
- Masks sensitive values while keeping the overall data format readable
- Works with CSV input containing `record_id` and `Data_json` columns
- Exports a new **redacted CSV** with detection flags (`is_pii = True/False`)

---

## 📂 Example Input

**CSV (`input.csv`):**

| record_id | Data_json |
|-----------|-----------|
| 1 | {"name":"John Doe","phone":"9876543210","email":"john@example.com"} |
| 2 | {"aadhaar":"1234 5678 9012","address":"123 MG Road, Bangalore, 560001"} |

---

## 📂 Example Output

**CSV (`redacted_output_candidate.csv`):**

| record_id | redacted_data_json | is_pii |
|-----------|--------------------|--------|
| 1 | {"name":"JXXX DXX","phone":"98XXXXXX10","email":"jo***@example.com"} | True |
| 2 | {"aadhaar":"XXXX XXXX 9012","address":"123****"} | True |



TO RUN 

python3 detector_full_candidate_name.py iscp_pii_dataset.csv

