# Kubernetes Network Policy Exercises

This repository contains a series of exercises to practice and enhance your skills with Kubernetes Network Policies. These exercises cover various use cases including `AND/OR` logic, pod selectors, namespace selectors, IP blocks, and more advanced configurations.

## Exercises

---

### 1. **Basic AND Logic with Pod Selectors (Namespace: `prodnamespace`)**
**Question:**  
Write a **Network Policy** for the `prodnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods only from pods that meet both of the following conditions:
- The pod must be labeled with `role:api`.
- The pod must be labeled with `env:prod`.
  
Additionally, the policy should allow traffic only on **TCP port 80**.

---

### 2. **Basic OR Logic with Pod Selectors (Namespace: `stagingnamespace`)**
**Question:**  
Create a **Network Policy** for `stagingnamespace` that allows **ingress traffic** to the `app:frontend` pods from:
- Pods labeled with `role:backend` **or**
- Pods labeled with `role:api`.

The policy should only allow traffic on **TCP port 443**.

---

### 3. **Combining AND and OR Logic with Pod Selectors (Namespace: `devnamespace`)**
**Question:**  
Write a **Network Policy** for the `devnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods from:
- Pods with label `role:client` in `testnamespace` **and** pods in the `devnamespace` namespace with label `role:service`, **or**
- Pods with label `role:api` in the `devnamespace` namespace.

The policy should allow traffic only on **TCP port 8080**.

---

### 4. **Complex AND Logic with Namespace and Pod Selectors (Namespace: `goodnamespace`)**
**Question:**  
Create a **Network Policy** for the `goodnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods from:
- Pods in the `backendnamespace` labeled with `role:frontend`, **and**
- Pods in the `goodnamespace` labeled with `role:api`.

The policy should allow traffic on **TCP port 443**.

---

### 5. **Combining Pod Selector and Namespace Selector with OR Logic (Namespace: `appnamespace`)**
**Question:**  
Write a **Network Policy** for the `appnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods from:
- Pods labeled with `role:api` in `appnamespace` **or**
- Pods in the `othernamespace` with label `app:service`.

The policy should allow traffic only on **TCP port 80**.

---

### 6. **Using IPBlock and Pod Selectors with AND Logic (Namespace: `prodnamespace`)**
**Question:**  
Write a **Network Policy** for the `prodnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods if the traffic is:
- From any pod labeled with `role:api`, **and**
- The source IP must be in the range `192.168.1.0/24`.

The policy should allow traffic only on **TCP port 443**.

---

### 7. **Combining Namespace Selector and IP Block with OR Logic (Namespace: `testnamespace`)**
**Question:**  
Create a **Network Policy** for `testnamespace` that allows **ingress traffic** to the `app:frontend` pods from:
- Any pod in the `othernamespace` namespace labeled with `role:api`, **or**
- Any IP in the range `172.16.0.0/16`.

The policy should allow traffic only on **TCP port 80**.

---

### 8. **Complex OR Logic with Multiple Pod Selectors (Namespace: `stagingnamespace`)**
**Question:**  
Write a **Network Policy** for the `stagingnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods from:
- Pods labeled with `role:api` **or**
- Pods in the `backendnamespace` with label `role:service` **or**
- Any IP in the range `192.168.1.0/24`.

The policy should allow traffic on **TCP port 3306**.

---

### 9. **Using IPBlock with AND Logic for Egress (Namespace: `devnamespace`)**
**Question:**  
Write a **Network Policy** for `devnamespace` that allows **egress traffic** from the `app:frontend` pods to:
- IP address block `10.0.0.0/8`, **and**
- Pods labeled `role:database` in the `prodnamespace`.

The policy should allow traffic only on **TCP port 5432**.

---

### 10. **Combining Egress and Ingress with OR Logic (Namespace: `goodnamespace`)**
**Question:**  
Create a **Network Policy** for `goodnamespace` that allows:
- **Ingress traffic** from any pod in `othernamespace` labeled `role:client`, **or**
- **Egress traffic** to any pod in `goodnamespace` labeled `role:service`.

The policy should allow traffic on **TCP port 443**.

---

### 11. **Default Deny with OR Logic for Ingress (Namespace: `prodnamespace`)**
**Question:**  
Create a **default-deny Network Policy** in `prodnamespace` that denies all **ingress traffic** to the `app:frontend` pods except for:
- Pods labeled with `role:api`, **or**
- Pods in the `stagingnamespace` labeled `role:service`.

The policy should allow traffic only on **TCP port 8080**.

---

### 12. **Default Deny with AND Logic for Egress (Namespace: `testnamespace`)**
**Question:**  
Write a **default-deny policy** for `testnamespace` that denies all **egress traffic** from the `app:frontend` pods except for:
- Traffic to any pod labeled `role:db` in `prodnamespace`, **and**
- Traffic to IP block `192.168.0.0/24`.

The policy should allow traffic only on **TCP port 3306**.

---

### 13. **AND/OR Logic with Multiple Criteria (Namespace: `devnamespace`)**
**Question:**  
Write a **Network Policy** that allows **ingress traffic** to the `app:frontend` pods only if the traffic:
- Comes from pods labeled `role:api`, **or**
- Comes from `testnamespace` labeled `role:frontend`, **and**
- The traffic must come from IP block `192.168.1.0/24` **or** `10.0.0.0/8`.

The policy should allow traffic only on **TCP port 80**.

---

### 14. **IPBlock and Pod Selectors with AND/OR Logic (Namespace: `stagingnamespace`)**
**Question:**  
Create a **Network Policy** for the `stagingnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods if:
- The source is either any pod labeled `role:backend`, **or**
- The source is an IP block `172.16.0.0/12` **and**
- The source pod is labeled `role:service`.

The policy should allow traffic only on **TCP port 443**.

---

### 15. **Combining Pod Selector and IPBlock with AND/OR (Namespace: `goodnamespace`)**
**Question:**  
Write a **Network Policy** for the `goodnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods only if:
- The source pod is labeled `role:backend`, **and**
- The source IP is `192.168.1.0/24`, **or**
- The source pod is labeled `role:client`.

The policy should allow traffic only on **TCP port 80**.

---

### 16. **IP Block with Exclusion and Pod Selector (Namespace: `appnamespace`)**
**Question:**  
Write a **Network Policy** for the `appnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods from:
- Any IP in `192.168.1.0/24` **except**
- IP `192.168.1.10/32`, **and**
- Pods labeled `role:api`.

The policy should allow traffic on **TCP port 8080**.

---

### 17. **Complex AND/OR Logic with Pod and Namespace Selectors (Namespace: `prodnamespace`)**
**Question:**  
Create a **Network Policy** for `prodnamespace` that allows **ingress traffic** to `app:frontend` pods in `prodnamespace` from:
- Pods in `testnamespace` labeled `role:frontend`, **and**
- Pods in `prodnamespace` labeled `role:api`, **or**
- Pods in `stagingnamespace` labeled `role:backend`.

The policy should allow traffic on **TCP port 443**.

---

### 18. **Combining IP Block with Multiple Pod Selectors (Namespace: `stagingnamespace`)**
**Question:**  
Write a **Network Policy** for the `stagingnamespace` namespace that allows **ingress traffic** to `app:frontend` pods from:
- IP block `172.16.0.0/12`, **or**
- Pods in `othernamespace` labeled `role:api`, **and**
- Pods in `stagingnamespace` labeled `role:frontend`.

The policy should allow traffic only on **TCP port 3306**.

---

### 19. **Egress with Pod Selectors and IP Block (Namespace: `testnamespace`)**
**Question:**  
Write a **Network Policy** for `testnamespace` that allows **egress traffic** from the `app:frontend` pods to:
- IP block `10.0.0.0/8`, **or**
- Pods in `prodnamespace` labeled `role:database`, **and**
- Pods in `testnamespace` labeled `role:service`.

The policy should allow traffic on **TCP port 5432**.

---

### 20. **Combining IPBlock, PodSelector, and NamespaceSelector (Namespace: `goodnamespace`)**
**Question:**  
Create a **Network Policy** for the `goodnamespace` namespace that allows **ingress traffic** to the `app:frontend` pods from:
- Pods in `goodnamespace` with label `role:frontend`, **or**
- Pods from `othernamespace` with label `role:api`, **and**
- The source IP must be in the `192.168.1.0/24` block.

The policy should allow traffic on **TCP port 443**.

---

## Conclusion

These exercises cover a wide range of use cases and logic combinations for Kubernetes Network Policies. By completing them, you will gain a deeper understanding of how to define and apply network restrictions in a Kubernetes cluster.
