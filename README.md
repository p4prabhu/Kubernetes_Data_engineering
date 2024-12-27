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


## Getting Started

### Prerequisites

- A Kubernetes cluster.
- `kubectl` installed and configured on your local machine.
- Helm (optional, but recommended for managing Kubernetes applications like Apache Airflow).

### Setup

1. Deploy the Kubernetes Dashboard

To set up the Kubernetes Dashboard, apply the YAML configuration files in your repository:

```bash
kubectl apply -f dashboard-adminuser.yaml
kubectl apply -f dashboard-clusterrole.yaml
kubectl apply -f dashboard-secret.yaml
```

2. Accessing the Kubernetes Dashboard
 To access the Dashboard, you may need to start a proxy server:
```bash
kubectl proxy
```
Then, access the Dashboard at: http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/.
Use the token generated for the admin user to log in (see dashboard-secret.yaml)

3. Deploy Apache Airflow:
You can deploy Apache Airflow using Helm or by applying custom YAML files. For Helm:
```bash
helm repo add apache-airflow https://airflow.apache.org
helm install airflow apache-airflow/airflow -f values.yaml
```
This will deploy Airflow with the settings defined in values.yaml.

4. Adding DAGs to Airflow:
   Copy your DAG files (e.g., fetch_and_preview.py, hello.py) into the DAGs folder of your Airflow deployment. The method of copying depends on your Airflow setup (e.g., using Persistent Volume, Git-sync).
   After copying the DAG files, restart the Airflow scheduler and webserver if required to ensure the new DAGs are loaded.

### Usage
- Kubernetes Dashboard: Use the Kubernetes Dashboard to monitor and manage your Kubernetes cluster. You can view logs, check resource usage, and manage workloads through the Dashboard interface.
- Apache Airflow: Access the Airflow web UI to schedule, manage, and monitor workflows. Ensure that your DAGs are visible in the UI and functioning as expected.


