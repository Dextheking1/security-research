# Security research

**Benjamin Kincses (Dextheking1)**. Security research focused on AI products and open source. Every finding below was verified locally before it was reported, and serious findings go through each project's own private disclosure process first.

Site: [benihacking.top](https://benihacking.top) · GitHub: [Dextheking1](https://github.com/Dextheking1)

## Record

Counts verified against GitHub on 2026-10-24.

| | |
|---|---|
| Security fix PRs merged | 4 |
| Security fix PRs open and under review | 58 |
| GitHub advisories filed, in coordinated disclosure | 11 |
| Advisories published | 0 |
| Coordinated disclosures in progress, all channels | 26 |

Advisories are published by project maintainers at the end of coordinated disclosure, not by the reporter. The 11 filed advisories are in triage with the maintainers; published ones will be listed here as they land.

## Published advisories

| GHSA | Project | Severity | Link |
|---|---|---|---|
| None published yet | 11 advisories filed and in coordinated disclosure | | |

## Merged security fixes

| Project | PR | Fix |
|---|---|---|
| ruvnet/ruflo | [#4416](https://github.com/ruvnet/ruflo/pull/4416) | Reject `..` in roomId, closing a path traversal through the room log path |
| ruvnet/ruflo | [#4418](https://github.com/ruvnet/ruflo/pull/4418) | Unguessable MCP session ids (crypto randomUUID) |
| kirodotdev/KiroCrew | [#23327](https://github.com/kirodotdev/KiroCrew/pull/23327) | Snapshot tar filter rejects special files (FIFO, device nodes) on extraction |
| takiAA/twitter-scraper-mcp | [#13](https://github.com/takiAA/twitter-scraper-mcp/pull/13) | Worker child process receives an environment allowlist instead of the server's full environment |

## Selected fixes under review

58 security fix and hardening PRs are open. A selection:

- supabase/postgres-meta [#1171](https://github.com/supabase/postgres-meta/pull/1171): enum allowlists closing SQL injection in trigger and policy creation
- supabase/auth [#2885](https://github.com/supabase/auth/pull/2885): timeout and size cap on the SAML metadata fetch
- vxcontrol/pentagi [#468](https://github.com/vxcontrol/pentagi/pull/468) and [#469](https://github.com/vxcontrol/pentagi/pull/469): privilege checks on REST token endpoints; caps on terminal directory reads
- deepseek-ai/Janus [#243](https://github.com/deepseek-ai/Janus/pull/243), [#244](https://github.com/deepseek-ai/Janus/pull/244), [#245](https://github.com/deepseek-ai/Janus/pull/245): `trust_remote_code` removed, demo sharing defaults fixed, checkpoint loads pinned to `weights_only`
- deepseek-ai/DeepSeek-VL2 [#158](https://github.com/deepseek-ai/DeepSeek-VL2/pull/158), DeepSeek-V3 [#1724](https://github.com/deepseek-ai/DeepSeek-V3/pull/1724) and [#1725](https://github.com/deepseek-ai/DeepSeek-V3/pull/1725), DeepSeek-Coder [#723](https://github.com/deepseek-ai/DeepSeek-Coder/pull/723)
- localhost8083/marscli [#1](https://github.com/localhost8083/marscli/pull/1) to [#4](https://github.com/localhost8083/marscli/pull/4): credential storage and updater hardening for an OpenCode fork
- CodebuffAI/freebuff [#1545](https://github.com/CodebuffAI/freebuff/pull/1545) and [#1546](https://github.com/CodebuffAI/freebuff/pull/1546): sponsored-mode refusal walk fails closed; `read_url` refuses under a proxy instead of dropping DNS pinning
- Logflare/logflare [#4200](https://github.com/Logflare/logflare/pull/4200) and [#4201](https://github.com/Logflare/logflare/pull/4201): atom exhaustion via flash keys; PII redaction header and results cache fixes
- pollinations/pollinations [#18163](https://github.com/pollinations/pollinations/pull/18163) and [#18164](https://github.com/pollinations/pollinations/pull/18164): publishable keys stripped of account scopes; quest reward parsing bounded
- Comfy-Org/ComfyUI-Manager [#3410](https://github.com/Comfy-Org/ComfyUI-Manager/pull/3410) and Comfy-Org/Comfy-Desktop [#1786](https://github.com/Comfy-Org/Comfy-Desktop/pull/1786): TLS verification respected in share requests; http(s) allowlist on window-open
- cloudflare/circl [#711](https://github.com/cloudflare/circl/pull/711): blind RSA salt read from the supplied randomness source

## Method

1. Audit the public source code locally. No live service is probed.
2. Prove the finding on local ground only: extracted functions, harnesses, or a local instance, with synthetic data, and state the proof level honestly.
3. Write the fix: minimal, with a regression test that fails before and passes after.
4. Disclose through the project's own process. Private report first for anything serious; a public fix PR only where the fix does not teach the exploit.
5. Ask for a published advisory, a CVE, and Finder credit under the name Benjamin Kincses (Dextheking1).

## Contact

GitHub: [Dextheking1](https://github.com/Dextheking1) · Site: [benihacking.top](https://benihacking.top)

To report a vulnerability in a project I contribute to, use that project's own security process.
