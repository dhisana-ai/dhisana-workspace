---
name: tune-policy
description: Inspect and tune Dhisana signal-monitoring policies (RFP watchlists, market sensing): keywords, exclusions, buyer roles, regions, schedule, pause/resume and run-now. Use when the user wants fewer irrelevant findings, to exclude something, change cadence, or run a monitor now.
---

Policies are tenant configuration. Read before you change; change only what
the user asked for; show the exact change before applying it.

1. `list_signal_policies` → identify the policy (and policy group) the user
   means; `get_signal_policy` for its full rules. The `tunable_metadata`
   block shows the current values of what can be patched: opportunity and
   buyer keywords, exclusions, regions, source families, exclude keywords,
   trusted source domains, exclude-expired-opportunities and minimum score.
2. `get_policy_tuning_recommendations` surfaces proposals derived from
   reviewer accept/reject feedback, each with a code. Explain each proposal
   in one line; do not apply any without instruction.
3. Propose the change as a before/after diff. Then call `apply_policy_tuning`
   with `dry_run=true` to preview, show the preview, and only after explicit
   approval call it again without `dry_run`. Pass only keys the user agreed
   to; unknown keys are rejected by the server. Schedule changes use
   `cadence`, `cron_rule`, `timezone`, `priority`, `max_records_per_run`.
4. `set_signal_policy_state` pauses or resumes a policy. `run_signal_policy`
   starts a run now: it consumes provider credits and runs in the
   background; report the run ID and follow with `get_signal_policy_runs`.
   Never retry a run after an ambiguous failure before checking run status.

Customer product names, competitor lists and source packs live in tenant
data; do not hard-code or guess them. Summarize what changed at the end.
