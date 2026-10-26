# City Name Validation Engine (Multi-LLM via Groq API)

An end-to-end data validation pipeline that evaluates city name occurrences within text descriptions by benchmarking predictions from multiple Large Language Models (LLMs) against an automated rule-based ground-truth engine.

This system reads structured Excel datasets, applies dynamic prompt templates, and executes parallel API calls to open-weight models (`qwen/qwen3.8-27b` and `openai/gpt-oss-20b`) hosted on **Groq**. It incorporates rate-limit safeguards, reasoning token optimization, and output classification verification.

---

## 🌟 Key Features

* **Multi-LLM Comparative Benchmarking**: Evaluates and compares predictions simultaneously across different model architectures (**Qwen 27B** vs **GPT-OSS 20B**).
* **Rule-Based Ground-Truth Engine**: Implements a Python substring matching mechanism (`City_Check`) to serve as an objective baseline for model accuracy verification.
* **Reasoning Model Token Handling**: Configured with `max_tokens: 500` to ensure `gpt-oss` reasoning models complete internal thinking steps without returning blank responses.
* **Rate-Limit Safe Concurrency**: Uses `ThreadPoolExecutor` (`MAX_THREADS = 2`) coupled with calibrated delays (`time.sleep(8.0)`) to maintain strict compliance with Groq's 30 Requests Per Minute (RPM) free-tier limit.
* **Modular Model Execution**: Streamlined model iteration using concise list comprehensions for scalable multi-model calls.
* **Automated Audit Matrix**: Generates a consolidated `Result_Check` column that auto-classifies model correctness, pinpoints mismatches, and outputs summary execution metrics.

---

## 🛠️ Tech Stack

* **Language**: Python 3.10+
* **Data Manipulation**: Pandas, OpenPyXL
* **LLM Infrastructure**: Groq REST API (`requests`)
* **Concurrency & Execution**: `concurrent.futures.ThreadPoolExecutor`, `tqdm`
* **Configuration**: `python-dotenv`

---

## 🚀 Setup & Installation

### 1. Clone & Install Dependencies

```bash
git clone [https://github.com/Sarwesh0206/LLM_Comparison_Data.git](https://github.com/Sarwesh0206/LLM_Comparison_Data.git)
cd LLM_Comparison_Data
pip install pandas requests tqdm python-dotenv openpyxl
