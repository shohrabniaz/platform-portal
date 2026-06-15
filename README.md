# Platform Portal (Backstage)

Internal developer platform — service catalog for the DevOps portfolio.

## Catalog

All portfolio components are defined under `catalog/` and registered via `catalog-info.yaml`.

| Component | Repo |
|-----------|------|
| devsecops-pipeline | CI/CD security gates |
| terraform-modules | Reusable IaC modules |
| gitops-platform | Argo CD app-of-apps |
| ai-incident-copilot | K8s incident RCA |
| cloud-security-scanner | Azure posture checks |
| finops-guardian | Cost leak detection |
| sentinel-soc-lab | Sentinel KQL rules |

## Run Backstage on kind/DOKS

```powershell
kubectl config use-context kind-gitops-lab   # or DOKS context
.\scripts\install-backstage-local.ps1
kubectl port-forward -n backstage svc/backstage 7007:7007
```

Open http://localhost:7007

## Local GitOps lab

```powershell
.\scripts\bootstrap-gitops-local.ps1 -UseKind
.\scripts\verify-gitops-lab.ps1
```

## Phase 2 status

- [x] Catalog YAML for all 10 portfolio repos
- [x] Helm install script for Backstage
- [ ] Custom software templates (optional)
