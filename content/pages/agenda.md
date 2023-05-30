---
title: Agenda
keywords: kubecamp.io kubernetes learning tech
framed: false
---

# Day 1

**Focus**: developers, administrators

**Level**: entry, intermediate

### 1. Containers and Kubernetes
   * Containers vs VMs
   * Understanding Docker/Container DNA & its limitations
    * Immutability
    * Ephemeral identity/network identity
    * Singular execution unit - 1 process per container
   * Solving a modern web application concerns without an orchestrator
     * Networking
     * Loadbalancing - Exposing to the outside world
     * Storage & backups
     * Security:
       * Common*sense security concerns
       * Compliance security concerns
     * Configuration management
     * Change management - Rollout process
     * Logging, monitoring and observability
     * Long*term maintenance
   * The tipping point: understanding the threshold of complexity for introducing K8s
     * Technology implications:
       * Traditional cloud architecture vs the platform model.
       * Consistency vs glue.
       * The container orchestration landscape, circa 2023.
     * Social implications:
   * Implications on the existing in-house team
   * Implications on hiring
### 2. Docker images and containers
   * Building images
   * Running containers
   * Mounting volumes & the storage layers
      * Understand process isolation
      * Exposing ports & the overlay “virtual” network
### 3. Orchestration & Control-Plane Basics
   * The Kubernetes architecture
   * How would you architect a solution that solves the web application’s problems?
   * The 3 pillars of K8s design:
     * Namespaces & Isolation
     * The reconciliation loop pattern & controllers. Desired vs Current state.
     * Abstraction & interfaces are everywhere.
   * The anatomy of the control-plane
   * State: ETCD
   * CRUD API: API server
   * Scheduler
   * Reconciliation: Controller*manager
   * Other needed add*ons
     * Network & CNIs
     * Internal DNS
     * Kubelet service
     * Storage & CSIs
     * Cloud controller manager
   * Pods
     * Solving the limitations of the Container DNA
     * New design patterns emerge:
       * Sidecar
       * Init
       * Adapter
     * Pod DNA and co-located container attributes.
   * Wtf are all those legos?
     * Deployments & ReplicaSets: A good example of multi-layer abstraction to achieve change management good practices.
     * StatefulSets: Can I run my database as containers?
     * DaemonSets
     * Jobs, CronJobs
   * Networking
     * Services - Endpoints
     * Ingresses - Ingress classes
       * A gentle introduction to ingress controllers
     * Internal DNS
     * Exotic design examples with services
   * Understanding headless services
   * Storage
   * PVC, PV
     * Storage Classes
   * Configuration
     * ConfigMaps
     * Secrets
   * Setup a local k8s cluster
     * Local K8s flavours:
   * Kind
   * Minikube
   * K3s
   * Microk8s
### 4. Managing containers on Kubernetes
   * `kubectl`
   * Deployments
   * Examples
### 5. Everything is Resources, except for resource definitions
   * Anatomy of common resource building blocks
   * Metadata
   * Template
### 6. Scheduling
   * How does the scheduler works
   * Filtering, annotations, labels, node labels & groups
   * Node selectors
   * Pod affinity/anti-affinity, Node affinity
   * Taints and tolerations
### 7. Application packaging and management
   * Yaml
   * Helm
      * Anatomy of a chart
      * Release management
   * Kustomize
### 8. Deployment strategies
   * Error budgets
   * Canary deployments and Blue/green deployments
   * Probes, health checking.
      * Liveness
      * Readiness
   * Zero downtime deployments
   * Rollbacks
   * Fail fast, hard, loud
### 9. Kubernetes Cluster options
   * Tier 1: Managed K8s
      * Major cloud providers
     * DigitalOcean
     * Civo
   * Tier 2: Self-hosted management: enterprise providers
     * Rancher
     * Openshift
   * Tier 3: Self-hosted management: open-source providers
     * Gardener
     * Kops
     * Cluster API
   * Tier 4: Self-hosted low level administrations
   * `kubeadm`

# Day 2

**Focus**: power developers, administrators 

**Level**: intermediate, advanced

### 1. Scalability design principles
   * Scalability of Performance
   * Scalability of Availability
   * Scalability of Expenditure
   * Scalability of Maintenance
   * Single points of failure
   * Horizontal scalability
   * Caching, fresh data as needed
   * Asynchronous vs synchronous
   * Stateless workloads
### Networking
   * Understanding networking requirements
   * Routing traffic with kube*proxy
   * Service types
   * Service discovery
   * Service meshes
   * Ingress controllers
   * Gateways
   * External services & hybrid infrastructure possibilities
### Storage
   * VolumeSnapshot, VolumeSnapshotClaim
### Access control
   * RBAC
### Extending the base API with CRDs
   * Operators: Schema + Controller + Reconciliation
   * Abstracting away operational knowledge
### The CNCF ecosystem
   * What it is, how the graduation process works and how to navigate
   * Monitoring and observability
     1. Prometheus, Grafana, Loki, Tempo
     2. Datadog, Elastic, other vendors
   * Backups
     1. Velero
     2. Vendor-specific solutions
   * Security
    * Vulnerability management
     * Trivy
   * Intrusion detection
     * Falco
   * Network security
     * Network Policies
     * Falco
     * Calico
   * Extending access control & authorization
     * Dex
   * Limiting attack surface
   * `seccomp`
   * Certificate management & rotation
     * Cert*manager
### Capacity planning
   * Horizontal scaling
   * Vertical scaling
   * Metrics*based scaling
   * LimitRanges
   * Serverless workloads
   * Functions*as*a*Service
### Operators
   * Anatomy of operators
   * Development options
     1. Kubebuilder
     2. Operator-framework
   * Maturity
