# Agent Supervision Canary

This repository is a synthetic public surface for the E2 read-mostly supervision experiment. It contains no production or private project state.

## Trial rule

Do not treat this repository as canonical project truth. It exists only to measure whether a persistent supervisor can detect and classify bounded canary events.

Canary types will be injected only after the supervisor is confirmed active:

1. `late-review` — an independent review result appears after an implementation report.
2. `ci-failure` — a check/result becomes explicitly failing.
3. `stale-state` — a pointer is deliberately contradicted by a newer source.
4. `decision-required` — an issue explicitly requires user/integrator judgment.

Each injected event will record its creation timestamp and expected classification. Detection latency is measured from that timestamp to the first traceable supervisor alert.

## Pass boundary

- no seeded material canary is missed;
- alerts remain source-traceable;
- no autonomous mutation is needed;
- noise/duplicate alerts remain low;
- no second project-state database is introduced.

## Control

Existing Chat/PCN attention mechanisms remain active as fallback and are measured separately. Dot or another supervisor is evidence-producing transport, not project authority.
