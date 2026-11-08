# <p align="center">Huy Nguyen | Senior DevSecOps & Cloud Security Engineer</p>

<p align="center">
  <a href="https://linkedin.com/in/huy8114644"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:contact@huynguyen.security"><img src="https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email" /></a>
  <img src="https://img.shields.io/badge/Location-Vietnam%20%2F%20Remote-blue?style=flat-square&logo=googlemaps&logoColor=white" alt="Location" />
  <img src="https://img.shields.io/badge/Status-Open%20to%20Opportunities-success?style=flat-square" alt="Status" />
</p>

<p align="center">
  <em>Specializing in Zero-Trust Architecture, Shift-Left CI/CD Pipelines, Kubernetes Hardening, Policy-as-Code, and Immutable Infrastructure as Code.</em>
</p>

---

## 🎯 About Me

I am a **Senior DevSecOps & Cloud Security Engineer** with 6+ years of experience bridging the gap between Software Development, Security Engineering, and Cloud Infrastructure. 

My core focus is designing and operating **Automated Security Golden Paths**—enabling engineering teams to ship high-velocity, production-grade cloud workloads without sacrificing compliance, data privacy, or security posture.

- 🛡️ **Shift-Left Security:** Automated SAST (Semgrep), SCA (Trivy), Secret Scanning (Gitleaks), and DAST (OWASP ZAP) with GitHub Security SARIF integration.
- 🔐 **Supply Chain Security:** SLSA Level 3 compliance, SBOM generation (Syft/CycloneDX), and keyless cryptographic container signing (Cosign / Sigstore OIDC).
- ☸️ **Kubernetes Hardening:** Pod Security Standards (PSS Restricted), Kyverno & OPA/Gatekeeper admission control, Cilium/Calico Zero-Trust NetworkPolicies, and Falco eBPF runtime threat detection.
- ☁️ **Cloud Infrastructure as Code:** Terraform / OpenTofu enterprise modules compliant with CIS AWS Foundations Benchmark 3.0, verified via Checkov and tfsec.

---

## 🏛️ Enterprise DevSecOps Architecture (The Golden Path)

```mermaid
flowchart LR
    subgraph Dev ["1. Developer Workstation"]
        A[Code Commit] --> B[Pre-commit Hooks<br/>Gitleaks / TFLint]
    end

    subgraph CI ["2. Shift-Left CI Pipeline (GitHub Actions)"]
        B --> C[SAST: Semgrep]
        C --> D[SCA: Trivy FS]
        D --> E[Hardened Build<br/>Distroless Base]
        E --> F[Container Scan<br/>Trivy Image]
        F --> G[SBOM: Syft]
        G --> H[Sign: Cosign Keyless]
    end

    subgraph Registry ["3. OCI Secure Registry"]
        H --> I[(Container Image +<br/>Signed In-Toto Attestation)]
    end

    subgraph CD ["4. GitOps & Admission Control"]
        I --> J[ArgoCD Sync]
        J --> K[Kyverno / Gatekeeper<br/>Verify Cosign Signature<br/>Enforce Non-Root / ReadOnly]
    end

    subgraph Runtime ["5. Hardened Runtime (Kubernetes)"]
        K --> L[EKS / GKE Pods]
        L --> M[Calico NetworkPolicy<br/>Default Deny + mTLS]
        L --> N[Falco eBPF<br/>Runtime Threat Detection]
        L --> O[Vault Agent Injector<br/>Dynamic Ephemeral Secrets]
    end

    classDef stage fill:#0a192f,stroke:#4fd6a8,stroke-width:1.5px,color:#e6f1ff;
    class Dev,CI,Registry,CD,Runtime stage;
```

---

## 🛠️ DevSecOps Technical Arsenal

| Domain | Tools & Technologies |
|---|---|
| **Cloud Platforms** | AWS (EKS, VPC, KMS, IAM Least-Privilege, GuardDuty, Security Hub), GCP, Multi-Cloud Hybrid |
| **Containers & K8s** | Kubernetes, Docker, Helm 3, ArgoCD (GitOps), Cilium (eBPF CNI), Istio Service Mesh |
| **Infrastructure as Code** | Terraform, OpenTofu, Terragrunt, Ansible, Packer, Infracost |
| **Pipeline Security (Shift-Left)** | Semgrep (Custom rules), Trivy, Gitleaks, TruffleHog, SonarQube, OWASP ZAP |
| **Software Supply Chain** | Cosign (Sigstore OIDC Keyless), Syft, Grype, CycloneDX, SPDX, SLSA Framework |
| **Policy as Code & Admission** | Kyverno, OPA / Gatekeeper, Conftest, Rego |
| **Runtime Security & SIEM** | Falco (eBPF probes), Wazuh, Auditd, AWS CloudTrail, Falcosidekick |
| **Secrets & Identity** | HashiCorp Vault, AWS Secrets Manager, External Secrets Operator, SOPS, SPIFFE/SPIRE |
| **Observability & Telemetry** | Prometheus, Grafana, Loki, OpenTelemetry, Jaeger, Fluent Bit |

---

## 🏆 Featured DevSecOps Repositories

### 1. [enterprise-devsecops-pipeline](https://github.com/huy8114644/enterprise-devsecops-pipeline)
> **Production-grade Reusable DevSecOps Golden Path Pipeline**
- Automated Security Gates: Gitleaks (Secrets) ➔ Semgrep (SAST) ➔ Trivy (SCA) ➔ Distroless Build ➔ Trivy Container Scan ➔ Syft (SBOM) ➔ Cosign Keyless Image Signing ➔ OWASP ZAP (DAST).
- Uploads SARIF alerts natively into GitHub Security tab.
- Scheduled daily CVE vulnerability assessment and automated pull request patching.

### 2. [hardened-k8s-gitops-platform](https://github.com/huy8114644/hardened-k8s-gitops-platform)
> **Zero-Trust Kubernetes Hardening & GitOps Blueprint**
- Kyverno Policy-as-Code enforcing Pod Security Standards (PSS) Restricted: block privileged pods, require read-only root filesystems, drop all capabilities, enforce non-root UID.
- Zero-Trust Calico NetworkPolicies (Default Deny Ingress/Egress, DNS egress allowlist).
- Falco eBPF runtime threat detection rules (shell spawned in pod, sensitive directory tampering).
- HashiCorp Vault Agent Injector configuration for dynamic database credential leasing.

### 3. [terraform-aws-security-baseline](https://github.com/huy8114644/terraform-aws-security-baseline)
> **Enterprise AWS Infrastructure as Code Compliant with CIS Benchmark 3.0**
- Hardened EKS (Private cluster endpoint, envelope encryption with KMS CMK, Bottlerocket nodes).
- Secure VPC (Flow Logs enabled, S3 VPC Gateway Endpoints, isolated database subnets).
- Enforces Checkov, tfsec, and tflint compliance gates in CI with 0 High/Critical violations.

---

## 📊 GitHub Security & Activity Analytics

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=huy8114644&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="Huy's GitHub Stats" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=huy8114644&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" alt="Top Languages" />
</p>

---

<p align="center">
  <sub>Built with security, precision, and automation by <strong>Huy Nguyen</strong> • Updated continuously via DevSecOps CI/CD Automation</sub>
</p>

