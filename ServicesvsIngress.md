⚙️ **Kubernetes / Core Concepts – Services vs Ingress**
**Question:**
What is the difference between a Service and an Ingress in Kubernetes? When would you use each?

---

### ✅ Look for:

* **Service** exposes a set of Pods internally or externally by creating a stable IP and DNS name, supporting different types like ClusterIP, NodePort, and LoadBalancer.
* **Ingress** manages external HTTP/HTTPS traffic routing into the cluster, providing URL-based routing, SSL termination, and virtual hosting.
* Service operates at the TCP/UDP level (L4), while Ingress operates at the HTTP layer (L7).
* Use Service to expose pods internally or externally without advanced routing; use Ingress for advanced traffic routing and managing multiple hostnames or paths.

---

### Score | Criteria

| Score | Description                                                                                                  |
| ----- | ------------------------------------------------------------------------------------------------------------ |
| 5     | Clearly explains both Service and Ingress, their differences, how they work together, and use cases for each |
| 3     | Understands basic concepts and usage but lacks detail on differences or limitations                          |
| 1     | Confuses Service and Ingress or explains only one with errors                                                |

---

### Full Score Answer (Score: 5)

A **Service** in Kubernetes provides a stable endpoint to a set of Pods, abstracting their IPs and allowing communication inside or outside the cluster. It supports several types:

* **ClusterIP** (default) exposes service only inside the cluster,
* **NodePort** exposes on a static port on each node,
* **LoadBalancer** provisions a cloud provider load balancer.

A **Ingress** is a collection of rules that allow inbound connections to reach cluster services, typically managing HTTP and HTTPS traffic. It provides advanced routing features such as host- or path-based routing, SSL termination, and can route traffic to multiple services under the same IP.

You use a **Service** when you want to expose your app internally or externally with simple load balancing and stable endpoints. You use an **Ingress** when you want to consolidate external HTTP(S) traffic under one IP address, apply SSL, and route traffic based on hostname or URL paths.

---

### ⚠️ Medium Answer (Score: 3)

A Service exposes Pods either inside the cluster or to the outside world. An Ingress routes HTTP traffic to different Services based on rules. You use Services for basic access and Ingress when you need to route traffic to multiple apps.

> **Analysis:** Basic understanding of Service and Ingress but missing details on Service types and Ingress features like SSL or path routing.

---

### ❌ Poor Answer (Score: 1)

Service and Ingress are the same thing; both expose apps to the outside. You just use Ingress when Service is not enough.

> **Analysis:** This answer confuses concepts and fails to explain differences or when to use each, showing a lack of understanding.
