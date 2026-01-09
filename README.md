
🚀 StreamingApp -- Orchestration and Scaling of a MERN Application
==================================================================

📌 Project Overview
-------------------

This project demonstrates **end-to-end orchestration, containerization, CI/CD automation, monitoring, and scaling** of a **MERN (MongoDB, Express, React, Node.js) application** using modern **DevOps and Cloud-Native practices**.

The application is containerized with Docker, automated using Jenkins CI pipelines, deployed on **Amazon EKS**, managed via **Helm**, and monitored using Kubernetes-native tooling.

---

🧰 Tech Stack
-------------

| Category           | Tools / Services               |
| ------------------ | ------------------------------ |
| Version Control    | Git, GitHub                    |
| Containerization   | Docker                         |
| CI/CD              | Jenkins                        |
| Container Registry | Amazon ECR                     |
| Orchestration      | Amazon EKS                     |
| Package Manager    | Helm                           |
| Monitoring         | Kubernetes Metrics Server, HPA |
| Logging            | kubectl logs                   |
| Cloud              | AWS (eu-west-2)                |

---

🗂️ Repository Structure
-------------------------

<pre class="overflow-visible!" data-start="1910" data-end="2115"><div class="contain-inline-size rounded-2xl relative bg-token-sidebar-surface-primary"><div class="sticky top-9"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>
  .
├── backend/                  # Node.js backend service
│   ├── Dockerfile
│   ├── index.js
│   └── package.json
│
├── frontend/                 # React frontend
│   ├── Dockerfile
│   └── nginx.conf
│
├── helm/
│   └── streamingapp/
│       ├── Chart.yaml
│       ├── values.yaml
│       └── templates/
│           ├── backend-deployment.yaml
│           ├── backend-service.yaml
│           ├── frontend-deployment.yaml
│           └── frontend-service.yaml
│
├── Jenkinsfile               # CI pipeline
└── README.md

</span></span></code></div></div></pre>
---

🔄 Project Workflow
-------------------

### 1️⃣ Version Control

- Forked the original repository
- Maintained a `dev` branch
- Synced upstream changes when required

---

🏗️ Architecture Diagram – Orchestration & Scaling

<img width="1816" height="568" alt="diagram-export-10-01-2026-00_53_45" src="https://github.com/user-attachments/assets/91060668-790b-4e60-999c-5fb3b0af888d" />

---

### 2️⃣ Containerization

- **Backend**: Node.js service containerized using `node:18-alpine`
- **Frontend**: React app built and served via `nginx` using multi-stage Docker builds
- Images tested locally before cloud deployment

---

### 3️⃣ AWS Setup

- AWS CLI configured
- Region standardized to **`eu-west-2`**
- Amazon ECR repositories created for frontend and backend

---

### 4️⃣ CI/CD with Jenkins

- Jenkins installed and configured
- Pipeline stages:

  - Git checkout
  - Docker build
  - ECR authentication
  - Docker image push
- Jenkinsfile committed to repository
- Successful green pipeline execution

---

### 5️⃣ Kubernetes Deployment (EKS)

- EKS cluster created using `eksctl`
- Managed node group with auto-scaling capability
- `kubectl` configured automatically

---

### 6️⃣ Helm-Based Deployment

- Helm chart created for application
- Separate Kubernetes Deployments and Services for frontend and backend
- Frontend exposed using **LoadBalancer**
- Backend exposed using **ClusterIP**

---

### 7️⃣ Monitoring & Scaling

- **metrics-server** enabled
- Resource metrics verified using:

  `kubectl top nodes kubectl top pods`
- **Horizontal Pod Autoscaler (HPA)** configured for backend:

  `kubectl autoscale deployment streaming-backend --cpu-percent=50 --min=2 --max=5`
- Manual scaling validated using:

  `kubectl scale deployment streaming-backend --replicas=4`

---

### 8️⃣ Logging

- Application logs accessed using:

  `kubectl logs deployment/streaming-backend kubectl logs deployment/streaming-frontend`
- Logging strategy documented for production readiness

---

🌐 Application Access
---------------------

- Frontend exposed via AWS LoadBalancer
- External URL obtained using:

  `kubectl get svc streaming-frontend`
- Application accessible via browser

---

📸 Evidence & Validation
------------------------

The following were captured for validation and submission:

- Jenkins pipeline success
- EKS node readiness
- Running pods and services
- Application UI access
- Metrics and HPA output

<img width="1366" height="699" alt="Screenshot from 2026-01-05 22-07-35" src="https://github.com/user-attachments/assets/3ba8ce8c-0fb9-430f-9f4c-78ae2737df5a" />

<img width="1366" height="699" alt="Screenshot from 2026-01-06 01-21-26" src="https://github.com/user-attachments/assets/4a0f33d0-5175-48c2-a6f7-be2fe39cfa36" />

<img width="1366" height="699" alt="Screenshot from 2026-01-06 01-25-04" src="https://github.com/user-attachments/assets/a30aba95-6a96-4087-851a-378c29655800" />

<img width="1366" height="699" alt="Screenshot from 2026-01-06 01-26-36" src="https://github.com/user-attachments/assets/c46a734f-3c71-45e7-9888-72a656a0a011" />

<img width="1366" height="699" alt="Screenshot from 2026-01-06 01-31-28" src="https://github.com/user-attachments/assets/32f1824c-84e2-48ae-b046-79ba7397930e" />

<img width="1366" height="499" alt="Screenshot from 2026-01-10 01-07-39" src="https://github.com/user-attachments/assets/a0b77929-fa54-4dda-b16f-a3c0d9be06cc" />

<img width="1366" height="499" alt="Screenshot from 2026-01-10 01-09-21" src="https://github.com/user-attachments/assets/1671ad18-5265-492f-971d-48e7079d3856" />

<img width="1366" height="499" alt="Screenshot from 2026-01-10 01-10-06" src="https://github.com/user-attachments/assets/7fd5c371-1a7d-4578-b015-cdb0dd2287e8" />

<img width="1366" height="499" alt="Screenshot from 2026-01-10 01-11-06" src="https://github.com/user-attachments/assets/d1a73916-1bcf-414c-b943-76cf7ecd9486" />

<img width="1365" height="700" alt="Screenshot from 2026-01-10 01-35-09" src="https://github.com/user-attachments/assets/30d0f6b7-b776-4908-97cd-f58802782e9c" />

<img width="1365" height="378" alt="Screenshot from 2026-01-10 01-35-54" src="https://github.com/user-attachments/assets/9584c7f9-42e0-46f7-a8dd-7b638db9e0c6" />

---

<img width="1365" height="700" alt="Screenshot from 2026-01-10 01-24-02" src="https://github.com/user-attachments/assets/bcbb4193-9d54-4eab-8e91-d88b9013e696" />

---





---

🧠 Key Learnings
----------------

- Practical CI/CD pipeline implementation
- Cloud-native deployment using Kubernetes
- Helm chart structuring and troubleshooting
- Debugging real-world DevOps issues
- Monitoring and scaling containerized workloads

---

✅ Project Status
-----------------

✔ Fully deployed
✔ Scalable
✔ Monitored
✔ CI/CD automated
✔ Ready for submission

---

### 🏆 Final Note

This project demonstrates a **complete DevOps lifecycle** --- from source code to scalable production deployment --- following industry best practices.
which demonstrates CI/CD automation, container orchestration, and scalable deployment of a MERN application using Jenkins, Docker, Amazon ECR, Amazon EKS, Helm, and Kubernetes autoscaling.

---

📌 Author
---------

**DEEPIKA NARENDRAN**
Project: StreamingApp -- Orchestration and Scaling of a MERN Application
GitHub: @JoinDeeHub
