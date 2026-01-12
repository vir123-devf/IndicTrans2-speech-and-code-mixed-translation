# 📘 Evaluation of IndicTrans2 on Spoken and Code-Mixed Hindi–English Translation

This repository contains the complete implementation, experiments, and report for the academic assignment on **evaluating and fine-tuning IndicTrans2** for **spoken Hindi–English** and **code-mixed Hinglish–English** machine translation.

The project covers **data analysis (Task 1)**, **baseline evaluation without LoRA (Task 2)**, and **parameter-efficient fine-tuning using LoRA (Task 3)**.

---

## 📂 Repository Structure

The repository is organized as follows:

```
KAGGLE_NOTEBOOKS/
│
├── FINETUNE_WITHOUT_LORA (TASK-2)/
│   ├── en-hi-indictrans2.ipynb
│   ├── hi-en-indictrans2.ipynb
│   ├── en-hinglish-indictrans2.ipynb
│   └── hing-en-indictrans2.ipynb
│
├── FINETUNE_WITH_LORA (TASK-3)/
│   ├── Evaluation of LORA Finetuned Models/
│   │   ├── en-hi-indictrans2-lora-finetuned.ipynb
│   │   ├── hi-en-indictrans2-lora-finetuned.ipynb
│   │   ├── en-hing-indictrans2-lora-finetuned.ipynb
│   │   └── hing-en-indictrans2-lora-finetuned.ipynb
│
├── Finetuning Notebooks/
│   ├── finetuning-indictrans2-1b-en-hi.ipynb
│   ├── finetuning-indictrans2-1b-hi-en.ipynb
│   ├── finetuning-indictrans2-1b-en-hing.ipynb
│   └── finetuning-indictrans2-1b-hing-en.ipynb
│
├── Assignment_Report (TASK-1,2,3).pdf
├── README.md
```

---

## 🧪 Tasks Overview

### ✅ **Task 1 – Data Collection and Analysis**

* Identification and analysis of **spoken Hindi–English** and **code-mixed Hinglish–English** parallel corpora.
* Datasets studied include:

  * IIT Bombay English–Hindi Corpus
  * Samanantar
  * OpenSubtitles
  * GlobalVoices
  * PHINC
  * HINMIX
  * HinGE
  * GLUECoS
  * CALCS 2021
* Corpus statistics and qualitative examples are reported in the assignment report.

---

### ✅ **Task 2 – Baseline Evaluation (Without LoRA)**

**Models Used**

* `indictrans2-en-indic-dist-200M`
* `indictrans2-indic-en-dist-200M`

**Training Setup**

* ~2,000 sentence pairs for training per direction
* Standard train/validation/test splits

**Translation Directions**

* English → Hindi
* Hindi → English
* English → Hinglish
* Hinglish → English

**Evaluation Metrics**

* BLEU
* chrF
* BERTScore
* COMET
* BLEURT

📁 Implemented in:

```
FINETUNE_WITHOUT_LORA (TASK-2)/
```

---

### ✅ **Task 3 – Fine-Tuning with LoRA**

**Models Used**

* `ai4bharat/indictrans2-en-indic-1B`
* `ai4bharat/indictrans2-indic-en-1B`

**LoRA Configuration**

* Parameter-efficient fine-tuning with frozen base model
* 10,000 sentence pairs used for training
* 1 epoch fine-tuning

**LoRA Repositories**

* `Vir123-dev/indictrans2_en_hi_finetune_1B`
* `Vir123-dev/indictrans2_hi_en_finetune_1B`
* `Vir123-dev/indictrans2_en_hing_finetune_1B`
* `Vir123-dev/indictrans2_hing_en_finetune_1B`

**Observed Outcomes**

* Significant improvement for spoken Hindi–English translation
* Partial failure for Hinglish tasks due to:

  * `transformers` dependency issues
  * CUDA device-side assertion errors

📁 Implemented in:

```
FINETUNE_WITH_LORA (TASK-3)/
Finetuning Notebooks/
```

---

## 📊 Evaluation Metrics

All experiments (baseline and LoRA) are evaluated using:

* **BLEU** – n-gram overlap
* **chrF** – character-level similarity
* **BERTScore** – contextual semantic similarity
* **COMET** – learned metric correlated with human judgment
* **BLEURT** – BERT-based quality estimation

---

## 📝 Assignment Report

* The complete academic report is written in **LaTeX**
* Includes:

  * Abstract
  * Dataset analysis
  * Methodology
  * Baseline results
  * LoRA fine-tuning results
  * Comparative analysis
  * Limitations
  * Conclusion

📄 File:

```
Assignment_Report (TASK-1,2,3).pdf
```

---

## ⚠️ Known Issues & Limitations

* LoRA fine-tuning for **Hinglish ↔ English** failed due to:

  * `transformers.utils.is_hqq_available` import error
  * CUDA device-side assertion error
* Metrics for these directions are **not reported** and clearly documented.

---

## 🧑‍🎓 Author

**Virendra Badgotya**
Final Year Student
National Institute of Technology Surat (NIT Surat), Gujarat, India

---

## 📌 Notes

* All results are reported **honestly and reproducibly**
* No fabricated scores are included
* This repository is intended for **academic evaluation and learning purposes**
