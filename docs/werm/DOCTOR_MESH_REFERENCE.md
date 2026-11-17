# WERM Doctor Mesh Reference

WERM remains the single recovery authority. OpenHuman is a diagnostic/reference participant only until the WERM golden baseline is sealed.

Current canonical WERM source:
- Windows: `C:\AI\JoshuaArchitecture\vNext\02-Core\WERM`
- WSL link: `~/.openclaw/workspace-phoenixrise/nvidia-werm`
- Doctor source: `C:\AI\JoshuaArchitecture\vNext\02-Core\WERM\doctor`
- Live Doctor runtime: `~/.local/share/werm-doctor`

Recovery mesh:
- WERM Doctor: central diagnosis, incident queue, bounded repair, validation.
- WERM Doctor Escalator: unresolved-incident handoff to the canonical owner agent, then post-repair Doctor validation.
- Phoenix Continuity Supervisor / Checkpoint Resume / Repair Collector: runtime continuity, resume, and shared repair knowledge.
- Hermes: offline/local repair worker.
- Phoenix Rise / Aura owner gateway: canonical privileged owner execution path.
- Phoenix capability bridge: allowlisted local execution bridge.
- ODS diagnostics: optional resource-fabric/inference diagnostics when ODS is active.
- OpenClaw Doctor: gateway/channel/state diagnostics used as evidence.
- OpenHuman Memory Doctor: future memory-pipeline diagnostic candidate after explicit integration acceptance.

Self-healing behavior:
1. Required services are started automatically only when inactive.
2. Required recovery timers are automatically re-enabled and started.
3. WERM Doctor and WERM Doctor Escalator monitor one another's schedulers.
4. A transient health miss never causes an automatic restart of an already-running owner gateway.
5. Missing/corrupt WERM assets become unresolved incidents instead of being silently recreated.
6. Unknown incidents enter the shared repair queue, are evidence-enriched with OpenClaw Doctor output, and are escalated through the existing owner/WERM path.
7. Repairs are cooldown/rate-limited, then revalidated by WERM Doctor.
8. User data, credentials, canonical versions, checkpoints, and dirty Git state must be preserved.
9. Multiple agents may contribute diagnosis/evidence, but canonical mutation authority stays centralized.
10. `production_enabled=false` remains mandatory for OpenHuman until WERM golden acceptance.

Verified November 17, 2026 acceptance:
- WERM Doctor source/runtime hashes match.
- Required current services are active.
- Required recovery timers are enabled + active.
- Deliberately disabled repair-collector timer was automatically restored.
- Deliberately disabled escalator timer was automatically restored by WERM Doctor.
- Deliberately disabled WERM Doctor timer was automatically restored by escalator.
- Final WERM Doctor result: healthy, zero unresolved incidents.
- Escalator idle state: no unresolved incidents.
