# NexBank - Modern Banking Platform

## 📋 Project Overview

A comprehensive, production-ready microservices-based banking application built with modern DevOps practices, cloud-native architecture, and complete observability stack. NexBank provides secure, scalable banking services with enterprise-grade monitoring and deployment automation.

## 🏗️ Project Structure

### Multi-Repository Structure

```
nexbank-api-gateway/
├── src/
├── tests/
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── cd.yml
├── Dockerfile
├── package.json / pom.xml
└── README.md

nexbank-user-service/
├── src/
├── tests/
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── cd.yml
├── Dockerfile
├── package.json / pom.xml
└── README.md

nexbank-account-service/
├── src/
├── tests/
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── cd.yml
├── Dockerfile
├── package.json / pom.xml
└── README.md

nexbank-transaction-service/
├── src/
├── tests/
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── cd.yml
├── Dockerfile
├── package.json / pom.xml
└── README.md

nexbank-notification-service/
├── src/
├── tests/
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── cd.yml
├── Dockerfile
├── package.json / pom.xml
└── README.md

nexbank-web-app/
├── src/
├── public/
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── cd.yml
├── Dockerfile
├── package.json
└── README.md

nexbank-infrastructure/
├── terraform/
│   ├── modules/
│   │   ├── vpc/
│   │   │   ├── main.tf
│   │   │   ├── variables.tf
│   │   │   └── outputs.tf
│   │   ├── eks/
│   │   │   ├── main.tf
│   │   │   ├── variables.tf
│   │   │   └── outputs.tf
│   │   ├── rds/
│   │   │   ├── main.tf
│   │   │   ├── variables.tf
│   │   │   └── outputs.tf
│   │   ├── s3/
│   │   │   ├── main.tf
│   │   │   ├── variables.tf
│   │   │   └── outputs.tf
│   │   ├── iam/
│   │   │   ├── main.tf
│   │   │   ├── variables.tf
│   │   │   └── outputs.tf
│   │   └── security-groups/
│   │       ├── main.tf
│   │       ├── variables.tf
│   │       └── outputs.tf
│   ├── environments/
│   │   ├── dev/
│   │   │   ├── main.tf
│   │   │   ├── variables.tf
│   │   │   ├── terraform.tfvars
│   │   │   └── backend.tf
│   │   ├── staging/
│   │   │   ├── main.tf
│   │   │   ├── variables.tf
│   │   │   ├── terraform.tfvars
│   │   │   └── backend.tf
│   │   └── production/
│   │       ├── main.tf
│   │       ├── variables.tf
│   │       ├── terraform.tfvars
│   │       └── backend.tf
│   └── README.md
├── ansible/
│   ├── playbooks/
│   │   ├── setup-monitoring.yml
│   │   ├── configure-nodes.yml
│   │   ├── deploy-prometheus.yml
│   │   ├── deploy-grafana.yml
│   │   └── deploy-logging-stack.yml
│   ├── inventory/
│   │   ├── dev.ini
│   │   ├── staging.ini
│   │   └── production.ini
│   ├── roles/
│   │   ├── prometheus/
│   │   │   ├── tasks/
│   │   │   ├── templates/
│   │   │   └── defaults/
│   │   ├── grafana/
│   │   │   ├── tasks/
│   │   │   ├── templates/
│   │   │   └── defaults/
│   │   ├── fluentd/
│   │   │   ├── tasks/
│   │   │   ├── templates/
│   │   │   └── defaults/
│   │   └── node-exporter/
│   │       ├── tasks/
│   │       ├── templates/
│   │       └── defaults/
│   └── README.md
├── .github/
│   └── workflows/
│       ├── terraform-plan.yml
│       ├── terraform-apply.yml
│       └── ansible-deploy.yml
└── README.md

nexbank-gitops/
├── argocd/
│   ├── install/
│   │   └── argocd-install.yaml
│   ├── applications/
│   │   ├── api-gateway-app.yaml
│   │   ├── user-service-app.yaml
│   │   ├── account-service-app.yaml
│   │   ├── transaction-service-app.yaml
│   │   ├── notification-service-app.yaml
│   │   ├── web-app.yaml
│   │   ├── monitoring-stack-app.yaml
│   │   └── logging-stack-app.yaml
│   └── projects/
│       ├── nexbank-dev.yaml
│       ├── nexbank-staging.yaml
│       └── nexbank-production.yaml
├── manifests/
│   ├── base/
│   │   ├── namespaces/
│   │   ├── configmaps/
│   │   └── secrets/
│   ├── dev/
│   │   ├── api-gateway/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── ingress.yaml
│   │   │   └── kustomization.yaml
│   │   ├── user-service/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── configmap.yaml
│   │   │   └── kustomization.yaml
│   │   ├── account-service/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── configmap.yaml
│   │   │   └── kustomization.yaml
│   │   ├── transaction-service/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── configmap.yaml
│   │   │   └── kustomization.yaml
│   │   ├── notification-service/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── configmap.yaml
│   │   │   └── kustomization.yaml
│   │   └── web-app/
│   │       ├── deployment.yaml
│   │       ├── service.yaml
│   │       ├── ingress.yaml
│   │       └── kustomization.yaml
│   ├── staging/
│   │   ├── api-gateway/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── ingress.yaml
│   │   │   └── kustomization.yaml
│   │   ├── user-service/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── configmap.yaml
│   │   │   └── kustomization.yaml
│   │   ├── account-service/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── configmap.yaml
│   │   │   └── kustomization.yaml
│   │   ├── transaction-service/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── configmap.yaml
│   │   │   └── kustomization.yaml
│   │   ├── notification-service/
│   │   │   ├── deployment.yaml
│   │   │   ├── service.yaml
│   │   │   ├── hpa.yaml
│   │   │   ├── configmap.yaml
│   │   │   └── kustomization.yaml
│   │   └── web-app/
│   │       ├── deployment.yaml
│   │       ├── service.yaml
│   │       ├── ingress.yaml
│   │       └── kustomization.yaml
│   └── production/
│       ├── api-gateway/
│       │   ├── deployment.yaml
│       │   ├── service.yaml
│       │   ├── hpa.yaml
│       │   ├── ingress.yaml
│       │   └── kustomization.yaml
│       ├── user-service/
│       │   ├── deployment.yaml
│       │   ├── service.yaml
│       │   ├── hpa.yaml
│       │   ├── configmap.yaml
│       │   └── kustomization.yaml
│       ├── account-service/
│       │   ├── deployment.yaml
│       │   ├── service.yaml
│       │   ├── hpa.yaml
│       │   ├── configmap.yaml
│       │   └── kustomization.yaml
│       ├── transaction-service/
│       │   ├── deployment.yaml
│       │   ├── service.yaml
│       │   ├── hpa.yaml
│       │   ├── configmap.yaml
│       │   └── kustomization.yaml
│       ├── notification-service/
│       │   ├── deployment.yaml
│       │   ├── service.yaml
│       │   ├── hpa.yaml
│       │   ├── configmap.yaml
│       │   └── kustomization.yaml
│       └── web-app/
│           ├── deployment.yaml
│           ├── service.yaml
│           ├── ingress.yaml
│           └── kustomization.yaml
├── monitoring/
│   ├── prometheus/
│   │   ├── prometheus-config.yaml
│   │   ├── prometheus-deployment.yaml
│   │   ├── prometheus-service.yaml
│   │   └── service-monitors/
│   ├── grafana/
│   │   ├── grafana-deployment.yaml
│   │   ├── grafana-service.yaml
│   │   ├── dashboards/
│   │   └── datasources/
│   └── alertmanager/
│       ├── alertmanager-config.yaml
│       ├── alertmanager-deployment.yaml
│       └── alertmanager-service.yaml
├── logging/
│   ├── elasticsearch/
│   │   ├── statefulset.yaml
│   │   └── service.yaml
│   ├── fluentd/
│   │   ├── daemonset.yaml
│   │   └── configmap.yaml
│   └── kibana/
│       ├── deployment.yaml
│       └── service.yaml
├── .github/
│   └── workflows/
│       ├── sync-manifests.yml
│       └── validate-manifests.yml
└── README.md
```

## 🎯 Microservices Architecture

### 1. **API Gateway Service** (`nexbank-api-gateway`)
- **Purpose**: Central entry point for all client requests
- **Responsibilities**:
  - Request routing and load balancing
  - Authentication and authorization (JWT validation)
  - Rate limiting and throttling
  - API composition and aggregation
  - Request/response transformation
  - CORS handling
- **Tech Stack**: Spring Cloud Gateway / Kong / Node.js + Express
- **Port**: 8080
- **Database**: PostgreSQL (for API logs and metrics)

### 2. **User Service** (`nexbank-user-service`)
- **Purpose**: User authentication, authorization, and profile management
- **Responsibilities**:
  - User registration and login
  - Password management and recovery
  - User profile CRUD operations
  - Role-based access control (RBAC)
  - KYC (Know Your Customer) management
  - Session management
  - Customer document management
  - Two-factor authentication (2FA)
- **Tech Stack**: Spring Boot / Node.js + Express
- **Port**: 8081
- **Database**: PostgreSQL

### 3. **Account Service** (`nexbank-account-service`)
- **Purpose**: Core banking account and transaction management
- **Responsibilities**:
  - Account creation (Savings, Checking, Fixed Deposit)
  - Account balance management
  - Account status management (Active, Inactive, Frozen)
  - Account details retrieval
  - Account statement generation
  - Deposits and withdrawals
  - Internal transfers (between accounts)
  - External transfers (to other banks)
  - Transaction history and search
  - Transaction validation
  - Multi-currency account support
- **Tech Stack**: Spring Boot / Node.js + Express
- **Port**: 8082
- **Database**: PostgreSQL (with write-ahead logging)

### 4. **Transaction Service** (`nexbank-transaction-service`)
- **Purpose**: Payment processing and third-party integrations
- **Responsibilities**:
  - Bill payments (utilities, credit cards, loans)
  - Online payment gateway integration
  - Payment scheduling and automation
  - Recurring payment setup
  - Payment reconciliation
  - Loan application processing
  - Loan eligibility calculation
  - EMI calculation and scheduling
  - Loan payment processing
  - Interest calculation
- **Tech Stack**: Spring Boot / Node.js + Express
- **Port**: 8083
- **Database**: PostgreSQL

### 5. **Notification Service** (`nexbank-notification-service`)
- **Purpose**: Multi-channel notification delivery
- **Responsibilities**:
  - Email notifications
  - SMS notifications
  - Push notifications (mobile app)
  - In-app notifications
  - Notification templating
  - Notification history and tracking
  - Notification preferences management
  - Transaction alerts
  - Account activity alerts
- **Tech Stack**: Spring Boot / Node.js + Express
- **Port**: 8084
- **Database**: MongoDB (for notification logs)
- **External Services**: AWS SES, SNS, Twilio

## 🗂️ Repository Naming Conventions

### Multi-Repository Structure
We follow a **multi-repo** approach where each microservice, frontend, infrastructure, and GitOps configuration has its own dedicated repository.

### Repository Naming Pattern
All repositories follow the pattern: `nexbank-<component-name>`

### Microservices Repositories
```
nexbank-api-gateway          # API Gateway service
nexbank-user-service         # User authentication and profile management
nexbank-account-service      # Account and transaction management
nexbank-transaction-service  # Payment processing and loans
nexbank-notification-service # Multi-channel notifications
```

### Frontend Repositories
```
nexbank-web-app             # Customer web application (React/Next.js)
nexbank-mobile-app          # Mobile application (React Native/Flutter)
nexbank-admin-portal        # Admin dashboard (React/Next.js)
```

### Infrastructure Repository
```
nexbank-infrastructure      # Terraform + Ansible configurations
```

### GitOps Repository
```
nexbank-gitops             # ArgoCD apps and Kubernetes manifests
```

### Shared Libraries (Optional)
```
nexbank-common-lib         # Shared utilities and common code
nexbank-security-lib       # Shared security components
```

### Branch Naming Conventions
```
main                                      # Production-ready code
develop                                   # Integration branch
feature/<ticket-id>-<description>         # Feature branches
bugfix/<ticket-id>-<description>          # Bug fix branches
hotfix/<ticket-id>-<description>          # Hotfix branches
release/<version>                         # Release branches
```

Examples:
```
feature/NBK-123-add-account-creation
feature/NBK-234-implement-2fa
bugfix/NBK-456-fix-transaction-validation
hotfix/NBK-789-patch-security-vulnerability
release/v1.2.0
```

### Commit Message Convention
Following Conventional Commits specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks
- `perf`: Performance improvements
- `ci`: CI/CD changes

**Examples:**
```
feat(account-service): add multi-currency account support

Implemented support for USD, EUR, GBP, and INR currencies with 
automatic exchange rate fetching from external API.

Closes NBK-234

---

fix(user-service): resolve JWT token expiration issue

Fixed bug where JWT tokens were expiring prematurely due to 
incorrect timezone handling.

Fixes NBK-456

---

ci(api-gateway): update GitHub Actions workflow for deployment

Added staging environment deployment step and improved 
Docker build caching.

Related to NBK-567
```

## 🛠️ Technology Stack

### Backend
- **Language**: Java 17+ (Spring Boot) / Node.js 18+ (Express)
- **API**: RESTful APIs with OpenAPI 3.0 specification
- **Authentication**: JWT (JSON Web Tokens), OAuth 2.0
- **Service Discovery**: Kubernetes DNS / Eureka (optional)
- **Config Management**: Kubernetes ConfigMaps and Secrets

### Frontend
- **Web**: React 18+ / Next.js with TypeScript
- **Mobile**: React Native / Flutter
- **State Management**: Redux Toolkit / Zustand
- **UI Library**: Material-UI / Ant Design / Tailwind CSS

### Databases
- **RDBMS**: PostgreSQL 15+ (for transactional data)
- **NoSQL**: MongoDB 6+ (for logs and notifications)

### DevOps & Infrastructure

#### Containerization
- **Docker**: Multi-stage builds for optimized images
- **Docker Compose**: Local development environment

#### Orchestration
- **Kubernetes**: EKS (Elastic Kubernetes Service)
- **Helm**: Package management for Kubernetes

#### Infrastructure as Code
- **Terraform**: AWS infrastructure provisioning
  - VPC, Subnets, Security Groups
  - EKS Cluster
  - RDS (PostgreSQL)
  - DocumentDB (MongoDB compatible)
  - S3 Buckets
  - IAM Roles and Policies
  - Application Load Balancers
  - Route53 DNS
  - CloudWatch

#### Configuration Management
- **Ansible**: Server configuration and software deployment
  - Node configuration
  - Monitoring agent installation
  - Security hardening
  - Log collector setup
  - System updates and patches

**Note**: Both Terraform and Ansible are maintained in a single repository: `nexbank-infrastructure`

#### GitOps
- **ArgoCD**: Continuous deployment and GitOps workflow
  - Automated synchronization
  - Multi-environment management (dev, staging, prod)
  - Rollback capabilities
  - Progressive delivery with Argo Rollouts

#### CI/CD
- **GitHub Actions**: Continuous Integration and Continuous Deployment
- **Pipeline Stages**:
  - Code checkout
  - Dependency installation
  - Unit tests
  - Integration tests
  - Code quality analysis (SonarQube)
  - Security scanning (Snyk, Trivy)
  - Docker image build (multi-stage builds)
  - Image vulnerability scanning
  - Push to Amazon ECR
  - Update image tags in GitOps repository (nexbank-gitops)
  - ArgoCD auto-sync detects changes and deploys

#### GitHub Actions Workflows (per repository)
Each microservice repository contains:
- **ci.yml**: Build, test, scan code, and push Docker image to ECR
- **cd.yml**: Update image tags in GitOps repository manifests to trigger ArgoCD deployment

### Observability Stack

#### Metrics & Monitoring
- **Prometheus**: Metrics collection and storage
  - Service metrics (latency, throughput, error rate)
  - JVM metrics (heap, GC, threads)
  - Custom business metrics
  - Node metrics (CPU, memory, disk)
- **Grafana**: Visualization and dashboards
  - Pre-built dashboards for each microservice
  - Infrastructure dashboards
  - Business metrics dashboards
  - Alerting rules
- **kube-state-metrics**: Kubernetes cluster metrics
- **Node Exporter**: Hardware and OS metrics

#### Logging
- **Fluentd / Fluent Bit**: Log collection and forwarding
- **Elasticsearch**: Log storage and indexing
- **Kibana**: Log visualization and search
- **Log Format**: JSON structured logging
- **Log Levels**: ERROR, WARN, INFO, DEBUG, TRACE

#### Tracing
- **Jaeger** / **Zipkin**: Distributed tracing
- **OpenTelemetry**: Instrumentation

#### Alerting
- **Alertmanager**: Alert routing and notification
- **PagerDuty** / **OpsGenie**: Incident management integration
- **Slack / Email**: Alert notifications

### Security
- **SSL/TLS**: Certificate management with cert-manager
- **Secrets Management**: HashiCorp Vault / AWS Secrets Manager
- **Network Policies**: Kubernetes Network Policies
- **Pod Security**: Pod Security Standards
- **API Security**: OAuth 2.0, JWT, API rate limiting

## 🚀 Deployment Strategy

### Environments
1. **Development**: Feature testing and integration
2. **Staging**: Pre-production testing with production-like data
3. **Production**: Live environment

### Deployment Pattern
- **Blue-Green Deployment**: Zero-downtime deployments
- **Canary Deployment**: Gradual rollout with Argo Rollouts
- **Rolling Updates**: Default Kubernetes strategy

### Auto-scaling
- **Horizontal Pod Autoscaler (HPA)**: CPU and memory-based scaling
- **Cluster Autoscaler**: Node-level scaling
- **KEDA**: Event-driven autoscaling for Kafka consumers

## 📊 Monitoring & Observability Setup

### Prometheus Configuration
- **Scrape Interval**: 15s
- **Retention**: 15 days
- **Service Monitors**: Auto-discovery of services
- **Recording Rules**: Pre-aggregated metrics
- **Alert Rules**: SLA-based alerting

### Grafana Dashboards
1. **Overview Dashboard**: System-wide health
2. **Microservice Dashboards**: Per-service metrics
3. **Infrastructure Dashboard**: Cluster and node metrics
4. **Business Metrics Dashboard**: Transaction volume, user activity
5. **Database Dashboard**: Query performance, connections
6. **API Gateway Dashboard**: Request rates, latency percentiles

### Log Collection Pipeline
```
Application Logs → Fluentd/Fluent Bit → Elasticsearch → Kibana
```

### Key Metrics to Monitor
- **RED Metrics**: Rate, Errors, Duration
- **USE Metrics**: Utilization, Saturation, Errors
- **Business Metrics**: Transactions/sec, Active users, Failed transactions
- **Infrastructure**: CPU, Memory, Disk I/O, Network

## 🔄 GitOps Workflow with ArgoCD

### Workflow
1. Developer pushes code to microservice Git repository
2. CI pipeline runs tests, builds Docker image, and pushes to ECR
3. CD pipeline updates image tags in GitOps repository (nexbank-gitops)
4. ArgoCD detects manifest changes and syncs with Kubernetes cluster
5. Kubernetes pulls new images from ECR and performs rolling update
6. Prometheus and Grafana monitor deployment health
7. Alerts trigger on anomalies or deployment failures

### ArgoCD Features Used
- **App of Apps Pattern**: Manage multiple applications
- **Sync Waves**: Ordered deployment
- **Health Checks**: Custom health assessments
- **Auto-sync**: Automated deployment
- **Self-healing**: Automatic drift correction

## 🏁 Getting Started

### Prerequisites
- Docker Desktop
- kubectl
- Terraform 1.5+
- Ansible 2.14+
- AWS CLI v2
- ArgoCD CLI
- Helm 3+
- Git

### Local Development Setup

#### Option 1: Docker Compose (Recommended for local development)
```bash
# Clone a microservice repository
git clone https://github.com/your-org/nexbank-user-service.git
cd nexbank-user-service

# Start the service with dependencies
docker-compose up -d

# Access the service
# API: http://localhost:8081
# Health check: http://localhost:8081/actuator/health
```

#### Option 2: Run locally with database
```bash
# Clone the repository
git clone https://github.com/your-org/nexbank-user-service.git
cd nexbank-user-service

# Set up environment variables
cp .env.example .env
# Edit .env with your local configuration

# Install dependencies
npm install  # For Node.js
# OR
mvn clean install  # For Java

# Run the service
npm run dev  # For Node.js
# OR
mvn spring-boot:run  # For Java
```

### AWS Infrastructure Setup

```bash
# Clone infrastructure repository
git clone https://github.com/your-org/nexbank-infrastructure.git
cd nexbank-infrastructure/terraform/environments/dev

# Initialize Terraform
terraform init

# Review infrastructure plan
terraform plan

# Apply infrastructure
terraform apply

# Note the outputs (EKS cluster name, RDS endpoint, etc.)
```

### Kubernetes Cluster Setup

```bash
# Update kubectl context
aws eks update-kubeconfig --name nexbank-eks-cluster --region us-east-1

# Verify cluster access
kubectl cluster-info
kubectl get nodes

# Create namespaces
kubectl create namespace nexbank-dev
kubectl create namespace nexbank-staging
kubectl create namespace nexbank-prod
kubectl create namespace monitoring
kubectl create namespace logging
```

### ArgoCD Installation

```bash
# Clone GitOps repository
git clone https://github.com/your-org/nexbank-gitops.git
cd nexbank-gitops

# Create ArgoCD namespace
kubectl create namespace argocd

# Install ArgoCD
kubectl apply -n argocd -f argocd/install/argocd-install.yaml

# Wait for ArgoCD to be ready
kubectl wait --for=condition=available --timeout=300s \
  deployment/argocd-server -n argocd

# Get initial admin password
kubectl -n argocd get secret argocd-initial-admin-secret \
  -o jsonpath="{.data.password}" | base64 -d

# Port forward to access ArgoCD UI
kubectl port-forward svc/argocd-server -n argocd 8080:443

# Access ArgoCD UI at https://localhost:8080
# Username: admin
# Password: (from previous command)
```

### Deploy Applications via ArgoCD

```bash
# Apply ArgoCD projects
kubectl apply -f argocd/projects/

# Deploy all applications
kubectl apply -f argocd/applications/

# Check application sync status
argocd app list

# Sync a specific application
argocd app sync nexbank-user-service-dev
```

### Set up Monitoring Stack

```bash
# Using Ansible from infrastructure repository
cd nexbank-infrastructure/ansible

# Deploy Prometheus and Grafana
ansible-playbook -i inventory/dev.ini playbooks/setup-monitoring.yml

# Access Grafana
kubectl port-forward svc/grafana -n monitoring 3000:3000
# URL: http://localhost:3000
# Default credentials: admin/admin

# Access Prometheus
kubectl port-forward svc/prometheus -n monitoring 9090:9090
# URL: http://localhost:9090
```

### Set up Logging Stack

```bash
# Deploy ELK stack via Ansible
cd nexbank-infrastructure/ansible
ansible-playbook -i inventory/dev.ini playbooks/deploy-logging-stack.yml

# OR deploy via kubectl
cd nexbank-gitops
kubectl apply -f logging/

# Access Kibana
kubectl port-forward svc/kibana -n logging 5601:5601
# URL: http://localhost:5601
```

## 📈 Scaling Considerations

### Horizontal Scaling
- All microservices are stateless
- Database read replicas for read-heavy operations
- Connection pooling for database connections

### Database Optimization
- Transaction data indexed by date and account ID
- User data indexed by email and user ID
- Query optimization with proper indexes

## 🔐 Security Best Practices

- Secrets stored in AWS Secrets Manager
- Network segmentation with security groups
- Pod-to-pod encryption with service mesh (Istio/Linkerd)
- Regular security scanning with Trivy and Snyk
- OWASP Top 10 compliance
- PCI DSS compliance for payment data

## 📞 Support & Documentation

- **API Documentation**: Available at `/api/docs` (Swagger UI)
- **Architecture Diagrams**: See `docs/architecture/`
- **Runbooks**: See `docs/runbooks/`
- **Troubleshooting**: See `docs/troubleshooting/`

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Contributing

Please read CONTRIBUTING.md for details on our code of conduct and the process for submitting pull requests.

---

**NexBank - Built with ❤️ for modern banking solutions**
