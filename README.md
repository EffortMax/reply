# Relay bootstrap Skill — portable source

Files: `SKILL.md` (instructions), `relay.py` (sanitized single-file MCP relay, including SIGPIPE fix), `PROTOCOL.md` (reference protocol). Intended to be installed under `skills/relay-bootstrap/` in the current workbench; the *new Agent* must copy `relay.py` into its **own** cloud workspace and use its own private connection settings/key. This package intentionally contains no endpoint, Bearer token, Agent key or conversation ID.

The reference protocol's sample path `/home/user/relay/relay.py` is an example, not a portable requirement. Adapt it to the new Agent's actual workspace. Commands in the protocol are examples and are not automatic permissions to install dependencies, run commands, delete files or restart services. Check capabilities with `tools/list`; use the actual schema. A Skill selection is not a persistent process.

One-time local checks: `python3 relay.py --help`; install `mcp` if needed (e.g. isolated `pip install mcp`, or `pip install --target vendor mcp`). Supply the private endpoint through a secure channel; on the new Agent's own copy configure `DEFAULT_URL` or pass `--url`. Do not edit the shared Skill with secrets. Check daemon status before starting; register a new key and save it securely. Message polling must be bounded by the caller's execution limit, and is not guaranteed to persist across model turns.
