<h1> AWS Cloud (Core + Infra)</h1>

<h2>A. Beginner / Easy </h2>

  
	•	Can S3 deleted objects be restored?
  
	•	EC2 vs S3 difference?
  
	•	What is IAM and what is s3 versioning?
  
	•	What is a security group?
  
	•	Difference between SG and NACL?
  
	•	What does /32 mean?
  
	•	What is an IGW?    
  

⸻

<h2>B. Intermediate / Medium </h2>

Compute

	•	Managing EC2 instances?
  
	•	Using CloudWatch Agent for memory & disk metrics?
  
	•	Creating alarms & scaling policies?

Networking

	•	App A calling App B behind ALB → does traffic go to Internet?
	•	When does traffic stay inside VPC?
	•	Why is SG stateful vs NACL stateless?
	•	If NACL denies but SG allows — what happens?

S3

	•	Lifecycle rules?
	•	Delete object+versions after X days?

RDS

	•	Identify RDS performance issues.
	•	Metrics to check (CPU/memory/latency/connections)
	•	High memory pressure — immediate action without downtime?
	•	Read replica?
	•	RDS logs / Performance Insights?

⸻

<h2>C. Advanced / Hard </h2>

VPC Architecture

	•	Migrating from public → private subnets with zero downtime
	•	Multi-tier architecture on AWS
	•	Multi-region and DR strategy
	•	Designing HA for a 3-tier application
	•	Handling AWS region-level outages

IAM Security

	•	Create IAM role allowing only S3+DynamoDB access; deny all else
	•	Explicit deny policies
	•	Restricting AWS account to only 2 services
