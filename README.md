# SonarQube
# SonarQube - Code Quality Analysis  


[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](#)  
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](#)  
[![Jenkins](https://img.shields.io/badge/Jenkins-8080-orange?logo=jenkins)](#)  
[![SonarQube](https://img.shields.io/badge/SonarQube-9000-blue?logo=sonarqube)](#)  

---

## 📑 Table of Contents  

1. [Overview](#overview)  
2. [Architecture](#architecture)  
3. [Setup Instructions](#setup-instructions)  
   - [Step 1: Launch Ubuntu VM](#-step-1-launch-ubuntu-vm)  
   - [Step 2: Connect to VM](#-step-2-connect-to-the-vm)  
   - [Step 3: Update Packages](#-step-3-update-packages)  
   - [Step 4: Install Jenkins](#-step-4-install-jenkins)  
   - [Step 5: Setup SonarQube](#-step-5-setup-sonarqube-via-docker)  
   - [Step 6: Jenkins Pipeline Job](#-step-6-jenkins-pipeline-job-for-sonarqube-analysis)  
4. [Sample Jenkinsfile](#-sample-jenkinsfile)  
5. [References](#-references)  

---

## 📖 Overview  

This project demonstrates how to set up **Jenkins** and **SonarQube** on an **Ubuntu VM**, integrate them for automated **code quality analysis**, and configure a Jenkins pipeline with Maven.  

---

## 🏗️ Architecture  

```mermaid
flowchart LR
    Dev[Developer] -->|Push Code| GitHub[GitHub Repo]
    GitHub --> Jenkins[Jenkins CI/CD]
    Jenkins -->|Build & Test| Maven[Maven Build]
    Jenkins -->|Analyze| SonarQube[SonarQube Server]
    SonarQube -->|Quality Gate Results| Jenkins
    Jenkins --> Dev[Developer Feedback]
