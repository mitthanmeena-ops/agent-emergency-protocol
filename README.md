# Agent Emergency Protocol (AEP)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23188364.svg)](https://doi.org/10.5281/zenodo.23188364)

**A vendor-neutral runtime emergency-code language for autonomous AI agents.**

Pilots and air traffic control act on the same transponder code the moment something goes wrong. AEP does the same for AI agents. Every incident gets:

- a short **code** for what is happening (for example `2100 HIJACK`, `5200 SWARM`),
- a **level** for how severe it is (L1 Watch → L5 Ground),
- a **default first response** that runs automatically, and
- a standard **evidence record** that any vendor, SIEM or auditor can read.

> **Agent Emergency Protocol (AEP) was originated and authored by Mitthan Meena.**
> Fortik is the intended reference implementation, but AEP is vendor-neutral.

**Status:** v0.1 draft for review. Not yet a standard.

## Read the spec

- **[SPEC.md](SPEC.md)** — the full v0.1 draft specification
- **[schemas/aep-declaration.schema.json](schemas/aep-declaration.schema.json)** — JSON Schema for declaration events
- **[examples/](examples/)** — `2100-hijack.json`, `5200-swarm.json`, `9900-fleet-stop.json`

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

## How AEP relates to existing frameworks

- **MITRE ATLAS / ATT&CK** describe what adversary technique *may have caused* an event. AEP maps to them with an explicit strength (Direct, Partial, Conditional, None).
- **NIST SP 800-53** describes control objectives. AEP events produce evidence that *may support* an assessment; a declaration never by itself satisfies a control.
- **AEP** covers what neither defines: loss of control, unsafe authority, business harm, undo and fleet response — whether the cause is an attacker or an accident.

## License and attribution

© 2026 Mitthan Meena. The specification, schemas and examples are licensed under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). You may copy, adapt and
implement AEP, including commercially, provided you:

1. credit **"Agent Emergency Protocol (AEP), created by Mitthan Meena"**,
2. link to this repository, and
3. state any changes you made.

**Cite as:** Meena, M. (2026). *Agent Emergency Protocol (AEP) v0.1 — Draft Specification.* Zenodo. https://doi.org/10.5281/zenodo.23188364

**Repository:** https://github.com/mitthanmeena-ops/agent-emergency-protocol

See [CITATION.cff](CITATION.cff) for machine-readable citation data.

## Contributing

Feedback is welcome through issues. By submitting a contribution you agree it may be included in AEP under CC BY 4.0, with the project's authorship and credit unchanged.
