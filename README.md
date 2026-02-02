# Tenx MCP — Cursor Submission (TRP 1)

This repository contains the configuration and documentation used to connect Cursor to the Tenx MCP server (tenxfeedbackanalytics) for the TRP 1 MCP Setup Challenge.

## What I did

1. Created `.cursor/mcp.json` to configure the Tenx MCP endpoint.
2. Created `.cursor/rules/agent.mdc` with a rules template that guides the agent behavior in Cursor.
3. Tested the connection by toggling the MCP server in Cursor and authenticating with GitHub.
4. Performed minimal agent interaction to generate logs captured by the MCP server.

## What worked

- MCP server configuration (`.cursor/mcp.json`) was accepted after toggling the server and authenticating GitHub.
- The agent responded to the rules file and executed the test task (simple README creation), producing a transcript snippet.

## What didn't work / troubleshooting

- If authentication fails during the GitHub OAuth redirect, re-check browser cookies and ensure the system is not blocking popups or redirections.
- If the Tenx server URL is unreachable, confirm network access and try again.

## Insights gained

- Rules files (agent.mdc) significantly shape the agent's output: explicit `actions` and `final_artifact` fields produce reproducible results.
- Small, verifiable tasks (creating a README or running `echo`) are the fastest way to prove MCP logging.
