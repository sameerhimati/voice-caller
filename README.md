# voice-caller

AI voice agent that calls commercial property owners using a structured calling script. Logs call outcomes for scoring model feedback.

## What it replaces
Cold callers / BD teams dialing through lead lists.

## Usage
```bash
voice-caller call --phone "+12145551234" --owner "John Smith" --property "123 Main St"
voice-caller batch --call-sheet leads.csv --max-calls 20
voice-caller outcomes --show-today
```

## Call Flow
1. Dial owner
2. Introduce (natural conversation, not robotic)
3. Gauge interest in selling
4. Log outcome: interested / not interested / wrong number / voicemail / callback requested

## Input / Output

**Input:**
- Single call: `--phone`, `--owner` (name), `--property` (address)
- Batch mode: call sheet CSV with columns: `phone`, `owner_name`, `property_address`, `lead_score`
- Environment: `RETELL_API_KEY` or `BLAND_API_KEY`

**Output:**
- Outcome JSON per call: `{ "phone", "owner_name", "property_address", "outcome" (interested|not_interested|wrong_number|voicemail|callback), "notes", "duration_seconds", "timestamp" }`
- Batch mode: outcomes CSV with all call results
- Exit code 0 on success, 1 on failure
- stdout: batch summary (total calls, outcomes breakdown)

## Stack
- Python 3.14
- Retell.ai or Bland.ai (voice AI platform)
- Typer + Rich for CLI

## Status
🔴 Blocked — validate calling script with 10-15 manual calls first
