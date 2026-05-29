# Phase 0 deliverables matrix

This matrix links each Phase 0 task group to its corresponding deliverable file. Subtasks represent the work required to produce the deliverable; they do not create separate files.

All deliverables are stored under:

docs/planning/

## 0.1 Project scope and objectives

**Deliverable:**  
docs/planning/0.1-project-scope-and-objectives.md

**Subtasks:**

- 0.1.1 Document business goals and constraints
- 0.1.2 Identify required Azure capabilities
- 0.1.3 Define success criteria and measurable outcomes

## 0.2 Cost constraints and design boundaries

**Deliverable:**  
docs/planning/0.2-cost-constraints.md

**Subtasks:**

- 0.2.1 Identify cost-sensitive services to avoid
- 0.2.2 Define acceptable monthly spend
- 0.2.3 Document cost-driven deviations from CAF

## 0.3 Subscription and service requirements

**Deliverable:**  
docs/planning/0.3-subscription-strategy.md

**Subtasks:**

- 0.3.1 Determine number of platform and workload subscriptions
- 0.3.2 Validate subscription availability

## 0.4 Management group hierarchy

**Deliverable:**  
docs/planning/0.4-management-group-hierarchy.md

**Subtasks:**

- 0.4.1 Define root, platform, LandingZones, sandbox
- 0.4.2 Map subscriptions to management groups

## 0.5 Naming and tagging standards

**Deliverable:**  
docs/planning/0.5-naming-and-tagging.md

**Subtasks:**

- 0.5.1 Create naming convention document
- 0.5.2 Define mandatory tags and allowed values

## 0.6 RBAC model and separation of duties

**Deliverable:**  
docs/planning/0.6-rbac-model.md

**Subtasks:**

- 0.6.1 Identify platform admin roles
- 0.6.2 Identify CI/CD roles
- 0.6.3 Identify workload admin roles

## 0.7 Assumptions and constraints

**Deliverable:**  
docs/planning/0.7-assumptions-and-constraints.md

**Subtasks:**

- 0.7.1 Capture technical assumptions
- 0.7.2 Capture operational assumptions
- 0.7.3 Capture security constraints

## 0.8 Architectural decision records

**Deliverables directory:**  
docs/planning/decisions/

**Expected ADRs:**

- 0001-repo-structure.md
- 0002-cicd-approach.md
- 0003-cost-deviations.md

**Subtasks:**

- 0.8.1 Repo structure ADR
- 0.8.2 CI/CD approach ADR
- 0.8.3 Cost-driven deviations ADR

## 0.9 Security baseline (ISM Essential Eight)

**Deliverable:**  
docs/planning/0.9-security-baseline.md

**Subtasks:**

- 0.9.1 Application control strategy
- 0.9.2 Patch management approach
- 0.9.3 Microsoft 365 hardening baseline
- 0.9.4 Identity hardening
- 0.9.5 Privileged access model
- 0.9.6 Backup and recovery strategy
- 0.9.7 Logging and monitoring baseline
- 0.9.8 Maturity level target and deviations

## 0.10 Repository structure

**Deliverable:**  
docs/planning/0.10-repository-structure.md

**Subtasks:**

- 0.10.1 Create initial folder scaffolding
- 0.10.2 Add README files
- 0.10.3 Document repository structure guide

## 0.11 Local development environment

**Deliverable:**  
docs/planning/0.11-local-dev-setup.md

**Subtasks:**

- 0.11.1 Install Azure CLI
- 0.11.2 Install Bicep tooling
- 0.11.3 Configure VS Code extensions
- 0.11.4 Document local environment setup

## 0.12 CI/CD approach (GitHub Actions and OIDC)

**Deliverable:**  
docs/planning/0.12-cicd-architecture.md

**Subtasks:**

- 0.12.1 Select pipeline provider (GitHub Actions)
- 0.12.2 Define workflow naming conventions
- 0.12.3 Define workflow folder structure

## 0.13 Project roadmap

**Deliverable:**  
docs/planning/0.13-project-roadmap.md

**Subtasks:**

- 0.13.1 Define roadmap structure
- 0.13.2 Define milestone checkpoints

## 0.14 Work item templates (optional)

**Deliverable:**  
None (optional task)

## 0.15 CAF and AVM alignment

**Deliverable:**  
docs/planning/0.15-caf-avm-alignment.md

**Subtasks:**

- 0.15.1 Validate alignment with CAF
- 0.15.2 Validate alignment with AVM

## 0.16 Cost-driven deviations

**Deliverable:**  
docs/planning/0.16-cost-deviations.md

**Subtasks:**

- 0.16.1 Document deviations required for cost reduction

## Phase 0 summary document

**Deliverable:**  
docs/planning/phase-0-overview.md

**Subtasks:**

- Summarise all Phase 0 decisions
- Define Phase 0 exit criteria
- Confirm readiness for Phase 1
