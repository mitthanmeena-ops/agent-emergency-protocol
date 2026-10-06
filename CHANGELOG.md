# Changelog

All notable changes to the Agent Emergency Protocol (AEP) are recorded here.
AEP was created by Mitthan Meena.

## [0.1-draft] — 2026-10-06

First public draft, written by Mitthan Meena.

- 21 emergency codes in 8 families (1xxx identity through 9xxx response states).
- Five levels: L1 Watch, L2 Contain, L3 Isolate, L4 Quarantine, L5 Ground.
- Six protocol rules, including "declared from outside", two-person release from L4 and above, and sticky codes.
- Mapping strength (Direct, Partial, Conditional, None, Response) for every MITRE ATLAS and ATT&CK mapping.
- NIST SP 800-53 mappings stated as evidence that *may support* a control, never as satisfying it.
- Declaration event format (`aep.v0.declaration`) with JSON Schema and three examples: 2100 HIJACK, 5200 SWARM, 9900 FLEET STOP.
