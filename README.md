# Kubernetes MongoDB Deployment

A hands-on Kubernetes project demonstrating how multiple Kubernetes components work together to deploy MongoDB and Mongo Express on a local Minikube cluster.

## 🚀 Overview

This project deploys:

- **MongoDB** — database
- **Mongo Express** — web-based MongoDB interface

The application demonstrates the use of Kubernetes **Deployments, Pods, Services, ConfigMaps, and Secrets**.

## 🏗️ Architecture

Browser
   |
   v
Mongo Express Service
   |
   v
Mongo Express Pod
   |
   v
MongoDB Service
   |
   v
MongoDB Pod


### Kubernetes Components

| Component  | Purpose                                                            |
| ---------- | ------------------------------------------------------------------ |
| Deployment | Manages MongoDB and Mongo Express Pods                             |
| Pod        | Runs the application containers                                    |
| Service    | Enables communication between components and exposes Mongo Express |
| ConfigMap  | Stores MongoDB connection configuration                            |
| Secret     | Stores MongoDB credentials                                         |
| Minikube   | Runs the Kubernetes cluster locally                                |

## 🛠️ Technologies

* Kubernetes
* Minikube
* kubectl
* Docker
* MongoDB
* Mongo Express
* YAML

## 📁 Project Structure


k8s-mongo-demo/
├── .gitignore
├── README.md
├── mongo.yaml
├── mongo-configmap.yaml
├── mongo-express.yaml
└── mongo-secret.example.yaml


### Files

* `mongo.yaml` — MongoDB Deployment and Service
* `mongo-express.yaml` — Mongo Express Deployment and Service
* `mongo-configmap.yaml` — MongoDB connection configuration
* `mongo-secret.example.yaml` — Secret template
* `.gitignore` — Prevents the real Secret file from being committed

## ⚙️ Setup

### Prerequisites

Install:

* Docker
* Minikube
* kubectl
* Git

### 1. Start Minikube


minikube start

### 2. Create the Secret

Create a local `mongo-secret.yaml` based on `mongo-secret.example.yaml`.

Then:


kubectl apply -f mongo-secret.yaml

> The real `mongo-secret.yaml` is excluded from GitHub because it contains credentials.

### 3. Create the ConfigMap


kubectl apply -f mongo-configmap.yaml


### 4. Deploy MongoDB


kubectl apply -f mongo.yaml


### 5. Deploy Mongo Express


kubectl apply -f mongo-express.yaml


### 6. Verify the Deployment


kubectl get pods


Expected:

mongo-express-xxxxx             1/1   Running
mongodb-deployment-xxxxx        1/1   Running


Check Services:


kubectl get services


### 7. Access Mongo Express


minikube service mongo-express-service


This opens Mongo Express in the browser.

## 🔐 Security

The actual `mongo-secret.yaml` is excluded using `.gitignore`.

Kubernetes Secrets are Base64 encoded by default, which is **not encryption**. Real credentials should never be committed to a public repository.

