# Home Kubernetes Configuration

## Overview

This repository is a personal reference and pattern library used to learn and reinforce core Kubernetes concepts through hands-on configuration of a bare metal, multi-node cluster.

The focus of this project is not to build a production platform, but to gain a practical understanding of how Kubernetes components behave under real conditions such as node restarts, service exposure, and configuration changes.

Everything here exists to support learning, experimentation, and future recall.

---

## Purpose

The primary goals of this repository are to:

- Learn Kubernetes fundamentals through configuration rather than theory
- Explore core cluster concepts in a controlled, self-managed environment
- Capture patterns and configurations that can be referenced later

This repository acts as a living notebook and a place to record approaches, decisions, and lessons learned while building and evolving a Kubernetes cluster from first principles.

---

## Cluster Context

- Environment: Bare metal
- Topology: Multi-node
- Lifecycle: Exploratory and evolving
- Usage: Personal home lab

The cluster is intentionally simple but realistic enough to surface operational behaviour such as scheduling, networking, service exposure, and restart characteristics.

---

## Areas of Focus

This repository explores the following Kubernetes concepts.

### Networking
- Ingress configuration
- Load balancing patterns
- Service discovery and routing

### Service Exposure
- MetalLB for bare metal load balancing
- NodePort services
- Ingress controllers and traffic flow

### Storage
- Persistent volumes
- Local versus networked storage
- Stateful workload behaviour

### Reliability and Behaviour
- Pod and service restart characteristics
- Behaviour during node outages or restarts
- Declarative configuration effects over time

---

## What This Repository Deliberately Does Not Cover

To keep learning focused on Kubernetes fundamentals, the following areas are intentionally out of scope.

- Secrets management
- Production-grade authentication or authorisation
- Full monitoring or observability stacks
- CI/CD integration or deployment pipelines

These omissions are deliberate. The aim is to understand the foundational mechanics of Kubernetes before introducing production concerns.

---

## Intended Audience

This repository is primarily for future reference and self-documentation.

It is not intended as a reusable framework or a production-ready solution.

---

## Project State

This repository is exploratory and evolving.

Configurations may change as understanding improves. Not all approaches represent best practice outside the context of learning and experimentation.

---

## What This Demonstrates

This repository demonstrates:

- Practical understanding of Kubernetes cluster configuration
- Comfort working directly with core Kubernetes concepts
- Hands-on experience configuring networking, storage, and service exposure
- An iterative, learning-driven approach to platform engineering

This repository shows that Keith understands how to configure a Kubernetes cluster.

---

## Notes

All configuration in this repository is intentionally self-contained and free of environment-specific secrets or credentials.

Nothing in this repository represents proprietary or employer-owned work.
