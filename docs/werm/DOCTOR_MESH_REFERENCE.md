# WERM Doctor Mesh Reference

WERM remains the single recovery authority. OpenHuman is a diagnostic/reference participant only until the WERM golden baseline is sealed.

Recovery mesh:
- WERM Doctor: central diagnosis, incident queue, bounded repair, validation.
- Phoenix Guardian / Continuity / Failsafe: runtime recovery.
- Hermes: offline/local repair planning and repair-KB consumer.
- Phoenix Rise: privileged allowlisted execution.
- Aura1 + WERM: orchestration, alternate-provider reasoning, unknown-failure research escalation.
- ODS Doctor: resource-fabric/inference diagnostics.
- OpenClaw Doctor/Triage: gateway/channel diagnostics and repair evidence.
- OpenHuman Memory Doctor: future memory-pipeline diagnostics after explicit integration acceptance.

Rules:
1. Diagnose broadly; mutate only through bounded allowlisted repair actions.
2. Never let multiple agents independently rewrite canonical configuration.
3. Never restart a healthy/running Rise or Aura1 gateway because of one transient health miss.
4. Preserve dirty/user Git state; never auto-reset it.
5. Rate-limit repairs, validate every action, record evidence, and keep rollback paths.
6. Unknown failures go to the shared repair queue/knowledge base and escalate to Aura1/WERM research rather than to the user for routine debugging.
7. `production_enabled=false` remains mandatory for OpenHuman until WERM golden acceptance.
