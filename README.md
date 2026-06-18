# Platform Portal (Backstage)

Internal developer platform — service catalog for the DevOps portfolio.

## Run locally (Docker)

```powershell
cd "D:\New folder"
.\scripts\run-backstage-local.ps1
```

Open http://localhost:7007 — guest auth in development mode.

Catalog loads all 10 portfolio components from `catalog/`.

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
