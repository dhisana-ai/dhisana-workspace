---
name: review-rfps
description: Review RFP, tender and market-signal findings in Dhisana, record accept/reject decisions with reasons, and send accepted findings to the team. Use when the user asks for today's findings, new RFPs, what needs review, or to accept, reject or share a finding.
---

Work only from the Dhisana connection; never invent findings, buyers, deadlines
or sources. Start with `open_dhisana_workspace` if no workspace is selected.

1. **Fetch the queue.** Call `get_workspace_signal_review` (page with
   `offset`/`limit`). If the user named a policy or group, use
   `list_signal_policies` to identify it and keep only matching findings when
   presenting. Present each finding as: buyer, closing date, confidence,
   Why It Matters, then the official source link first. Say when a tender is
   expired or flagged as a repeat; never upgrade a hypothesis to a fact.
2. **Answer questions from evidence.** Use `ask_signal_finding` for "why was
   this matched", "when does it close", "is this a duplicate"; report its
   confidence and sources. If the source looks stale, offer
   `reverify_finding_source` (background, consumes credits).
3. **Record decisions only on explicit instruction.** Before `review_signal`,
   restate the exact item and decision. Reject and request-more-information
   decisions need a useful note. A 428 means the user must complete sensitive
   reauthentication in Dhisana; never invent a token. Respect `can_act` and
   server errors; host approval does not replace Dhisana's reviewer policy.
4. **Share accepted findings.** `list_signal_review_batches` (ready-to-send
   first) then `send_accepted_findings` for the batch the user names. This
   sends external email, one finding per message with source links first:
   show the batch, counts and that email will be sent, and obtain explicit
   confirmation. Use `force_resend` only with a reason the user gave.

Never enrol contacts, start campaigns or draft outreach as an implied next
step of a review. Acceptance is a review outcome, not a sales win.
