# 🧪 CKAD Exam-Style Exercises: Jobs and CronJobs

This repository contains a comprehensive set of CKAD-style (and slightly harder) exercises for Jobs and CronJobs. Questions cover all important specs, edge cases, and best practices from the official Kubernetes documentation.

---

## 🔧 Job & CronJob Challenges

---

### 🔹 Q1: Basic Job with Restart Policy and Deadline

Create a Job in a namespace of your choice that runs a `busybox` container with restart policy set to `Never`.  
It should print `Running batch job` using `echo`, and have an `activeDeadlineSeconds` of **10 seconds**.  
Make sure the container name is `echoer`.

---

### 🔹 Q2: Parallel Job with Specific Completions and Retries

Create a parallel Job named `multi-runner` that uses `alpine` and prints a hostname using `echo`.  
Set `completions` to **3**, `parallelism` to **2**, and `backoffLimit` to **1**.  
Namespace: `batch-exec`.

---

### 🔹 Q3: Cron Job that Runs Every 2 Minutes

Create a CronJob that runs **every 2 minutes** using the `busybox` image and restart policy `Never`.  
It should use a test command like `echo Hello from CronJob`.  
Set:

- `successfulJobsHistoryLimit: 2`  
- `failedJobsHistoryLimit: 3`  
- `activeDeadlineSeconds: 8`

Also, **manually create a Job** from the CronJob’s template to validate its configuration.

---

### 🔹 Q4: Suspended CronJob with Timezone

Create a suspended CronJob scheduled to run every day at 6 AM UTC using the `alpine` image.  
It should execute `date` and print the current time.  
Set the timezone to **Asia/Kolkata**.  
Name: `time-printer`.

---

### 🔹 Q5: CronJob with Cleanup Logic

Build a CronJob that runs daily and removes temporary files. Use `busybox` and command `rm -rf /tmp/old/*`.  
Set:

- `successfulJobsHistoryLimit: 1`  
- `failedJobsHistoryLimit: 0`  
- `ttlSecondsAfterFinished: 300`

Namespace: `maintenance`.

---

### 🔹 Q6: Fix the CronJob YAML

```yaml
apiVersion: batch/v1
kind: CronJob
metadata:
  name: wrong-cron
spec:
  schedule: "* * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: runner
            image: busybox
            command: ["echo", "missing something"]
          restartPolicy: Always
