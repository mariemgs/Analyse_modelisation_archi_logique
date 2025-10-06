Project Description
This document presents the microservices architecture of DeepSeek, an advanced artificial intelligence platform. The architecture aims to ensure scalability, high availability, and performance for modern AI workloads.

Warning
Following discussions with team members and feedback from DeepSeek, it appears that the inference engine needs to be re-evaluated, as no blocking issues were identified during our exchanges. For this reason, we propose separating responsibilities into two services: the first dedicated to the inference engine, and the second to deep learning, to be used when the response is not known.

Available Documents

Initial Version: main.tex - Basic Architecture

Improved Version: main-version-ameliorer.tex - Enhanced Architecture

Architecture Evolution
Version 1 → Version 2: UML Component Diagram Improvements

Service Mesh
Change: Addition of a cross-cutting Service Mesh layer
Objectives: Secure inter-service communication, improve observability, and manage automatic policies (retry, circuit breaking).

Intelligent Load Balancer
Change: Addition of a Load Balancer component for AI services
Objectives: Optimize routing to available GPUs, manage auto-scaling, and reduce latency.

Fine-tuning Service
Change: Separation of the fine-tuning service from the Training Service
Objectives: Specialize fine-tuning, optimize resources, and facilitate maintenance.

Feature Store
Change: Addition of a dedicated Feature Store service
Objectives: Centralize feature management, ensure consistency and traceability, and promote reuse.

Message Broker
Change: Introduction of an asynchronous messaging service
Objectives: Decouple services, handle traffic spikes, and promote event-driven architecture.

Consolidated Monitoring
Change: Grouping of monitoring services
Objectives: Centralize observability, reduce complexity, and facilitate consistent alerts.

Dependency Reorganization
Change: Optimization of the dependency graph
Objectives: Reduce coupling, improve modularity, and optimize data flows.

Technical Architecture

Architectural Layers

API: Gateway and authentication

Service Mesh: Secure communication and observability

Core Services: AI business services

Data: Management and storage

Infrastructure: Support services

Technologies Used

Orchestration: Kubernetes

Service Mesh: Istio/Envoy

API Gateway: Kong/Envoy

Languages: Python/Go

Databases: PostgreSQL, Redis, Vector DB (Milvus/Pinecone)

Message Queue: Apache Kafka

Monitoring: Prometheus/Grafana

Logging: ELK Stack

Advantages of the Improved Version

Better scalability through intelligent load balancing

Enhanced security with Service Mesh and mTLS

Consolidated observability with distributed tracing

Increased resilience via circuit breakers and retry policies

Optimized performance with Feature Store and cache

Improved maintainability through decoupled services

