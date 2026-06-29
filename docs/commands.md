# Commands Reference

## Overview

This document contains the commonly used commands during the setup and execution of the End-to-End CI/CD Pipeline.

---

# System Information
hostname
hostnamectl

---

# Java
java -version

---

# Git Commands
git clone <repository-url>
git status
git add .
git commit -m "Commit message"
git push origin main

# Jenkins Commands

sudo systemctl start jenkins
sudo systemctl stop jenkins
sudo systemctl restart jenkins
sudo systemctl status jenkins
---

# SonarQube Commands
sudo systemctl start sonarqube
sudo systemctl stop sonarqube
sudo systemctl status sonarqube
---

# Nexus Repository Commands
sudo systemctl start nexus
sudo systemctl stop nexus
sudo systemctl restart nexus
sudo systemctl status nexus

---

# Apache Tomcat Commands
sudo systemctl start tomcat
sudo systemctl stop tomcat
sudo systemctl restart tomcat
sudo systemctl status tomcat
./startup.sh
./shutdown.sh

---

# Backup Commands
ll mybackup/
