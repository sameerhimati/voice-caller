# voice-caller

## What This Is
AI voice calling agent for CRE owner outreach. Calls property owners, follows a structured script, logs outcomes.

## Key Constraints
- DO NOT build until calling script validated with 10-15 manual calls
- TCPA compliance: check DNC list, respect calling hours, identify as caller
- Outcomes feed back into scoring model — this is the feedback loop
- Outcomes table is for scoring feedback, NOT CRM
- Voice platform: evaluate Retell ($0.07/min) vs Bland ($0.09/min)

## Architecture
- Call script: structured prompt for voice AI (from docs/calling-script.md)
- Voice platform adapter: abstract over Retell/Bland API
- Outcome logger: call result → structured data → output file/webhook
- CLI: single call or batch from call sheet

## Tech
- Python 3.14, httpx (API calls), Typer + Rich
- Use venv/bin/python and venv/bin/pytest

## Anti-Patterns
- Don't build CRM features — outcomes are scoring feedback only
- Don't automate before manual validation
- Don't use AI for negotiation or sensitive conversations
