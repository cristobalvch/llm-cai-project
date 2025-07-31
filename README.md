## Introduction

This project focuses on exploring and evaluating the integration of large language models (LLMs) into web application attack scenarios using the **Cybersecurity AI (CAI)** framework. This involves testing various prompting methods and LLMs to assess their effectiveness in identifying vulnerabilities within web applications.


## Objectives

This project focuses on the following objectives:

- **Compare** the performance of **GPT-4o** and **DeepSeek V3** within the [**CAI Framework**](https://aliasrobotics.github.io/cai/).
- Use [*PortSwigger labs*](https://portswigger.net/web-security) as an environment to test the LLMs.
- Evaluate the effectiveness of the models in identifying and exploiting common web vulnerabilities, specifically **SQL Injection (SQLi)**, **Cross-Site Scripting (XSS)**, and **Cross-Site Request Forgery (CSRF)**.
- Compare the models using prompting methods: **zero-shot**, **few-shot**, and **chain-of-thought**.
- Assess performance using metrics such as **turns, time, cost, tokens,** and **number of payloads (tools) generated**.


## Project Folder Structure
In this section, the main folder structure is described.
```plaintext
llm-cai-project/                  # Root directory of the project
├── logs/                         # CAI log outputs
├── results/                      # Final experiment logs
├── terminal-output/              # Saved terminal output sessions
├── metrics-experiment/           # Metrics of the experiment
│   ├── calculated-evaluation-metrics.xlsx   # Average and sum-based metrics
│   └── evaluation-metrics.xlsx              # Metrics of each lab
├── utils/                        # Utility scripts and configs
│   ├── helpers.py                # General helper functions
│   ├── portswiggerbot.py         # Automation for PortSwigger bot
│   └── topics-prefixes.json      # Topic prefixes for PortSwigger bot
├── main.py                       # Main execution script
├── metrics.ipynb                 # Notebook for evaluating metrics
└── prompts.yml                   # Prompt templates
```
## Steps for Reproducibility

1. Create a `.env` file in the main folder. For more details, see [**.env.example**](https://github.com/cristobalvch/llm-cai-project/blob/main/.env.example) file.  
2. Configure the variables related to the PortSwigger account and the LLM used.  
3. Install the Python dependencies with the command:  
   ```bash
   pip install -r requirements.txt
   ```
4. Configure the labs and agent parameters in the main.py script as follows. To see more available sections, see  [**topic_prefixes.json**](https://github.com/cristobalvch/llm-cai-project/blob/main/utils/topics_prefixes.json) file.
   ```python
    SECTION = "sql-injection"  # Change this to the type of lab
    N_LABS = 4                 # To test all the labs in the section, change this to -1
    AGENT = "webbounty"
    PROMPT_TYPE = "zero-shot"  # Change this to the desired prompt method
   ```
5. Open a terminal in the main folder and run the main script with the command:
    ```python
    python main.py
    ```
6. Once the script stops, create the metrics table and graphs running the notebook
metrics.ipynb

