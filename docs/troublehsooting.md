# Troubleshooting Guide

## Overview

This document summarizes common issues encountered while building the End-to-End CI/CD Pipeline and the steps taken to resolve them.

---

# 1. Jenkins Service Failed to Start

### Issue - Jenkins service did not start successfully.

### Cause -
* Incorrect Java version

### Resolution -
* Verified Java installation.
* Checked the Jenkins service status.
* Restarted the Jenkins service.

---

# 2. SonarQube Analysis Failed

### Issue - SonarQube analysis did not complete successfully.

### Cause -
* Invalid authentication token
* SonarQube service unavailable

### Resolution -
* Verified the SonarQube server URL.
* Generated a new authentication token.
* Updated Jenkins credentials.
* Restarted the SonarQube service.

---

# 3. Email Notification Not Received

### Issue - Build completed successfully but no email notification was received.

### Cause - 
* Incorrect SMTP configuration
* Authentication failure
* Invalid recipient email address

### Resolution -
* Verified SMTP server configuration.
* Updated email credentials.
* Sent a test email.
* Verified the Email Extension Plugin configuration.

---

# 4. ThinBackup Failed

### Issue - ThinBackup did not create a backup.

### Cause -
* Invalid backup directory

### Resolution - 
* Verified backup directory permissions.
* Configured the correct backup location.
* Executed a manual backup successfully.

---

# Lessons Learned

Through this project, I gained practical experience in:

* Configuring Jenkins pipelines
* Maven build automation
* SonarQube integration
* Nexus artifact management
* Tomcat deployment
* Email notification setup
* Jenkins backup using ThinBackup
* Troubleshooting CI/CD pipeline failures

---

# Best Practices

* Verify service status before starting the pipeline.
* Use Jenkins Credentials for sensitive information.
* Validate Maven configuration before deployment.
* Review logs whenever a pipeline stage fails.
* Keep Jenkins backups up to date.
