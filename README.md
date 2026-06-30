# jenkins-remoting-project
Jenkins Remoting setup using AWS EC2 Ubuntu instances with remote agent configuration.
# 🚀 Jenkins Remoting Project using AWS EC2

## 📌 Project Overview

This project demonstrates the setup of **Jenkins Remoting** by configuring a Jenkins Controller and a Remote Agent on two separate AWS EC2 Ubuntu instances. The objective was to distribute build workloads securely, execute jobs on a remote machine, and gain practical experience with Jenkins' distributed build architecture.

---

## 🎯 Objectives

* Set up Jenkins Controller on AWS EC2.
* Configure a Remote Jenkins Agent.
* Execute build jobs on the remote node.
* Learn Jenkins Remoting using WebSocket.
* Understand distributed builds and node management.
* Troubleshoot common Jenkins connectivity issues.

---

## 🛠️ Technologies Used

* AWS EC2
* Ubuntu 26.04 LTS
* Jenkins
* Java 21
* Jenkins Remoting (JNLP/WebSocket)
* Linux
* Git & GitHub

---

## 📋 Project Architecture

```text
               +----------------------+
               |  Jenkins Controller  |
               |      AWS EC2 #1      |
               +----------+-----------+
                          |
                  WebSocket (JNLP)
                          |
                          |
               +----------+-----------+
               |    Jenkins Agent     |
               |      AWS EC2 #2      |
               +----------------------+
```

---

## ⚙️ Steps Performed

### 1. Installed Java

Installed OpenJDK 21 on the Jenkins Controller and Agent.

### 2. Installed Jenkins

* Added the Jenkins repository.
* Installed Jenkins.
* Started and enabled the Jenkins service.

### 3. Configured Jenkins

* Accessed Jenkins through the EC2 Public IP.
* Installed suggested plugins.
* Created the administrator account.

### 4. Created a Remote Agent

* Added a new Permanent Agent.
* Configured the Remote Root Directory.
* Assigned labels to the node.
* Selected **Launch agent by connecting it to the controller**.

### 5. Connected the Agent

* Downloaded `agent.jar`.
* Connected the agent using the generated secret.
* Established communication using **WebSocket**.

### 6. Executed Remote Build

Created a Freestyle Project and successfully executed it on the remote Jenkins Agent.

---

## ⚠️ Challenges Faced

During the implementation, several real-world issues were encountered and resolved.

### Jenkins Repository Key Error

**Issue**

```
NO_PUBKEY 7198F4B714ABFC68
```

**Solution**

* Removed the expired Jenkins repository key.
* Added the latest Jenkins signing key.
* Updated the repository configuration.
* Successfully installed Jenkins.

---

### Agent Connection Issues

**Issue**

* Connection terminated
* Handshake error
* Agent remained Offline

**Solution**

* Recreated the Jenkins Agent.
* Installed the correct Java version.
* Downloaded a fresh `agent.jar`.
* Generated a new secret.
* Successfully connected the agent using WebSocket.

---

## 📸 Screenshots

### Jenkins Dashboard

![Dashboard](screenshots/jenkins-dashboard.png)

---

### Remote Agent Online

![Nodes](screenshots/nodes-online.png)

---

### Agent Successfully Connected

![Agent](screenshots/agent-connected.png)

---

### Freestyle Project

![Project](screenshots/freestyle-project.png)

---

### Successful Build

![Build](screenshots/build-success.png)

---

### Console Output

![Console](screenshots/console-output.png)

---

## 📚 Learning Outcomes

Through this project, I gained hands-on experience with:

* Jenkins installation and configuration
* Jenkins Controller and Agent architecture
* Jenkins Remoting
* WebSocket communication
* Distributed builds
* Linux administration
* AWS EC2 management
* Troubleshooting Jenkins connectivity issues
* CI/CD fundamentals

---

## ✅ Project Outcome

Successfully configured Jenkins Remoting between two AWS EC2 Ubuntu instances and executed build jobs on a remote Jenkins Agent using WebSocket communication.

---

## 👩‍💻 Author

**Lakshana V**
