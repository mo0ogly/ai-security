# Security Frameworks

Open, practitioner-oriented resources for securing, governing, auditing, and continuously assuring AI and agentic systems.

This repository is not dedicated to a single standard. It is an evolving collection of **security frameworks, audit methodologies, control models, cross-framework mappings, and continuous-monitoring approaches** intended for security practitioners, auditors, governance teams, researchers, and AI system owners.

The repository focuses on turning high-level requirements into operational and auditable resources:

* AI security verification frameworks
* Governance and assurance models
* Audit questions and evidence requirements
* Control implementation criteria
* Cross-framework mappings
* Continuous Controls Monitoring for AI
* Agentic-system security and governance
* Evidence validity and change detection
* Maturity and assessment methodologies

The objective is not to create another isolated compliance checklist. It is to provide a reusable framework repository for evaluating whether AI security controls are defined, implemented, evidenced, monitored, and maintained as systems evolve.

## Repository principles

The resources published here follow several principles:

1. **Auditability**

   Requirements are translated into explicit audit questions, expected evidence, and assessable response criteria.

2. **Traceability**

   Controls are linked to their original standards, regulations, frameworks, or authoritative sources.

3. **No flat crosswalks**

   Mappings distinguish between direct obligations, implementation evidence, supporting measures, and contextual relationships.

4. **Evidence over declaration**

   A documented claim is not treated as equivalent to observed operating evidence.

5. **Time-bounded assurance**

   Evidence does not remain valid indefinitely. Changes to models, data, prompts, tools, permissions, infrastructure, or providers may invalidate previous assessments.

6. **AI and agentic-system awareness**

   The frameworks account for systems that can change behavior, access new tools, retrieve new data, or act with increasing autonomy.

7. **Practitioner orientation**

   The repository is designed to support real audits, control reviews, assurance activities, security programs, and continuous monitoring.

## Current frameworks and resources

### OWASP AISVS 1.0.1-dev — Complete Framework, Audit Edition

File:

`owasp-aisvs-1-0-1_complete_framework_en_v2.pdf`

A complete audit-oriented rendering of the OWASP Artificial Intelligence Security Verification Standard 1.0.1-dev.

The framework contains:

* 203 auditable questions across 16 parts
* 192 official OWASP AISVS control references
* The official requirement associated with each control
* A dedicated audit question
* Expected evidence
* Six response criteria:

  * Fully implemented
  * Largely implemented
  * Partially implemented
  * Planned
  * Not implemented
  * Not applicable

It also includes cross-framework mappings to:

* ISO/IEC 27001:2022
* NIST Cybersecurity Framework 2.0
* NIS2
* EU AI Act
* HIPAA
* ANSSI guidance and frameworks

EU AI Act relationships are typed as:

* Direct obligation
* Implementation evidence
* Supporting measure

They are never reduced to a flat “mapped / not mapped” relationship.

The document also includes **Annex A — Evidence Freshness**.

## Evidence Freshness

### Continuous Controls Monitoring for AI Controls

Evidence Freshness is a proposed assurance model for treating AI control evidence as time-bounded rather than permanent.

Traditional audits often treat evidence as a durable checkbox. This assumption is unsuitable for AI and agentic systems, which can materially change between two assessments.

Examples:

* A permissions assessment may become invalid when an agent receives access to a new tool.
* A retrieval-control assessment may become invalid when a new data source is connected.
* A model assessment may become invalid when the provider deploys a new model version.
* A prompt-security assessment may become invalid after a system-prompt modification.
* A tool-security assessment may become invalid when an API, plugin, or execution capability changes.

The model draws from:

* NIST SP 800-137 — Information Security Continuous Monitoring
* Continuous Controls Monitoring
* EU AI Act Article 72 — Post-market monitoring
* SOC 2 distinctions between design effectiveness and operating effectiveness

These concepts are adapted to AI and agentic controls.

### Hybrid invalidation model

Evidence remains valid only until the first of two conditions occurs:

1. Its maximum validity period expires.
2. An invalidating event occurs.

This combines:

* A time-to-live backstop
* Event-driven invalidation

The first condition to occur invalidates or degrades the evidence.

### AI-BOM evidence envelope

The proposed model uses a versioned assurance envelope, referred to as an **AI-BOM**, covering five principal axes:

1. Model
2. Retrieval data
3. Prompts
4. Tools
5. Permissions

A significant change becomes a measurable difference between two known system states.

Each axis should have:

* A known version or state
* A change detector
* An accountable owner
* Associated control evidence
* Defined invalidation rules

### Attested versus observed evidence

Evidence is classified into two principal types:

* **Attested evidence**: a person or organization declares that a control exists or operates as intended.
* **Observed evidence**: the control’s operation is independently demonstrated through logs, tests, technical observations, monitoring, or other objective records.

Observed evidence carries more assurance weight than a signed attestation.

An attestation-only control should therefore be represented as **attested**, not **verified**.

### Staleness and scoring

Evidence staleness should not always produce an immediate binary pass or fail.

Instead, staleness may progressively reduce the assurance score according to:

* Evidence age
* Control criticality
* System changes
* Evidence type
* Monitoring coverage
* Known invalidating events

Returning an invalidated control to a valid state requires an explicit human **re-service decision**.

The control must not silently return to a compliant state merely because new evidence has been uploaded.

### Living assurance register

The resulting assurance dashboard becomes a living control register containing, at minimum:

* Control identifier
* Control objective
* Current status
* Evidence type
* Evidence reference
* Evidence owner
* Last validation date
* Maximum validity period
* Next review date
* Triggering or invalidating event
* Current system version
* Re-service decision
* Decision owner
* Decision date

## Framework categories

The repository is intended to grow across several complementary categories.

### Verification frameworks

Resources that translate security requirements into auditable controls, questions, evidence, and implementation criteria.

### Governance frameworks

Models for defining accountability, decision rights, oversight, risk acceptance, escalation, and executive reporting for AI systems.

### Agentic-security frameworks

Resources addressing AI systems capable of using tools, modifying plans, accessing external systems, coordinating actions, or operating with partial autonomy.

### Assurance frameworks

Models for determining whether controls are not only designed but also implemented and operating effectively.

### Continuous-monitoring frameworks

Approaches for monitoring control validity as models, prompts, data, tools, permissions, infrastructure, and providers change.

### Cross-framework mappings

Typed mappings between security controls, regulatory obligations, implementation evidence, and supporting measures.

### Maturity and assessment models

Methods for evaluating progression from informal or undocumented practices to measured, controlled, and continuously improved AI security processes.

## Standards and frameworks referenced

Current resources reference or build upon:

* OWASP Artificial Intelligence Security Verification Standard 1.0.1-dev
* NIST SP 800-137 — Information Security Continuous Monitoring
* NIST Cybersecurity Framework 2.0
* EU AI Act, including Article 72
* SOC 2 design effectiveness and operating effectiveness concepts
* ISO/IEC 27001:2022
* NIS2
* HIPAA
* ANSSI guidance and security frameworks

Additional standards and frameworks may be incorporated as the repository evolves.

## Intended audience

This repository is intended for:

* AI security engineers
* Cybersecurity architects
* AI governance teams
* Internal and external auditors
* Risk and compliance teams
* CISOs and security leadership
* Model-risk teams
* AI product owners
* Red teams
* Assurance professionals
* Researchers working on AI and agentic-system security

## Status of the resources

Unless explicitly stated otherwise, resources in this repository are:

* Practitioner-oriented interpretations
* Audit and implementation aids
* Cross-framework integration work
* Design proposals submitted for community review
* Educational and research resources

They are not certifications.

They do not replace the official standards, regulations, or authoritative source documents.

They do not imply endorsement by OWASP, NIST, ISO, the European Union, ANSSI, or any other referenced organization.

## License and attribution

The OWASP AISVS requirement texts are the property of the OWASP Foundation and its contributors and are licensed under CC BY-SA 4.0.

Official source:

`https://github.com/OWASP/AISVS`

The following elements constitute the authoring and integration layer added in this repository:

* Audit questions
* Expected evidence
* Response criteria
* Cross-framework mappings
* Mapping relationship types
* Evidence Freshness model
* AI-BOM assurance envelope
* Evidence invalidation logic
* Continuous-monitoring concepts
* Audit and assurance presentation

These additions do not imply endorsement by the OWASP Foundation and do not constitute an official OWASP crosswalk.

Unless otherwise specified, documents in this repository are shared for review and educational use under CC BY-SA 4.0.

See `LICENSE`.

## Important notes

The **Evidence Freshness** annex is a design proposal presented for community review.

It is:

* Not a certification
* Not an official standard
* Not part of the OWASP AISVS standard
* Not an official OWASP publication
* Not an official EU AI Act compliance methodology

Its purpose is to explore how continuous assurance, evidence validity, system-state versioning, and event-driven control reassessment can be applied to AI and agentic systems.

## Contributions and review

Constructive review is welcome, particularly regarding:

* Control wording
* Auditability
* Evidence expectations
* Cross-framework relationships
* AI-specific invalidation events
* Agentic-system risks
* Assurance scoring
* Evidence freshness
* Continuous monitoring
* Regulatory traceability
* Practical implementation experience

The long-term objective is to maintain an open repository of practical, traceable, and reviewable **AI security frameworks** rather than a single static compliance document.
