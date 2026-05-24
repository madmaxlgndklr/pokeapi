# sync-logs

This branch tracks the automated upstream sync of this repository with [PokeAPI/pokeapi](https://github.com/PokeAPI/pokeapi).

## Cron Job

A scheduled Claude Code remote agent runs daily at **03:00 EDT (07:00 UTC)**. Each run:

1. Mirror-clones the upstream PokeAPI repository
2. Pushes all branches and tags to this repo (the `sync-logs` branch is preserved)
3. Appends a timestamped entry to `sync.log`

The full routine configuration is stored in [`cron-job.json`](./cron-job.json).  
Manage the routine at: https://claude.ai/code/routines/trig_01TGK8efUBKyYt9tdVpxGRoA

## Logs

Each run appends an entry to [`sync.log`](./sync.log):

```
--- SYNC yyyy-mm-dd HH:MM:SS UTC ---
Status: success | failed
Branches updated: N
Tags updated: N
Notes: ...
```

## Files

| File | Description |
|------|-------------|
| `sync.log` | Timestamped log of every sync run |
| `cron-job.json` | Claude Code routine configuration |
