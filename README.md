## DevOps Application Deployment Capstone

### Project Overview

### Technologies Used

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| **Version Control** | **Git & GitHub** | Used for source code management, branch-based development, and to trigger the CI/CD pipeline. |
| **Containerization** | **Docker** | Used to containerize the application, ensuring it runs consistently across different environments. |
| **Automation Server** | **Jenkins** | The central automation server that orchestrates the entire CI/CD pipeline. |
| **Cloud Provider** | **AWS EC2** | The virtual server where the application is hosted and deployed. |
| **Monitoring** | **Prometheus & Grafana** | An open-source solution for real-time monitoring of application health and server metrics. |
| **Scripting** | **Bash Scripting** | Custom scripts were written to automate the Docker build and deployment processes. |

---

### CI/CD Pipeline Architecture

The pipeline is designed to provide a clear separation between the development and production environments, ensuring a smooth and reliable deployment process.

1.  **Code Commit**: Developers push code changes to the **`dev`** branch on GitHub.
2.  **Jenkins Trigger**: A webhook notifies Jenkins of the new commit, automatically starting the pipeline.
3.  **Build & Push**: The Jenkins pipeline builds a Docker image of the application and pushes it to a private Docker Hub repository.
4.  **Development Deployment**: The pipeline then connects to the AWS EC2 instance and deploys the newly built image to the development environment.
5.  **Production Deployment**: Once changes are validated, the `dev` branch is merged into the **`main`** branch. This triggers a separate Jenkins pipeline to build and deploy the application to the production environment.



---

### Project Achievements

* Successfully implemented a complete CI/CD pipeline from code commit to application deployment.
* Containerized a React application using a `Dockerfile` for easy portability and scalability.
* Automated the build and deployment process using bash scripts, reducing manual effort.
* Configured Jenkins with SCM integration and credentials to securely interact with GitHub, Docker Hub, and AWS.
* Set up secure server access on AWS EC2 using a customized Security Group.
* Established an open-source monitoring system using Prometheus and Grafana to track application health.

---

### Submission Deliverables

As part of the final submission, the following items have been prepared to demonstrate the project's completion:

* **GitHub Repo URL**: `https://github.com/mythili1-14/devops-build`
* **Screenshots**: A comprehensive set of screenshots including Jenkins job logs, AWS EC2 configuration, Docker Hub repositories, the deployed application, and the monitoring dashboard.

<img src="https://github.com/mythili1-14/devops-build/blob/main/screenshots/Screenshot_20250923_214416.png" alt="Banner" />

<img src="https://github.com/mythili1-14/devops-build/blob/main/screenshots/Screenshot_20250923_212922.png" alt="Banner" />

<img src="https://github.com/mythili1-14/devops-build/blob/main/screenshots/Screenshot_20250923_212746.png" alt="Banner" />

[<img src="https://github.com/mythili1-14/devops-build/blob/fc8a9f3f1b5125b62504f8223b121ef1dc4a0f4a/screenshots/Screenshot_20250923_212746.png" alt="Banner" />



## More Screenshots available at `Screenshots`



