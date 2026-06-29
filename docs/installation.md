# Installation Guide

## Overview

This document describes the setup required to build and run the End-to-End CI/CD Pipeline using Jenkins, SonarQube, Maven, Nexus Repository Manager, and Apache Tomcat on a Linux server.

---

# Prerequisites

Ensure the following software is installed before configuring the pipeline.

* Java JDK 21 (or compatible version)
* Git
* Maven
* Jenkins
* SonarQube
* Nexus Repository Manager
* Apache Tomcat
* Email Extension Plugin
* ThinBackup Plugin

---

# Installation Steps

## Step 1: Install Java

Install Java and verify the installation.

```bash
java -version
```

---

## Step 2: Install Git

Install Git and verify the version.

```bash
git --version
```

---

## Step 3: Install Maven

Install Maven and verify the installation.

```bash
mvn -version
```

---

## Step 4: Install Jenkins

* Install Jenkins.
* Start the Jenkins service.
* Access Jenkins using a web browser.
* Complete the initial setup and install the recommended plugins.

---

## Step 5: Configure Maven in Jenkins

Navigate to:

```
Manage Jenkins
→ Global Tool Configuration
→ Maven Installations
```

Configure the Maven installation and save the settings.

---

## Step 6: Install and Configure SonarQube

* Install SonarQube.
* Start the SonarQube service.
* Create an authentication token.
* Configure the SonarQube server in Jenkins under **Manage Jenkins → System**.
* Install the SonarQube Scanner plugin if required.

---

## Step 7: Install Nexus Repository Manager

* Install Nexus Repository Manager.
* Start the Nexus service.
* Access the Nexus web interface.
* Create a Hosted Maven Repository for artifact storage.
* Configure user credentials.

---

## Step 8: Install Apache Tomcat

* Install Apache Tomcat.
* Configure the Tomcat Manager application.
* Start the Tomcat server.
* Verify that the server is accessible through the browser.

---

## Step 9: Configure Jenkins Credentials

Add the required credentials in Jenkins.

Examples include:

* GitHub Credentials
* Nexus Credentials
* SonarQube Token
* Tomcat Credentials

Navigate to:

```
Manage Jenkins
→ Credentials
```

---

## Step 10: Create the Jenkins Pipeline

Create a new Jenkins Pipeline job and configure the following stages:

* Source Code Checkout
* Maven Build
* SonarQube Analysis
* Artifact Upload to Nexus
* Deploy to Apache Tomcat
* Email Notification
* ThinBackup Execution

---

## Step 11: Configure Email Notifications

Install and configure the **Email Extension Plugin**.

Configure:

* SMTP Server
* Sender Email Address
* Recipient Email Address
* Authentication Details

Verify email notifications by triggering a successful build.

---

## Step 12: Configure ThinBackup

Install the **ThinBackup Plugin**.

Configure:

* Backup Directory
* Backup Schedule (optional)
* Manual Backup

Verify that Jenkins configuration files are successfully backed up.

---

# Verification

After completing the installation, verify the following:

* Jenkins service is running.
* SonarQube dashboard is accessible.
* Nexus Repository Manager is accessible.
* Apache Tomcat is running.
* Maven builds complete successfully.
* SonarQube analysis executes successfully.
* WAR artifacts are uploaded to Nexus.
* Application is deployed to Tomcat.
* Email notifications are received.
* ThinBackup completes successfully.

---

# Next Steps

Once the environment is configured:

1. Push the application source code to GitHub.
2. Trigger the Jenkins pipeline.
3. Monitor each pipeline stage.
4. Verify the deployment.
5. Review the SonarQube report.
6. Confirm the artifact in Nexus.
7. Verify email notifications.
8. Check the ThinBackup backup files.
