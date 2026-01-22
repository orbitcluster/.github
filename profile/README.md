<div align="center">

![OrbitCluster Banner](orbitcluster_banner.png)

# OrbitCluster CI/CD Platform

### Accelerating Software Delivery with Automated Excellence

[![CI/CD](https://img.shields.io/badge/Platform-CI%2FCD-blue?style=for-the-badge&logo=github-actions)](https://github.com/orbitcluster)
[![Security](https://img.shields.io/badge/Security-First-red?style=for-the-badge&logo=shield)](https://github.com/orbitcluster)
[![Quality](https://img.shields.io/badge/Code-Quality-green?style=for-the-badge&logo=sonarqube)](https://github.com/orbitcluster)

</div>

---

## 📈 Platform Activity

<div align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=orbitcluster&theme=react-dark&hide_border=true&area=true" alt="OrbitCluster Activity Graph" />
</div>

---

## 🚀 Overview

Welcome to **OrbitCluster**, the centralized CI/CD platform designed to streamline, secure, and accelerate your software delivery lifecycle.

Our mission is to provide a robust, standardized, and automated ecosystem that empowers development teams to focus on building features while we handle the heavy lifting of:

- **Building & Testing** across multiple languages.
- **Security Enforcement** with secret scanning and vulnerability checks.
- **Quality Assurance** via automated code analysis.
- **Seamless Deployment** to target environments.

## 🛠️ Architecture

Our platform leverages a modular design where optimized **Templates** consume powerful **Shared Workflows** to deliver consistent results.

```mermaid
flowchart TD
    subgraph Users
        PyUser[Python Team]
        DotnetUser[.NET Team]
    end

    PyUser --> PyTmpl[oc-python-template]
    DotnetUser --> DotnetTmpl[oc-dotnet-template]

    PyTmpl --> PyRepo[App Repository]
    DotnetTmpl --> DotnetRepo[App Repository]

    PyRepo --> PyWF[oc-cicd-python-workflow]
    DotnetRepo --> DotnetWF[oc-cicd-dotnet-workflow]

    subgraph "🛡️ Shared Security & CI Pipelines"
        SecretWF[Secret Scanning]
        SastWF[SAST Analysis]
        SonarWF[SonarQube Quality]
        DockerWF[Docker Build]
        ReleaseWF[Release Management]
    end

    PyWF --> SecretWF & SastWF & SonarWF & DockerWF & ReleaseWF
    DotnetWF --> SecretWF & SastWF & SonarWF & DockerWF & ReleaseWF

    classDef users fill:#1565c0,color:#ffffff,stroke:#0d47a1,stroke-width:1px;
    classDef templates fill:#2e7d32,color:#ffffff,stroke:#1b5e20,stroke-width:1px;
    classDef repos fill:#ef6c00,color:#ffffff,stroke:#e65100,stroke-width:1px;
    classDef workflows fill:#6a1b9a,color:#ffffff,stroke:#4a148c,stroke-width:1px;

    class PyUser,DotnetUser users;
    class PyTmpl,DotnetTmpl templates;
    class PyRepo,DotnetRepo repos;
    class PyWF,DotnetWF,SecretWF,SastWF,SonarWF,DockerWF,ReleaseWF workflows;
```

## ☁️ OrbitCluster EKS Platform

Beyond CI/CD, we provide a comprehensive **EKS Platform** built on a **Hub and Spoke** architecture to manage Kubernetes workloads at scale.

### Core Components

- **EKS**: Managed Kubernetes for container orchestration.
- **Istio**: Service mesh for traffic management, security, and observability.
- **ArgoCD**: GitOps continuous delivery tool.

### Hub & Spoke Architecture

We utilize a centralized management plane (Hub) to control workload clusters (Spokes), ensuring isolation and scalability.

```mermaid
graph TD
    Hub[Hub EKS Cluster]
    Spoke1[Spoke EKS Cluster 1]
    Spoke2[Spoke EKS Cluster 2]
    Spoke3[Spoke EKS Cluster 3]

    Hub -->|Manages| Spoke1
    Hub -->|Manages| Spoke2
    Hub -->|Manages| Spoke3

    classDef hub fill:#d32f2f,color:#ffffff,stroke:#b71c1c,stroke-width:1px;
    classDef spoke fill:#1976d2,color:#ffffff,stroke:#0d47a1,stroke-width:1px;

    class Hub hub;
    class Spoke1,Spoke2,Spoke3 spoke;
```

### Key Principles

- **Centralization**: Core components managed from a single Hub.
- **Scalability**: Auto-scaling clusters to handle dynamic loads.
- **Security & Compliance**: Strict access controls and encrypted traffic.
- **Infrastructure as Code**: Fully provisioned via Terraform & Terragrunt.

## 🧩 Key Features

| Feature                      | Tooling                                                                        | Description                                                  |
| ---------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------ |
| **Secret Scanning**          | <img src="https://img.shields.io/badge/Gitleaks-MediumPurple" valign="middle"> | Prevents credentials and secrets from entering the codebase. |
| **Code Quality**             | <img src="https://img.shields.io/badge/SonarQube-4E9BCD" valign="middle">      | Automated static analysis to maintain high code standards.   |
| **Vulnerability Assessment** | <img src="https://img.shields.io/badge/Trivy-00A000" valign="middle">          | Scans containers and dependencies for known CVEs.            |
| **Standardized Builds**      | <img src="https://img.shields.io/badge/Docker-2496ED" valign="middle">         | Unified build processes for consistency across all apps.     |

## 📚 Repository Index

### 📦 Application Templates

Start your new project with best practices built-in:

- **[🐍 oc-python-template](https://github.com/orbitcluster/oc-python-template)** - For Python applications.
- **[🔷 oc-dotnet-template](https://github.com/orbitcluster/oc-dotnet-template)** - For .NET Core applications.

### 🔄 Language Workflows

Orchestration for specific language ecosystems:

- **[oc-cicd-python-workflow](https://github.com/orbitcluster/oc-cicd-python-workflow)**
- **[oc-cicd-dotnet-workflow](https://github.com/orbitcluster/oc-cicd-dotnet-workflow)**

### ⚡ Shared Core Actions

The building blocks of our CI/CD pipeline:

- **[🔒 oc-cicd-secretscanner-workflow](https://github.com/orbitcluster/oc-cicd-secretscanner-workflow)**
- **[🔍 oc-cicd-sast-workflow](https://github.com/orbitcluster/oc-cicd-sast-workflow)**
- **[📊 oc-cicd-sonarscan-workflow](https://github.com/orbitcluster/oc-cicd-sonarscan-workflow)**
- **[🐳 oc-cicd-docker-build-workflow](https://github.com/orbitcluster/oc-cicd-docker-build-workflow)**
- **[🚀 oc-cicd-release-workflow](https://github.com/orbitcluster/oc-cicd-release-workflow)**

---

<div align="center">
  <sub>Built with ❤️ by the OrbitCluster Platform Engineering Team</sub>
</div>
