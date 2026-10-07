# Agent Emergency Protocol Incident Codes

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23188364.svg)](https://doi.org/10.5281/zenodo.23188364)

**A vendor-neutral runtime incident-code language for autonomous AI agents.**

Pilots and air traffic control act on the same transponder code the moment something goes wrong. Agent Emergency Protocol Incident Codes bring the same idea to AI agents.

Every incident gets:

- a short **code** for what is happening, for example `2100 HIJACK`, `5200 SWARM`, `9900 FLEET STOP`
- a **level** for how severe it is, from `L1 Watch` to `L5 Ground`
- a **default first response**
- a standard **evidence record** that any vendor, SIEM or auditor can read

> **Agent Emergency Protocol Incident Codes were originated and authored by Mitthan Meena.**

**Status:** v0.1 draft for review. Not yet a standard.

---

## Review requested

This is a public v0.1 draft. I am looking for feedback from people running AI agents, building agent security, or working on MITRE ATLAS, OWASP, NIST, ISACA, incident response, audit, or governance frameworks.

Please open an issue for:

- missing incident codes
- wrong default levels
- bad MITRE / NIST mappings
- unclear response states
- better naming
- production scenarios this draft does not cover

---

## Read the spec

- **[SPEC.md](SPEC.md)** — the full v0.1 draft specification
- **[schemas/aep-declaration.schema.json](schemas/aep-declaration.schema.json)** — JSON Schema for declaration events
- **[examples/](examples/)** — `2100-hijack.json`, `5200-swarm.json`, `9900-fleet-stop.json`

---

## The codes at a glance

| Family | Codes |
|---|---|
| 1xxx Identity and ownership | 1100 IMPOSTOR · 1200 ORPHAN · 1300 SHADOW |
| 2xxx Control-plane compromise | 2100 HIJACK · 2200 ESCALATE · 2300 TAMPER |
| 3xxx State and context compromise | 3100 DRIFT · 3200 POISON |
| 4xxx Business harm | 4100 LEAK · 4200 DESTROY · 4300 SPEND |
| 5xxx Autonomy failure | 5100 RUNAWAY · 5200 SWARM · 5300 SPAWN |
| 6xxx Supply chain | 6100 BAD TOOL · 6200 BAD MODEL · 6300 BAD CONNECTOR |
| 7xxx Observability failure | 7100 DARK · 7200 BLIND |
| 9xxx Response states | 9000 GROUND STOP · 9900 FLEET STOP |

---

## Why this exists

Everyone is talking about AI agent kill switches.

But a kill switch is only one action. Real incidents need a shared language:

- What happened?
- How bad is it?
- What authority should be cut first?
- What evidence should be preserved?
- Who can release the agent back into operation?

Agent Emergency Protocol Incident Codes define that runtime language.

---

## How this relates to existing frameworks

- **MITRE ATLAS / ATT&CK** describe what adversary technique *may have caused* an event. This draft maps to them with an explicit mapping strength: Direct, Partial, Conditional, None, or Response.
- **NIST SP 800-53** describes control objectives. These events produce evidence that *may support* an assessment; a declaration never by itself satisfies a control.
- **Agent Emergency Protocol Incident Codes** cover what neither defines: loss of control, unsafe authority, business harm, undo and fleet response — whether the cause is an attacker or an accident.

---

## License and attribution

© 2026 Mitthan Meena.

The specification, schemas and examples are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

You may copy, adapt and implement this work, including commercially, provided you:

1. credit **"Agent Emergency Protocol Incident Codes, created by Mitthan Meena"**
2. link to this repository
3. state any changes you made

**Cite as:** Meena, M. (2026). *Agent Emergency Protocol Incident Codes v0.1 — Draft Specification.* Zenodo. https://doi.org/10.5281/zenodo.23188364

**Repository:** https://github.com/mitthanmeena-ops/agent-emergency-protocol

See [CITATION.cff](CITATION.cff) for machine-readable citation data.

---

## Contributing

Feedback is welcome through issues.

By submitting a contribution, you agree it may be included under CC BY 4.0, with the project’s original authorship and attribution preserved.

Suggested first issues:

- Are any incident codes missing?
- Are the default levels too aggressive or too weak?
- Are the MITRE ATLAS / ATT&CK mappings correct?
- Are the NIST SP 800-53 evidence mappings useful?
- Should response-state codes use different names?
