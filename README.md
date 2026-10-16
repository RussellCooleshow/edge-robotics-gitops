# Edge Robotics GitOps Infrastructure (K3s + ArgoCD on NVIDIA Jetson)

Production-grade, resource-constrained GitOps architecture for autonomous edge robotics running on NVIDIA Jetson Nano (`aarch64`, L4T Kernel 4.9, 4GB RAM).

## Key Engineering Highlights
- **Hardened K3s Control Plane**: Tuned for `cgroup v1` (L4T 4.9-tegra), running native `containerd` without Docker daemon overhead or bloated default ingress (`traefik` disabled).
- **Lightweight Pull-Based GitOps**: Custom-tuned **ArgoCD** Helm profile with non-essential controllers (`dex`, `notifications`, `applicationset`) disabled to preserve edge RAM for AI workloads.
- **Zero-Touch Reconciliation**: Self-healing workloads managed strictly via Git with enforced memory/CPU `resources.limits`.
