# voice-caller Roadmap

## v0.0 — Manual Validation (PREREQUISITE)
- [ ] Generate call sheet from scored leads
- [ ] Make 10-15 manual calls with calling script
- [ ] Track outcomes manually (spreadsheet)
- [ ] Validate: do high scores correlate with actual interest?
- [ ] Refine script based on real conversations

## v0.1 — Platform Evaluation
- [ ] Project setup (venv, requirements.txt, CLI skeleton)
- [ ] Evaluate Retell.ai — test voice quality, latency, script following
- [ ] Evaluate Bland.ai — same tests
- [ ] Pick winner

## v0.2 — MVP Agent
- [ ] Voice platform adapter (abstract API)
- [ ] Call script as structured prompt
- [ ] CLI: `voice-caller call --phone --owner --property`
- [ ] Outcome logging (JSON output)

## v0.3 — Batch + Feedback
- [ ] Batch calling from call sheet CSV
- [ ] Outcome webhook for scoring model feedback
- [ ] Call recording storage
- [ ] Analytics: hit rate, best times, script effectiveness
