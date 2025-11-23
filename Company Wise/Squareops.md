<h1>Round 1 </h1>

<h2>Project & Infrastructure Questions</h2>

Q1. Explain the infrastructure and application setup of your last project. How is the application hosted?

Follow-ups:
• Where exactly is the frontend hosted?
• Where is the backend hosted?
• Where is the database stored?
• Is everything on AWS or multi-cloud?
• What part of the infra do you manage personally?	
• What are the microservices doing?
• Why did you choose this architecture?

Q2. What exactly do you do in AWS cloud in this project?

Follow-ups:
• Do you manage VPC/subnets/security groups?
• Do you create EC2/EKS/ECS resources?
• Do you manage S3 lifecycle policies?
• Do you handle IAM + RBAC in Kubernetes?
• Do you participate in cost-optimization?

<h2>Container & Kubernetes Questions  </h2> 
Q1. On which compute platform are the applications hosted?

Follow-ups:
• Why EKS over ECS?
• How do you manage worker nodes?
• How many replicas do you run?
• Do you use Cluster Autoscaler / Karpenter?

Q2. Have you created a kubernetes cluster & EKS cluster? Explain the process.

Follow-ups:
• Did you use console, CLI, or Terraform?
• Which VPC/subnet configuration did you use?
• How did you configure node groups?
• How do you bootstrap kubectl access?

Q3. Have you upgraded an EKS cluster before? How?

Follow-ups:
• What risks come with upgrading?
• How do you handle node draining?
• Do deployments get recreated?
• What checks do you perform post-upgrade?

Q4. If your teammate also wants access to the same cluster through kubectl, what steps do you follow?

Follow-ups:
• What IAM policy do you attach?
• What is aws-auth ConfigMap?
• Where is aws-auth stored? (kube-system)
• How do you map users and roles?
• Do you provide RoleBinding or ClusterRoleBinding?

Q5. In which Kubernetes resource do you map IAM users/roles?
→ AWS Auth ConfigMap

Follow-ups:
• What sections inside it? (mapUsers, mapRoles)
• What mistakes can break authentication?

Q6. Have you worked with Helm and Helm Charts?

Follow-ups:
• Why use Helm instead of plain YAML?
• Show the folder structure of a Helm chart.
• What is the templates folder?
• What is values.yaml used for?
• How do you manage multiple environments?

Q7. How do you securely inject sensitive data into Helm?

Follow-ups:
• Do you use AWS Secrets Manager?
• Do you avoid committing secrets in values.yaml?
• What is Sealed Secrets?
• What is the purpose of –set and –set-file flags?

Q8. Can a public Helm chart be customized?

Follow-ups:
• Why is it not recommended to edit the chart directly?
• How do you update config safely?
• What happens during chart upgrades?
• How do you extend a chart with new templates?

Q9. How do you add extra Kubernetes manifest files to a public Helm chart?

Follow-ups:
• Where do you put extra YAML files? (templates folder)
• How do you reference new values?
• Can this break the original chart?

Q10. How to implement shared storage across multiple pods running on multiple nodes in EKS?

Follow-ups:
• Why EFS over EBS?
• What is the EFS CSI driver?
• What are the access modes?
• How do you mount PVC in deployment?

Q11. If there is one node but multiple pods, can we use EBS for shared storage?

Follow-ups:
• What access mode does EBS support? (RWO)
• Why can’t EBS work across multiple nodes?
• When is EFS mandatory?

Q12. What is a Pod Disruption Budget (PDB)?

Follow-ups:
• What is voluntary disruption?
• What is involuntary disruption?
• When do we use minAvailable vs maxUnavailable?

Q13. What is your approach to debug a CrashLoopBackOff?

Follow-ups:
• What logs do you check?
• How do you check events?
• How do you inspect liveness/readiness probes?
• How do you check resource limits?
• How do you inspect environment variables and config maps?

Q14. During peak traffic (2 hours/day), ingress controller is routing requests slowly. How do you debug it?

Follow-ups:
• Check ingress controller logs?
• Check CPU/memory usage?
• Check pod replicas?
• Do you use autoscaling (HPA)?
• Load balancer throttling issues?
• Endpoint misconfigurations?
• Are readiness probes failing?
• Is target response latency high?

Q15. Should we increase ingress controller replicas permanently or dynamically?

Follow-ups:
• Why is static scaling bad?
• When to use HPA?
• When to use Cluster Autoscaler?


Q16. Why choose EFS over EBS?

Follow-ups:
• Which one supports multi-node?
• Which one is cheaper?
• Which one is faster?

Q17. Can EBS be attached to multiple nodes? Why not?

Follow-ups:
• Explain RWO vs RWX
• Who enforces the mount restriction?


<h2> CI/CD Questions </h2>

Q1. What CI/CD tools have you worked with?

Follow-ups:
• Explain your GitHub Actions pipeline.
• How do you run iOS build automation?
• How do you handle secrets in pipelines?
• How do you deploy to EKS through GitHub Actions?

Q2. How do you handle multi-environment pipelines?

Follow-ups:
• Dev → QA → Prod
• Promotion strategy (manual approvals?)
• Git branching strategy?

Q3. How do you implement rolling deployments?

Follow-ups:
• What happens to old pods?
• What is maxSurge, maxUnavailable?

<h2>  Terraform Questions </h2>

Q1. Have you used Terraform?

Follow-ups:
• Show module structure.
• Show provider file.
• How do you manage remote backend?
• How do you manage state locking?
• What is a data block?
• What is a module block?



<h1> Round 2 </h1>

<h2> KUBERNETES (K8s)</h2>

1. Explain your project’s Kubernetes infrastructure setup.
2. On which platform is your application hosted (EKS/ECS/EC2)?
3. Have you created an EKS cluster? Explain the steps.
4. Have you upgraded an EKS cluster? How?
5. What are node groups?
6. How do you authenticate to an EKS cluster?


<h3> Access & RBAC </h3>

1. How do you give another IAM user access to your EKS cluster for kubectl?
2. What role does aws-auth ConfigMap play?
3. Where is aws-auth located (namespace)?
4. What is mapUsers and mapRoles?
5. How do you create ClusterRoleBinding for access control?


<h3> Helm & Application Deployment </h3>

1. Have you worked with Helm and Helm charts?
2. What is the structure of a Helm chart?
3. How do you securely inject sensitive values into Helm?
4. Can you customize a public Helm chart? How?
5. Why should you not directly edit a public chart?
6. How do you add new YAML templates into a Helm chart?
7. How do you override values.yaml for different environments?


<h3> Volumes & Storage </h3>

1. How do you implement shared storage across multiple nodes & pods?
2. Why EFS over EBS for multi-node pods?
3. What driver is needed for EFS in EKS?
4. When can EBS be used for shared storage?


<h3> Workload Management </h3>

1. What is CrashLoopBackOff?
2. How do you debug a CrashLoopBackOff error?
3. What is a Pod Disruption Budget (PDB)?
4. What is node affinity & anti-affinity?
5. What are liveness and readiness probes?


<h3>Ingress & Load Balancing</h3>

1. During peak traffic, your ingress becomes slow — how do you debug?
2. Should we always keep ingress replicas high?
3. When do you use HPA for ingress controllers?



<h2> AWS (Cloud) </h2>

<h3>Core questions </h3>
1. Which AWS services are you most confident with?
2. What is your hands-on experience with EC2?
3. What is your hands-on experience with IAM?
4. What is your hands-on experience with VPC?
5. What is your hands-on experience with S3?
6. What is your hands-on experience with RDS?
7. What is your hands-on experience with CloudWatch?


<h3> IAM & Permissions </h3>

1. Create an IAM role for EC2 that:
 – Allows only S3 + DynamoDB access
 – Denies all other services

2. What is explicit deny?
3. How do you restrict all AWS services except 2?


<h3> EC2 & Auto Scaling </h3>

1. How do you create scaling policies based on memory/disk usage?
2. Are memory/disk metrics available by default?
3. Why do we need CloudWatch Agent?
4. How to configure CloudWatch Agent in ASG (Launch Template)?
5. How to create CloudWatch alarms for memory/disk?
6. How do scaling policies use alarms?


<h3> S3</h3>

1. What is versioning in S3?
2.How do you create lifecycle rules for versioned buckets?
3. How do you delete object + previous versions after 10 days?
4. What actions exist for lifecycle rules?

<h3>RDS</h3>

1. App is slow → how to check if RDS is the issue?
2. Which RDS metrics do you check (CPU/Memory/Latency/Connections)?
3. What RDS logs do you check?
4. What is Performance Insights?
5. High memory pressure: what can you do immediately without downtime?
6. How does a read replica help?


<h3>Load Balancers & Cost</h3>

1. If App A calls App B (both behind public ALB), how does traffic flow?
2. Does it go to Internet and come back?
3. Public ALB vs Private ALB — which costs more?
4. When does internal traffic stay inside VPC?

<h3>NACL vs SG </h3>
 
1. After IGW, which layer comes first — NACL or SG?
2. Why is NACL stateless?
3. Why is SG stateful?
4. If NACL denies but SG allows — what happens?
5. How to check if IP falls under a CIDR?
6. Does IP X fall under CIDR Y? (CIDR test questions)
7. What does /32 mean in 0.0.0.0/32?
8. How many IPs in 0.0.0.0/32?



<h2> CI/CD </h2>

<h3>CI/CD Concepts </h3>

1. Your app has 3 branches — dev, staging, prod.
    - How do you deploy each branch to its environment?
    - Do you create 3 pipelines or 1 pipeline?
    - Which Jenkins job type is best?
    - Why not use freestyle job?



2. How do branch-based triggers work?
3. What is a webhook in CI/CD?
4. Have you set up rollback in CI/CD?
    - How do you implement rollback?
    - What triggers rollback?

   

<h3> CI/CD Tools </h3>
1. Have you worked with GitHub Actions?Explain the pipeline
2. Have you worked with Jenkins? Explain the pipeline.
3. How different the Github Action pipleline was with teh Jenkins ?
4. What tool do you preffer and why ?
5. If a Jenkins job is stuck (not queued, but running) how do you debug?
6. How do you check agent resources?
7. How do you debug hanging shell steps?



<h3> Static Code Analysis (SonarQube) </h3>

1.Have you integrated SonarQube?
2. How do you get the SonarQube token?
3. How to configure scanner in Jenkins?
4. What is a quality gate?





<h2> TERRAFORM</h2>

<h3>General</h3>

1. Have you used Terraform to deploy AWS infra?
2. How do you manage state files?
3. What backend did you use?

<h3> RDS Password Issue </h3>

1. Terraform auto-generated RDS password; you lost it → can you retrieve it?
2. Where is password stored? 
3. How do you reset password via Terraform?

<h3> Modules </h3> 

1. Have you created custom Terraform modules?
2. What is a custom module?
3. What files does a module contain? (main.tf / variables.tf / outputs.tf)
4. What goes inside main.tf?
5. How do you call a module from root module?



<h2> PROJECT QUESTIONS </h2> 

<h3>1. Explain infra of your last project (end-to-end). </h3>

<h3> 2. How does your CI/CD pipeline work? </h3>

<h3> 3. What are your day-to-day DevOps responsibilities?</h3>

<h3> 4. What challenges have you solved recently? </h3>



<h1> ROUND 3  </h1> 

<h2> Personal & Background Questions  </h2>

1. Tell me about your career journey, your technical expertise, and the roles & responsibilities you have handled so far.
2. What is your experience with scripting and coding (Python, Lambda, shell scripts, Terraform, CloudFormation)?
3. Did you develop scripts from scratch or only maintain existing ones?


<h2>Company & Project Questions </h2>

1. What was the product at XYZ?
2. What was the size of the team?
3. What was the tech stack behind this application?
4. Was it microservices? How many microservices were there?
5. What frontend and backend technologies were used?
6. Which databases were used? PostgreSQL, MongoDB — any others?
7. Did you use S3 or EFS? For what purpose?

<h2> ECS / EFS / Storage Questions </h2> 

1. How did you mount EFS to ECS containers?
2. If five tasks are using the same EFS, do you mount the same EFS or separate folders?
3. How do you mount EFS on EKS pods using CSI driver?
4. What are the step-by-step instructions to mount EFS on a pod?
5. Why create a PersistentVolume directly instead of using a StorageClass?
6. Kubernetes only allows PVC to mount to one pod — how do you share storage across multiple pods?


<h2> CI/CD, Deployment & Workflow Questions </h2> 

1. How did you deploy microservices for the first time?
2. What is your CI/CD workflow for continuous deployment?
3. Without ArgoCD or Helm, how do you deploy a new image version using only YAML & kubectl?
4. What are the exact deployment commands after the image is pushed to ECR?
5. How do deployment commands change with Helm?
6. How do they change with ArgoCD?
7. If deploying to dev, staging, prod — how do commands or configs differ?
8. Are values.yaml stored in Git?
9. For multiple microservices, do you store all Helm charts in a single repo or separate repos?
10. How do CD steps work when Helm chart repo is separate from app repo?
11. Does the pipeline clone the Helm repo? How is image tag updated for deployment?


<h2> Kubernetes Cluster Management </h2> 

1. How did you create new clusters?
2. How did you provide access to your team?
3. How did you upgrade clusters?
4. Which versions did you upgrade from → to?
5. When was version 1.23 available or deprecated?
6. How do you authenticate users now that aws-auth ConfigMap is deprecated?
7. What is the new mechanism for giving EKS access?


<h2> Monitoring: Grafana / Prometheus </h2> 

1. How did you install Grafana?
2. What metrics did you monitor?
3. How did you set up alerting?
4. What sources were used for metrics?
5. How did Prometheus get worker node metrics if nodes have no HTTP endpoint?
6. How were container metrics fetched?
7. How were application metrics (SSL, latency, error rate) collected?


<h2> Security, DevSecOps, AWS Security </h2> 

1. What is your experience with DevSecOps?
2. What is your experience with AWS security practices?
3. Did you integrate AWS Secrets Manager with EKS applications?
4. Did the application fetch secrets itself or were secrets injected?
5. How do pods fetch secrets?
6. How does the secret reach the application code?
7. What mechanism passes secrets from Secrets Manager to the running app?


<h2> Vulnerability Scanning / Trivy / Pipeline Security  </h2>

1. How did you fail the pipeline if vulnerabilities were detected?
2. Trivy only gives a report — how do you actually fail the pipeline?
3. What if we want to fail the pipeline only for critical CVEs but ignore medium ones?
4. Have you ever fixed any vulnerabilities to make pipeline pass?
5. Explain the process how you fixed the vulnerability. 
