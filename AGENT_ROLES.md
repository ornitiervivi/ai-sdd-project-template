# AGENT_ROLES.md

## Objective

Define specialized simulated subagent roles for the SDD harness. These roles are operating lenses that the AI agent must apply according to task scope, even when the execution environment does not provide real parallel subagents.

## Mandatory role orchestration

Before implementing or changing documentation, the agent must:

1. Identify which roles are relevant to the task.
2. State or record the selected roles in the working plan when the task is non-trivial.
3. Execute each selected role's responsibilities in the order that reduces risk.
4. Use the smallest sufficient set of roles.
5. Escalate to blocking questions when any selected role identifies ambiguity that affects requirements, architecture, data, security, UX, cost, operations, validation, or compatibility.
6. Keep this repository generic and avoid implementing product-specific behavior in the template.

When real subagents are unavailable, the agent must simulate them explicitly by reviewing the task from each selected role's perspective. When real subagents are available, delegation may be used only when permitted by the execution environment and should still follow the responsibilities below.

## Default orchestration sequence

For feature or product work in a derived project, use this default sequence unless the task clearly requires a smaller flow:

1. Product Analyst
2. Solution Architect
3. Relevant implementation roles
4. Security Reviewer
5. QA/Test Engineer
6. DevOps Engineer when build, deployment, runtime, or operational validation is affected
7. Code Reviewer
8. SDD Scribe

For template-only changes, use Product Analyst, Solution Architect, QA/Test Engineer, Code Reviewer, and SDD Scribe at minimum when applicable.

## Roles

### Product Analyst

Focuses on requirements, scope, blocking questions, and acceptance criteria.

Responsibilities:

- Understand user intent, stakeholders, constraints, and explicit non-goals.
- Identify missing or conflicting requirements.
- Define or refine acceptance criteria before implementation.
- Prevent invented business requirements.
- Confirm that the task does not implement product behavior when the repository is still a template.

Outputs:

- Clarified scope.
- Blocking questions when needed.
- Acceptance criteria or documented gaps.

### Solution Architect

Focuses on architecture, boundaries, integrations, trade-offs, and risks.

Responsibilities:

- Define system boundaries and separation of responsibilities.
- Check compatibility with `ARCHITECTURE.md` and `.compatibility/` files.
- Identify integration, scalability, maintainability, and migration risks.
- Record meaningful architectural decisions in `DECISIONS.md`.
- Keep the template generic unless a derived project has approved requirements.

Outputs:

- Architecture approach.
- Risks and mitigations.
- Decision records when relevant.

### Backend Engineer

Focuses on backend implementation according to the selected stack.

Responsibilities:

- Implement domain, application, infrastructure, and interface layers as appropriate.
- Keep controllers and adapters thin.
- Validate inputs at boundaries and protect domain invariants.
- Follow stack compatibility rules such as `.compatibility/java-spring.md` when applicable.
- Add tests proportional to risk, including required coverage for business rules.

Outputs:

- Backend changes.
- Backend tests and validation notes.

### Frontend/Mobile Engineer

Focuses on web, mobile, panels, UI flows, and UX.

Responsibilities:

- Implement accessible, responsive, and testable UI components.
- Separate UI state, remote state, and presentation rules.
- Cover loading, empty, error, and success states.
- Avoid heavy visual dependencies without justification.
- Preserve frontend compatibility and documented UX contracts.

Outputs:

- Frontend or mobile changes.
- UX and accessibility validation notes.

### Database Engineer

Focuses on data modeling, migrations, indexes, consistency, and retention.

Responsibilities:

- Model data from use cases and invariants.
- Create small, versioned, reversible migrations when possible.
- Define indexes from real query patterns.
- Evaluate consistency, isolation, locking, volume, retention, backup, and rollback.
- Document data decisions and migration risks.

Outputs:

- Data model and migration changes.
- Consistency and rollback notes.

### AI/Voice Engineer

Focuses on voice, transcription, parsing, AI interpretation, and human confirmation.

Responsibilities:

- Define voice and transcription boundaries, confidence thresholds, and fallback paths.
- Separate AI-generated interpretation from deterministic business rules.
- Require human confirmation for ambiguous or high-impact AI/voice actions.
- Protect sensitive audio, transcripts, prompts, and derived data.
- Document model, provider, latency, cost, evaluation, and safety constraints when applicable.

Outputs:

- AI/voice flow design or implementation.
- Human-confirmation and evaluation notes.

### Security Reviewer

Focuses on authentication, authorization, sensitive data, abuse prevention, and secure defaults.

Responsibilities:

- Review authentication, authorization, auditability, and least privilege.
- Identify sensitive data exposure in storage, logs, telemetry, prompts, and UI.
- Check input validation, output encoding, rate limits, abuse paths, and dependency risk.
- Consult `.compatibility/security.md` and `.skills/security/SKILL.md` for sensitive tasks.
- Record residual security risks when they cannot be fully mitigated.

Outputs:

- Security findings.
- Required mitigations or documented residual risks.

### DevOps Engineer

Focuses on build, Docker, environments, runtime configuration, and operational validation.

Responsibilities:

- Keep builds and validations reproducible.
- Protect secrets and environment-specific configuration.
- Maintain Docker, CI/CD, deployment, and rollback concerns when applicable.
- Ensure operational commands are documented in `README.md` or `VALIDATION.md`.
- Consider observability, cost, and failure modes.

Outputs:

- DevOps changes.
- Operational validation notes.

### QA/Test Engineer

Focuses on test strategy, coverage, regression risk, and validation evidence.

Responsibilities:

- Define tests from requirements, risks, and acceptance criteria.
- Ensure unit, integration, end-to-end, accessibility, security, or migration tests are considered as applicable.
- Verify coverage requirements, especially business-rule coverage in Java/Spring projects.
- Record validation commands, limitations, and residual risks.
- Prevent unvalidated changes from being presented as fully verified.

Outputs:

- Test plan or test changes.
- Validation results and limitations.

### Code Reviewer

Focuses on quality, regressions, maintainability, compatibility, and final readiness.

Responsibilities:

- Review against `CODE_REVIEW.md`.
- Confirm scope is minimal and documentation is updated.
- Check naming, complexity, error handling, compatibility, and unintended changes.
- Confirm security and testing concerns were addressed or documented.
- Request rework when acceptance criteria are not met.

Outputs:

- Review findings.
- Approval notes or required fixes.

### SDD Scribe

Focuses on living documentation and traceability.

Responsibilities:

- Update `PROJECT_CONTEXT.md`, `SPEC.md`, `DECISIONS.md`, `TASKS.md`, `PLAN.md`, `BUGS.md`, and `LESSONS_LEARNED.md` when relevant.
- Keep requirement, decision, task, implementation, test, and validation traceability current.
- Record gaps, assumptions, risks, defects, and lessons learned.
- Preserve generic template language unless a derived project explicitly defines product-specific content.
- Avoid documentation drift after implementation or review changes.

Outputs:

- Updated SDD documentation.
- Traceability notes and documented gaps.
