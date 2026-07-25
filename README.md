# ai-security

Open, practitioner-oriented resources on **AI security, governance, and assurance** — verification standards, control frameworks, and continuous-monitoring models for AI and agentic systems.

---

## Contents

### OWASP AISVS 1.0.1-dev — Complete Framework (audit edition)

`owasp-aisvs-1-0-1_complete_framework_en_v2.pdf`

The complete **OWASP Artificial Intelligence Security Verification Standard 1.0.1-dev** rendered as an auditable framework:

- **203 auditable questions** across **16 parts** (192 official control references).
- Each control: official requirement, audit question, expected evidence, and **six response criteria** (fully / largely / partially implemented, planned, not implemented, not applicable).
- Cross-framework mappings: **ISO/IEC 27001:2022, NIST CSF 2.0, NIS2, EU AI Act, HIPAA, ANSSI**. EU AI Act links are typed as *direct obligation / implementation evidence / supporting measure*, never a flat "mapped / not mapped".
- **Annex A — Evidence Freshness** (see below).

### Annex A — Evidence Freshness: Continuous Controls Monitoring for AI Controls

A model for treating control **evidence as time-bounded** rather than a permanent checkbox — because AI systems mutate between audits.

- A permissions proof is void once an agent acquires a new tool; a data proof once a retrieval source changes; a model proof once a provider ships a new version.
- Frame: **ISCM (NIST SP 800-137)**, **Continuous Controls Monitoring (CCM)**, **EU AI Act Article 72** post-market monitoring, applied to AI and agentic controls.
- **Hybrid** invalidation: a maximum-validity (TTL) backstop **plus** invalidating events, first to trip wins.
- A **versioned envelope (AI-BOM)** over five axes — model, retrieval data, prompts, tools, permissions — makes a "significant change" a diff between two known states, each axis with a change detector.
- Evidence is typed **attestation vs observed** (the SOC 2 design-vs-operating-effectiveness distinction); observed evidence outweighs a signed attestation, and an attestation-only control is shown as *attested, not verified*.
- Staleness **degrades a score**, not a binary pass/fail; returning an invalidated control to valid requires an explicit **human re-service decision**.
- The dashboard becomes a **living register**: control, evidence, owner, last validation, next due, triggering event, re-service decision.

---

## Standards referenced

- OWASP Artificial Intelligence Security Verification Standard (AISVS) 1.0.1-dev
- NIST SP 800-137 — Information Security Continuous Monitoring (ISCM)
- EU AI Act — Article 72 (post-market monitoring)
- SOC 2 — design effectiveness vs operating effectiveness
- ISO/IEC 27001:2022, NIST CSF 2.0, NIS2

---

## License and attribution

- The **OWASP AISVS** requirement texts are the property of the OWASP Foundation and its contributors, licensed under **CC BY-SA 4.0**. Official source: <https://github.com/OWASP/AISVS>.
- The **audit questions, expected evidence, response criteria, cross-framework mappings, and the Evidence Freshness model** are the authoring/integration layer added on top; they do not imply endorsement by the OWASP Foundation and are not an official crosswalk.
- Documents in this repository are shared for review and educational use under **CC BY-SA 4.0**.

See [`LICENSE`](LICENSE).

---

## Notes

The Evidence Freshness annex is a **design proposal** presented for community review, not a certification, and not part of the OWASP AISVS standard itself.
