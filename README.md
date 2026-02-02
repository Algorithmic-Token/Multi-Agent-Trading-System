# Multi-Agent-Trading-System

# Quant-Committee: Multi-Asset Trading MAS

Quant-Committee is an agentic framework designed to simulate an institutional Investment Committee. Unlike traditional "black box" algorithmic trading, this system orchestrates a debate between specialized AI agents—Fundamental, Technical, and Risk Analysts—to execute trades across Equities, Bonds, and Digital Assets.
The project features a self-correcting Agentic Software Engineering (ASE) environment, allowing the system to inspect, generate, and audit its own strategy code before deployment.

## 🏗 Architectural Vision
The system operates on two distinct planes:

### 1. The Trading Plane ("The Investment Committee")
We replace the single-model paradigm with a Council of Agents:
  * The Analyst Layer: Specialized agents (Fundamental, Technical, Macro) that ingest distinct data streams (10-Ks, Price Action, Fed Minutes) and output signals.
  * The Governance Layer: An adversarial "Debate Protocol" where Bull and Bear agents argue their cases.
  * The Execution Layer: A Portfolio Manager (PM) agent acting as the "Judge," weighing conviction against the current regime (e.g., favoring fundamentals during earnings season).

### 2. The Engineering Plane ("The Factory")
A CI/AI pipeline that builds the strategies:
 *Architect Agent: Breaks requirements into technical specs.
 *Developer Agent: Writes Python code (using Decimal for precision).
 *Auditor Agent: Reviews code for financial "smells" (Look-ahead bias, floating point errors) and security flaws.
 *Sandbox (Executor): Runs code in isolated Docker containers/E2B to verify safety.

 ## 🚀 Key Capabilities

* Multi-Asset Abstraction: Generic Instrument classes allowing seamless analysis of:
  * Equities: Valuation (P/E, PEG), Earnings Calls, Insider Activity.
  * Bonds: Yield Spreads, Duration, Credit Ratings.
  * Digital Assets: Tokenomics (Burn/Mint), TVL, On-chain Activity.
* Tiered Model Routing:
  *Reasoning: GPT-5 / o1 for complex logic (PM decisions, Bond Math).
  *Context: Claude 3.5 for analyzing long documents (Prospectuses).
  *Coding: DeepSeek-V3 for cost-efficient code generation loops.
* Guardrails First:
  * Strict Auditor_Node implementation in LangGraph.
  * Automated "Hallucination Checks" for trade sizing.

## 🛠 Tech Stack  
* Orchestration: LangGraph (Stateful Multi-Agent workflows)
* LLMs: OpenAI (Reasoning), Anthropic (Context), DeepSeek (Code).
* Data Layer:
  * Time-Series: TimescaleDB / Polygon.io
  * Unstructured: Pinecone (Vector DB for News/Filings)
* Sandboxing: Docker / E2B
* Backtesting: Backtrader / Lean (QuantConnect) 

# 📂 Repository Structure

Bash 

quant-committee/

├── .github/workflows/         # CI/CD pipelines

├── core/
│   ├── agents/           # Agent definitions (Fundamental, Risk, Tech)

│   ├── memory/           # Redis/Vector DB connectors
│   └── instruments/      # Asset class abstractions (Equity, Bond, Token)

├── factory/              # The Agentic Engineering Loop

│   ├── architect.py      # Spec generation

│   ├── auditor.py        # Financial logic verification

│   └── sandbox/          # Docker execution environment

├── strategies/           # Generated trading strategies (Output of Factory)

└── main.py               # Entry point for the Trading Engine

# ⚡ Getting Started

## Prerequisites
* Python 3.11+
* Docker (for local sandboxing)
* API Keys: OpenAI, Anthropic, Financial Data Provider (e.g., Polygon/Alpaca)

## Installation
1 Clone the Repository

Bash

git clone https://github.com/your-org/quant-committee.git
cd quant-committee

2 Set up Environment

Bash

cp .env.example .env
# Edit .env with your API keys

3 Run the "Factory" (Generate a Strategy)
To spin up the Agentic Engineering loop that builds a new strategy:
Bash
python -m factory.main --request "Create a mean-reversion strategy for US10Y Bonds using RSI divergence"

4 Run the Trading Engine (Live/Paper)
Bash
python main.py --mode paper --portfolio "Conservative_Mix"


# 🗺 Roadmap

* [x] Phase 1: Core Architecture & Analyst Agent Prompts (Equities/Bonds/Crypto).
* [x] Phase 2: Agentic Engineering Boilerplate (LangGraph Factory).
* [ ] Phase 3: Sandbox Integration (Docker/E2B) & Backtesting Engine connection.
* [ ] Phase 4: Live Data Ingestion Pipelines (WebSockets).
* [ ] Future: Expansion to Private Credit (Document-heavy analysis).

# ⚠️ Disclaimer
This software is for educational and research purposes only. It is not financial advice. The "Auditor Agent" significantly reduces but does not eliminate the risk of algorithmic error. Use with paper money or strictly limited capital until fully validated.


## Next Step
This file is ready to be saved as README.md in your root folder.
Would you like me to now generate the folder structure (create the actual directories and empty __init__.py files) to match this README?















