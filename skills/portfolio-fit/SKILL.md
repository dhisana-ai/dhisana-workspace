---
name: portfolio-fit
description: Run and read Dhisana Account Portfolio Fit (Module 1) — one target account compared against the configured product catalogue, with supported, conditional and unsupported outcomes, evidence and gaps. Use when the user asks where we could help an account, which products fit, or for account planning input.
---

1. Resolve the account first: `find_matchmaker_accounts` by name or domain,
   or `interpret_sales_request` for free text. Confirm the company with the
   user before starting research. `list_offerings` shows the configured
   catalogue (names come from tenant data).
2. Check for a saved discovery before running a new one:
   `list_account_portfolio_fit_runs` filtered by `account_id`. Reuse a
   completed run unless the user wants fresh research.
3. `run_account_portfolio_fit` starts background research and consumes
   provider credits; tell the user it takes minutes and return the run ID.
   Do not pretend results exist yet.
4. `get_account_portfolio_fit` returns the run status and product-by-product
   outcomes. Present each offering with its outcome, the evidence, the gaps,
   and exclusions with their reasons. An empty shortlist is a valid result.
   Keep weak or unsupported ideas visible rather than hiding them.
5. Suggest the next step the brief supports: a Quick Match on one promising
   offering (`quick-match` skill) or a discovery question for the account
   lead. Bring a specialist in only when evidence justifies it.

Never fabricate evidence, buyer names or timing; distinguish fit from buying
timing; state missing evidence as missing.
