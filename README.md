# Cloud Computing Lab 5 - Assignment 1
**App:** Gitea (Git with a cup of tea)
**Database:** Amazon RDS (MySQL Free Tier)
**EC2 URL:** http://3.88.179.213/

## DB Deployment & Connection Steps
1. **RDS Provisioning:** Created an Amazon RDS instance using the MySQL engine (Free Tier `db.t3.micro`).
2. **Security Configuration:** Set "Public Access" to "No". Created a VPC Security Group (`RDS-Gitea-SG`) and added an inbound rule for Port 3306. The Source was strictly limited to the EC2 Instance's Security Group (`sg-0a58aef2757611dd2`) to meet security requirements.
3. **Database Initialization:** Connected to the RDS endpoint via the EC2 terminal using the `mysql` client and executed `CREATE DATABASE giteadb CHARACTER SET 'utf8mb4' COLLATE 'utf8mb4_unicode_ci';`.
4. **App Connection:** Restarted the Gitea service and completed the web-based installation, binding the application to the RDS Endpoint on port 3306.


## Assignment 2: DynamoDB Integration
**App:** MoneyCouncil Python Backend
**Database:** Amazon DynamoDB
**API Base URL / Execution Environment:** Local execution on EC2 via `boto3`.
**Security:** Accessed strictly via an IAM Role (`EC2-DynamoDB-Role`) attached to the EC2 instance. No hardcoded credentials.
**Data Model:** - `UserID` (Number)
- `ClientName` (String)
- `IsPremiumMember` (Boolean)
- `FinancialGoals` (List)
- `Portfolio` (Map)
