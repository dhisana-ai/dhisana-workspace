---
name: quick-match
description: Run and read a Dhisana Quick Match (Module 3) brief — one offering for one account with fit, timing, confidence, discovery questions, source links and a downloadable dossier. Use when the user asks whether a product could fit an account, what to validate before a call, or for a meeting-prep brief.
---

1. Identify offering and account: `list_offerings` (IDs and policy
   templates), `find_matchmaker_accounts`, or `interpret_sales_request` for
   free text. Confirm both with the user.
2. Prefer a saved assessment: `list_quick_match_runs` with `offering_id` and
   `account_id` (use `valid_only=true` for current ones). Run
   `run_quick_match` only when none is suitable; it consumes credits and
   runs in the background. Return the run ID and poll `get_quick_match_run`
   when the user asks; fresh research is not instant. Its `run_status`,
   `recommendation_ids` and `failure` fields say whether a brief exists.
3. `get_quick_match_recommendation` is the brief. Present four parts and keep
   them separate: **Fit** (outcome, rationale, sources), **Timing** (current
   evidence, or that none exists; old news may not justify outreach),
   **Discovery** (questions to validate need and ownership; buyer roles are
   hypotheses), **Confidence** (as returned). A score is not purchase intent.
4. `ask_quick_match_question` answers follow-ups from the saved evidence
   only. `get_quick_match_dossier` returns the permitted dossier record and
   download path (set `include_content=true` for small text dossiers);
   creating one is policy-controlled and recorded.
5. End with a defensible seller action: a discovery question, further
   research, or a watch (`watch-account` skill). The seller decides whether
   to engage; never enrol contacts or send outreach from here.
