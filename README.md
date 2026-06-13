Suggested repo name - Requirements-Extraction-Engine

[Requirements Engineering Toolkit] Rule-based pipeline for extracting and structuring requirements from safety-critical regulatory documents to support traceability and systems engineering analysis.

⭐ **1. Introduction**

Safety-critical automotive and aerospace systems rely on requirements management tools such as IBM DOORS, Jama Connect, and Polarion to ensure traceability, validation, and compliance across the system lifecycle. These tools depend on structured requirements derived from regulatory documents and standards.

This project provides an automated pipeline that extracts and structures requirements from regulatory text, generating a format suitable for downstream use in requirements management and traceability workflows.

<table>
  <tr>
    <td align="center">
      <b></b><br>
      <img src="Req_GIF.gif" width="700"/>
    </td>
  </tr>
</table>

---
🧩 **2. Challenge**


Manually reviewing regulatory documents to identify and extract requirements is highly time-consuming and effort-intensive. These documents are large, dense, and written in complex legal language, requiring careful interpretation to separate normative requirements from descriptive text.

Key challenges include:
- High manual effort required for screening large regulatory documents
- Time-consuming identification and extraction of normative requirements
- Inconsistencies in interpretation during manual structuring
- Difficulty in maintaining scalable and repeatable requirements traceability processes

---
🎯 **3. Objectives**

This project aims to automate the early-stage processing of regulatory documents into structured requirements suitable for use in requirements management tools such as IBM DOORS and Polarion.

Key objectives include:
- Automatically extract normative requirements from unstructured regulatory text
- Preserve regulatory structure by distinguishing MAIN and ANNEX sections
- Maintain clause-level traceability for requirements referencing
- Classify requirements into functional categories for systems engineering use

---

🛠 **4. Tech Stack**

This project uses rule-based Natural Language Processing (NLP) techniques to extract and structure requirements from regulatory documents.

Key technologies include:
- Python – core implementation of the requirements extraction pipeline
- pdfplumber – extraction of raw text from regulatory PDF documents
- re (Regular Expressions) – clause detection, sentence segmentation, and rule-based pattern matching
- Pandas – structured representation and analysis of extracted requirements
- OpenPyXL – export of structured outputs into Excel for traceability and review
- Matplotlib – basic analytics and distribution visualization of requirements

---

📘 **5. Key Regulatory Documents for ADAS & Autonomous Driving (EU Focus)**

| Category | Document |
|----------|----------|
| Functional Safety | ISO 26262 – Road Vehicles Functional Safety |
| SOTIF | ISO 21448 – Safety of the Intended Functionality |
| Cybersecurity | ISO/SAE 21434 – Cybersecurity Engineering |
| Cybersecurity Regulation | UNECE R155 – Cybersecurity Management System |
| Software Updates | UNECE R156 – Software Update Management System |
| General Safety | EU Regulation 2019/2144 – General Safety Regulation |
| Automated Driving | UNECE R157 – Automated Lane Keeping Systems (ALKS) |
| Event Data Recording | UNECE R140 – Event Data Recorder |

Some of these documents were used to test the model developed. 

---

🧠 **6. System Architecture**

```mermaid
flowchart TD

A[Input: Regulatory PDF]

subgraph PREP[Preprocessing]
B[Text Extraction]
C[Cleaning]
D[Paragraph Structuring]
E[Sentence Segmentation]
end

subgraph CORE[Requirement Engine]
F[Detection]
G[Classification]
H[Clause Mapping]
end

subgraph OUTPUT[Outputs]
I[Structured Dataset]
J[Excel Export]
K[Analytics]
end

A --> B --> C --> D --> E --> F --> G --> H --> I --> J --> K
```
---

📈 **7. Project Highlights**

- **Text Extraction & Cleaning Functions** - Extract raw regulatory PDF text and perform structured cleaning by removing headers, footers, page artifacts, and noise tokens to produce normalized input text for processing.
- **Paragraph structuring** - Reconstruct coherent paragraphs from raw line-based PDF extraction using rule-based segmentation and hyphenation handling to preserve regulatory document structure.
- **Sentence Segmentation** - Split structured paragraphs into individual sentences to enable requirement-level analysis and classification.
- **Requirements Detection** - Identify candidate requirements using rule-based linguistic patterns, filtering normative statements containing regulatory obligation keywords such as shall, must, and required.
- **Requirements Classification** - Categorize extracted requirements into engineering-relevant classes (e.g., Functional, Safety, HMI, Verification, and Documentation) using a rule-based classification framework.
- **Clause Mapping** - Map each extracted requirement to its originating clause and regulatory hierarchy, preserving document traceability across MAIN and ANNEX sections.
- **Excel Export and Analysis** - Generate a structured Excel-based requirements dataset and provides analytics on requirement distribution, classification trends, and clause-level hotspots.
---
  
📊 **8. Example Use Case**

<p align="center">
  <img src="Console_Output.PNG" width="70%"><br>
  <b>Python Console</b>
</p>

<p align="center">
  <img src="Results_GIF_High_Quality.gif" width="120%">
  <b>Excel file generated by the tool</b>
</p>
