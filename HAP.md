⚙️ **Kubernetes / Autoscaling – Horizontal Pod Autoscaler (HPA)**
**Question:**
What is a Horizontal Pod Autoscaler (HPA) in Kubernetes? How does it work, and what metrics can it use to scale pods?

---

### ✅ Look for:

* HPA automatically adjusts the number of pod replicas based on observed metrics.
* It commonly uses CPU utilization but can use custom or external metrics.
* HPA continuously monitors metrics and scales pods up or down to meet demand.
* It helps maintain application performance and resource efficiency.

---

### Score | Criteria

| Score | Description                                                                            |
| ----- | -------------------------------------------------------------------------------------- |
| 5     | Clearly explains HPA functionality, supported metrics, and typical use cases           |
| 3     | Understands the basic concept of autoscaling but lacks details on metrics or operation |
| 1     | Provides inaccurate or incomplete explanation of HPA                                   |

---

### Full Score Answer (Score: 5)

The **Horizontal Pod Autoscaler (HPA)** in Kubernetes automatically scales the number of pod replicas in a Deployment, ReplicaSet, or StatefulSet based on observed metrics such as CPU utilization or custom metrics. It periodically queries the metrics API and adjusts the replicas to keep the metric near the target value.

For example, if the average CPU utilization across pods exceeds a threshold, HPA will increase the number of pods to handle load; if it falls below, it will scale down. HPA supports built-in metrics like CPU and memory, as well as custom or external metrics for more complex scaling scenarios.

HPA helps maintain application performance during load spikes and saves resources during idle times.

---

### ⚠️ Medium Answer (Score: 3)

HPA changes the number of pods based on CPU usage. It makes sure the app can handle traffic by scaling pods up or down.

> **Analysis:** Captures main idea but doesn’t mention custom metrics or how scaling decisions are made.

---

### ❌ Poor Answer (Score: 1)

HPA automatically makes pods faster or slower. It’s like a performance booster.

> **Analysis:** Misunderstands autoscaling as changing pod speed, not quantity; lacks understanding of how HPA works.
