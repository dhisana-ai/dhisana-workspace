---
name: watch-account
description: Set up and read Dhisana account watches (Module 2) — account-product watchlists that record a baseline and surface material changes with urgency, rationale and gaps. Use when the user wants to be told when something changes at an account, to follow up later, or to see what changed since the last review.
---

1. `list_account_watches` shows existing watches, their cadence, members and
   status, plus the catalogue of offerings and policies a watch can use.
   Reuse an existing watch where one covers the account and offering.
2. To create one: gather name, `offering_id`, `policy_id`, the account IDs
   (`find_matchmaker_accounts`) and cadence (daily, weekly, manual). Call
   `preview_account_watch` first and show the baseline it would record.
   Only after explicit confirmation call `create_account_watch`; scans
   consume provider credits.
3. `get_watch_impacts` lists changes since the baseline with category
   (new opportunity, risk, timing, no change, insufficient evidence),
   urgency, why it matters for the account and product, evidence and gaps.
   Report `no_change` and `insufficient_evidence` honestly; do not promote
   them to opportunities.
4. `update_account_watch` pauses, resumes, retires or scans a watch on
   explicit instruction; a scan consumes credits.

A watch surfaces changes for a human to judge; it never contacts anyone.
