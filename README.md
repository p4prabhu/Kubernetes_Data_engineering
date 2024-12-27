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

## dags

The `dags` directory contains Python scripts for Apache Airflow workflows (Directed Acyclic Graphs).

- **fetch_and_preview.py**:
  - A DAG designed to fetch data from a source and provide a preview of the dataset.
  - Demonstrates data fetching and simple processing as part of an ETL workflow.

- **hello.py**:
  - A basic example DAG for Airflow.
  - Useful for understanding Airflow’s structure and testing your setup.
 
## Kubernetes Configuration

This project includes essential YAML configuration files for setting up and managing the Kubernetes Dashboard and related services:

- **dashboard-adminuser.yaml**:
  - YAML file for setting up an admin user for the Kubernetes Dashboard.
  - Grants administrative access for easier cluster management.

- **dashboard-clusterrole.yaml**:
  - YAML file defining the cluster role required for the Kubernetes Dashboard.
  - Ensures proper permissions for accessing cluster resources.

- **dashboard-secret.yaml**:
  - YAML file for managing secrets used by the Kubernetes Dashboard.
  - Includes the admin user token needed for authentication.

- **values.yaml**:
  - YAML file containing customizable values for the Kubernetes setup.
  - Used for configuring Helm-based deployments, such as Apache Airflow.


