# AI Use Case Check – free sample

A small, free toolkit to learn how to **review an AI tool before approving it**, and how to **automate the first draft** of that review with an AI while a human keeps the decision.

> Educational sample. Fictional data only. Not legal advice. The AI drafts; a person decides.

## What's inside

| File | What it is |
|---|---|
| `AI_Use_Case_Check_Sample.xlsx` | 8-tab workbook: intake, 24 review questions, scoring, safeguards, decision log, 8 AI prompts, one fictional worked example |
| `batch_use_cases.xlsx` | Five fictional use cases for the automation demo |
| `automate.py` | Reads the batch file, asks an AI for a draft risk assessment per row, writes it back |

## Try it with zero setup (copy-paste mode)
1. Open the workbook and read `Start_Here`, then `7_Worked_Example`.
2. Fill `1_Intake` and answer the questions in `2_Review` for a fictional AI tool.
3. Use the prompts in `6_AI_Prompts` in any chatbot (fictional data only) and paste the answers back.

## Try the automation
```bash
pip install openpyxl requests
# Free, local, no key (install Ollama first, then: ollama pull llama3.2)
python automate.py

# Or with the Anthropic API (paid; key stays in your environment, never in the code)
PROVIDER=anthropic ANTHROPIC_API_KEY=your_key python automate.py
```
Then review **every** row in `batch_use_cases.xlsx`: columns H–K are for you (agree/disagree, what the AI missed, minutes by hand vs with AI).

## Limits and risks (read this)
- **The AI can be wrong.** It may sound confident while misjudging a risk, invent facts or miss context. That is why a human reviews every row.
- **Data leakage.** Public AI tools send your text to a third party. Use fictional or approved data only; in a real company use an approved tool with a data-protection contract.
- **Scores are teaching assumptions.** Weights and thresholds are my own choices, not an official standard. Adjust them in `3_Scoring`.
- **Local models are weaker.** A small local model gives rougher drafts than a large hosted one; this is useful to see.
- **Not a compliance guarantee.** Check the EU AI Act, GDPR and your own policies for real decisions.

## Author
Keren Adamu – GRC engineering & AI risk governance.
