# Pi-Cluster

My home Kubernetes cluster running on Raspberry Pi, managed with GitOps.

## What I Built

A fully automated GitOps pipeline where pushing to this repo automatically deploys to my cluster:

```
Git Push → Flux CD → Kubernetes → Cloudflare Tunnel → Internet
```

## What I Learned

- **Flux CD** - GitOps operator that watches this repo and syncs changes to the cluster
- **Kustomize** - Base/overlay pattern for managing configs across environments
- **SOPS + Age** - Encrypting secrets so they can be safely stored in Git
- **Cloudflare Tunnels** - Exposing services without opening ports on my home network


## Running Apps

- **Linkding** - Self-hosted bookmark manager
- **Cloudflared** - Tunnel for secure external access

## Useful Commands

```bash
# Check what's deployed
flux get all

# Force a sync
flux reconcile kustomization flux-system --with-source
```
