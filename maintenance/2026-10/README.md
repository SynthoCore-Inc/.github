# October 2026 Gold Standard Maintenance (STAGED, NOT VALIDATED)

**Status: DRAFT / INACTIVE.** Branch: `maintenance/2026-10-gold-standard`. Nothing here authorizes a production rollout.

This repository's 0 workflow definitions were copied from `main` and staged for qualification at:

- `backup/workflows/`: preserved original workflow text fetched from the active branch (one file per original).
- `candidate/workflows/`: proposed replacements targeting current GitHub Action majors and Node 26; **NOT** yet tested for compatibility.
- `.github/dependabot.yml` on this staging branch: proposed update bot configuration; activates only if merged into the default branch.

A staging workflow is NOT an active GitHub workflow. DO NOT move/copy these files under `.github/workflows` until a runner canary has passed and CI plus deployment smoke tests succeed. Preserve the prior `.github/workflows` until after sign-off. Review live `main` again immediately before promotion because sources may have changed while staging.

**Promotion order:** runner/OS baseline and rollback image → actionlint and zizmor → canary runners → workflow action-major upgrades on Node 24 → Node 26 dual-matrix tests → controlled deployment smoke → feature promotion → compare evidence and approve.

**Rollback:** revert the actual workflow promotion commit on default branch, restore backed-up runner VM (only if needed), return app Node to 24, restore previous runner group capacity, and confirm checks/deploy health before reopening automations.

Full maintenance instructions and hand-operated steps are in the private SynthoCore standards maintenance runbook and the separately supplied report.
