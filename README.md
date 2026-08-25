# ☸️ Kubernetes Notes

> A structured collection of **Kubernetes learning notes**, concepts, architecture, and core components — written in a simple and easy-to-understand way.

---

## 📚 About This Repository

This repository contains my notes while learning **Kubernetes (K8s)**.

The goal is to understand Kubernetes from the fundamentals and build a strong foundation around how Kubernetes works internally, how its components communicate, and how applications are managed inside a cluster.

The notes focus on **understanding the concepts**, rather than simply memorizing commands.

---

## 🗂️ Contents

### 🏗️ Kubernetes Fundamentals

* [Kubernetes Architecture](./kubernetes-architecture.md)
* Control Plane
* Data Plane / Worker Nodes
* Kubernetes Components
* Pods
* Deployments
* Services
* Networking
* Storage
* ConfigMaps
* Secrets

> More topics will be added as I continue learning Kubernetes.

---

## 🏛️ Kubernetes Architecture

The Kubernetes cluster is broadly divided into two major parts:

```text
                    Kubernetes Cluster
                           │
             ┌─────────────┴─────────────┐
             │                           │
        Control Plane                Data Plane
        (Management)                (Worker Nodes)
             │                           │
      ┌──────┼────────┐           ┌──────┼────────┐
      │      │        │           │      │        │
    API    etcd   Scheduler    Kubelet  kube-   Runtime
   Server         Controller            proxy
                  Manager                 │
                                         ▼
                                        Pods
```

### Control Plane

The Control Plane manages the Kubernetes cluster and maintains its desired state.

| Component                    | Responsibility                               |
| ---------------------------- | -------------------------------------------- |
| **API Server**               | Central communication point of Kubernetes    |
| **etcd**                     | Stores cluster state and configuration       |
| **Scheduler**                | Decides which node should run a Pod          |
| **Controller Manager**       | Maintains the desired state                  |
| **Cloud Controller Manager** | Connects Kubernetes with cloud-provider APIs |

### Data Plane

Worker nodes are responsible for running the actual applications.

| Component             | Responsibility                    |
| --------------------- | --------------------------------- |
| **Kubelet**           | Ensures assigned Pods are running |
| **Kube-proxy**        | Helps provide Service networking  |
| **Container Runtime** | Actually runs the containers      |

---

## 🧠 Core Kubernetes Concept

One of the most important ideas in Kubernetes is **Desired State vs Actual State**.

```text
              Desired State
                    │
                    ▼
             Kubernetes Control
                    │
                    ▼
              Actual State
                    │
                    ▼
              Reconciliation
                    │
                    └──────► Desired State
```

Kubernetes continuously works to make the **actual state of the cluster match the desired state**.

This reconciliation model is fundamental to understanding how Kubernetes works.

---

## 🎯 Learning Goals

This repository is intended to help me:

* Understand Kubernetes architecture.
* Understand the role of each Kubernetes component.
* Understand how Control Plane and Worker Nodes communicate.
* Understand how Pods are scheduled and executed.
* Understand Kubernetes networking and services.
* Understand how Kubernetes maintains the desired state.
* Build a strong foundation before moving into advanced Kubernetes concepts.

---

## 🛠️ Tools & Technologies

* ☸️ Kubernetes
* 🐳 Containers
* 🐧 Linux
* 🔧 kubectl
* 📦 containerd / CRI-O
* 🌐 Kubernetes Networking
* ☁️ Cloud Infrastructure

---

## 📈 Learning Path

```text
Kubernetes Basics
       │
       ▼
Architecture
       │
       ▼
Pods
       │
       ▼
Deployments
       │
       ▼
Services
       │
       ▼
Networking
       │
       ▼
Storage
       │
       ▼
ConfigMaps & Secrets
       │
       ▼
Ingress
       │
       ▼
Advanced Kubernetes
       │
       ▼
Production & Cloud
```

---

## 📁 Repository Structure

```text
kubernetes-notes/
│
├── README.md
│
├── kubernetes-architecture.md
│
└── ...
```

More notes will be added as the learning progresses.

---

## 🚀 Progress

* [x] Kubernetes Architecture
* [ ] Pods
* [ ] Deployments
* [ ] ReplicaSets
* [ ] Services
* [ ] Namespaces
* [ ] ConfigMaps
* [ ] Secrets
* [ ] Volumes
* [ ] Networking
* [ ] Ingress
* [ ] StatefulSets
* [ ] DaemonSets
* [ ] Jobs & CronJobs
* [ ] Helm
* [ ] RBAC
* [ ] Kubernetes Security
* [ ] Production Kubernetes

---

## 📖 Philosophy

> **Don't just memorize Kubernetes commands. Understand what Kubernetes is doing behind the command.**

The objective of these notes is to build an understanding of the **architecture, components, communication, and internal working of Kubernetes**.

---

## ⭐ Repository

If these notes help you understand Kubernetes, feel free to ⭐ the repository.

**Learning Kubernetes — one concept at a time. ☸️**
