# DeepSeek Microservices Architecture

## Project Description
This document presents the microservices architecture of DeepSeek, an advanced artificial intelligence platform. The architecture aims to ensure **scalability, high availability, and performance** for modern AI workloads.

## ⚠️ Important Notice
> Following discussions with team members and feedback from DeepSeek, it appears that the inference engine needs to be re-evaluated, as no blocking issues were identified during our exchanges. For this reason, we propose separating responsibilities into two services:
> - **Inference Engine Service** - dedicated to inference operations
> - **Deep Learning Service** - to be used when responses are not known

## 📁 Available Documents
| Version | File | Description |
|---------|------|-------------|
| Initial | `main.tex` | Basic Architecture |
| Improved | `main-ameliorée.tex` | Enhanced Architecture |

## 🚀 Architecture Evolution
*Version 1 → Version 2: UML Component Diagram Improvements*

### Key Improvements

| # | Component | Change | Objectives |
|---|-----------|--------|------------|
| 1 | **Service Mesh** | Added cross-cutting Service Mesh layer | 🔒 Secure inter-service communication<br/>📊 Improve observability<br/>⚡ Automatic policies (retry, circuit breaking) |
| 2 | **Intelligent Load Balancer** | Added Load Balancer for AI services | 🎯 Optimize routing to available GPUs<br/>📈 Manage auto-scaling<br️/>⚡ Reduce latency |
| 3 | **Fine-tuning Service** | Separated from Training Service | 🎯 Specialize fine-tuning<br️/>🔄 Optimize resources<br️/>🔧 Facilitate maintenance |
| 4 | **Feature Store** | Added dedicated service | 📊 Centralize feature management<br️/>🔍 Ensure consistency & traceability<br️/>♻️ Promote reuse |
| 5 | **Message Broker** | Introduced async messaging | 🔗 Decouple services<br️/>📈 Handle traffic spikes<br️/>🎯 Event-driven architecture |
| 6 | **Monitoring** | Consolidated monitoring services | 📊 Centralize observability<br️/>🔄 Reduce complexity<br️/>⚠️ Consistent alerts |
| 7 | **Dependencies** | Optimized dependency graph | 🔗 Reduce coupling<br️/>🧩 Improve modularity<br️/>📊 Optimize data flows |

## 🏗️ Technical Architecture

### Architectural Layers
| Layer | Components | Purpose |
|-------|------------|---------|
| **API Layer** | Gateway, Authentication | External interface & security |
| **Service Mesh** | Istio/Envoy | Secure communication & observability |
| **Core Services** | AI business services | Core platform functionality |
| **Data Layer** | Databases, Storage | Data management & persistence |
| **Infrastructure** | Support services | Platform operations |

### 🛠️ Technologies Used
| Category | Technologies |
|----------|-------------|
| **Orchestration** | Kubernetes |
| **Service Mesh** | Istio, Envoy |
| **API Gateway** | Kong, Envoy |
| **Programming** | Python, Go |
| **Databases** | PostgreSQL, Redis, Vector DB (Milvus/Pinecone) |
| **Messaging** | Apache Kafka |
| **Monitoring** | Prometheus, Grafana |
| **Logging** | ELK Stack |

## ✨ Advantages of Improved Version

### 🎯 **Enhanced Scalability**
- Intelligent load balancing across GPU resources
- Better handling of variable AI workloads

### 🔒 **Improved Security**
- Service Mesh with mTLS for secure communication
- Automated security policies

### 📊 **Superior Observability**
- Consolidated monitoring with distributed tracing
- Real-time performance insights

### 🛡️ **Increased Resilience**
- Circuit breakers and retry policies
- Graceful failure handling

### ⚡ **Optimized Performance**
- Feature Store for efficient data access
- Intelligent caching strategies

### 🔧 **Better Maintainability**
- Decoupled services with clear boundaries
- Simplified deployment and updates
