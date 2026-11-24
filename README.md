# LeakTrace AI: Document Leak Tracing & Forensic Investigation

> **Graduation project.** I led the project and handled system integration.
> 🔒 The source code is private. This repository is only a showcase. You can request access to the code or a live demo by messaging me on [LinkedIn](https://www.linkedin.com/in/bassam-alanzi-508b99325).

LeakTrace AI gives every recipient their own **fingerprinted copy** of a sensitive PDF. If a copy leaks later, the system checks the leaked sample, pulls out the embedded mark and traces it back to the exact copy that was issued. It also shows what was changed.

## The problem
Organizations share confidential documents with many employees. When one leaks, there is usually no reliable way to know which copy it came from.

## How it works
1. **Issue a protected copy.** The admin uploads the original PDF and enters the recipient's details. The system embeds a unique identifier and a **digital signature**, then logs the issuance with a **SHA-256** hash.
2. **Investigate a suspected leak.** You upload the leaked file, or even a **phone photo** of a printed page. The system extracts the mark, checks the signature and matches it to the issuance record.
3. **Show the evidence.** It runs text, visual and layout comparisons, reports similarity scores and the pages that changed, and uses Arabic and English **OCR** when the file has no digital text.
4. **Report.** It produces investigation reports as PDF, JSON or TXT, plus a dashboard and a full case history.

## Key features
- Per-recipient watermarking with signed identifiers (QR or barcode marks are detectable even in photos)
- Integrity checks: hashing, tamper detection, "matches issued copy" vs "modified copy"
- **Local AI assistant**: a local LLM (Llama 3.2 through Ollama) summarizes the evidence, and **no document ever leaves the machine**
- Role-based access (admin and investigator), user management and password policy
- Employee directory import (CSV), backup and restore
- Optional Oracle Cloud database integration
- Arabic-first interface
- Automated test suite covering the full issue → leak → investigate workflow

## Tech stack
`Python` · `Streamlit` · `SQLite` / `Oracle` · `PyMuPDF` · `ReportLab` · `Tesseract OCR` · `zxing-cpp` · `Pillow` · `Ollama (Llama 3.2)` · `pytest`

## Screenshots
| Issue a protected copy | Dashboard |
|---|---|
| ![Issue](screenshots/01_issue_screen.png) | ![Dashboard](screenshots/02_dashboard.png) |
| **Investigation result** | **System health** |
| ![Result](screenshots/06_investigation_result.png) | ![Health](screenshots/03_system_health.png) |

## My role
- Project lead and system integration
- Main UI and access control (`app`), orchestration of the issue and investigation workflows (`service`)
- Investigation reports (PDF/JSON) and the local AI analysis assistant
- End-to-end testing, final delivery and the live demo

---

## بالعربي
**LeakTrace AI** نظام لحماية المستندات وتتبّع تسريبها. يُصدر لكل مستلم نسخة PDF خاصة تحمل بصمة وتوقيعًا رقميًا، وعند تسريب ملف أو صورة منه يستخرج النظام البصمة ويحدد النسخة المصدر، ويبيّن التعديلات التي طرأت عليها مع تقرير تحقيق كامل. يعمل المساعد الذكي محليًا دون إرسال أي مستند إلى خدمة خارجية.

مشروع تخرج، وتولّيت فيه قيادة المشروع وتكامل النظام. **الكود المصدري خاص** ويُتاح عند الطلب.

© All rights reserved. No part of this project may be copied or reused without written permission.
