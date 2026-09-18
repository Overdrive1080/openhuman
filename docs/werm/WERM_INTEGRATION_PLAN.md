# OpenHuman × NVIDIA WERM Integration Plan

Status: DEFERRED / ISOLATED REFERENCE
Authority: NVIDIA WERM remains canonical.

## Goal
Evaluate selected OpenHuman capabilities only after the WERM golden baseline is sealed and regression-tested.

## Candidate capabilities
- persistent/local memory patterns
- context compression / token reduction
- MCP and external integration patterns
- checkpointed agent workflows
- research and recovery patterns

## Explicit non-goals
- Do not replace WERM routing.
- Do not replace Aura1/Super Crew control flow.
- Do not introduce a second authoritative orchestrator.
- Do not modify production WERM before golden-baseline acceptance.
- Do not import secrets, OAuth tokens, or user data during evaluation.

## Acceptance gates
1. WERM golden baseline sealed.
2. OpenHuman dependency/license/security review complete.
3. Each candidate capability benchmarked independently.
4. No regression in WERM routing, fallback, recovery, context bounds, or startup/restart behavior.
5. Rollback path proven before production adoption.

## Integration strategy
Treat OpenHuman as a vendor/reference system. Extract or adapt only capabilities that outperform the existing WERM implementation. Keep WERM as the single source of truth for orchestration, routing, provider policy, validation, fallback, and recovery.
