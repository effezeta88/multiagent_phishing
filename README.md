# Multi-Agent Phishing System (ScanPhish)

This project includes data used in the paper "*Prioritising Phishing Threats in the Financial Ecosystem Using Agentic AI*".
The study proposes a multi-agent system based on Large Language Models (LLMs) for the prioritisation of phishing domains. Three specialised experts analyse the domain string and threat intelligence, the hosting infrastructure and registration records, and the campaign history of the hosting IP, each producing a standardised report with a risk level and a confidence score. Then, a forth agent synthesises these reports into a final severity level, an adjusted confidence score, and an operational recommendation.

The system is evaluated on 3,070 domains impersonating five European banks, using [VirusTotal](https://www.virustotal.com/) labels as an independent reference, and compare two LLM models of different capacity and cost. 

## Repository Contents

The repository is organized into the following directories:

### 1. Domain Dataset (`data/`)

This folder contains a CSV file with the **3,070 samples** used in this study. Each sample includes the following information:

- **Root domain:** The root domain associated with the sample.
- **Subdomain:** The corresponding subdomain.
- **Resolved IP address:** The IP address to which the subdomain resolved.
- **Target brand:** The name of the bank targeted by the domain.
- **VirusTotal label:** The classification assigned by VirusTotal, which can be one of the following:
  - `malicious`
  - `suspicious`
  - `harmless`

### 2. System Prompts (`prompts/`)

This folder contains the text files defining the skills and instructions assigned to each agent in the proposed system. The system consists of four agents:

- **URL Agent:** Responsible for analyzing URLs and their associated characteristics.
- **Server Agent:** Responsible for analyzing server-related information.
- **Campaign Agent:** Responsible for identifying and analyzing potential relationships between domains and campaigns.
- **Judge Agent:** Responsible for evaluating the information provided by the other agents and producing a final assessment.

## Repository Structure

```text
.
├── data/
│   └── dataset.csv
│
├── prompts/
│   ├── URL.txt
│   ├── Server.txt
│   ├── Campaign.txt
│   └── Judge.txt
│
└── README.md
```
*Note: The filenames shown above are illustrative and should be adapted to match the actual files in the repository.*

## Citation

If you use the dataset or system prompts in your research, please cite the study.
