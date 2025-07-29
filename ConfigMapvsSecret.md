⚙️ **Kubernetes / Configuration Management – ConfigMap vs Secret**
**Question:**
What are the differences between a ConfigMap and a Secret in Kubernetes? When would you use each?

---

### ✅ Look for:

* **ConfigMap** stores **non-sensitive** configuration data like app settings, environment variables.
* **Secret** stores **sensitive** data like passwords, tokens, and SSH keys.
* Both can be used as **environment variables**, **volume mounts**, or injected into Pods.
* **Secret is base64-encoded** and stored more securely (with stricter access controls).
* Use **ConfigMap** for general configs; use **Secret** for credentials or sensitive info.

---

### Score | Criteria

| Score | Description                                                                                |
| ----- | ------------------------------------------------------------------------------------------ |
| 5     | Accurately explains purpose, differences in use case, storage, and access control          |
| 3     | Understands basic distinction between sensitive and non-sensitive data, but misses details |
| 1     | Confuses the two or explains only one with incorrect usage                                 |

---

### Full Score Answer (Score: 5)

A **ConfigMap** is used to store non-sensitive configuration data such as key-value pairs, environment variables, command-line arguments, and config files. It's useful for externalizing application settings from your container images.

A **Secret** is used to store sensitive data like passwords, access tokens, or TLS certificates. Although it's also stored in etcd like ConfigMaps, Kubernetes treats it differently by encoding the data in **base64**, and applying **RBAC restrictions** to limit access.

Both ConfigMaps and Secrets can be mounted as files, exposed as environment variables, or used by other resources. The key difference lies in **security**—Secrets are intended for confidential data and should be used when information must be protected.

---

### ⚠️ Medium Answer (Score: 3)

ConfigMap is for app configs, Secret is for passwords. You use Secrets when the data is sensitive. Both can be mounted into Pods.

> **Analysis:** Covers the core idea, but lacks explanation of how they're stored or what base64 means in this context.

---

### ❌ Poor Answer (Score: 1)

They both store config data. I usually just use ConfigMap for everything.

> **Analysis:** Misunderstands use cases and security implications of Secrets. Using ConfigMap for sensitive data is a common mistake.