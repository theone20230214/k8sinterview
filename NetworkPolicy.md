⚙️ **Kubernetes / Networking – NetworkPolicy**
**Question:**
What is a NetworkPolicy in Kubernetes, and how does it control traffic between Pods?

---

### ✅ Look for:

* **NetworkPolicy** defines rules for **ingress** (incoming) and **egress** (outgoing) traffic between Pods.
* It uses **labels and selectors** to target Pods and control communication.
* By default, **all traffic is allowed**; once a policy is applied, **only permitted traffic is allowed**.
* NetworkPolicies enhance **security** and **isolation** within a cluster.
* Requires a **network plugin** that supports NetworkPolicy (e.g., Calico, Cilium).

---

### Score | Criteria

| Score | Description                                                                                        |
| ----- | -------------------------------------------------------------------------------------------------- |
| 5     | Clearly explains what NetworkPolicy is, how it works, its defaults, and when it’s useful           |
| 3     | Understands general purpose but lacks details on selectors, default behavior, or plugin dependency |
| 1     | Misunderstands what NetworkPolicy does or confuses it with other security mechanisms               |

---

### Full Score Answer (Score: 5)

A **NetworkPolicy** in Kubernetes is a resource used to control traffic flow at the IP/network level between Pods. It defines **rules for allowed ingress and egress traffic** using Pod labels and namespace selectors.

By default, all Pods can communicate with each other. Once a NetworkPolicy is applied to a Pod, that Pod **only accepts traffic explicitly allowed by the policy**. This allows teams to isolate services, enforce zero-trust networking, and limit blast radius in the case of compromise.

NetworkPolicies are enforced by the underlying network plugin, so a CNI (like Calico or Cilium) that supports them must be installed for them to take effect.

---

### ⚠️ Medium Answer (Score: 3)

NetworkPolicy is used to restrict traffic between Pods. You can allow or block connections to certain Pods. It helps with security.

> **Analysis:** Captures the high-level concept but lacks specifics on default behavior, selectors, or plugin support.

---

### ❌ Poor Answer (Score: 1)

NetworkPolicy is for managing internet access for the cluster. It blocks users from accessing Kubernetes.

> **Analysis:** Completely misinterprets the concept; confuses Pod-to-Pod networking control with user authentication or firewalling.