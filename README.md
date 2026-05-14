# Kubernetes Service Account Management Guide

This repository contains a comprehensive guide on managing **Service Accounts (SA)** in Kubernetes. It focuses on how to provide secure identities for automated processes (machines) to interact with the Kube-API server.

## 📋 Key Topics Covered

* **Service vs. User Accounts**: Understanding the distinction between identities for machines (e.g., Prometheus, Jenkins) and identities for humans (Admins/Developers).


* **Pod Integration**: How to assign a specific identity to a workload using the `serviceAccountName` parameter within the Pod specification.


* **Token Lifecycle**: Deep dive into the "Projected Volume" mechanism where Kubernetes automatically mounts short-lived tokens into Pods.


* **Security Hardening**:
* Instructions on disabling the `automountServiceAccountToken` to follow the principle of least privilege.


* Managing token expiration and availability relative to the Pod's lifecycle.




* **Manual Token Management**: Generating manual Bearer tokens via CLI (`kubectl create token`) with custom durations for external API authentication.



## 🚀 Quick Reference

| Action | Command/Parameter |
| --- | --- |
| **Create SA** | `kubectl create serviceaccount <name>`<br> |
| **Link to Pod** | `serviceAccountName: <name>`<br> |
| **Manual Token** | `kubectl create token <name> --duration 2h`<br> |
| **Disable Auto-mount** | `automountServiceAccountToken: false`<br> |

## 🛡️ Best Practices Included

The guide emphasizes creating unique Service Accounts for each workload and using RBAC to limit their power within the cluster.

---

*This documentation is designed for DevOps engineers and SREs looking to harden their Kubernetes identity management.*
