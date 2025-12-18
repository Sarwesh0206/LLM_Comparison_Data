City Name Validation using Multi-LLM (Groq API):

This project automates the validation of city names present within textual descriptions by comparing an expected city against the actual content using multiple Large Language Models (LLMs).

The solution processes structured data from Excel, applies carefully designed prompts, and queries Moonshot and LLaMA models through the Groq API. Alongside model-based reasoning, a rule-based validation mechanism is used to independently verify city name presence, improving reliability and consistency.

Parallel processing is implemented to handle large datasets efficiently, and all results—including model outputs and verification status—are written back to Excel for easy analysis and review.


Key Capabilities:

Multi-LLM comparison using Moonshot and LLaMA
High-performance inference via Groq API
Prompt-driven city name classification
Rule-based validation for accuracy assurance
Scalable parallel execution
End-to-end Excel automation


Technology Stack:
Python, Pandas, Groq API, Prompt Engineering, Concurrent Processing, Excel Automation
