# VProfile DevOps Lab — Vagrant & AWS

A hands-on DevOps project exploring multi-tier application deployment, infrastructure provisioning, and cloud deployment strategies using the VProfile application.

This project covers three implementations: a Vagrant-based local environment, an AWS lift-and-shift deployment, and an AWS refactored deployment. The objective is to understand how application infrastructure evolves from local virtual machines to cloud-based deployment architectures.

## Project Overview

The project explores deploying a Java-based multi-tier web application with separate web, application, database, caching, and messaging components.

### Project Versions

| Branch | Implementation | Focus |
|---|---|---|
| `monitoring` | Vagrant / local infrastructure | Virtual machines, service configuration, and multi-tier deployment |
| `lift-and-shift` | AWS Lift and Shift | Migrating the application deployment to AWS |
| `awsrefactor` | AWS Refactor | Exploring a refactored cloud deployment architecture |

Each branch represents a different stage of the project. Refer to the branch-specific configuration files for the exact infrastructure and deployment details.

## Architecture and Technology Stack

### Application and Infrastructure Components

- **Java** — application development
- **Apache Maven** — build and packaging
- **Apache Tomcat** — application server
- **Nginx** — web server and reverse proxy
- **MySQL / MariaDB** — relational database
- **Memcached** — caching
- **RabbitMQ** — message broker
- **Elasticsearch** — search and indexing
- **Vagrant and VirtualBox** — local infrastructure provisioning
- **AWS** — cloud infrastructure and deployment

The Vagrant setup guide describes a multi-VM environment with dedicated hosts for the web server, application server, database, cache, and message broker.

## Version 1: Vagrant-Based Deployment

**Branch:** `monitoring`

The local deployment explores separating application components into individual virtual machines.

### Key learning areas

- Provisioning virtual machines with Vagrant and VirtualBox
- Understanding service dependencies and communication
- Configuring Linux services
- Deploying a Java application to Tomcat
- Configuring Nginx as a reverse proxy
- Connecting the application to database, caching, and messaging services

### Prerequisites

- Oracle VM VirtualBox
- Vagrant
- Git Bash or an equivalent terminal
- The `vagrant-hostmanager` plugin, if required by the Vagrant configuration

Install the plugin:

```bash
vagrant plugin install vagrant-hostmanager
```

### Start the environment

Navigate to the repository's Vagrant manual-provisioning directory:

```bash
cd vagrant/Manual_provisioning
vagrant up
```

Check the virtual machine status:

```bash
vagrant status
```

Connect to a configured VM, for example:

```bash
vagrant ssh db01
```

The actual VM names and provisioning requirements depend on the checked-out branch and its Vagrantfile.

## Version 2: AWS Lift and Shift

**Branch:** `lift-and-shift`

This implementation explores moving the application deployment to AWS while retaining its core application architecture.

### Learning objectives

- Understanding application migration to cloud infrastructure
- Working with AWS compute and networking resources
- Configuring connectivity between application components
- Understanding security groups and service ports
- Deploying and validating the application in a cloud environment
- Troubleshooting deployment and connectivity issues

The specific AWS resources, configuration steps, and deployment topology should be documented from the infrastructure files in this branch.

## Version 3: AWS Refactor

**Branch:** `awsrefactor`

This implementation explores refactoring the cloud deployment rather than simply reproducing the original infrastructure.

### Learning objectives

- Comparing lift-and-shift deployment with cloud refactoring
- Evaluating managed services and infrastructure responsibilities
- Understanding cloud networking and application connectivity
- Improving configuration management and deployment practices
- Considering security, scalability, reliability, and operational cost

The final architecture and managed services used should be confirmed from the actual branch configuration before deployment.

## Learning Progression

The project provides an opportunity to compare three infrastructure approaches:

1. **Local infrastructure:** Understand application components, service dependencies, and VM provisioning.
2. **Cloud migration:** Explore deploying the application on AWS while retaining its core architecture.
3. **Cloud refactoring:** Investigate how infrastructure and service choices can change when adapting an application to the cloud.

This progression helps build practical understanding of Linux administration, deployment workflows, networking, cloud infrastructure, and DevOps troubleshooting.

## Security and Configuration

Before deploying or publishing this project:

- Never commit real AWS access keys, secret keys, API tokens, passwords, or private keys.
- Replace example credentials with placeholders.
- Keep local environment files and credentials out of Git.
- Review security groups and avoid unnecessarily exposing database or messaging ports.
- Rotate any real credentials that have already been exposed.
- Review the original project's license and attribution requirements.

Example `.gitignore` entries:

```gitignore
.env
.env.*
!.env.example
*.pem
*.key
.aws/
.vagrant/
target/
.DS_Store
```

Adapt these rules to the actual project files and ensure required source files are not accidentally excluded.

## Resume Summary

**VProfile DevOps Deployment Lab | Vagrant, Linux and AWS**

- Explored deployment of a multi-tier Java application using Vagrant-based virtual machines and AWS infrastructure.
- Practiced configuring application, web, database, caching, and messaging services.
- Compared lift-and-shift and cloud-refactoring approaches to application deployment.
- Developed practical experience in infrastructure configuration, application deployment, networking, and troubleshooting.

Include only the technologies and tasks you personally implemented and can explain during an interview.

## Acknowledgements

VProfile is an existing application. This repository documents my learning and deployment work around the project. Credit the original maintainers and follow the project's applicable license terms.

Original repository: https://github.com/hkhcoder/vprofile-project
