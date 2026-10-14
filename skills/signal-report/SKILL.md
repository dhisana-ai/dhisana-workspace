---
name: signal-report
description: Report Dhisana signal-monitoring outcomes and usage: findings evaluated, assigned, accepted, rejected and duplicates by policy group, policy performance over a date window, and credits consumed. Use when the user asks how monitoring is performing, for a weekly or monthly summary, or for acceptance rates.
---

1. `get_signal_program_summary` returns the program summary and policy
   performance; pass `candidate_created_from` / `candidate_created_before`
   (epoch milliseconds) for a window, and `policy_id` for one policy's
   outcome analytics. `get_signal_policy_runs` lists runs and credits for a
   policy.
2. Present counts exactly as returned, by policy group, and say what each
   count means: evaluations include repeats across runs; assigned findings
   are review assignments, not confirmed views; recorded outcomes include
   automatic rejections; acceptance does not mean a sales win.
3. Credits are usage units, not currency. Do not estimate figures the tools
   did not return; if a window has no data, say so.
4. Offer next steps that stay in Dhisana: tune a policy (`tune-policy`
   skill) or review open findings (`review-rfps` skill).
