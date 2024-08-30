# Kubernate-SpringPetClinic
Spring Petclinic with MySQL on Kubernetes

This repository contains the Kubernetes manifests required to deploy the Spring Petclinic application with a MySQL backend on a Kubernetes cluster.
Table of Contents

    Overview
    Prerequisites
    Kubernetes Components
    Setup Instructions
    Accessing the Application
    Contributing
    License

Overview

The Spring Petclinic application is a sample application designed to demonstrate the capabilities of the Spring Framework. In this deployment, the application is backed by a MySQL database, both of which are managed on a Kubernetes cluster.
Prerequisites

    A running Kubernetes cluster (e.g., Minikube, GKE, EKS, AKS, etc.)
    kubectl CLI tool installed and configured to connect to your Kubernetes cluster.
    Basic knowledge of Kubernetes and Docker.

Kubernetes Components
1. ConfigMap and Secrets

    ConfigMap: Stores the MySQL database URL configuration required by the Spring Petclinic application.
    Secrets: Securely manages sensitive information like MySQL credentials.

2. Deployments

    MySQL Deployment:
        A single replica of a MySQL container, configured with environment variables from Secrets.
        Persistent storage is attached to store the MySQL data.
    Spring Petclinic Deployment:
        Two replicas of the Spring Petclinic application to ensure high availability and load balancing.
        Configured to use the MySQL database backend.

3. Services

    MySQL Service: Exposes the MySQL database on port 3306 via a LoadBalancer service.
    Spring Petclinic Service: Exposes the Spring Petclinic application on port 8080 via a LoadBalancer service.

4. Persistent Volume and Persistent Volume Claim

    PersistentVolume (PV): Provides 1Gi of local storage with the ReadWriteMany access mode to support multiple read/write operations.
    PersistentVolumeClaim (PVC): Requests storage defined by the PV for the MySQL database.

