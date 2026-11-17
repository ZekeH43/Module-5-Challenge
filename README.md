# Financial Planning — Python notebook

A historical FinTech course assignment that explores **emergency savings** and **retirement projections** using cryptocurrency prices, equity/bond market data, and Monte Carlo simulation. The original coursework instructions are preserved in [Instructions/README.md](Instructions/README.md).

## What is in the repository?

- [Financial planner notebook](Instructions/Starter_Code/financial-planner.ipynb) — calculations, savings composition, and portfolio simulations
- [MCForecastTools.py](Instructions/Starter_Code/MCForecastTools.py) — the original Monte Carlo helper
- [Original instructions](Instructions/README.md) — assignment requirements and illustrations

This is **educational, historical code**, not an investment recommendation or a production financial planner. The notebook uses live services and older library interfaces; its outputs are not guaranteed to reproduce on a modern environment.

## Local setup

1. Install Python 3.10 or an environment compatible with the original course notebook. The original helper uses older pandas interfaces, so modern pandas releases may require code updates.
2. Create an isolated environment from the repository root:
   ```bash
   python -m venv .venv
   # Windows PowerShell: .venv\Scripts\Activate.ps1
   # macOS/Linux: source .venv/bin/activate
   python -m pip install notebook numpy pandas matplotlib requests python-dotenv alpaca-trade-api pytz
   ```
3. Copy [`.env.example`](Instructions/Starter_Code/.env.example) to `Instructions/Starter_Code/.env` **locally** and enter newly generated credentials. Never commit real keys.
4. Start Jupyter from the notebook directory so relative paths and `.env` discovery are consistent:
   ```bash
   cd Instructions/Starter_Code
   jupyter notebook financial-planner.ipynb
   ```
5. Run notebook cells sequentially and inspect any API failures. Price services, credential permissions, and API signatures may have changed since the course exercise.

Dependencies above are an illustrative starting point, **not a tested lockfile**. The code has not been validated against current live API services in this cleanup.

## Learning goals

The notebook considers hypothetical BTC and ETH holdings plus SPY and AGG positions, calculates whether total savings meet an emergency-fund threshold, and uses a Monte Carlo model to illustrate a possible distribution of retirement outcomes. A Monte Carlo interval is an output of modeling assumptions, **not a guaranteed investment outcome**.

## Security notes

A credentials file was previously committed to this repository and is removed in this cleanup. **Deleting the current file does not erase earlier commits.** Any actual API keys ever stored there should be revoked/rotated through their providers. Avoid posting the old values in issues, logs, or pull requests. `.gitignore` now excludes environment files, checkpoints, and Python bytecode.

## Portfolio context

This project demonstrates reading external APIs, manipulating pandas DataFrames, plotting financial data, and reasoning about simulation assumptions. The modernized, reproducible risk-simulation portfolio project lives separately in [Project-1](https://github.com/ZekeH43/Project-1).
