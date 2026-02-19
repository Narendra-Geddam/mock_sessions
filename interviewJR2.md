## INTERVIEW QUESTION 1: Intro

## Direct Interview Answer
My name is Narendra Geddam, and I am a DevOps Engineer with hands-on experience in designing, implementing, and managing CI/CD pipelines, Kubernetes-based deployments, and AWS cloud infrastructure. My primary focus is on automating software delivery, ensuring high availability, improving deployment reliability, and maintaining production-grade Kubernetes environments using tools such as Jenkins, Docker, Helm, Amazon EKS, Terraform, and Git.

I work extensively with containerization, orchestration, infrastructure as code, deployment automation, monitoring, and troubleshooting distributed systems in production environments.

---

## Concept Definition
An introduction in a DevOps interview establishes your professional identity, technical expertise, infrastructure exposure, and operational responsibilities.

It provides the interviewer with:

- Your technical specialization
- Your infrastructure exposure level
- Your production environment experience
- Your ownership areas

---

## Why This Exists
This question helps interviewers evaluate:

- Whether you have real production experience
- Whether your experience aligns with their infrastructure
- Your depth in DevOps lifecycle management

---

## Internal Working Mechanism (Step-by-Step)

A strong DevOps introduction must include:

Step 1: Role Identity  
DevOps Engineer responsible for automation and infrastructure.

Step 2: Toolchain Exposure  
Mention tools:

Git  
Jenkins  
Docker  
Kubernetes  
Helm  
Terraform  
AWS  

Step 3: Infrastructure Scope  
Mention infrastructure scale:

Production clusters  
CI/CD pipelines  
Cloud environments  

Step 4: Ownership Areas  

CI/CD pipeline management  
Deployment automation  
Cluster management  
Monitoring and troubleshooting  

---

## Architecture-Level Explanation

Typical infrastructure you manage:

Developer → Git → Jenkins → Docker Build → Image Registry → Helm Deployment → EKS Cluster → Load Balancer → Users

You operate and automate this entire flow.

---

## Production Scenario Example

In production:

- Developers push code to Git
- Jenkins automatically builds Docker image
- Helm deploys image to EKS cluster
- Kubernetes manages scaling and availability

You ensure:

Deployment reliability  
Zero downtime  
Fast rollback  

---

## Failure Scenario and Troubleshooting

Weak introduction failure:

Symptom:
Interviewer cannot identify your experience level

Fix:

Use structured format:

Role → Tools → Infrastructure → Responsibilities → Production exposure

---

## Interview Follow-Up Questions and Answers

Q: Do you work more on development or operations?

Answer:
My role focuses on infrastructure automation, CI/CD pipeline management, Kubernetes deployment automation, and production troubleshooting.

---

## Best Practices

Always include:

Role  
Tools  
Cloud platform  
Kubernetes experience  
CI/CD responsibility  
Production exposure  

Never give generic answers.

---

Cognitive Checkpoint for Narendra:

Explain your introduction in exactly this structured format:

Role → Tools → Infrastructure → Responsibilities → Production exposure


## INTERVIEW QUESTION 2: Your roles and responsibilities

## Direct Interview Answer

My roles and responsibilities include designing and managing CI/CD pipelines, containerizing applications using Docker, deploying applications using Helm into Kubernetes clusters running on Amazon EKS, managing infrastructure using Terraform, monitoring applications using Prometheus and Grafana, and troubleshooting production issues to ensure high availability and reliability.

I am also responsible for automating deployments, managing Kubernetes cluster health, performing rolling updates, handling rollbacks, and ensuring secure and efficient application delivery.

---

## Concept Definition

Roles and responsibilities define your operational ownership areas in DevOps lifecycle:

Build automation  
Deployment automation  
Infrastructure management  
Monitoring  
Troubleshooting  

---

## Why This Exists

DevOps exists to:

Automate software delivery  
Reduce deployment failures  
Increase deployment frequency  
Improve system reliability  

---

## Internal Working Mechanism (Step-by-Step)

Your responsibilities exist across multiple layers:

Layer 1: Source Control

Manage Git repositories  
Branch management  

Layer 2: Build Automation

Jenkins builds applications  
Docker images created  

Layer 3: Deployment Automation

Helm deploys to Kubernetes  

Layer 4: Infrastructure Management

Terraform creates infrastructure  

Layer 5: Cluster Management

Manage EKS cluster  
Scaling  
Troubleshooting  

Layer 6: Monitoring

Prometheus collects metrics  
Grafana visualization  

---

## Architecture-Level Explanation

DevOps responsibility spans entire pipeline:

Git → Jenkins → Docker → Registry → Helm → Kubernetes → LoadBalancer → Monitoring

You manage each stage.

---

## Production Scenario Example

When developer pushes code:

Jenkins automatically builds  
Docker image created  
Helm deploys new version  
Kubernetes updates pods  

You monitor and verify deployment success.

---

## Failure Scenario and Troubleshooting

Problem:
Deployment failed

Root cause could be:

Image pull failure  
Pod crash  
Configuration error  

Fix:

Check:

kubectl get pods  
kubectl describe pod  
kubectl logs  

---

## Interview Follow-Up Questions and Answers

Q: What is your most critical responsibility?

Answer:
Ensuring reliable, automated, and zero-downtime deployments in production Kubernetes environments.

---

## Best Practices

Automate everything  
Avoid manual deployments  
Use Infrastructure as Code  
Implement monitoring  

---

Cognitive Checkpoint for Narendra:

Which layers of infrastructure do you fully manage in your current role?


## INTERVIEW QUESTION 3: Explain your CI/CD pipeline

## Direct Interview Answer

Our CI/CD pipeline starts when developers push code to Git. Jenkins automatically triggers a pipeline that builds the application, creates a Docker image, scans it for vulnerabilities, pushes it to Amazon ECR, and deploys it to Amazon EKS using Helm. Kubernetes performs rolling updates to ensure zero downtime deployment. Monitoring tools such as Prometheus and Grafana are used to verify deployment health.

---

## Concept Definition

CI/CD pipeline is an automated workflow that builds, tests, and deploys applications.

CI = Continuous Integration  
CD = Continuous Deployment

---

## Why This Exists

CI/CD solves:

Manual deployment errors  
Slow deployment  
Inconsistent environments  

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Developer Push

Code pushed to Git

Step 2: Jenkins Trigger

Webhook triggers Jenkins pipeline

Step 3: Build Stage

Application compiled

Step 4: Docker Build

Docker image created

Step 5: Security Scan

Trivy scans image

Step 6: Image Push

Image pushed to Amazon ECR

Step 7: Helm Deployment

Helm deploys image to EKS

Step 8: Kubernetes Rolling Update

Pods replaced gradually

---

## Architecture-Level Explanation

Pipeline architecture:

Developer  
↓  
Git  
↓  
Jenkins  
↓  
Docker  
↓  
Amazon ECR  
↓  
Helm  
↓  
Amazon EKS  
↓  
LoadBalancer  
↓  
Users

---

## Production Scenario Example

Deployment happens automatically after Git push.

No manual intervention required.

---

## Failure Scenario and Troubleshooting

Failure example:

Image not deploying

Check:

kubectl get pods  
kubectl describe pod  

Check Helm release:

helm list  

---

## Interview Follow-Up Questions and Answers

Q: What ensures zero downtime deployment?

Answer:
Kubernetes rolling update strategy ensures pods are replaced gradually without downtime.

---

## Best Practices

Always use automated pipeline  
Use container registry  
Use rolling deployments  
Use monitoring  

---

Cognitive Checkpoint for Narendra:

Explain full flow from Git push to deployment in EKS cluster.

## INTERVIEW QUESTION 4: Which Helm repository are you using?

## Direct Interview Answer

We use an internal Helm repository to store and manage our Helm charts. This repository is hosted either in Amazon ECR as an OCI-compliant Helm registry or in an artifact management system such as Nexus or Artifactory. Our CI/CD pipeline pushes versioned Helm charts to this repository, and during deployment, Jenkins or ArgoCD pulls the charts from this repository and deploys them to the Amazon EKS cluster.

---

## Concept Definition

A Helm repository is a centralized storage location where Helm charts are stored, versioned, and distributed.

It acts like:

Docker Hub → for Docker images  
Helm Repo → for Helm charts  

Helm charts define Kubernetes application deployment configurations.

---

## Why This Exists

Helm repository solves these problems:

Version control of deployments  
Centralized chart management  
Reusable deployments  
Consistent environment configuration  

Without Helm repo:

Deployment configuration becomes unmanageable  
No version tracking  
Difficult rollback  

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Helm chart is created

Example structure:

Chart.yaml  
values.yaml  
templates/

Step 2: Chart is packaged

Command:

helm package myapp

Output:

myapp-1.0.0.tgz

Step 3: Chart pushed to Helm repository

Example:

helm push myapp-1.0.0.tgz oci://<ECR repo>

Step 4: During deployment

Helm pulls chart:

helm install myapp oci://repo/myapp

---

## Architecture-Level Explanation

Pipeline flow:

Developer  
↓  
Git Repo  
↓  
Jenkins Pipeline  
↓  
Helm Package  
↓  
Helm Repo (ECR / Nexus)  
↓  
Helm Pull  
↓  
EKS Deployment  

---

## Production Scenario Example

Your organization maintains multiple versions:

myapp-1.0.0  
myapp-1.1.0  
myapp-2.0.0  

You deploy specific version to production.

Rollback becomes easy.

---

## Failure Scenario and Troubleshooting

Problem:

Helm cannot pull chart

Root cause:

Repository not added

Fix:

helm repo add myrepo <repo-url>  
helm repo update  

---

## Interview Follow-Up Questions and Answers

Q: Can Helm repo store multiple versions?

Answer:
Yes. Helm repository supports versioning, allowing multiple chart versions and enabling rollback.

---

## Best Practices

Use versioned charts  
Use secure private repository  
Avoid storing charts locally  

---

Cognitive Checkpoint for Narendra:

Where is your Helm repository hosted? ECR, Nexus, or Artifactory?



## INTERVIEW QUESTION 5: In what step are you generating Helm repo?

## Direct Interview Answer

Helm chart packaging and pushing to the Helm repository happens during the CI pipeline stage after the Docker image is built and pushed to the container registry. Jenkins packages the Helm chart using the new image tag and pushes it to the Helm repository before triggering deployment to the Kubernetes cluster.

---

## Concept Definition

Helm chart generation happens during CI stage.

It prepares deployment configuration.

---

## Why This Exists

Helm chart must include correct image version.

Example:

image:
  repository: myapp
  tag: v1.0.0

Without updating Helm chart, Kubernetes deploys wrong version.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Docker image build

docker build -t myapp:v1.0.0 .

Step 2: Push image to registry

docker push myapp:v1.0.0

Step 3: Update Helm values.yaml

image:
  tag: v1.0.0

Step 4: Package Helm chart

helm package myapp

Step 5: Push chart to Helm repo

helm push myapp-1.0.0.tgz

---

## Architecture-Level Explanation

Pipeline:

Git push  
↓  
Jenkins  
↓  
Docker build  
↓  
Image push to ECR  
↓  
Helm package  
↓  
Helm repo push  
↓  
Deployment  

---

## Production Scenario Example

Every commit generates:

New Docker image  
New Helm chart version  

Ensures correct deployment.

---

## Failure Scenario and Troubleshooting

Problem:

Wrong version deployed

Cause:

Helm chart using old image tag

Fix:

Update values.yaml

---

## Interview Follow-Up Questions and Answers

Q: Why not deploy Docker image directly?

Answer:
Helm manages deployment configuration, scaling, service, and environment variables.

---

## Best Practices

Always version Helm charts  
Sync image version with Helm chart  

---

## INTERVIEW QUESTION 6: How do you process from dev to prod?

## Direct Interview Answer

The deployment process follows a multi-environment promotion model. Developers push code to Git, triggering CI pipeline in Jenkins. The application is built, containerized, scanned, and deployed first into the Dev environment. After validation, the same Helm chart and image are promoted to Test, Stage, and finally Production environments using controlled approval gates and deployment pipelines.

---

## Concept Definition

Environment promotion = deploying same artifact across environments.

Dev → Test → Stage → Prod

---

## Why This Exists

Prevents production failures.

Testing ensures stability.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Developer push

Triggers CI

Step 2: Dev deployment

Testing happens

Step 3: Test deployment

Integration testing

Step 4: Stage deployment

Pre-production validation

Step 5: Production deployment

Live traffic

---

## Architecture-Level Explanation

Pipeline:

Git  
↓  
Jenkins  
↓  
ECR  
↓  
Helm  
↓  
Dev cluster  
↓  
Test cluster  
↓  
Stage cluster  
↓  
Prod cluster  

---

## Production Scenario Example

Bug found in Dev → fixed before Prod.

---

## Failure Scenario and Troubleshooting

Problem:

Production failure

Solution:

Rollback using Helm.

---

## Interview Follow-Up Questions and Answers

Q: Do you rebuild image for each environment?

Answer:
No. Same image promoted across environments to ensure consistency.

---

## Best Practices

Never rebuild image per environment  
Promote same artifact  

---

Cognitive Checkpoint for Narendra:

Why should you promote same artifact instead of rebuilding?




## INTERVIEW QUESTION 7: Where is Helm build happening?

## Direct Interview Answer

Helm chart packaging happens inside the CI pipeline, typically in Jenkins. Jenkins pulls the Helm chart source code from Git, updates the image tag dynamically, packages the chart using helm package command, and pushes it to the Helm repository.

---

## Concept Definition

Helm build = Helm chart packaging.

---

## Why This Exists

Ensures deployment automation.

---

## Internal Working Mechanism

Jenkins executes:

helm package myapp

---

## Architecture-Level Explanation

Jenkins → Helm build → Helm repo → EKS deployment

---

## Production Scenario Example

Fully automated pipeline builds Helm chart.

---

## Failure Scenario and Troubleshooting

Helm command fails → check Jenkins logs.

---

## Best Practices

Always automate Helm packaging.

---

Cognitive Checkpoint for Narendra:

Why should Helm packaging happen in CI and not manually?

## INTERVIEW QUESTION 8: What are you using to scan Helm artifacts?

## Direct Interview Answer

We use security scanning tools such as Trivy to scan Helm artifacts and the Docker images referenced in the Helm charts. Trivy scans Helm charts for misconfigurations, vulnerabilities, and insecure Kubernetes configurations. This scanning happens during the CI pipeline before deployment to ensure that only secure and compliant Helm charts are deployed to the EKS cluster.

---

## Concept Definition

Helm artifact scanning is the process of analyzing Helm charts and referenced container images to detect:

Security vulnerabilities  
Misconfigurations  
Compliance violations  

This ensures secure Kubernetes deployments.

---

## Why This Exists

Helm charts define critical infrastructure configurations such as:

Container image  
Secrets  
Security context  
Network policies  

If misconfigured, it can expose:

Root access  
Public services  
Privilege escalation  

Scanning prevents production security breaches.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Jenkins builds Docker image

Step 2: Jenkins runs Trivy scan

Example:

trivy image myapp:v1.0.0

Step 3: Scan Helm chart

Example:

trivy config ./helm-chart/

Step 4: Detect issues such as:

Privilege escalation  
Root container  
Public exposure  

Step 5: Pipeline fails if vulnerability detected

---

## Architecture-Level Explanation

Pipeline flow:

Git  
↓  
Jenkins  
↓  
Docker build  
↓  
Trivy scan  
↓  
Helm package  
↓  
Helm repo  
↓  
EKS deployment  

---

## Production Scenario Example

If Helm chart contains:

privileged: true

Trivy detects and blocks deployment.

---

## Failure Scenario and Troubleshooting

Problem:

Deployment blocked

Cause:

Critical vulnerability detected

Fix:

Modify Helm chart security settings

---

## Interview Follow-Up Questions and Answers

Q: Can Helm charts introduce vulnerabilities?

Answer:
Yes. Helm charts define container security context, network exposure, and access permissions. Misconfigurations can introduce vulnerabilities.

---

## Best Practices

Always scan Helm charts  
Always scan container images  
Fail pipeline on critical vulnerabilities  

---

Cognitive Checkpoint for Narendra:

What happens if a vulnerable Helm chart is deployed without scanning?



## INTERVIEW QUESTION 9: How to upgrade Helm to new version?

## Direct Interview Answer

Helm can be upgraded by downloading the latest binary from the official Helm repository or using a package manager. In production environments, Helm upgrade should be done carefully to ensure compatibility with existing Kubernetes clusters and Helm releases.

Example upgrade using script:

curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

---

## Concept Definition

Helm upgrade means updating Helm CLI version.

Not upgrading application.

Helm CLI manages Kubernetes deployments.

---

## Why This Exists

New Helm versions provide:

Bug fixes  
Security patches  
New features  
Performance improvements  

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Check current version

helm version

Step 2: Download latest version

curl script install

Step 3: Replace Helm binary

Step 4: Verify installation

helm version

---

## Architecture-Level Explanation

Helm CLI interacts with:

Kubernetes API Server  
Helm repository  

Upgrading Helm improves deployment reliability.

---

## Production Scenario Example

Older Helm version may fail with new Kubernetes version.

Upgrade ensures compatibility.

---

## Failure Scenario and Troubleshooting

Problem:

Helm commands failing

Cause:

Version incompatibility

Fix:

Upgrade Helm CLI

---

## Interview Follow-Up Questions and Answers

Q: Does Helm upgrade affect running applications?

Answer:
No. Helm CLI upgrade does not affect running deployments.

---

## Best Practices

Test Helm upgrade in staging  
Verify compatibility  

---

## INTERVIEW QUESTION 10: How to verify everything is working fine in EKS?

## Direct Interview Answer

To verify deployment health in EKS, I check the status of pods, services, deployments, and logs using kubectl commands. I also monitor application health using Prometheus and Grafana dashboards and verify load balancer accessibility.

Key commands:

kubectl get pods  
kubectl get svc  
kubectl get deployments  
kubectl logs <pod>

---

## Concept Definition

Verification ensures:

Application running  
Pods healthy  
Service accessible  

---

## Why This Exists

Deployment success must be validated before production usage.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Check pod status

kubectl get pods

Step 2: Check service

kubectl get svc

Step 3: Check deployment

kubectl get deployment

Step 4: Check logs

kubectl logs pod-name

Step 5: Check load balancer access

---

## Architecture-Level Explanation

Verification checks:

Pod → Service → LoadBalancer → User access

---

## Production Scenario Example

After deployment:

Pods must be Running  
Service must be Active  

---

## Failure Scenario and Troubleshooting

Problem:

Pod CrashLoopBackOff

Fix:

Check logs

kubectl logs pod-name

---

## Interview Follow-Up Questions and Answers

Q: What is first thing to check after deployment?

Answer:
Pod status using kubectl get pods.

---

## Best Practices

Always verify after deployment  
Monitor logs and metrics  

---

Cognitive Checkpoint for Narendra:

What command helps identify failing pods immediately?



## INTERVIEW QUESTION 11: Explain deployment strategies

## Direct Interview Answer

Deployment strategies define how application updates are rolled out in Kubernetes. Common strategies include Rolling Update, Blue-Green Deployment, and Canary Deployment. These strategies ensure zero downtime and safe application updates by gradually replacing old versions with new versions.

---

## Concept Definition

Deployment strategy defines update process.

Controls:

Traffic flow  
Pod replacement  
Rollback capability  

---

## Why This Exists

Prevents downtime during deployment.

---

## Internal Working Mechanism

Kubernetes creates new pods gradually.

Old pods terminated safely.

---

## Architecture-Level Explanation

LoadBalancer distributes traffic across pods.

New pods replace old pods safely.

---

## Production Scenario Example

Rolling update replaces pods gradually.

---

## Failure Scenario and Troubleshooting

Deployment failure → rollback.

---

## Interview Follow-Up Questions and Answers

Q: Which strategy is default?

Answer:
Rolling update is default Kubernetes strategy.

---

## Best Practices

Use rolling update  
Use readiness probes  

---

Cognitive Checkpoint for Narendra:

Why is rolling update safer than recreate strategy?

## INTERVIEW QUESTION 12: What is the strategy you are using?

## Direct Interview Answer

We use the Rolling Update deployment strategy in Kubernetes, managed through Helm deployments in our Amazon EKS cluster. This strategy ensures zero downtime by gradually replacing old pods with new pods while maintaining application availability. Kubernetes ensures that a minimum number of pods remain available during the update using parameters such as maxUnavailable and maxSurge.

---

## Concept Definition

Rolling Update is the default Kubernetes deployment strategy where:

Old pods are replaced gradually  
New pods are created incrementally  
Traffic shifts automatically  

---

## Why This Exists

To ensure:

Zero downtime  
High availability  
Safe updates  

Without Rolling Update:

Application downtime occurs during deployment.

---

## Internal Working Mechanism (Step-by-Step)

Example:

Deployment has 4 pods.

Step 1: Kubernetes creates 1 new pod

Total pods = 5

Step 2: New pod becomes Ready

Step 3: Kubernetes deletes 1 old pod

Total pods = 4

Step 4: Repeat until all pods replaced

---

## Architecture-Level Explanation

Traffic flow:

LoadBalancer  
↓  
Service  
↓  
Old Pods + New Pods  

Service automatically routes traffic only to Ready pods.

---

## Production Scenario Example

Application running with 10 pods.

Rolling update replaces pods gradually without downtime.

---

## Failure Scenario and Troubleshooting

Problem:

New pods failing

Kubernetes stops rollout automatically.

Command to check:

kubectl rollout status deployment myapp

---

## Interview Follow-Up Questions and Answers

Q: How does Kubernetes ensure availability during rolling update?

Answer:
Using maxUnavailable and maxSurge settings.

---

## Best Practices

Always use readiness probes  
Use rolling updates for production  

---

Cognitive Checkpoint for Narendra:

If you have 10 pods and maxUnavailable=2, how many pods can be unavailable during update?



## INTERVIEW QUESTION 13: How to do rolling updates in EKS?

## Direct Interview Answer

Rolling updates in EKS are performed automatically when a new Docker image version is deployed using Helm or kubectl. Kubernetes Deployment resource manages the rolling update process by gradually replacing old pods with new pods while maintaining availability.

Example command:

helm upgrade myapp ./chart --set image.tag=v2

---

## Concept Definition

Rolling update replaces pods gradually.

Managed by Kubernetes Deployment controller.

---

## Why This Exists

Ensures continuous service availability during updates.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Update deployment image

Step 2: Kubernetes creates new pods

Step 3: New pods pass readiness probe

Step 4: Old pods terminated

Step 5: Repeat until complete

---

## Architecture-Level Explanation

Deployment controller manages pod replacement.

Service routes traffic to healthy pods.

---

## Production Scenario Example

Deploy new version using Helm upgrade.

Kubernetes performs rolling update automatically.

---

## Failure Scenario and Troubleshooting

Check rollout status:

kubectl rollout status deployment myapp

Rollback if failure:

kubectl rollout undo deployment myapp

---

## Interview Follow-Up Questions and Answers

Q: What component controls rolling updates?

Answer:
Deployment Controller.

---

## Best Practices

Always use Helm upgrade  
Never delete and recreate deployment  

---

## INTERVIEW QUESTION 14: What is pod lifecycle?

## Direct Interview Answer

Pod lifecycle defines the sequence of states a pod goes through from creation to termination. The main phases include Pending, Running, Succeeded, Failed, and Terminated. Kubernetes manages pod lifecycle through the kubelet and scheduler.

---

## Concept Definition

Pod lifecycle = Pod state transitions.

States include:

Pending  
Running  
Succeeded  
Failed  

---

## Why This Exists

Helps Kubernetes manage pod execution and health.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Pod created

State = Pending

Step 2: Pod scheduled to node

Step 3: Container starts

State = Running

Step 4: Pod completes or fails

State = Succeeded or Failed

---

## Architecture-Level Explanation

Flow:

API Server  
↓  
Scheduler assigns node  
↓  
Kubelet runs container  

---

## Production Scenario Example

Application deployed → pod transitions to Running state.

---

## Failure Scenario and Troubleshooting

Pod stuck in Pending → insufficient resources.

Check:

kubectl describe pod pod-name

---

## Interview Follow-Up Questions and Answers

Q: Which component starts container?

Answer:
Kubelet.

---

## Best Practices

Always monitor pod lifecycle states.

---

Cognitive Checkpoint for Narendra:

Which Kubernetes component assigns pod to node?



## INTERVIEW QUESTION 15: What is difference between Ready and Running?

## Direct Interview Answer

Running means the container is started and running, but Ready means the pod is fully prepared to receive traffic. A pod can be Running but not Ready if readiness probes have not passed. Kubernetes sends traffic only to Ready pods, not just Running pods.

---

## Concept Definition

Running = container started  
Ready = ready to serve traffic  

---

## Why This Exists

Prevents sending traffic to unhealthy pods.

---

## Internal Working Mechanism

Pod starts → Running

Readiness probe checks health → Ready

---

## Architecture-Level Explanation

Service routes traffic only to Ready pods.

---

## Production Scenario Example

Application initializing → Running but not Ready.

After initialization → Ready.

---

## Failure Scenario and Troubleshooting

Pod Running but not Ready → readiness probe failing.

Check:

kubectl describe pod pod-name

---

## Interview Follow-Up Questions and Answers

Q: Does Kubernetes send traffic to Running pod?

Answer:
No. Only Ready pods receive traffic.

---

## Best Practices

Always configure readiness probes.

---

Cognitive Checkpoint for Narendra:

Why is readiness probe critical in production?



## INTERVIEW QUESTION 16: What are probes and different types?

## Direct Interview Answer

Probes are Kubernetes health check mechanisms used to determine the status of a container. Kubernetes uses probes to check whether a container is alive, ready to accept traffic, or properly started. There are three types of probes: Liveness Probe, Readiness Probe, and Startup Probe. Liveness Probe checks if the container is alive, Readiness Probe checks if the container is ready to serve traffic, and Startup Probe checks if the application has started successfully.

---

## Concept Definition

Probe = Health check mechanism used by Kubernetes to monitor container health.

Types:

Liveness Probe → checks if container is alive  
Readiness Probe → checks if container ready to serve traffic  
Startup Probe → checks application startup completion  

---

## Why This Exists

Prevents sending traffic to unhealthy containers.

Allows automatic recovery.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Kubernetes creates pod

Step 2: Kubelet executes probe

Probe types:

HTTP probe  
TCP probe  
Command probe  

Step 3: Based on probe result:

Success → container healthy  
Failure → restart or remove from service  

---

## Architecture-Level Explanation

Probe flow:

Kubelet  
↓  
Probe check  
↓  
Container health decision  

Service sends traffic only if readiness probe succeeds.

---

## Production Scenario Example

Application crashed internally.

Liveness probe detects failure.

Kubernetes restarts container automatically.

---

## Failure Scenario and Troubleshooting

Pod continuously restarting.

Cause:

Liveness probe failing.

Check:

kubectl describe pod pod-name

---

## Interview Follow-Up Questions and Answers

Q: Which probe controls traffic routing?

Answer:
Readiness probe.

---

## Best Practices

Always configure readiness and liveness probes.

Avoid aggressive probe timing.

---

Cognitive Checkpoint for Narendra:

Which probe prevents traffic from reaching unhealthy containers?



## INTERVIEW QUESTION 17: Explain rolling updates step by step

## Direct Interview Answer

Rolling update replaces old pods with new pods gradually. Kubernetes creates new pods with the updated version, waits for them to become Ready, and then terminates old pods. This process continues until all pods are updated, ensuring zero downtime deployment.

---

## Concept Definition

Rolling update = gradual replacement of pods.

---

## Why This Exists

Ensures continuous availability during updates.

---

## Internal Working Mechanism (Step-by-Step)

Example: Deployment has 4 pods.

Step 1: Create 1 new pod

Total pods = 5

Step 2: New pod becomes Ready

Step 3: Delete 1 old pod

Total pods = 4

Step 4: Repeat until all replaced

---

## Architecture-Level Explanation

Service routes traffic only to Ready pods.

Traffic shifts gradually.

---

## Production Scenario Example

Application upgraded from v1 to v2 without downtime.

---

## Failure Scenario and Troubleshooting

Check rollout status:

kubectl rollout status deployment myapp

---

## Interview Follow-Up Questions and Answers

Q: Who manages rolling update?

Answer:
Deployment controller.

---

## Best Practices

Use readiness probes.

---

## INTERVIEW QUESTION 18: During rolling updates new request will go to new or old pods?

## Direct Interview Answer

During rolling updates, traffic is sent to both old and new pods, but only if they are in Ready state. Kubernetes Service distributes traffic among all Ready pods regardless of version. As new pods become Ready and old pods are terminated, traffic gradually shifts to new pods.

---

## Concept Definition

Traffic routing controlled by Kubernetes Service.

Only Ready pods receive traffic.

---

## Why This Exists

Ensures smooth traffic transition.

---

## Internal Working Mechanism

Service checks Ready pods.

Load balances traffic across Ready pods.

---

## Architecture-Level Explanation

Service → Ready Pods → Traffic distributed

---

## Production Scenario Example

Deployment has 3 old pods and 1 new pod.

Traffic distributed across all 4 Ready pods.

---

## Failure Scenario and Troubleshooting

New pods not receiving traffic.

Cause:

Readiness probe failing.

---

## Interview Follow-Up Questions and Answers

Q: Does Kubernetes send traffic to not Ready pods?

Answer:
No.

---

## Best Practices

Configure readiness probes properly.

---

Cognitive Checkpoint for Narendra:

If new pod is Running but not Ready, will it receive traffic?



## INTERVIEW QUESTION 19: What is sticky session and where do you configure it?

## Direct Interview Answer

Sticky session, also called session affinity, ensures that all requests from a specific client are routed to the same pod. It is configured at the load balancer or Kubernetes service level. In Kubernetes, session affinity can be enabled using Service configuration.

Example:

sessionAffinity: ClientIP

---

## Concept Definition

Sticky session ensures same client connects to same pod.

---

## Why This Exists

Required for stateful applications.

Example:

Login session handling.

---

## Internal Working Mechanism

Load balancer maps client IP to specific pod.

Future requests routed to same pod.

---

## Architecture-Level Explanation

Client → LoadBalancer → Same Pod

---

## Production Scenario Example

User logged into application.

Requests routed to same pod.

---

## Failure Scenario and Troubleshooting

User session lost.

Cause:

Sticky session not enabled.

---

## Interview Follow-Up Questions and Answers

Q: Where configured?

Answer:
Kubernetes Service or LoadBalancer.

---

## Best Practices

Use sticky sessions only when required.

Prefer stateless applications.

---

Cognitive Checkpoint for Narendra:

Why are stateless applications preferred over sticky session?


## INTERVIEW QUESTION 20: There is some issues in new deployment how to rollback?

## Direct Interview Answer

Rollback in Kubernetes can be performed using Helm or kubectl. If deployment was done using Helm, rollback can be performed using the helm rollback command, which restores the previous release version. If using kubectl, rollback can be done using kubectl rollout undo deployment command. Kubernetes stores deployment history and allows reverting to a previous stable version.

Example:

helm rollback myapp 1

or

kubectl rollout undo deployment myapp

---

## Concept Definition

Rollback = reverting application to previous stable version.

---

## Why This Exists

Prevents prolonged downtime due to faulty deployments.

Ensures quick recovery.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Helm stores release history

Example:

helm list

Step 2: View revision history

helm history myapp

Step 3: Rollback to previous version

helm rollback myapp <revision>

Step 4: Kubernetes replaces faulty pods with previous version pods

---

## Architecture-Level Explanation

Helm Release History  
↓  
Rollback command  
↓  
Deployment Controller  
↓  
Pod replacement  

---

## Production Scenario Example

New version causes application crash.

Rollback restores stable version within seconds.

---

## Failure Scenario and Troubleshooting

Rollback fails.

Cause:

Previous version unavailable.

Fix:

Always maintain Helm release history.

---

## Interview Follow-Up Questions and Answers

Q: How does Kubernetes know previous version?

Answer:
Deployment controller maintains ReplicaSet history.

---

## Best Practices

Always deploy using Helm  
Maintain version history  

---

Cognitive Checkpoint for Narendra:

Which resource stores deployment history: Pod, ReplicaSet, or Service?



## INTERVIEW QUESTION 21: Do you use manual or automatic rollback?

## Direct Interview Answer

We primarily use manual rollback using Helm rollback command after identifying deployment failure through monitoring and logs. However, Kubernetes also supports automatic rollback when integrated with deployment tools such as ArgoCD or when readiness probes fail and rollout is automatically paused.

---

## Concept Definition

Rollback types:

Manual rollback → engineer triggers rollback  
Automatic rollback → system triggers rollback  

---

## Why This Exists

Allows recovery from faulty deployments.

---

## Internal Working Mechanism

Manual rollback:

Engineer executes helm rollback

Automatic rollback:

Deployment controller detects failure

---

## Architecture-Level Explanation

Monitoring → Failure detection → Rollback triggered

---

## Production Scenario Example

Monitoring detects crash.

Engineer performs rollback.

---

## Failure Scenario and Troubleshooting

Rollback unavailable.

Cause:

No version history.

---

## Interview Follow-Up Questions and Answers

Q: Which rollback is safer?

Answer:
Automatic rollback reduces downtime.

---

## Best Practices

Implement automated rollback when possible.

---

## INTERVIEW QUESTION 22: Difference between Blue-Green and Canary deployment

## Direct Interview Answer

Blue-Green deployment involves maintaining two identical environments, Blue (current) and Green (new version). Traffic is switched completely from Blue to Green after validation. Canary deployment releases the new version gradually to a small percentage of users and increases traffic gradually after validation.

---

## Concept Definition

Blue-Green = full environment switch  
Canary = gradual traffic shift  

---

## Why This Exists

Reduces deployment risk.

---

## Internal Working Mechanism

Blue-Green:

Blue → current  
Green → new  
Switch traffic completely

Canary:

Deploy new version partially  
Gradually increase traffic

---

## Architecture-Level Explanation

Blue-Green:

LoadBalancer switches environments.

Canary:

LoadBalancer splits traffic.

---

## Production Scenario Example

Canary deploys new version to 10% users.

---

## Failure Scenario and Troubleshooting

New version failure → rollback traffic.

---

## Interview Follow-Up Questions and Answers

Q: Which is safer?

Answer:
Canary is safest because exposure is limited.

---

## Best Practices

Use Canary for critical systems.

---

Cognitive Checkpoint for Narendra:

Which deployment strategy exposes fewer users initially?




## INTERVIEW QUESTION 23: How to configure it?

## Direct Interview Answer

Blue-Green and Canary deployments can be configured using Kubernetes Deployments, Services, and Helm charts. Separate deployments are created for different versions, and traffic routing is controlled using Kubernetes Services or Ingress rules.

---

## Concept Definition

Traffic routing determines deployment strategy.

---

## Why This Exists

Controls application rollout safely.

---

## Internal Working Mechanism

Multiple deployments created.

Service routes traffic accordingly.

---

## Architecture-Level Explanation

Service → selects deployment version.

---

## Production Scenario Example

Service switches selector label.

---

## Failure Scenario and Troubleshooting

Wrong selector → traffic routing failure.

---

## Best Practices

Use Helm to manage deployments.

---


## INTERVIEW QUESTION 24: Advantages and disadvantages of Blue-Green and Canary deployment

## Direct Interview Answer

Blue-Green deployment provides instant rollback capability and complete environment isolation, but it requires double infrastructure cost because both environments must run simultaneously. Canary deployment reduces risk by exposing the new version to a small subset of users, but it requires more complex traffic management and monitoring.

---

## Concept Definition

Blue-Green and Canary are deployment risk mitigation strategies.

Blue-Green = full environment switch  
Canary = gradual rollout  

---

## Why This Exists

Minimizes production deployment failures.

Protects users from faulty releases.

---

## Internal Working Mechanism (Step-by-Step)

Blue-Green:

Step 1: Blue environment running production

Step 2: Green environment deployed with new version

Step 3: Traffic switched from Blue to Green

Step 4: Blue becomes standby environment

Canary:

Step 1: Deploy new version alongside old version

Step 2: Route small percentage traffic

Step 3: Monitor health and metrics

Step 4: Gradually increase traffic

---

## Architecture-Level Explanation

Blue-Green:

LoadBalancer → Blue OR Green

Canary:

LoadBalancer → Blue + Green (traffic split)

---

## Production Scenario Example

Blue-Green used during major releases.

Canary used during risky releases.

---

## Failure Scenario and Troubleshooting

Canary failure:

Stop rollout immediately.

Blue-Green failure:

Switch traffic back instantly.

---

## Interview Follow-Up Questions and Answers

Q: Which provides instant rollback?

Answer:
Blue-Green deployment.

---

## Best Practices

Use Canary for gradual rollout  
Use Blue-Green for instant rollback  

---

Cognitive Checkpoint for Narendra:

Which deployment strategy requires double infrastructure?



## INTERVIEW QUESTION 25: Where do you define Blue-Green in Helm?

## Direct Interview Answer

Blue-Green deployment in Helm is defined using separate Kubernetes Deployments and Services with different labels and selectors. Helm values.yaml and templates are configured to deploy two versions of the application, and traffic switching is controlled by updating the Service selector or Ingress routing configuration.

---

## Concept Definition

Helm manages Blue-Green using labels and selectors.

---

## Why This Exists

Allows controlled traffic switching between versions.

---

## Internal Working Mechanism (Step-by-Step)

Example Helm labels:

Blue deployment:

app: myapp
version: blue

Green deployment:

app: myapp
version: green

Service selector:

version: blue

Switch to green by updating selector:

version: green

---

## Architecture-Level Explanation

Service routes traffic based on label selector.

---

## Production Scenario Example

Switch from Blue to Green instantly.

---

## Failure Scenario and Troubleshooting

Traffic not switching.

Cause:

Incorrect selector label.

---

## Interview Follow-Up Questions and Answers

Q: What controls traffic switching?

Answer:
Service selector labels.

---

## Best Practices

Use consistent labels.

---

## INTERVIEW QUESTION 26: How decides Blue or Green?

## Direct Interview Answer

The Kubernetes Service or Load Balancer decides whether traffic goes to Blue or Green deployment based on label selectors. When the Service selector label is updated to point to Green deployment, traffic automatically shifts to Green pods.

---

## Concept Definition

Service selector determines traffic routing.

---

## Why This Exists

Provides controlled deployment switching.

---

## Internal Working Mechanism

Service selector updated.

Traffic redirected.

---

## Architecture-Level Explanation

Service → Label selector → Pod selection

---

## Production Scenario Example

Change selector version: blue → green

Traffic shifts immediately.

---

## Failure Scenario and Troubleshooting

Traffic still going to old version.

Cause:

Selector not updated.

---

## Best Practices

Verify selectors before switching.

---

Cognitive Checkpoint for Narendra:

Which Kubernetes resource controls traffic routing: Deployment or Service?




## INTERVIEW QUESTION 27: How to do Canary in Helm?

## Direct Interview Answer

Canary deployment in Helm is implemented by deploying multiple versions of the application with different replica counts and labels. Traffic distribution is controlled using Kubernetes Service, Ingress, or service mesh such as Istio, allowing gradual traffic shifting to the new version.

---

## Concept Definition

Canary = gradual traffic shift to new version.

---

## Why This Exists

Limits risk exposure.

---

## Internal Working Mechanism

Deploy two versions.

Gradually increase replicas of new version.

---

## Architecture-Level Explanation

LoadBalancer splits traffic.

---

## Production Scenario Example

New version starts with 10% traffic.

Gradually increased.

---

## Failure Scenario and Troubleshooting

New version failure → reduce replicas.

---

## Best Practices

Monitor during rollout.

---

## INTERVIEW QUESTION 28: Application is not running how to debug it?

## Direct Interview Answer

To debug a non-running application in Kubernetes, I first check pod status using kubectl get pods, then describe the pod using kubectl describe pod, and check logs using kubectl logs. I also verify deployment configuration, image availability, resource limits, and node status.

---

## Concept Definition

Debugging involves identifying root cause of failure.

---

## Internal Working Mechanism (Step-by-Step)

Step 1:

kubectl get pods

Step 2:

kubectl describe pod

Step 3:

kubectl logs pod-name

Step 4:

kubectl get events

---

## Architecture-Level Explanation

Pod failure may occur at:

Image pull  
Container start  
Node scheduling  

---

## Production Scenario Example

ImagePullBackOff error → image missing.

---

## Failure Scenario and Troubleshooting

Check logs and events.

---

## Interview Follow-Up Questions and Answers

Q: Which command shows pod events?

Answer:
kubectl describe pod

---

## Best Practices

Always check logs first.

---

Cognitive Checkpoint for Narendra:

What is first command you run when application fails?


## INTERVIEW QUESTION 29: What are the issues when pod is not in running state?

## Direct Interview Answer

When a pod is not in Running state, it can be due to several issues such as ImagePullBackOff, CrashLoopBackOff, insufficient resources, node scheduling failure, configuration errors, failed probes, or network issues. To identify the issue, I check pod status, describe the pod, and review logs using kubectl commands.

---

## Concept Definition

Pod not in Running state means container has not started successfully or has failed.

Common pod states:

Pending  
CrashLoopBackOff  
ImagePullBackOff  
Error  

---

## Why This Exists

Pod failure indicates infrastructure, configuration, or application issue.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Scheduler tries to assign pod to node

Failure → Pending state

Step 2: Kubelet tries to pull image

Failure → ImagePullBackOff

Step 3: Container starts

Failure → CrashLoopBackOff

Step 4: Probes check health

Failure → Restart loop

---

## Architecture-Level Explanation

Failure points:

Scheduler  
Kubelet  
Container runtime  
Application  

---

## Production Scenario Example

Wrong image name → ImagePullBackOff

Application crash → CrashLoopBackOff

---

## Failure Scenario and Troubleshooting

Commands:

kubectl get pods

kubectl describe pod pod-name

kubectl logs pod-name

---

## Interview Follow-Up Questions and Answers

Q: What causes CrashLoopBackOff?

Answer:
Application crashing repeatedly.

---

## Best Practices

Use correct image  
Verify configuration  
Monitor logs  

---

Cognitive Checkpoint for Narendra:

Which command shows detailed pod failure reason?



## INTERVIEW QUESTION 30: What is taint and node affinity?

## Direct Interview Answer

Taint and node affinity are Kubernetes scheduling mechanisms used to control pod placement on nodes. Taints prevent pods from being scheduled on certain nodes unless the pod has a matching toleration, while node affinity allows pods to be scheduled only on specific nodes based on labels.

---

## Concept Definition

Taint = restriction applied on node  
Affinity = preference or requirement applied on pod  

---

## Why This Exists

Ensures workload isolation.

Example:

Database runs only on dedicated nodes.

---

## Internal Working Mechanism (Step-by-Step)

Taint example:

kubectl taint nodes node1 key=value:NoSchedule

Pod must have toleration to run.

Affinity example:

Pod specifies node label requirement.

---

## Architecture-Level Explanation

Scheduler matches:

Pod requirements  
Node labels  

---

## Production Scenario Example

GPU workloads scheduled only on GPU nodes.

---

## Failure Scenario and Troubleshooting

Pod stuck in Pending.

Cause:

No matching node.

---

## Interview Follow-Up Questions and Answers

Q: Which controls node restriction?

Answer:
Taint.

---

## Best Practices

Use taints for isolation  
Use affinity for placement  

---

## INTERVIEW QUESTION 31: Major difference between Taint and Affinity

## Direct Interview Answer

The main difference is that taints are applied to nodes and repel pods unless tolerated, while affinity is applied to pods and attracts pods to specific nodes. Taints work as node restrictions, whereas affinity works as pod scheduling rules.

---

## Concept Definition

Taint = node-level restriction  
Affinity = pod-level placement rule  

---

## Why This Exists

Provides flexible scheduling control.

---

## Internal Working Mechanism

Scheduler checks:

Node taints  
Pod tolerations  
Pod affinity  

---

## Architecture-Level Explanation

Pod scheduling controlled by scheduler.

---

## Production Scenario Example

Database pods allowed only on database nodes.

---

## Failure Scenario and Troubleshooting

Pod cannot schedule due to missing toleration.

---

## Best Practices

Use taints for exclusive nodes.

---

Cognitive Checkpoint for Narendra:

Which one is applied to node: taint or affinity?



## INTERVIEW QUESTION 32: In what scenario we have to use taint and node affinity?

## Direct Interview Answer

Taints are used when we want to restrict certain nodes for specific workloads, such as reserving nodes for critical applications. Node affinity is used when we want to ensure pods run on specific nodes based on hardware, location, or environment requirements.

---

## Concept Definition

Taint = restrict nodes  
Affinity = select nodes  

---

## Why This Exists

Ensures workload isolation and optimized resource usage.

---

## Internal Working Mechanism

Scheduler evaluates:

Node labels  
Taints  
Pod tolerations  

---

## Architecture-Level Explanation

Scheduler makes final placement decision.

---

## Production Scenario Example

Dedicated node for production workloads.

---

## Failure Scenario and Troubleshooting

Pod stuck in Pending due to affinity mismatch.

---

## Best Practices

Use affinity for workload placement  
Use taints for node isolation  

---


## INTERVIEW QUESTION 33: What is CIDR block?

## Direct Interview Answer

CIDR (Classless Inter-Domain Routing) block is a method used to define IP address ranges in networking. It specifies the network address and the number of available IP addresses using prefix notation. For example, 10.0.0.0/16 defines a network where the first 16 bits represent the network and the remaining bits represent host addresses.

---

## Concept Definition

CIDR = IP address range notation.

Format:

Network address / Prefix length

Example:

10.0.0.0/24

---

## Why This Exists

Efficient IP allocation.

Supports subnetting.

Reduces IP wastage.

---

## Internal Working Mechanism (Step-by-Step)

CIDR structure:

Example:

10.0.0.0/24

24 bits → network portion  
8 bits → host portion  

Total IP addresses:

2^(32 − prefix)

---

## Architecture-Level Explanation

CIDR used in:

VPC  
Subnets  
Pod networking  

---

## Production Scenario Example

AWS VPC defined with CIDR:

10.0.0.0/16

Supports 65,536 IP addresses.

---

## Failure Scenario and Troubleshooting

CIDR overlap causes network conflicts.

---

## Interview Follow-Up Questions and Answers

Q: Where CIDR used in Kubernetes?

Answer:
Pod CIDR and Service CIDR.

---

## Best Practices

Use non-overlapping CIDR ranges.

---

Cognitive Checkpoint for Narendra:

Which CIDR provides more IP addresses: /16 or /24?




## INTERVIEW QUESTION 34: 10.0.0.0/26 how many IP addresses we get?

## Direct Interview Answer

A /26 CIDR block provides 64 total IP addresses. However, in AWS, 5 IP addresses are reserved, so 59 IP addresses are usable.

Calculation:

2^(32 − 26) = 64 total IPs

AWS reserved IPs:

Network address  
Router address  
DNS address  
Future use  
Broadcast address  

Usable IPs = 59

---

## Concept Definition

Prefix length determines number of IPs.

---

## Internal Working Mechanism

Formula:

2^(32 − prefix)

---

## Architecture-Level Explanation

Used in subnet design.

---

## Production Scenario Example

Subnet /26 supports small workloads.

---

## Interview Follow-Up Questions and Answers

Q: How many usable IPs in AWS /26?

Answer:
59 usable IPs.

---

## Best Practices

Plan CIDR carefully.

---

## INTERVIEW QUESTION 35: Divide this network into 4 different subnets what will be the CIDR?

Network:

10.0.0.0/26

## Direct Interview Answer

To divide a /26 network into 4 equal subnets, increase prefix by 2 bits.

New prefix:

/28

Subnets:

10.0.0.0/28  
10.0.0.16/28  
10.0.0.32/28  
10.0.0.48/28  

Each subnet contains 16 IP addresses.

---

## Concept Definition

Subnetting divides network into smaller networks.

---

## Internal Working Mechanism

Original prefix:

/26

Add 2 bits:

/28

---

## Architecture-Level Explanation

Used in VPC subnet design.

---

## Production Scenario Example

Separate subnets for:

Public  
Private  
Database  
Internal  

---

## Interview Follow-Up Questions and Answers

Q: How many IPs in /28?

Answer:
16 IP addresses.

---

## Best Practices

Use subnetting for network segmentation.

---

Cognitive Checkpoint for Narendra:

Why subnetting is required in cloud architecture?




## INTERVIEW QUESTION 36: What is subnet mask?

## Direct Interview Answer

Subnet mask is a 32-bit number used to separate network portion and host portion of an IP address. It defines how many bits belong to network and how many belong to hosts.

Example:

255.255.255.0 = /24

---

## Concept Definition

Subnet mask defines network boundary.

---

## Why This Exists

Separates network and host addresses.

---

## Internal Working Mechanism

Subnet mask applied using binary logic.

---

## Architecture-Level Explanation

Used in:

VPC  
Subnets  
Routing  

---

## Production Scenario Example

Subnet mask /24 used for medium network.

---

## Interview Follow-Up Questions and Answers

Q: What subnet mask corresponds to /26?

Answer:
255.255.255.192

---

## Best Practices

Choose correct subnet mask based on requirement.

---

## INTERVIEW QUESTION 37: How pod to pod communication happens across cluster?

## Direct Interview Answer

Pod-to-pod communication across the Kubernetes cluster happens through the Container Network Interface (CNI) plugin. Each pod gets a unique IP address, and Kubernetes networking ensures that pods can communicate directly with each other using these IP addresses without NAT. The CNI plugin configures routing tables and networking rules across nodes to enable seamless communication between pods on different nodes.

---

## Concept Definition

Pod-to-pod communication is direct IP-based communication between pods across nodes.

Each pod gets:

Unique IP address  
Routable within cluster  

---

## Why This Exists

Enables microservices communication.

Allows distributed application architecture.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Pod created

CNI assigns IP address

Example:

Pod A → 10.244.1.5  
Pod B → 10.244.2.7  

Step 2: Routing table updated

Node knows how to reach remote pod.

Step 3: Traffic flows directly

Pod A → Pod B via network routing

---

## Architecture-Level Explanation

Flow:

Pod A  
↓  
Node network interface  
↓  
CNI routing rules  
↓  
Node hosting Pod B  
↓  
Pod B

---

## Production Scenario Example

Frontend pod communicates with backend pod using pod IP or service.

---

## Failure Scenario and Troubleshooting

Pods cannot communicate.

Check:

CNI plugin status

kubectl get pods -n kube-system

---

## Interview Follow-Up Questions and Answers

Q: Do pods communicate using NAT?

Answer:
No. Pods communicate using direct IP routing.

---

## Best Practices

Use stable CNI plugin.

Avoid overlapping CIDR ranges.

---

Cognitive Checkpoint for Narendra:

Which component assigns IP address to pod: kubelet or CNI?




## INTERVIEW QUESTION 38: Which CNI plugin you are using?

## Direct Interview Answer

We use the AWS VPC CNI plugin in our Amazon EKS cluster. This plugin assigns VPC IP addresses directly to pods, allowing pods to communicate using native AWS VPC networking. This provides high performance, low latency, and seamless integration with AWS networking services.

---

## Concept Definition

CNI plugin manages pod networking.

---

## Why This Exists

Enables pod communication.

---

## Internal Working Mechanism (Step-by-Step)

AWS VPC CNI assigns:

Elastic Network Interface (ENI)

Pod gets VPC IP.

---

## Architecture-Level Explanation

Pod → ENI → VPC network

---

## Production Scenario Example

Pod communicates directly with database inside VPC.

---

## Failure Scenario and Troubleshooting

Pod has no IP → CNI failure.

---

## Interview Follow-Up Questions and Answers

Q: Default CNI in EKS?

Answer:
AWS VPC CNI.

---

## Best Practices

Use AWS VPC CNI in EKS.

---

## INTERVIEW QUESTION 39: How to define network policies?

## Direct Interview Answer

Network policies are defined using Kubernetes NetworkPolicy resource. They control traffic flow between pods by specifying allowed ingress and egress traffic using pod selectors, namespace selectors, and IP blocks.

Example:

apiVersion: networking.k8s.io/v1
kind: NetworkPolicy

---

## Concept Definition

NetworkPolicy controls pod network access.

---

## Why This Exists

Improves security.

Restricts unauthorized communication.

---

## Internal Working Mechanism

NetworkPolicy defines allowed traffic.

Other traffic blocked.

---

## Architecture-Level Explanation

Pod → NetworkPolicy → Allow/Deny traffic

---

## Production Scenario Example

Frontend allowed to access backend.

Other pods blocked.

---

## Failure Scenario and Troubleshooting

Pod cannot communicate due to policy restriction.

---

## Best Practices

Use NetworkPolicy for security.

---

Cognitive Checkpoint for Narendra:

Which Kubernetes resource controls pod network access?




## INTERVIEW QUESTION 40: How does multi-cluster communication happen?

## Direct Interview Answer

Multi-cluster communication happens through load balancers, VPN connections, VPC peering, or service mesh technologies such as Istio. These mechanisms allow services in one Kubernetes cluster to communicate with services in another cluster using internal networking, DNS resolution, or secure network tunnels.

---

## Concept Definition

Multi-cluster communication = communication between different Kubernetes clusters.

---

## Why This Exists

Supports multi-region deployment.

Improves availability.

---

## Internal Working Mechanism

Cluster network connected via:

VPC Peering  
VPN  
LoadBalancer  

---

## Architecture-Level Explanation

Cluster A → LoadBalancer → Cluster B

---

## Production Scenario Example

Application running across regions.

---

## Failure Scenario and Troubleshooting

Clusters cannot communicate → network connectivity issue.

---

## Best Practices

Use VPC peering or service mesh.

---

## INTERVIEW QUESTION 41: How will it know it has to go to that cluster?

## Direct Interview Answer

Multi-cluster routing is determined using DNS resolution, load balancer endpoints, or service mesh routing rules. Each service exposed externally has a DNS name or load balancer endpoint. When a request is made, DNS resolves the service name to the correct cluster endpoint, and networking infrastructure such as VPC peering, VPN, or load balancer routes the traffic to the appropriate cluster.

---

## Concept Definition

Cluster routing is controlled by:

DNS resolution  
Load balancer endpoint  
Routing tables  

---

## Why This Exists

Allows services across clusters to discover and communicate.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Service exposed using LoadBalancer

Example:

service.myapp.com → LoadBalancer IP

Step 2: DNS resolves hostname

Step 3: Request sent to correct cluster endpoint

Step 4: LoadBalancer routes traffic to pod

---

## Architecture-Level Explanation

Client  
↓  
DNS resolution  
↓  
LoadBalancer  
↓  
Cluster  
↓  
Pod

---

## Production Scenario Example

Frontend in Cluster A calls backend in Cluster B using DNS name.

---

## Failure Scenario and Troubleshooting

DNS resolution failure.

Check:

nslookup service-name

---

## Interview Follow-Up Questions and Answers

Q: What resolves service name to IP?

Answer:
DNS.

---

## Best Practices

Use proper DNS configuration.

---

Cognitive Checkpoint for Narendra:

Which component resolves service hostname to IP address?




## INTERVIEW QUESTION 42: Pod to service how communication happens?

## Direct Interview Answer

Pod-to-service communication happens through Kubernetes Service abstraction. The service provides a stable virtual IP address and DNS name. Kubernetes uses kube-proxy to manage iptables or IPVS rules that route traffic from the service IP to the backend pod IP addresses.

---

## Concept Definition

Service provides stable access to pods.

---

## Why This Exists

Pods are dynamic.

Service provides stable endpoint.

---

## Internal Working Mechanism (Step-by-Step)

Step 1: Service created

Service gets ClusterIP.

Step 2: kube-proxy creates routing rules.

Step 3: Traffic sent to service IP.

Step 4: kube-proxy forwards traffic to pod.

---

## Architecture-Level Explanation

Pod  
↓  
Service ClusterIP  
↓  
kube-proxy routing  
↓  
Backend pod

---

## Production Scenario Example

Frontend calls backend using service name.

backend-service.default.svc.cluster.local

---

## Failure Scenario and Troubleshooting

Service cannot reach pod.

Check:

kubectl get svc  
kubectl get endpoints  

---

## Interview Follow-Up Questions and Answers

Q: Which component routes service traffic?

Answer:
kube-proxy.

---

## Best Practices

Use service DNS instead of pod IP.

---

## INTERVIEW QUESTION 43: L3 and L4 and L7 load balancer

## Direct Interview Answer

Layer 3 load balancer operates at network layer and routes traffic based on IP address. Layer 4 load balancer operates at transport layer and routes traffic based on TCP or UDP ports. Layer 7 load balancer operates at application layer and routes traffic based on HTTP headers, URL paths, or hostnames.

---

## Concept Definition

Load balancer distributes traffic across servers.

Layers:

L3 → IP routing  
L4 → TCP/UDP routing  
L7 → HTTP routing  

---

## Why This Exists

Improves scalability and availability.

---

## Internal Working Mechanism

L3 → IP based routing

L4 → Port based routing

L7 → Content based routing

---

## Architecture-Level Explanation

Client → LoadBalancer → Backend pod

---

## Production Scenario Example

ALB is L7 load balancer.

---

## Failure Scenario and Troubleshooting

Incorrect routing rule.

---

## Interview Follow-Up Questions and Answers

Q: Which load balancer supports path-based routing?

Answer:
Layer 7 load balancer.

---

## Best Practices

Use L7 load balancer for web applications.

---

Cognitive Checkpoint for Narendra:

Which load balancer type supports URL-based routing?

#### INTERVIEW QUESTION 44: If we don’t want to do SSL termination at load balancer how to do it?

## Direct Interview Answer

If SSL termination should not happen at the load balancer, then SSL passthrough must be configured. In SSL passthrough, the load balancer forwards encrypted traffic directly to the backend pods without decrypting it. The SSL termination happens inside the application container or at the ingress controller instead of the load balancer. This can be achieved using TCP mode load balancer or configuring ingress controller with SSL passthrough enabled.

---

## Concept Definition

SSL termination = decrypting HTTPS traffic.

SSL passthrough = forwarding encrypted traffic without decrypting.

---

## Why This Exists

Required when:

Application handles encryption  
End-to-end encryption required  
Higher security compliance needed  

---

## Internal Working Mechanism (Step-by-Step)

Normal SSL termination flow:

Client  
↓  
LoadBalancer (decrypts SSL)  
↓  
Pod (receives HTTP)

SSL passthrough flow:

Client  
↓  
LoadBalancer (forwards encrypted traffic)  
↓  
Pod (decrypts SSL)

---

## Architecture-Level Explanation

SSL Passthrough architecture:

Client  
↓  
LoadBalancer (TCP mode)  
↓  
Ingress Controller / Application  
↓  
Pod decrypts traffic  

---

## Production Scenario Example

Banking application requires encryption inside application.

SSL termination done inside pod.

---

## Failure Scenario and Troubleshooting

Problem:

Application cannot decrypt SSL

Cause:

Certificate misconfigured

Fix:

Verify certificate inside pod.

---

## Interview Follow-Up Questions and Answers

Q: Which load balancer mode supports SSL passthrough?

Answer:
Layer 4 (TCP) load balancer supports SSL passthrough.

---

## Best Practices

Use SSL passthrough only when required.

Otherwise terminate SSL at load balancer for performance.

---

Cognitive Checkpoint for Narendra:

Which load balancer layer supports SSL passthrough: L4 or L7?




#### INTERVIEW QUESTION 45: What configuration we have to do so that Application Load Balancer should not do SSL termination?

## Direct Interview Answer

To prevent SSL termination at AWS Application Load Balancer (ALB), you should use TCP mode load balancing with Network Load Balancer (NLB) instead of ALB, because ALB always terminates SSL at Layer 7. Alternatively, configure the ALB to forward HTTPS traffic to backend using HTTPS target groups, where backend pods handle SSL termination using their own certificates.

In Kubernetes with AWS Load Balancer Controller, configure service with:

service.beta.kubernetes.io/aws-load-balancer-type: "nlb"

This ensures SSL passthrough using Network Load Balancer.

---

## Concept Definition

ALB operates at Layer 7 and typically terminates SSL.

NLB operates at Layer 4 and supports SSL passthrough.

---

## Why This Exists

Allows end-to-end encryption.

Improves security compliance.

---

## Internal Working Mechanism (Step-by-Step)

ALB SSL termination flow:

Client HTTPS  
↓  
ALB decrypts SSL  
↓  
Forward HTTP to pod

NLB SSL passthrough flow:

Client HTTPS  
↓  
NLB forwards encrypted traffic  
↓  
Pod decrypts SSL

---

## Architecture-Level Explanation

Recommended architecture for SSL passthrough:

Client  
↓  
Network Load Balancer (L4)  
↓  
Ingress Controller  
↓  
Pod handles SSL

---

## Production Scenario Example

Application requires internal certificate validation.

SSL handled inside application container.

---

## Failure Scenario and Troubleshooting

Problem:

SSL handshake failure

Cause:

Certificate missing inside pod

Fix:

Configure TLS certificate correctly.

---

## Interview Follow-Up Questions and Answers

Q: Can ALB do SSL passthrough?

Answer:
No. ALB terminates SSL at Layer 7. Use NLB for SSL passthrough.

---

## Best Practices

Use ALB when SSL termination at load balancer is acceptable.

Use NLB when SSL passthrough required.

Use ingress controller for TLS management.

---

FINAL COGNITIVE CHECKPOINT FOR NARENDRA:

Explain complete request flow with SSL passthrough:

Client → LoadBalancer → Kubernetes → Pod

Include which component performs SSL decryption.


