# Analysis Workspace Template

Copy this directory to start a new project or target analysis workspace.

Recommended command from a parent directory:

```bash
cp -a analysis-template NEW_ANALYSIS_NAME
```

After copying:

1. Replace placeholders in `governance/RoEAIFile.md`.
2. Fill `scope/current-scope.md`.
3. Add exact allowed hosts to `scope/allowed-hosts.txt`.
4. Record passive recon in `recon/`.
5. Track findings in `findings/`.
6. Keep `handoff/recon_handoff.md` current after every session.

No live testing should happen until scope confirmation, request budget, payload class, and stop conditions are recorded.
