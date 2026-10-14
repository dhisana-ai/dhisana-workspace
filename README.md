# Dhisana Workspace

Dhisana Workspace brings Dhisana's RFP and market-signal monitoring and its
Sales Brain account research into Claude and ChatGPT. Ask in plain language
and the assistant works through Dhisana's own tools: it reviews cited
findings and records your accept or reject decisions, tunes monitoring
rules, runs Account Portfolio Fit and Quick Match research, reads the
resulting briefs and dossiers, and watches accounts for material changes.
Every action goes through your Dhisana workspace, with Dhisana's reviewer,
approval, reauthentication and audit rules enforced on the server.

You need a Dhisana account with access to at least one workspace.

## What you can ask

| Ask | What happens |
| --- | --- |
| "Show today's RFP findings for review" | Lists pending findings with buyer, deadline, confidence and source links first |
| "Accept the first two, reject the third as expired" | Records the decisions after you confirm each one |
| "Send the accepted findings to the team" | Emails accepted findings, one per message, after you confirm |
| "Exclude retailers from this monitor" | Shows the exact rule change, previews it, applies it after you confirm |
| "How is the RFP watchlist performing this month?" | Accepted, rejected and duplicate counts by policy group |
| "Where could we help this account?" | Runs or reads Account Portfolio Fit across the configured catalogue |
| "Could this offering fit this account? What must we validate?" | Runs or reads a Quick Match brief with fit, timing, questions and sources |
| "Tell me when something material changes at this account" | Previews and creates an account watch, then reports impacts |

Skills included: `dhisana-workspace` (overview), `review-rfps`,
`tune-policy`, `signal-report`, `portfolio-fit`, `quick-match`,
`watch-account`.

## Connect

The plugin connects to Dhisana's remote MCP server at
`https://api-agent.dhisana.ai/mcp-server/mcp`. You sign in with your Dhisana
account and choose the workspace the connection may reach; there are no API
keys to copy.

**Claude (claude.ai, Desktop, Cowork).** Add the plugin from the directory, or
upload a zip of this repository under **Customize → Plugins → Add → Upload
plugin**, then connect the Dhisana connector from the plugin's **Connectors**
tab. Team and Enterprise owners add the connector for the organization first.

**Claude Code.**

```bash
claude plugin marketplace add dhisana-ai/dhisana-workspace
claude plugin install dhisana-workspace@dhisana
```

**Codex.**

```bash
codex plugin marketplace add dhisana-ai/dhisana-workspace
```

then install **Dhisana Workspace** from the plugin directory and sign in when
prompted.

**ChatGPT.** Install from the plugin directory once listed, or register the
MCP URL in developer mode.

## Data

The plugin itself stores nothing and contains no credentials. When you use
it, your requests and the identifiers of the records you act on are sent to
your Dhisana workspace through the MCP server above, and Dhisana returns
saved research, findings, briefs, dossiers and campaign data from that
workspace. Access uses an OAuth token tied to you and the workspace you chose
at sign-in; Dhisana checks your permissions on every request. Actions that
send email, start research runs or change monitoring rules ask for your
confirmation first and may consume Dhisana credits. Data handling is governed
by your organization's agreement with Dhisana AI.

## Support

Visit [dhisana.ai](https://www.dhisana.ai) or contact your Dhisana account
team.

## License

See [LICENSE](LICENSE).
