# Kubernetes Deployment Exercises (for KillerKoda)

These exercises are designed to test your knowledge and provide hands-on experience with Kubernetes Deployments on **KillerKoda**. Each question includes a task that you should complete in a Kubernetes environment.

## Exercises

---

### 1. **Basic Deployment (Namespace: `default`)**

**Objective:**  
Create a basic deployment in the `default` namespace.

**Task:**  
Create a `Deployment` resource named `nginx-deployment` that:
- Uses the `nginx` image (`nginx:1.19.10`).
- Has 3 replicas.
- Exposes port `80` inside the container.

---

### 2. **Rolling Update Deployment (Namespace: `devnamespace`)**

**Objective:**  
Create a deployment with a rolling update strategy.

**Task:**  
Create a `Deployment` in the `devnamespace` namespace.
- Use the `nginx` image (`nginx:1.19.10`).
- Set the `strategy` to `RollingUpdate` with a `maxSurge` of 1 and `maxUnavailable` of 1.
- Roll out an update to the `nginx:1.20.0` image.

---

### 3. **Deployment with Environment Variables (Namespace: `testnamespace`)**

**Objective:**  
Create a deployment with environment variables.

**Task:**  
Create a `Deployment` in the `testnamespace` namespace.
- Use the `nginx` image.
- Set an environment variable `APP_ENV=production` in the pod.

---

### 4. **Resource Requests and Limits (Namespace: `prodnamespace`)**

**Objective:**  
Create a deployment with resource requests and limits.

**Task:**  
Create a `Deployment` in the `prodnamespace` namespace.
- Use the `nginx` image (`nginx:1.19.10`).
- Set the CPU request to `500m` and memory request to `512Mi`.
- Set the CPU limit to `1` and memory limit to `1Gi`.

---

### 5. **Readiness and Liveness Probes (Namespace: `backendnamespace`)**

**Objective:**  
Create a deployment with readiness and liveness probes.

**Task:**  
Create a `Deployment` in the `backendnamespace` namespace.
- Use the `nginx` image (`nginx:1.19.10`).
- Add a **readiness probe** and a **liveness probe**:
  - Readiness probe checks `/healthz` on port `80`.
  - Liveness probe checks `/healthz` on port `80`.

---

### 6. **Multiple Containers in a Single Pod (Namespace: `appnamespace`)**

**Objective:**  
Create a deployment with multiple containers in a pod.

**Task:**  
Create a `Deployment` in the `appnamespace` namespace with two containers:
- The first container uses the `nginx` image and exposes port `80`.
- The second container uses the `redis` image and exposes port `6379`.

---

### 7. **Custom Labels and Annotations (Namespace: `stagingnamespace`)**

**Objective:**  
Create a deployment with custom labels and annotations.

**Task:**  
Create a `Deployment` in the `stagingnamespace` namespace.
- Use the `nginx` image (`nginx:1.19.10`).
- Add a label `app=nginx` and `env=staging`.
- Add an annotation `description="Staging Deployment for NGINX"`.

---

### 8. **Image Pull Secrets (Namespace: `secretnamespace`)**

**Objective:**  
Create a deployment that uses image pull secrets.

**Task:**  
Create a `Deployment` in the `secretnamespace` namespace.
- Use a private Docker registry for the `nginx` image.
- Create an image pull secret to access the private registry.

---

### 9. **Affinity and Anti-Affinity Rules (Namespace: `prodnamespace`)**

**Objective:**  
Create a deployment with affinity and anti-affinity rules.

**Task:**  
Create a `Deployment` in the `prodnamespace` namespace.
- Use the `nginx` image (`nginx:1.19.10`).
- Set the `affinity` to schedule pods on nodes labeled `role=frontend`.
- Set the `anti-affinity` to prevent pods from being scheduled on the same node with pods labeled `app=nginx`.

---

### 10. **Horizontal Pod Autoscaler (Namespace: `scalenamespace`)**

**Objective:**  
Create a deployment with Horizontal Pod Autoscaler (HPA).

**Task:**  
Create a `Deployment` in the `scalenamespace` namespace.
- Use the `nginx` image (`nginx:1.19.10`).
- Set the number of replicas to 2.
- Create a **Horizontal Pod Autoscaler** that scales based on CPU usage:
  - Min replicas: 2
  - Max replicas: 10
  - Target CPU utilization: 50%

---

### 11. **Init Containers (Namespace: `devnamespace`)**

**Objective:**  
Create a deployment with init containers.

**Task:**  
Create a `Deployment` in the `devnamespace` namespace with:
- An init container running `echo "Initializing..."`.
- A main container using the `nginx` image.

---

These exercises should be executed on **KillerKoda** step by step. Each task is designed to provide hands-on experience with various deployment configurations and features in Kubernetes. By following these instructions, you will become proficient in creating and managing Kubernetes deployments.
