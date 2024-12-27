# Kubernetes for Data Engineering

This repository contains the necessary configuration files and DAGs (Directed Acyclic Graphs) for setting up a robust data engineering environment using Kubernetes and Apache Airflow. It includes the setup for the Kubernetes Dashboard, which provides a user-friendly web interface for managing Kubernetes clusters, and Apache Airflow, a platform to programmatically author, schedule, and monitor workflows.

## Repository Structure
## File Structure

```bash
Kubernetes_Data_Engineering_Project/
├── dags/                       # Directory containing Airflow DAGs
│   ├── fetch_and_preview.py    # DAG for fetching data and providing a preview
│   └── hello.py                # A simple example DAG demonstrating Airflow basics
├── dashboard-adminuser.yaml    # Admin user setup for Kubernetes Dashboard
├── dashboard-clusterrole.yaml  # Cluster role definition for the Kubernetes Dashboard
├── dashboard-secret.yaml       # Secrets for the Kubernetes Dashboard
├── values.yaml                 # Helm values for Airflow or Kubernetes setup
├── .gitignore                  # File specifying ignored files for Git
├── .Python                     # Python virtual environment configuration
├── pyvenv.cfg                  # Python virtual environment configuration details
```

