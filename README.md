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







