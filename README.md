# DemoProject-Jenkins

# 🚀 End-to-End Automated CI/CD Pipeline

![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=Jenkins&logoColor=white)
![Git](https://img.shields.io/badge/GIT-F05032?style=for-the-badge&logo=git&logoColor=white)
![Maven](https://img.shields.io/badge/Apache_Maven-C71A36?style=for-the-badge&logo=Apache%20Maven&logoColor=white)
![SonarQube](https://img.shields.io/badge/SonarQube-4E9BCD?style=for-the-badge&logo=sonarqube&logoColor=white)

This repository hosts a comprehensive **CI/CD Pipeline** designed to automate the entire software delivery lifecycle—from source code management to final application deployment.

---

## 🛠️ Infrastructure & Tooling

| Phase | Tool | Description |
| :--- | :--- | :--- |
| **SCM** | **Git** | Distributed version control and source code management. |
| **Build** | **Maven** | Handles project compilation, dependency management, and unit testing. |
| **CQA** | **SonarQube** | Static code analysis to ensure high code quality and security standards. |
| **Orchestration** | **Jenkins** | The "Engine" that manages the entire automation pipeline. |
| **Artifact** | **Nexus** | Centralized repository for storing and versioning build artifacts. |
| **Deployment** | **Tomcat** | Lightweight application server for hosting the Java web application. |
| **Feedback** | **Email** | Automated notifications triggered by Post-Build Actions (PBA). |

---

## 🏗️ Pipeline Architecture

The pipeline follows a structured **DevOps workflow** to ensure rapid and reliable delivery:

1.  **Code Commit:** Developers push code to **Git**.
2.  **Continuous Integration:** **Jenkins** pulls the code and triggers a build via **Maven**.
3.  **Quality Gate:** **SonarQube** scans the code for bugs and vulnerabilities. If the quality gate fails, the build stops here.
4.  **Artifact Management:** Once verified, Maven packages the code into a `.war` file and uploads it to **Nexus Repository Manager**.
5.  **Continuous Deployment:** Jenkins pulls the latest stable artifact from Nexus and deploys it to the **Apache Tomcat** server.
6.  **Notification:** An **Email** is automatically sent to stakeholders with the build status and logs.

---

## 🌟 Key Highlights

* **Automated Quality Checks:** No code reaches production without passing SonarQube standards.
* **Version Control:** Every deployment is traceable to a specific version stored in Nexus.
* **Rapid Feedback:** Immediate email alerts for build failures or successes.
* **Scalability:** The pipeline is written as a script (Pipeline-as-Code), making it easy to replicate.

---

## 🚀 How to Setup

### 1. Prerequisites
* Jenkins installed with Maven, SonarQube, and Email Extension plugins.
* Running instances of SonarQube, Nexus, and Tomcat.

### 2. Configuration
* Add your **Nexus Credentials** and **Tomcat Manager** credentials to Jenkins.
* Configure the `settings.xml` in Maven to point to your Nexus repository.

### 3. Execution
* Create a **Pipeline Project** in Jenkins.
* Copy the `Jenkinsfile` from this repo into the project configuration.
* Click **Build Now**.

---

## 📬 Contact
For technical queries or collaboration, feel free to open a Pull Request or reach out via the automated email system integrated into the pipeline.
