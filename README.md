# Platform Portal (Backstage)

Internal developer platform — service catalog for the DevOps portfolio.

## Run locally (Docker) — experimental

The Janus showcase image requires full plugin configuration; the compose stack may crash-loop without additional setup. The **catalog YAML** in `catalog/` is the stable deliverable for Backstage registration.

```powershell
cd "D:\New folder"
.\scripts\run-backstage-local.ps1   # postgres + backstage on :7007
```

If the backstage container keeps restarting, use the catalog files directly or scaffold with `npx @backstage/create-app@latest`.

## Catalog structure

```
catalog-info.yaml          # Root location
catalog/all-repos.yaml     # Aggregates component YAMLs
catalog/components/*.yaml  # One file per repo
```

## Stop

```powershell
cd platform-portal
docker compose down
```

## Phase 2

- [x] Portfolio catalog YAML for all repos
- [x] Docker Compose local Backstage
- [ ] TechDocs per repo (optional)
- [ ] Deploy Backstage to DOKS (after `bootstrap-doks.ps1`)
