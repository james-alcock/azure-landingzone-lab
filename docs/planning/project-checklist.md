# Project Plan Checklist (GitHub + Bicep)

## Phase 0. Planning and Foundations

- [ ] 0.1 Define project scope and objectives
  - [ ] 0.1.1 Document business goals and constraints
  - [ ] 0.1.2 Identify required Azure capabilities
  - [ ] 0.1.3 Define success criteria and measurable outcomes

- [ ] 0.2 Confirm cost constraints and cost-driven design boundaries
  - [ ] 0.2.1 Identify cost-sensitive services to avoid
  - [ ] 0.2.2 Define acceptable monthly spend
  - [ ] 0.2.3 Document cost-driven deviations from CAF

- [ ] 0.3 Identify required Azure services and subscriptions
  - [ ] 0.3.1 Determine number of platform and workload subscriptions
  - [ ] 0.3.2 Validate subscription availability

- [ ] 0.4 Finalise management group hierarchy design
  - [ ] 0.4.1 Define root, platform, LandingZones, sandbox
  - [ ] 0.4.2 Map subscriptions to management groups

- [ ] 0.5 Define naming and tagging standards
  - [ ] 0.5.1 Create naming convention document
  - [ ] 0.5.2 Define mandatory tags and allowed values

- [ ] 0.6 Define RBAC model and separation of duties
  - [ ] 0.6.1 Identify platform admin roles (Cloud-Admins)
  - [ ] 0.6.2 Identify CI/CD roles (Platform-Engineers)
  - [ ] 0.6.3 Identify workload admin roles (Workload-Admins, per workload)

- [ ] 0.7 Document design assumptions and constraints
  - [ ] 0.7.1 Capture technical assumptions
  - [ ] 0.7.2 Capture operational assumptions
  - [ ] 0.7.3 Capture security constraints

- [ ] 0.8 Create initial ADRs for key decisions
  - [ ] 0.8.1 Repo structure ADR
  - [ ] 0.8.2 CI/CD approach ADR (GitHub + OIDC + Bicep)
  - [ ] 0.8.3 Cost-driven deviations ADR

- [ ] 0.9 Define security baseline aligned to ISM Essential Eight
  - [ ] 0.9.1 Application control strategy
  - [ ] 0.9.2 Patch management approach
  - [ ] 0.9.3 Microsoft 365 hardening baseline
  - [ ] 0.9.4 Identity hardening (MFA, conditional access)
  - [ ] 0.9.5 Privileged access model
  - [ ] 0.9.6 Backup and recovery strategy
  - [ ] 0.9.7 Logging and monitoring baseline
  - [ ] 0.9.8 Maturity level target and cost-driven deviations

- [ ] 0.10 Establish repo structure (single GitHub repo)
  - [ ] 0.10.1 Create initial folder scaffolding
  - [ ] 0.10.2 Add README files
  - [ ] 0.10.3 Document repository structure guide

- [ ] 0.11 Set up local development environment and tooling
  - [ ] 0.11.1 Install Azure CLI
  - [ ] 0.11.2 Install Bicep tooling
  - [ ] 0.11.3 Configure VS Code extensions
  - [ ] 0.11.4 Document local environment setup

- [ ] 0.12 Define CI/CD approach and workflow standards
  - [ ] 0.12.1 Select pipeline provider (GitHub Actions)
  - [ ] 0.12.2 Define workflow naming conventions
  - [ ] 0.12.3 Define workflow folder structure

- [ ] 0.13 Create initial project roadmap and milestones
- [ ] 0.14 Prepare work item import templates (optional)
- [ ] 0.15 Validate alignment with CAF and AVM standards
- [ ] 0.16 Document deviations required for cost reduction

## Phase 1. Bootstrap Identity

- [ ] 1.1 Create break-glass administrator account
  - [ ] 1.1.1 Configure MFA
  - [ ] 1.1.2 Store credentials securely

- [ ] 1.2 Create Cloud-Admins group and bootstrap administrator account
  - [ ] 1.2.1 Create Entra ID security group: Cloud-Admins
  - [ ] 1.2.2 Create bootstrap admin user account
  - [ ] 1.2.3 Assign directory roles to bootstrap account

- [ ] 1.3 Define GitHub OIDC trust model for platform deployments
  - [ ] 1.3.1 Define GitHub environments (dev, test, prod)
  - [ ] 1.3.2 Create federated credentials in Entra ID
  - [ ] 1.3.3 Assign minimal RBAC to federated identities

- [ ] 1.4 Assign minimal RBAC required for bootstrap operations
  - [ ] 1.4.1 Assign Owner/Contributor on platform MG or subscriptions

- [ ] 1.5 Create initial management group hierarchy (empty)
  - [ ] 1.5.1 Root
  - [ ] 1.5.2 Platform
  - [ ] 1.5.3 LandingZones
  - [ ] 1.5.4 Sandbox

- [ ] 1.6 Create or link required subscriptions
  - [ ] 1.6.1 Assign subscriptions to MGs

- [ ] 1.7 Define Bicep deployment model
  - [ ] 1.7.1 Define per-stack main.bicep entrypoints
  - [ ] 1.7.2 Define parameter file strategy per environment

- [ ] 1.8 Validate authentication paths for GitHub Actions and local tooling
  - [ ] 1.8.1 Test az login
  - [ ] 1.8.2 Test GitHub OIDC workflow login

- [ ] 1.9 Document bootstrap identity and access model
- [ ] 1.10 Create ADRs for bootstrap identity decisions

## Phase 2. DevOps and CI/CD Foundation (GitHub)

- [ ] 2.0 Define DevOps-Admins / Platform-Engineers group responsibilities
  - [ ] 2.0.1 Create Entra ID security group if required
  - [ ] 2.0.2 Document who can modify workflows and environments

- [ ] 2.1 Create reusable GitHub Actions components
  - [ ] 2.1.1 Create Bicep deploy composite action (optional)
  - [ ] 2.1.2 Create environment selection pattern

- [ ] 2.2 Implement validation workflow
  - [ ] 2.2.1 Bicep build/validate
  - [ ] 2.2.2 Linting (bicep linter, markdownlint)

- [ ] 2.3 Implement deployment workflow
  - [ ] 2.3.1 Use OIDC to obtain Azure token
  - [ ] 2.3.2 Deploy Bicep templates
  - [ ] 2.3.3 Capture deployment outputs

- [ ] 2.4 Configure GitHub environments for platform subscriptions
  - [ ] 2.4.1 Map environments to subscriptions
  - [ ] 2.4.2 Configure environment protection rules

- [ ] 2.5 Configure workflow permissions and RBAC boundaries
  - [ ] 2.5.1 Restrict who can run deployments
  - [ ] 2.5.2 Restrict who can modify workflows

- [ ] 2.6 Validate workflow execution with placeholder Bicep
  - [ ] 2.6.1 Create minimal main.bicep
  - [ ] 2.6.2 Run full workflow

- [ ] 2.7 Document CI/CD architecture
- [ ] 2.8 Create ADRs for CI/CD decisions

## Phase 3. Governance and Policy Foundation

- [ ] 3.1 Select vendor-approved governance modules/patterns
  - [ ] 3.1.1 AVM governance modules
  - [ ] 3.1.2 ESLZ governance patterns

- [ ] 3.2 Define custom policy definitions
  - [ ] 3.2.1 Required tags
  - [ ] 3.2.2 Allowed locations
  - [ ] 3.2.3 Diagnostic settings

- [ ] 3.3 Define policy assignments at MG level
  - [ ] 3.3.1 Platform MG assignments
  - [ ] 3.3.2 LandingZones MG assignments
  - [ ] 3.3.3 Sandbox MG assignments

- [ ] 3.4 Define initiatives and initiative assignments
  - [ ] 3.4.1 Create initiative definitions
  - [ ] 3.4.2 Assign initiatives

- [ ] 3.5 Define tagging enforcement policies
- [ ] 3.6 Define diagnostic settings baseline
  - [ ] 3.6.1 Activity logs
  - [ ] 3.6.2 Resource logs

- [ ] 3.7 Define resource locks for critical resources
- [ ] 3.8 Define RBAC assignments for governance layer
- [ ] 3.9 Define policy exemptions

- [ ] 3.10 Implement governance Bicep structure
  - [ ] 3.10.1 Create platform/governance folder
  - [ ] 3.10.2 Add module calls from modules/policy
  - [ ] 3.10.3 Add parameters and outputs

- [ ] 3.11 Deploy governance through GitHub Actions
- [ ] 3.12 Document governance architecture
- [ ] 3.13 Create ADRs for governance decisions

## Phase 4. Networking and Connectivity

- [ ] 4.1 Select vendor-approved network modules
- [ ] 4.2 Design hub network topology
  - [ ] 4.2.1 Address space
  - [ ] 4.2.2 Subnet layout
  - [ ] 4.2.3 Security zones
- [ ] 4.3 Define address spaces and segmentation
- [ ] 4.4 Configure hub virtual network and subnets
- [ ] 4.5 Configure NSGs and baseline rules
- [ ] 4.6 Configure private DNS zones
- [ ] 4.7 Implement networking Bicep structure
- [ ] 4.8 Deploy networking through GitHub Actions
- [ ] 4.9 Document network architecture
- [ ] 4.10 Create ADRs for networking decisions

## Phase 5. Shared Services Platform

- [ ] 5.1 Select vendor modules for shared services
- [ ] 5.2 Deploy Log Analytics workspace
- [ ] 5.3 Deploy diagnostic storage accounts
- [ ] 5.4 Deploy Key Vault for platform secrets
- [ ] 5.5 Deploy monitoring baseline
- [ ] 5.6 Implement shared services Bicep structure
- [ ] 5.7 Deploy shared services through GitHub Actions
- [ ] 5.8 Document shared services architecture
- [ ] 5.9 Create ADRs for shared services decisions
- [ ] 5.10 Deploy admin ingress components (optional)
- [ ] 5.11 Configure SSH key generation and storage in Key Vault
- [ ] 5.12 Restrict access appropriately
- [ ] 5.13 Document access model and operational entry points

## Phase 6. Platform Identity

- [ ] 6.1 Select vendor identity modules/patterns
- [ ] 6.2 Define managed identities for platform services
  - [ ] 6.2.1 Shared services MI
  - [ ] 6.2.2 Networking MI
- [ ] 6.3 Define workload identity patterns
  - [ ] 6.3.1 User-assigned MI
  - [ ] 6.3.2 System-assigned MI
- [ ] 6.4 Define identity-related RBAC assignments
- [ ] 6.5 Define identity-related policy assignments
- [ ] 6.6 Implement identity Bicep structure
- [ ] 6.7 Deploy platform identity through GitHub Actions
- [ ] 6.8 Document platform identity architecture
- [ ] 6.9 Create ADRs for identity decisions

## Phase 7. Utility Engineering

- [ ] 7.1 Create managed identity for automation
- [ ] 7.2 Assign RBAC for automation operations
- [ ] 7.3 Implement manual start/stop workflows (if required)
- [ ] 7.4 Implement time-based shutdown/destroy logic
- [ ] 7.5 Configure logging and diagnostics for automation components
- [ ] 7.6 Document utility automation architecture
- [ ] 7.7 Create ADRs for utility engineering decisions

## Phase 8. Workload Landing Zone Template

- [ ] 8.1 Select vendor modules for workload networks
- [ ] 8.2 Define workload subscription structure
- [ ] 8.3 Implement workload virtual network and security baseline
- [ ] 8.4 Configure workload diagnostic settings
- [ ] 8.5 Implement workload Bicep structure
- [ ] 8.6 Deploy workload landing zone through GitHub Actions
- [ ] 8.7 Document workload landing zone pattern
- [ ] 8.8 Create ADRs for workload landing zone design

## Phase 9. Documentation and Operational Readiness

- [ ] 9.1 Write platform overview documentation
- [ ] 9.2 Write identity and access documentation
- [ ] 9.3 Write governance and policy documentation
- [ ] 9.4 Write network and connectivity documentation
- [ ] 9.5 Write shared services documentation
- [ ] 9.6 Write CI/CD documentation
- [ ] 9.7 Write operational runbooks
- [ ] 9.8 Write onboarding guide
- [ ] 9.9 Finalise ADRs and archive superseded decisions

## Phase 10. Validation and Review

- [ ] 10.1 Validate platform deployment end to end
- [ ] 10.2 Validate RBAC and access boundaries
- [ ] 10.3 Validate policy enforcement
- [ ] 10.4 Validate network segmentation
- [ ] 10.5 Validate monitoring and diagnostics
- [ ] 10.6 Validate CI/CD workflows
- [ ] 10.7 Conduct cost review and optimise
- [ ] 10.8 Document validation results

## Phase 11. Finalisation

- [ ] 11.1 Clean up repo and ensure lint compliance
- [ ] 11.2 Tag initial release version
- [ ] 11.3 Archive planning artefacts
- [ ] 11.4 Prepare final documentation set
- [ ] 11.5 Review project against objectives
- [ ] 11.6 Close out project
