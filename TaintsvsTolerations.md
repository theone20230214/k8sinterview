⚙️ **Kubernetes / Scheduling – Taints vs Tolerations**
**Question:**
What are taints and tolerations in Kubernetes, and how do they work together to control pod scheduling?

---

### ✅ Look for:

* **Taints** are applied to **nodes** to prevent Pods from being scheduled unless they **tolerate** the taint.
* **Tolerations** are added to **Pods** to allow them to be scheduled on nodes with matching taints.
* Taints use a **key/value/effect** format (e.g., `key=value:NoSchedule`).
* Common use cases: **dedicated nodes**, **workload isolation**, or **special hardware**.
* Taints **repel** Pods; tolerations **allow** exceptions.

---

### Score | Criteria

| Score | Description                                                                                          |
| ----- | ---------------------------------------------------------------------------------------------------- |
| 5     | Clearly explains what taints and tolerations are, their relationship, syntax, and practical use      |
| 3     | Understands basic function but lacks depth in use cases or technical syntax                          |
| 1     | Confuses the concepts or misstates their directionality (e.g., taints on Pods, tolerations on nodes) |

---

### Full Score Answer (Score: 5)

In Kubernetes, **taints** are applied to nodes to **repel Pods** that do not explicitly tolerate them. A taint consists of a key, value, and an effect (`NoSchedule`, `PreferNoSchedule`, or `NoExecute`). It essentially marks the node as unsuitable for most Pods.

**Tolerations** are applied to Pods to **allow them to be scheduled** on tainted nodes. They match the taint’s key/value/effect and act as an exception.

For example, if a node is tainted with `dedicated=database:NoSchedule`, only Pods with a matching toleration will be allowed to run on that node. This mechanism is useful for **dedicating nodes to specific workloads**, **preventing resource contention**, or isolating **GPU-intensive tasks**.

---

### ⚠️ Medium Answer (Score: 3)

Taints are labels on nodes that block Pods, and tolerations let Pods go on those nodes. You use them when you want some Pods on specific nodes.

> **Analysis:** Grasped the general idea but lacks precise explanation of the taint/toleration mechanism and effect types.

---

### ❌ Poor Answer (Score: 1)

Taints are when a Pod is not working right. Tolerations help fix taints.

> **Analysis:** Completely wrong understanding—confuses taints with health issues or errors, not scheduling constraints.