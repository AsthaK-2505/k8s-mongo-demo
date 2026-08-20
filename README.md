# Kubernetes MongoDB Deployment

A hands-on Kubernetes project demonstrating how multiple Kubernetes components work together to deploy a MongoDB and Mongo Express application.

## Kubernetes Components Used

- Pod
- Deployment
- Service
- ConfigMap
- Secret
- Minikube
- kubectl

## Architecture

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

## Technologies

- Kubernetes
- Minikube
- Docker
- MongoDB
- Mongo Express
- YAML

## Project Structure

- `mongo.yaml` - MongoDB Deployment
- `mongo-service.yaml` - Internal MongoDB Service
- `mongo-express.yaml` - Mongo Express Deployment
- `mongo-express-service.yaml` - External Mongo Express Service
- `mongo-configmap.yaml` - MongoDB configuration
- `mongo-secret.example.yaml` - Example Kubernetes Secret
- `.gitignore` - Prevents sensitive files from being committed

## Running the Project

Start Minikube:

```bash
minikube start
