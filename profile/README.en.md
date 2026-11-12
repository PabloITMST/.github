<div align="center">

<img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/assets/character/preview/icon-256.png" width="96" alt="Pablo" />

# Pablo

**Software that helps you build code that follows your requirements.**

Pablo finds differences between documents and code, and reviews changes that may conflict with your requirements before they run.<br/>
Check the source sentence and code line, and keep a record of your decisions and reasons.

[**Download for Windows**](https://github.com/PabloITMST/Pablo_application/releases/latest) · [Application](https://github.com/PabloITMST/Pablo_application) · [Introduction video](https://youtu.be/nTx_CkDOp90) · [v5 poster](https://www.figma.com/design/IV8Epwttx5IgL1fkvrrB7v/Pablo-UI?node-id=322-2952) · [한국어](https://github.com/PabloITMST) · **English**

</div>

[![Pablo introduction video](https://img.youtube.com/vi/nTx_CkDOp90/hqdefault.jpg)](https://youtu.be/nTx_CkDOp90)

---

A project can start from a document and drift as errors are fixed and features are added. All tests may pass while **the paper says top-k 5 and the code uses 10**.

**An AI agent writes the code. Pablo checks its work in two ways.**

| Input | What Pablo does |
|---|---|
| Your documents + your code | Finds differences and their locations. |
| Your requirements + a code change | Reviews it before execution, asks when confirmation is needed, and records the decision and reason. |

## The Pablo workflow

### 1. Check the original text

Ask a question. Click the source. Read the original text. Inspect the evidence in PDFs and web sources yourself.

<p align="center">
  <img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/docs/images/paper-evidence.png" width="760" alt="An answer citation opens the quoted passage in the original PDF" />
</p>

### 2. Compare documents with code

Compare document conditions with code, configuration, and run logs. See the evidence and location for each difference.

| LinearRAG example in the poster | Document | Code |
|---|---|---|
| top-k | 5 — paper, p. 8 | 10 — `config.yaml`, line 5 |

<p align="center">
  <img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/docs/images/repro-audit.png" width="760" alt="The reproduction audit finds a different value and opens its code line" />
</p>

Pablo re-reads the file and line cited by the model to check that the quoted value or code is there. Verifying the location does not establish that the verdict is correct.

### 3. Save requirements and review changes

1. **Save a preference:** “If possible, don't extract function relationships with an LLM or rules.”
2. **Make a new request:** “Write `relations.py` to extract function relationships with an LLM.”
3. **Review before execution:** Pablo shows the related preference and proposed change and asks **Proceed / Cancel**.
4. **Record the decision:** Cancel, and the code stays unchanged. The decision and reason are saved.

An “if possible” preference is treated separately from a strict rule.

<p align="center">
  <img src="https://raw.githubusercontent.com/PabloITMST/Pablo_application/main/docs/images/guard.png" width="760" alt="Pablo shows the related requirement and proposed change and asks whether to proceed or cancel" /><br/>
  <sub>Screens show the Figma design (A2); details may differ from the app.</sub>
</p>

## Three key outcomes

| Outcome | What you can check |
|---|---|
| **Find differences** | Find values that differ between documents and code. |
| **Know what to check** | Each flag comes with its source or related requirement. |
| **See the exact locations** | Open the source sentence and code line. |

These are feature demonstrations from the [latest poster](https://www.figma.com/design/IV8Epwttx5IgL1fkvrrB7v/Pablo-UI?node-id=322-2952). Methods, results, and limitations of separate development experiments are in the [evaluation record](https://github.com/PabloITMST/Pablo_application/blob/main/docs/eval/README.md) (in Korean).

## Application

[Pablo_application](https://github.com/PabloITMST/Pablo_application) contains the Electron desktop app and Python engine. It runs the Codex agent with your ChatGPT account.

- [Windows installer](https://github.com/PabloITMST/Pablo_application/releases/latest)
- [Installation and usage](https://github.com/PabloITMST/Pablo_application/blob/main/README.en.md#install)
- [Development setup](https://github.com/PabloITMST/Pablo_application/blob/main/README.en.md#running-from-source)
- [Known limitations](https://github.com/PabloITMST/Pablo_application/blob/main/README.en.md#known-limitations)

The poster presents a workflow for websites, PDFs, and Word documents. The application currently imports PDFs and web sources; direct Word-file import is not available.

## Team

Capstone Design 2026 | ITM, Seoul National University of Science and Technology

- Jeongyun Lee · Daehun Kwon
- Advisor: Prof. Minkyu Sim
