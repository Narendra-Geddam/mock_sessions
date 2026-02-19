INTERVIEW QUESTION 1: Can you introduce yourself?

## Direct Interview Answer

My name is Narendra Geddam, and I am a DevOps Engineer with hands-on experience in designing, automating, and managing scalable infrastructure and CI/CD pipelines across cloud and Kubernetes environments. I specialize in Linux administration, Git-based workflows, Jenkins pipeline automation, Docker containerization, and Kubernetes orchestration.

In my current workflow, I design and maintain CI/CD pipelines that automate application build, security scanning, container image creation, and deployment into Kubernetes clusters using rolling and canary deployment strategies. I have worked extensively with AWS services such as EC2, IAM, VPC, ECR, and EKS to provision secure and highly available cloud infrastructure.

I also have experience implementing Infrastructure as Code using Terraform, configuring monitoring using Prometheus and Grafana, and securing workloads using IAM roles, Kubernetes RBAC, and secrets management. My focus is on improving deployment reliability, reducing manual intervention, and ensuring production-grade system stability.

## Concept Definition

This question evaluates your professional identity, technical scope, and real-world production exposure.

It assesses:

• Technical stack depth
• Toolchain familiarity
• Architecture-level understanding
• Production environment experience

## Why This Exists

Interviewers use this question to:

• Evaluate your experience level
• Identify relevant skill areas
• Determine your fit for the DevOps role
• Establish technical direction for deeper questions

This question sets the foundation for the entire interview.

## Internal Working Mechanism (Step-by-Step)

Interviewers evaluate:

Step 1: Clarity of role definition
Step 2: Mention of core DevOps tools
Step 3: Cloud platform familiarity
Step 4: Automation and CI/CD exposure
Step 5: Container and orchestration knowledge
Step 6: Production environment handling

Strong answers demonstrate system ownership and automation capability.

## Architecture-Level Explanation

Your introduction must demonstrate understanding of the DevOps lifecycle:

Developer
↓
Git Repository
↓
CI/CD Pipeline (Jenkins)
↓
Build → Test → Scan
↓
Docker Image Creation
↓
Container Registry (ECR)
↓
Kubernetes Deployment (EKS)
↓
Monitoring and Logging

This shows full lifecycle ownership.

## Production Scenario Example

Real-world production workflow example:

• Developers commit code to Git
• Jenkins pipeline triggers automatically
• Docker image built and pushed to ECR
• Kubernetes deployment updated
• Traffic routed to new version
• Monitoring tools track health

This demonstrates real production experience.

## Failure Scenario and Troubleshooting

Weak introduction symptoms:

• Only theoretical knowledge
• No mention of production tools
• No architecture exposure
• No automation experience

Correction:

Always mention:

• CI/CD pipelines
• Docker and Kubernetes
• Cloud platform (AWS)
• Automation and deployment

## Interview Follow-Up Questions and Answers

Follow-Up Question:
Which cloud platform have you worked on?

Answer:
I have worked extensively on AWS, provisioning infrastructure using EC2, configuring IAM roles and policies, deploying containerized applications on EKS, and managing container images in ECR.

Follow-Up Question:
Have you worked on production deployments?

Answer:
Yes, I have implemented CI/CD pipelines using Jenkins to automate application builds, container image creation, security scanning, and deployments to Kubernetes clusters.

## Best Practices

Always include:

• Your role
• Tools used
• Cloud platform
• Container experience
• CI/CD pipeline experience
• Production exposure

Avoid:

• Saying fresher-level answers
• Giving generic answers
• Mentioning tools without context

---

Cognitive Checkpoint for Narendra:

If Jenkins builds a Docker image and pushes to ECR, what component pulls that image and runs it in production?

---

INTERVIEW QUESTION 2: How do you implement a canary deployment in Kubernetes as it it wont support by default?

## Direct Interview Answer

Kubernetes does not provide native canary deployment functionality, but it can be implemented using multiple deployment resources combined with Kubernetes Services or using advanced tools like Istio or Ingress controllers.

The basic approach involves creating two separate deployments: one for the stable version and another for the canary version. Both deployments use the same Kubernetes Service selector so that traffic is distributed between them based on the number of pod replicas.

For example, if the stable deployment has 9 replicas and the canary deployment has 1 replica, approximately 10% of traffic will go to the canary version. Traffic percentage can be gradually increased by scaling up canary replicas and scaling down stable replicas.

For more advanced traffic control, tools like Istio or AWS Load Balancer Controller can split traffic precisely using weighted routing.

## Concept Definition

Canary deployment is a deployment strategy where a new application version is released to a small percentage of users before full rollout.

Purpose:

• Reduce production risk
• Detect issues early
• Prevent full system failure

## Why This Exists

Problem solved:

Traditional deployments replace all pods simultaneously.

If new version has bug:

Entire production fails.

Canary deployment limits blast radius.

## Internal Working Mechanism (Step-by-Step)

Step 1: Stable deployment running version v1

Example:

Deployment stable
Replicas: 10
Version: v1

Step 2: Create canary deployment

Deployment canary
Replicas: 1
Version: v2

Step 3: Both use same Service selector

Service routes traffic to both deployments.

Step 4: Traffic automatically load-balanced.

Step 5: Gradually increase canary replicas.

Step 6: Monitor metrics.

Step 7: Promote or rollback.

## Architecture-Level Explanation

Architecture:

User Traffic
↓
Load Balancer
↓
Kubernetes Service
↓
Stable Pods (v1)
Canary Pods (v2)

Service distributes traffic across pods.

## Production Scenario Example

Example:

Stable deployment: 10 pods
Canary deployment: 2 pods

Traffic distribution:

Approx 16% to canary

Monitor:

Error rate
Latency
CPU usage

If stable → increase canary.

If failure → remove canary.

## Failure Scenario and Troubleshooting

Failure symptoms:

• Increased error rate
• High latency
• Pod crashes

Diagnosis:

kubectl get pods
kubectl logs
kubectl describe pod

Rollback:

Delete canary deployment:

kubectl delete deployment canary

Traffic returns to stable automatically.

## Interview Follow-Up Questions and Answers

Follow-Up Question:
Why Kubernetes does not provide native canary deployment?

Answer:
Kubernetes provides basic deployment strategies like RollingUpdate but traffic-level routing control requires higher-level traffic management tools like Istio or Ingress controllers.

Follow-Up Question:
Which tools enable advanced canary deployment?

Answer:

Istio
Linkerd
NGINX Ingress
AWS Load Balancer Controller

## Best Practices

Use:

Istio VirtualService
Weighted routing
Monitoring tools

Avoid:

Manual replica scaling in production.

Automate using service mesh.

---

Cognitive Checkpoint for Narendra:

If stable deployment has 20 pods and canary has 5 pods, what percentage of traffic goes to canary?

---

INTERVIEW QUESTION 3: How can you perform a canary deployment in AWS? Which AWS services can be used to split traffic between application versions?

## Direct Interview Answer

Canary deployment in AWS is implemented by gradually shifting traffic from the old version to the new version using traffic routing and load balancing services. AWS provides multiple services such as Application Load Balancer (ALB), AWS CodeDeploy, Route 53 weighted routing, and AWS App Mesh to control traffic distribution between application versions.

One common approach is using an Application Load Balancer with two target groups, one pointing to the stable version and another pointing to the canary version. Traffic distribution can be controlled by adjusting routing weights.

Another advanced method is using AWS CodeDeploy with EC2 or ECS, where CodeDeploy automatically shifts traffic gradually using predefined deployment configurations such as 10%, 50%, and 100%.

For Kubernetes workloads running on EKS, AWS Load Balancer Controller or Istio integrated with ALB enables weighted routing between versions.

## Concept Definition

Canary deployment in AWS is a progressive traffic-shifting strategy where a new version receives a controlled percentage of production traffic before full rollout.

This reduces production risk and ensures system stability.

## Why This Exists

Problem solved:

Deploying new version to all users simultaneously can cause full production failure.

Canary deployment limits exposure.

Benefits:

• Early bug detection
• Safe deployment rollout
• Zero downtime deployment
• Controlled rollback

## Internal Working Mechanism (Step-by-Step)

Using Application Load Balancer:

Step 1: Create two application versions

Version v1 → stable
Version v2 → canary

Step 2: Create two target groups

Target Group 1 → v1 instances
Target Group 2 → v2 instances

Step 3: Configure ALB listener rule

Forward traffic with weight:

90% → v1
10% → v2

Step 4: Monitor performance metrics

CloudWatch monitors:

Error rate
Latency
CPU

Step 5: Gradually increase traffic

50% → v2
100% → v2

Step 6: Complete rollout

Remove v1.

## Architecture-Level Explanation

Architecture flow:

User Traffic
↓
Route 53 DNS
↓
Application Load Balancer
↓
Target Group v1 (Stable)
Target Group v2 (Canary)
↓
EC2 / ECS / EKS Pods

ALB controls traffic distribution.

## Production Scenario Example

Example:

Application running on EKS.

Two deployments:

app-v1
app-v2

AWS Load Balancer Controller creates ALB.

ALB routes:

95% → v1
5% → v2

If stable → increase v2 gradually.

## Failure Scenario and Troubleshooting

Failure symptoms:

High error rate in v2.

Diagnosis:

Check CloudWatch logs
Check EC2 / Pod logs
Check ALB target health

Rollback:

Change ALB weight:

100% → v1
0% → v2

Instant rollback.

## Interview Follow-Up Questions and Answers

Follow-Up Question:
Which AWS service provides automated canary deployment?

Answer:
AWS CodeDeploy provides built-in canary deployment with automated traffic shifting and rollback.

Follow-Up Question:
Which service controls traffic routing?

Answer:
Application Load Balancer and Route 53 weighted routing control traffic distribution.

## Best Practices

Use:

CodeDeploy for automation
ALB weighted routing
CloudWatch monitoring

Avoid:

Direct replacement deployments.

---

Cognitive Checkpoint for Narendra:

What happens if canary target group becomes unhealthy in ALB?

---

INTERVIEW QUESTION 4: If a single pod needs access to an AWS S3 bucket, how would you securely provide that access?

## Direct Interview Answer

The secure and recommended approach is to use IAM Roles for Service Accounts (IRSA). This allows a Kubernetes Service Account to assume an IAM Role that has permissions to access the S3 bucket. The pod uses this service account, and AWS automatically provides temporary credentials via the IAM role.

This avoids storing AWS access keys inside the pod and ensures secure, temporary credential access.

## Concept Definition

IAM Roles for Service Accounts (IRSA) enables Kubernetes pods to securely access AWS services using IAM roles.

It eliminates static credentials.

## Why This Exists

Problem solved:

Hardcoding AWS credentials inside pods creates security risk.

IRSA provides:

Temporary credentials
Automatic rotation
Secure access

## Internal Working Mechanism (Step-by-Step)

Step 1: Create IAM policy

Example:

Allows S3 access.

Step 2: Create IAM role

Attach policy.

Step 3: Configure IAM role trust policy

Trust Kubernetes OIDC provider.

Step 4: Create Kubernetes Service Account

Attach IAM role annotation.

Step 5: Assign service account to pod

Step 6: Pod automatically gets temporary credentials.

## Architecture-Level Explanation

Flow:

Pod
↓
Service Account
↓
IAM Role
↓
AWS STS
↓
Temporary credentials
↓
Access S3

Secure access chain.

## Production Scenario Example

Application needs to upload logs to S3.

Pod uses Service Account:

log-uploader-sa

IAM role attached:

S3 write permission.

Application uploads logs securely.

## Failure Scenario and Troubleshooting

Failure symptom:

Access denied error.

Diagnosis:

Check IAM policy
Check service account annotation
Check OIDC provider

Command:

kubectl describe serviceaccount

Check IAM role ARN.

## Interview Follow-Up Questions and Answers

Follow-Up Question:
Why not use AWS access keys?

Answer:
Access keys are static and insecure. IAM roles provide temporary credentials and automatic rotation.

Follow-Up Question:
What provides temporary credentials?

Answer:
AWS STS provides temporary credentials.

## Best Practices

Always use:

IRSA

Avoid:

Hardcoded credentials
Secrets with access keys

---

Cognitive Checkpoint for Narendra:

Which AWS service generates temporary credentials when using IAM roles?

---

INTERVIEW QUESTION 5: How do you attach a Kubernetes Service Account to an IAM Role?

## Direct Interview Answer

To attach a Kubernetes Service Account to an IAM Role, I use IAM Roles for Service Accounts (IRSA), which allows Kubernetes pods to securely assume IAM roles using OIDC federation. The process involves creating an IAM policy, creating an IAM role with a trust relationship to the Kubernetes OIDC provider, annotating the Kubernetes Service Account with the IAM role ARN, and assigning that Service Account to the pod. Once configured, the pod automatically receives temporary AWS credentials via the IAM role.

This enables secure access to AWS services like S3, DynamoDB, and SQS without using static credentials.

## Concept Definition

IAM Roles for Service Accounts (IRSA) is a mechanism that allows Kubernetes Service Accounts to assume AWS IAM Roles securely using OpenID Connect (OIDC).

This enables pods to access AWS services securely.

## Why This Exists

Problem solved:

Without IRSA:

Pods use hardcoded credentials → security risk

With IRSA:

• Temporary credentials
• Automatic rotation
• Fine-grained permissions
• Secure authentication

## Internal Working Mechanism (Step-by-Step)

Step 1: Enable OIDC provider for EKS cluster

Command:

aws eks describe-cluster --name cluster-name --query "cluster.identity.oidc.issuer"

Step 2: Create IAM policy

Example policy allows S3 access.

Step 3: Create IAM Role

Attach policy.

Step 4: Configure trust relationship

Trust Kubernetes OIDC provider.

Example trust flow:

Kubernetes Service Account
↓
OIDC provider
↓
IAM role

Step 5: Create Kubernetes Service Account

Example:

apiVersion: v1
kind: ServiceAccount
metadata:
name: s3-access-sa
annotations:
eks.amazonaws.com/role-arn: arn:aws:iam::ACCOUNT_ID:role/S3AccessRole

Step 6: Assign Service Account to Pod

Pod automatically assumes IAM role.

Step 7: AWS STS provides temporary credentials.

## Architecture-Level Explanation

Full authentication chain:

Pod
↓
Service Account
↓
OIDC Token
↓
AWS STS
↓
IAM Role
↓
Temporary credentials
↓
Access AWS service

Secure, dynamic authentication.

## Production Scenario Example

Scenario:

Application uploads files to S3.

Implementation:

Service Account → s3-access-sa
IAM Role → S3 access policy

Pod uses Service Account → gets credentials automatically.

No secrets required.

## Failure Scenario and Troubleshooting

Failure:

Access denied.

Check:

kubectl describe serviceaccount s3-access-sa

Verify annotation exists.

Check IAM trust policy.

Check OIDC provider configured.

Check IAM permissions.

## Interview Follow-Up Questions and Answers

Follow-Up Question:
Which component authenticates Kubernetes with AWS?

Answer:
OIDC provider authenticates Kubernetes Service Account with AWS IAM.

Follow-Up Question:
Which AWS service issues temporary credentials?

Answer:
AWS STS (Security Token Service).

## Best Practices

Use:

IRSA
Least privilege policy
Separate IAM roles per service

Avoid:

Sharing IAM roles between applications.

---

Cognitive Checkpoint for Narendra:

What is the role of OIDC provider in IRSA?

---

INTERVIEW QUESTION 6: Have you implemented a Service Mesh for canary deployments? If yes, how did you achieve traffic shifting between versions?

## Direct Interview Answer

Yes, I have implemented canary deployments using Istio Service Mesh. Istio enables advanced traffic routing using VirtualService and DestinationRule resources. I deployed two versions of the application, v1 and v2, and configured Istio VirtualService to split traffic between them using weighted routing.

For example, I configured VirtualService to route 90% traffic to version v1 and 10% traffic to version v2. After monitoring metrics like latency, error rate, and CPU usage, I gradually increased traffic to v2 until it reached 100%.

Istio provides precise traffic control, automatic retries, circuit breaking, and observability.

## Concept Definition

Service Mesh is an infrastructure layer that manages service-to-service communication, traffic routing, security, and observability.

Istio is a popular service mesh implementation.

## Why This Exists

Problem solved:

Kubernetes cannot precisely control traffic percentage.

Service Mesh provides:

• Traffic splitting
• Canary deployment
• Traffic routing
• Retry and fault tolerance

## Internal Working Mechanism (Step-by-Step)

Step 1: Deploy application version v1 and v2

Step 2: Create DestinationRule

Defines subsets:

version: v1
version: v2

Step 3: Create VirtualService

Defines traffic routing.

Example routing:

90% → v1
10% → v2

Step 4: Istio Envoy proxy intercepts traffic.

Step 5: Envoy routes traffic based on configuration.

## Architecture-Level Explanation

Flow:

User
↓
Ingress Gateway
↓
Envoy Proxy
↓
VirtualService rule
↓
DestinationRule subsets
↓
Pods (v1 and v2)

Envoy handles routing.

## Production Scenario Example

Scenario:

New application version deployed.

Traffic routing:

95% → stable
5% → canary

Gradually increase to 100%.

If error occurs → rollback instantly.

## Failure Scenario and Troubleshooting

Failure:

Traffic not routing correctly.

Check:

kubectl get virtualservice
kubectl get destinationrule

Check Envoy logs.

Verify labels match subsets.

## Interview Follow-Up Questions and Answers

Follow-Up Question:
What component routes traffic in Istio?

Answer:
Envoy proxy routes traffic based on VirtualService rules.

Follow-Up Question:
What defines traffic subsets?

Answer:
DestinationRule defines subsets.

## Best Practices

Use:

Gradual traffic shifting
Monitor metrics
Automate rollout

Avoid:

Immediate full rollout.

---

Cognitive Checkpoint for Narendra:

Which Istio component actually routes traffic — VirtualService or Envoy proxy?

---

INTERVIEW QUESTION 7: What are the steps to set up Istio Service Mesh in a Kubernetes cluster?

## Direct Interview Answer

To set up Istio Service Mesh in a Kubernetes cluster, I first install Istio using istioctl, enable automatic sidecar injection for the namespace, deploy the application, and configure traffic routing using VirtualService and DestinationRule.

The main steps include downloading Istio, installing the control plane, labeling the namespace for sidecar injection, deploying applications, verifying Envoy proxy injection, and configuring traffic management policies.

## Concept Definition

Istio is a Service Mesh that provides traffic management, security, observability, and resilience for microservices running in Kubernetes.

It uses Envoy sidecar proxies to intercept and control network traffic.

## Why This Exists

Problem solved:

Kubernetes lacks advanced traffic control features like:

• Traffic splitting
• Circuit breaking
• Service-to-service encryption
• Observability

Istio provides these features.

## Internal Working Mechanism (Step-by-Step)

Step 1: Download Istio

curl -L [https://istio.io/downloadIstio](https://istio.io/downloadIstio) | sh

Step 2: Install Istio control plane

istioctl install --set profile=demo -y

This installs:

istiod → control plane

Step 3: Enable namespace injection

kubectl label namespace default istio-injection=enabled

Step 4: Deploy application

Istio injects Envoy proxy automatically.

Step 5: Verify sidecar injection

kubectl get pods

Each pod contains:

Application container
Envoy sidecar container

Step 6: Configure traffic routing

Create VirtualService and DestinationRule.

Step 7: Verify traffic routing

Check logs and metrics.

## Architecture-Level Explanation

Architecture:

Application Pod
↓
Envoy Sidecar
↓
Istio Control Plane (istiod)
↓
Traffic routing policies

Envoy intercepts all incoming and outgoing traffic.

## Production Scenario Example

Scenario:

Microservices architecture.

Istio provides:

Secure communication
Traffic splitting
Monitoring

Example:

Canary deployment using VirtualService.

## Failure Scenario and Troubleshooting

Failure:

Sidecar not injected.

Check:

kubectl get namespace --show-labels

Ensure:

istio-injection=enabled

Check istiod status.

kubectl get pods -n istio-system

## Interview Follow-Up Questions and Answers

Follow-Up Question:
What is the Istio control plane component?

Answer:
istiod is the control plane component that manages configuration and traffic policies.

Follow-Up Question:
What is sidecar injection?

Answer:
Automatic addition of Envoy proxy container to each pod.

## Best Practices

Use:

Automatic injection
Production profile configuration

Avoid:

Manual sidecar injection.

---

Cognitive Checkpoint for Narendra:

What component inside the pod intercepts and routes traffic in Istio?

---

INTERVIEW QUESTION 8: How would you migrate an application from an on-premises environment to a cloud platform?

## Direct Interview Answer

Application migration from on-premises to cloud involves assessment, planning, containerization, infrastructure provisioning, data migration, deployment, testing, and cutover. I first analyze the application dependencies, databases, network requirements, and storage. Then I provision cloud infrastructure using Terraform, containerize the application using Docker, deploy it on Kubernetes or EC2, migrate the database using AWS DMS or backup and restore, validate functionality, and finally switch production traffic.

This ensures minimal downtime and safe migration.

## Concept Definition

Application migration is the process of moving applications, data, and infrastructure from on-premises to cloud platforms.

## Why This Exists

Cloud provides:

• Scalability
• High availability
• Cost efficiency
• Managed infrastructure

On-premises environments are limited.

## Internal Working Mechanism (Step-by-Step)

Step 1: Assessment phase

Identify:

Application dependencies
Database size
Network requirements

Step 2: Cloud infrastructure setup

Provision:

VPC
Subnets
Security Groups
EKS / EC2

Step 3: Containerization

Build Docker image.

Step 4: Push image to registry

Example:

Amazon ECR

Step 5: Deploy application

Kubernetes deployment.

Step 6: Database migration

Use AWS DMS or backup restore.

Step 7: Testing phase

Functional testing
Performance testing

Step 8: Cutover

Switch DNS to cloud.

## Architecture-Level Explanation

Migration architecture:

On-prem application
↓
Docker containerization
↓
Cloud infrastructure provisioning
↓
Kubernetes deployment
↓
DNS cutover

## Production Scenario Example

Example:

Java application running on on-prem VM.

Migration:

Dockerize application
Deploy to EKS
Migrate database using DMS
Update Route 53 DNS

Application runs fully in cloud.

## Failure Scenario and Troubleshooting

Failure:

Application fails after migration.

Check:

Network connectivity
Database access
Security groups

Check logs:

kubectl logs

## Interview Follow-Up Questions and Answers

Follow-Up Question:
Which AWS service migrates databases?

Answer:
AWS Database Migration Service (DMS).

Follow-Up Question:
Which service manages DNS?

Answer:
Amazon Route 53.

## Best Practices

Use:

Blue-green migration
Backup before migration
Test before cutover

Avoid:

Direct cutover without testing.

---

Cognitive Checkpoint for Narendra:

Which AWS service helps migrate databases with minimal downtime?

---

INTERVIEW QUESTION 9: If you have 20 microservices built using Java and Python, how would you design a CI/CD pipeline to build and deploy all of them?

## Direct Interview Answer

I would design a scalable CI/CD pipeline using Jenkins integrated with Git, Docker, Kubernetes, and container registry like Amazon ECR. Each microservice would have its own Git repository or directory structure, and Jenkins would use pipeline automation to detect changes, build the application, create Docker images, push them to ECR, and deploy them to Kubernetes using deployment manifests or Helm charts.

I would use Jenkins multibranch pipelines, shared libraries, and dynamic Kubernetes agents to parallelize builds and optimize performance. This ensures independent deployment, faster builds, and scalability.

## Concept Definition

CI/CD pipeline automates build, test, and deployment process.

It ensures continuous delivery.

## Why This Exists

Problem solved:

Manual deployment is slow and error-prone.

CI/CD provides:

Automation
Consistency
Reliability

## Internal Working Mechanism (Step-by-Step)

Step 1: Developer pushes code to Git

Step 2: Jenkins pipeline triggers automatically

Step 3: Build stage

Java → Maven build
Python → pip build

Step 4: Build Docker image

Step 5: Push image to ECR

Step 6: Deploy to Kubernetes

Step 7: Verify deployment

Step 8: Monitor application

## Architecture-Level Explanation

Pipeline architecture:

Developer
↓
Git Repository
↓
Jenkins Pipeline
↓
Docker build
↓
Amazon ECR
↓
Kubernetes cluster
↓
Application running

## Production Scenario Example

20 microservices.

Jenkins builds each independently.

Parallel execution reduces deployment time.

## Failure Scenario and Troubleshooting

Failure:

Build failure.

Check:

Jenkins logs
Build logs

Deployment failure:

Check:

kubectl get pods

## Interview Follow-Up Questions and Answers

Follow-Up Question:
How do you scale Jenkins agents?

Answer:
Use dynamic Kubernetes agents.

Follow-Up Question:
How do you manage deployment manifests?

Answer:
Use Helm charts.

## Best Practices

Use:

Parallel builds
Independent pipelines
Helm charts

Avoid:

Single pipeline for all services.

---

Cognitive Checkpoint for Narendra:

Why dynamic Kubernetes agents are better than static Jenkins agents?

---

INTERVIEW QUESTION 10: You have 10 TB of data stored on-premises. Which service you use and how you migrate?

## Direct Interview Answer

For migrating 10 TB of on-premises data to AWS, I would use AWS Snowball because it is designed for large-scale data transfer securely and efficiently. Snowball is a physical device provided by AWS that allows transferring large volumes of data without relying on network bandwidth.

I would request a Snowball device, copy the data onto it, and ship it back to AWS. AWS uploads the data into S3 automatically.

For smaller datasets, AWS DataSync or direct upload can be used.

## Concept Definition

AWS Snowball is a data transfer service using physical devices to migrate large data volumes.

## Why This Exists

Problem solved:

Network transfer of large data is slow.

Snowball provides:

Fast transfer
Secure transfer

## Internal Working Mechanism (Step-by-Step)

Step 1: Request Snowball device

Step 2: AWS ships device

Step 3: Copy data onto device

Step 4: Ship device back

Step 5: AWS uploads data to S3

## Architecture-Level Explanation

On-prem data
↓
Snowball device
↓
AWS data center
↓
S3 bucket

## Production Scenario Example

Company migrates 100 TB data.

Uses Snowball.

## Failure Scenario and Troubleshooting

Failure:

Data copy failure.

Check network and disk.

## Interview Follow-Up Questions and Answers

Follow-Up Question:
Alternative service?

Answer:
AWS DataSync.

## Best Practices

Use Snowball for large data.

---

Cognitive Checkpoint for Narendra:

Why Snowball is preferred over internet transfer for large data?

---


