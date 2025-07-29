⚙️ **Kubernetes / Scheduling & Availability – Liveness vs Readiness Probes**
**Question:**
What is the difference between a liveness probe and a readiness probe in Kubernetes? Why are both important?

---

### ✅ Look for:

* **Liveness Probe** checks if the container is still running; if it fails, Kubernetes restarts the container.
* **Readiness Probe** checks if the container is ready to serve traffic; if it fails, the Pod is temporarily removed from Service endpoints.
* **Liveness** is about container health, **Readiness** is about availability.
* Using both helps ensure reliability and smooth rollouts without dropping traffic.

---

### Score | Criteria

| Score | Description                                                                                                        |
| ----- | ------------------------------------------------------------------------------------------------------------------ |
| 5     | Clearly explains both probes, their purposes, and practical use in maintaining application health and availability |
| 3     | Understands the basic function of each probe, but lacks depth or clarity                                           |
| 1     | Confuses the two probes or explains only one incorrectly                                                           |

---

### Full Score Answer (Score: 5)

A **Liveness Probe** is used by Kubernetes to check if a container is still alive. If the probe fails, Kubernetes assumes the container is stuck and restarts it. This ensures that unhealthy containers do not continue running in a broken state.

A **Readiness Probe** checks if the container is ready to handle requests. If it fails, the Pod is removed from the list of endpoints of the associated Service, so it won't receive any traffic until it's ready again.

These two probes serve different purposes. Liveness ensures self-healing, while Readiness ensures traffic only reaches healthy instances. Both are important for maintaining high availability and smooth rolling updates.

---

### ⚠️ Medium Answer (Score: 3)

Liveness Probe restarts the container when it's not working. Readiness Probe checks if the container is ready for traffic. They are useful for keeping the app healthy.

> **Analysis:** Has the general idea, but doesn't distinguish clearly between "running" and "ready", nor explains implications of failure or integration with Services.

---

### ❌ Poor Answer (Score: 1)

They both check if the app is running. Kubernetes restarts it when probes fail.

> **Analysis:** Confuses probe purposes, ignores the difference between restarting and removing from service endpoints. Incomplete understanding.
