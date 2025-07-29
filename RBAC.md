⚙️ **Kubernetes / Security – Role-Based Access Control (RBAC)**
**Question:**
What is Role-Based Access Control (RBAC) in Kubernetes, and how does it work?

---

### ✅ Look for:

* RBAC controls user and service account permissions within the cluster.
* It uses **Roles** and **ClusterRoles** to define permissions.
* **RoleBindings** and **ClusterRoleBindings** assign Roles to users or groups.
* Roles are namespace-scoped; ClusterRoles are cluster-scoped.
* RBAC enforces the principle of least privilege for security.

---

### Score | Criteria

| Score | Description                                                                          |
| ----- | ------------------------------------------------------------------------------------ |
| 5     | Clearly explains RBAC components, scope differences, and how permissions are granted |
| 3     | Understands basic concept but lacks detail on bindings or scope                      |
| 1     | Confuses RBAC with other auth methods or incomplete explanation                      |

---

### Full Score Answer (Score: 5)

Role-Based Access Control (RBAC) in Kubernetes is a method to regulate access to cluster resources based on the roles assigned to users or service accounts. It defines **Roles** (namespace-scoped) and **ClusterRoles** (cluster-scoped) that list allowed actions on resources.

Users, groups, or service accounts are granted these permissions via **RoleBindings** (for namespace Roles) or **ClusterRoleBindings** (for ClusterRoles). This system enables fine-grained control over who can do what within the cluster, helping enforce security best practices like the principle of least privilege.

---

### ⚠️ Medium Answer (Score: 3)

RBAC controls who can do what in Kubernetes by assigning roles to users. Roles define permissions, and bindings connect users to roles.

> **Analysis:** Has the main idea but misses details on scope and types of roles/bindings.

---

### ❌ Poor Answer (Score: 1)

RBAC is how Kubernetes logs user actions. It tracks what users do.

> **Analysis:** Confuses RBAC with auditing; does not explain access control.