Copied from [here](https://github.com/borkod/AWS-Certified-Database-Specialty-Exam-Guide)

---

# AWS Certified Database - Specialty Exam Preparation Guide and Study Tips
In late November of 2019, AWS [announced](https://aws.amazon.com/blogs/database/new-aws-certification-purpose-built-to-validate-database-expertise/) a new specialty certification focusing specifically on database technologies.  The AWS Certified Database - Specialty Exam beta period started in early December of 2019 with the standard certification exam availability target date being April of 2020.  At the start of December, I participated in the beta attempting the beta exams.  As of this writing, I do not know my results and whether on not I achieved the certification.  Nevertheless, I thought it would be useful to share my experience.  I'll try to list the topics covered by the exam questions, and provide some insight and resources that are helpful in preparing for the exam.

## Exam Description
The database certification exam covers five domains:
- Domain 1: Workload-Specific Database Design (26%)
- Domain 2: Deployment and Migration (20%)
- Domain 3: Management and Operations (18%)
- Domain 4: Monitoring and Troubleshooting (18%)
- Domain 5: Database Security (18%)
  
The exam's goal is to test user's competence to:
- Understand the various AWS database services
- Recommend and design database solutions appropriate to satisfy specific problem requirements

AWS suggests that the examinee has:
- Minimum of 5 years of experience working with relational and NoSQL databases, including on-prem and cloud based implementations
- Minimum of 2 years of hand-on experience with AWS
  
## Exam Topics
- **Amazon RDS** is one of the core services offered by AWS, so having good understanding and thorough knowledge of this service is critical to succeeding in the exam.
  - You should have expertise in analyzing and identifying requirements / use cases when a relational database (and specifically RDS) is the appropriate solution.  You should also have a good understanding of the service capabilities and limitations.
  - Multi-AZ: Know technical details of its implementation and when it is appropriate (e.g. disaster recovery scenarios)
  - Read-Replicas: Know technical details and in what situations is it useful (e.g. off-loading read traffic)
  - Know the numerous engine options RDS has available
    - There are engine specific questions, so you should have some familiarity with each engine (e.g. Oracle TDE, PostgreSQL specific capabilities)
  - Backups
  - Option Groups
  - DB Parameter Groups
  - SQL Performance Insights (what is it, when is it applicable, and how is it different from CloudWatch)
- Alongside RDS, **DynamoDB** is probably the most crucial of AWS database services.  You should know it inside and out.
  - Understand Primary Keys/Partition Keys/Sort Keys.  Given a particular scenario, be able to design/choose them.
  - Global Secondary Indexes / Local Secondary Indexes.  Understand difference between them and applicable use cases.
  - DynamoDB Streams
  - Global Tables (and its use cases)
  - Data Modeling
    - Partition Sharding (e.g. adding random suffix)
    - Composite Keys
  - Design patterns and best practices
  - Querying and Filtering
  - DAX (vs ElastiCache)
  - Have a good understanding of the underlying technical architecture
- **Amazon Aurora**
  - Understand the technical architecture and use cases
  - Difference between Aurora Read Replicas/RDS Read Replicas
  - Scaling of Aurora
  - Understand Aurora Serverless
  - Understand Aurora Clones and when to you should use them
- **CloudWatch**
  - Understand the service functionality 
  - How to use in troubleshooting scenarios
  - Performance monitoring and notification/alerting scenarios
- **Database Migration**
  - There are questions around AWS SCT (Schema Conversion Tool) and AWS DMS (Database Migration Service).  You should have a general understanding of both, difference between them, and when you would use one vs the other.
- **ElastiCache**
  - Have a good understanding of use cases when caching is appropriate
  - Focus on Redis
  - Understand Redis architecture, Multi-AZ, etc.
  - Understand various caching strategies (Lazy Loading, Write-Through) and benefits/limitation of each
- **DocumentDB**
  - I don't recall many questions on this service, however you should have general familiarity with it
- **Redshift**
  - Have a general understanding of data-warehouse topics and columnar storage
  - Be familiar with technical architecture (single node deployment / cluster with leader and compute nodes)
  - Be familiar with Redshift Spectrum
  - Understand use cases for Redshift (e.g. Business Intelligence and Reporting).  Be able to differentiate applicability of Redshift vs RDS.
- **Neptune**
  - I don't recall many questions here.  However, you should have general understanding of graph database concepts and graph database applications.
  - I suggest being familiar with its technical architecture
  - Know supported APIs (Gremlin, SPARQL) and models (Property Graph/TinkerPop and W3C RDF/SPARQL)
- **Security**
  - Understand options and solutions for data encryption (both data at rest and data in transit)
  - Authentication options and capabilities
  - Access Management (IAM)
  - Have good understanding of services like Parameter Store and KMS
- **Networking**
  - Understand how to integrate various services with VPC (e.g. VPC Endpoints)
  - Know how to secure access at network level
- **Solutions Architecture**
  - There were a number of questions very reminiscent of questions from AWS Solutions Architect Exam.  I *strongly* suggest attaining AWS Solutions Architect Associate Certification before attempting this specialty exam.
  - Understand AWS Lambda and how it can be used in conjunction with all the other services mentioned above
  - Expect questions on High Availability, Disaster Recovery, and Fault Tolerance
- **Deployment and CI/CD**
  - There were quite a few (more than I expected) questions relating to deployment and CI/CD concepts.  I would *strongly* suggest attaining the AWS DevOps Engineer Professional certification prior to writing this specialty exam (or at least AWS Developer Associate Certification).  You need to understand the various DevOps services AWS offers (e.g. CloudFormation, CodeBuild, CodeDeploy) and how they can be utilized to assist deployment scenarios.

## General Tips
As mentioned above, I strongly suggest having both AWS Solutions Architect - Associate and AWS Certified Developer - Associate certifications (or preferably AWS DevOps Engineer - Professional) prior to entering to write this specialty exam. The experience and knowledge required to attain those certifications will go a long way in helping you do well in this exam.

As suggested by AWS, you should have significant experience designing and implementing solutions consisting of various database technologies.  This experience should include considerable understanding and practical use of AWS services.

Lastly, I suggest reviewing official [AWS documentation](https://docs.aws.amazon.com/), [AWS Whitepapers & Guides](https://aws.amazon.com/whitepapers/), blogs, and videos.  In particular, I found advanced level Re:Invent and Online Tech Talk videos particularly useful.

## Resources
Below is a list of few links I found especially informative.

### AWS Re:Invent Videos and Online Tech Talks: 

- [Amazon Relational Database Service (Amazon RDS)](https://www.youtube.com/watch?v=igRfulrrYCo)
- [AWS re:Invent 2017: Deep Dive on Amazon Relational Database Service (RDS) (DAT302)](https://www.youtube.com/watch?v=TJxC-B9Q9tQ)
- [AWS re:Invent 2018: Aurora Serverless: Scalable, Cost-Effective Application Deployment (DAT336)](https://www.youtube.com/watch?v=4DqNk7ZTYjA)
- [Migrating Microsoft SQL to AWS - AWS Online Tech Talks](https://www.youtube.com/watch?v=WeXXtBNtwxk)
  - Contains a good demo of DMS
- [AWS re:Invent 2017: ElastiCache Deep Dive: Best Practices and Usage Patterns (DAT305)](https://www.youtube.com/watch?v=_YYBdsuUq2M)
- [AWS re:Invent 2018: ElastiCache Deep Dive: Design Patterns for In-Memory Data Stores (DAT302-R1)](https://www.youtube.com/watch?v=QxcB53mL_oA)
- [AWS re:Invent 2018: Amazon DynamoDB Under the Hood: How We Built a Hyper-Scale Database (DAT321)](https://www.youtube.com/watch?v=yvBR71D0nAQ)
- [AWS re:Invent 2018: Accelerate Database Development and Testing with Amazon Aurora (DAT313)](https://www.youtube.com/watch?v=tJ0TWdIocz0)
- [Data Design and Modeling for Microservices](https://www.youtube.com/watch?v=KPtLbSEFe6c)
- [AWS re:Invent 2017: Best Practices for Data Warehousing with Amazon Redshift & Redshift Spectrum (ABD304)](https://www.youtube.com/watch?time_continue=1&v=Q_K3qH5OYaM)
- [AWS re:Invent 2018: Amazon DynamoDB Deep Dive: Advanced Design Patterns for DynamoDB (DAT401)](https://www.youtube.com/watch?v=HaEPXoXVf2k)

### AWS Whitepapers & Guides

- [An Overview of AWS Cloud Data Migration Services](https://d1.awsstatic.com/whitepapers/Storage/An_Overview_of_AWS_Cloud_Data_Migration_Services.pdf?did=wp_card&trk=wp_card)
- [Migrating Applications Running Relational Databases to AWS: Best Practices Guide](https://d1.awsstatic.com/whitepapers/Migration/migrating-applications-to-aws.pdf?did=wp_card&trk=wp_card)
- [AWS Database Migration Service Best Practices](https://d1.awsstatic.com/whitepapers/RDS/AWS_Database_Migration_Service_Best_Practices.pdf?did=wp_card&trk=wp_card)
- [Migrating Your Databases to Amazon Aurora](https://d1.awsstatic.com/whitepapers/RDS/Migrating%20your%20databases%20to%20Amazon%20Aurora.pdf?did=wp_card&trk=wp_card)
- [Best Practices for Migrating MySQL Databases to Amazon Aurora](https://d1.awsstatic.com/whitepapers/RDS/Best-Practices-for-Migrating-MySQL-Databases-to-Amazon-Aurora.pdf?did=wp_card&trk=wp_card)
- [Strategies for Migrating Oracle Databases to AWS](https://d1.awsstatic.com/whitepapers/strategies-for-migrating-oracle-database-to-aws.pdf?did=wp_card&trk=wp_card)
- [Best Practices for Running Oracle Database on AWS](https://d1.awsstatic.com/whitepapers/best-practices-for-running-oracle-database-on-aws.pdf?did=wp_card&trk=wp_card)
- [Deploying Microsoft SQL Server on AWS](https://d1.awsstatic.com/whitepapers/RDS/Deploying_SQLServer_on_AWS.pdf?did=wp_card&trk=wp_card)
- [Best Practices for Deploying Microsoft SQL Server on AWS](https://d1.awsstatic.com/whitepapers/best-practices-for-deploying-microsoft-sql-server-on-aws.pdf?did=wp_card&trk=wp_card)
- [Performance at Scale with Amazon ElastiCache](https://d1.awsstatic.com/whitepapers/performance-at-scale-with-amazon-elasticache.pdf?did=wp_card&trk=wp_card)
- [Database Caching Strategies Using Redis](https://d1.awsstatic.com/whitepapers/Database/database-caching-strategies-using-redis.pdf?did=wp_card&trk=wp_card)
- [Getting Started with Amazon DocumentDB (with MongoDB Compatibility)](https://d1.awsstatic.com/whitepapers/getting-started-with-amazon-documentdb.pdf?did=wp_card&trk=wp_card)

## Final Thoughts
In my opinion, AWS Database Specialty is an excellent addition to the AWS Certification program.  Database technologies are an integral and crucial part of any cloud based solution. Having a strong competency in these technologies is critical to being a successful architect and designing apt solutions.

I hope this guide and contents within are helpful to those preparing to attempt the exam in the future.

Good Luck!

---

Copied from [medium](https://medium.com/@vlad_13843/aws-certified-database-specialty-unofficial-exam-guide-4e38951481f5)

---

What Is the AWS Certified Database — Specialty Certification Exam?

The AWS Certified Database — Specialty certification tests your understanding of different AWS database offerings. It is designed for individuals who perform database-related activities. It focuses on various aspects, such as design, migration, deployment, maintenance, monitoring, security, and disaster recovery. Like any other AWS exam, it is a theoretical test that contains a handful of single-choice and multiple-choice questions. The duration is around two hours. The exam fee is $150 for the beta and $300 for the final version when it becomes available.
My impressions during the test

The exam questions primarily focus on RDS and RDS Aurora. DynamoDB and AWS Database Migration Service are secondary topics that exam questions are sourced from. There were a couple of questions about RedShift and Neptune. Some questions offered AWS ElasticSearch and AWS ElastiCache as optional answers but did not discuss these topics in great detail. On top of the database offerings, a strong emphasis is put on AWS CloudFormation and AWS KMS. Below is a breakdown of the estimated percentage of exam questions by AWS service:

    AWS RDS and Aurora — 40%
    - Read replicas and Multi-AZ deployments in details
    - Migrating from AWS RDS to Aurora
    - Performance tuning for both RDS and Aurora RDS
    - The “RDS Performance Insights” feature
    - Exporting, analyzing, and manipulating RDS logs
    AWS DynamoDB — 15%
    - On-demand throughput and provisioned throughput
    - Strongly consistent reads/writes and eventually consistent reads/writes
    - AWS DynamoDB streams
    - AWS DynamoDB global tables
    AWS Database Migration Tool and Schema Conversion Tool — 15 %
    - Use cases for AWS DMS and AWS SCT
    - Combining AWS DMS with AWS Snowball for large amounts of data
    - Conversion of stored procedures
    AWS CloudFormation — 10%
    - General questions about use cases
    - Managing sensitive information using AWS Secret Manager and SSM parameter store
    AWS Key Management Service — 10%
    - Enabling encryption for AWS RDS and Aurora with minimal downtime
    - Manipulating the encrypted database snapshots
    Troubleshooting Database Connection Issues — 5%
    - Network ACL and security groups pertaining to databases
    Other — 5%
    - Loading data into AWS Neptune
    - Troubleshooting AWS RedShift
    - Choosing the right database technology for a given use case

How to prepare

Preparation for this exam was a formidable challenge because there are almost no resources dedicated to the exam itself, except for the official exam guide, documentation, and AWS blogs. Below is a consolidated list of resources that I found helpful during my exam preparation.
Official exam guide

At the time of writing this report, this is the only official resource for the certification. There are no practice exams, LinuxAcademy, or ACloudGuru courses. You can download the exam guide here.
Breakout sessions from re:Invent

During my exam, I noticed that the use cases described in breakout sessions on re:Invent were sometimes a source of exam questions; this makes sense, as people who speak on stage often contribute to the exam questions. It’s not possible to watch all the sessions — but in general, the more sessions you watch, the higher your final score will be. Following this rule helped me to ace eight past AWS exams. Recordings of almost all re:Invent sessions are available on YouTube.
AWS Documentation by Exam Topic: Supporting Links Just for You

In the exam guide, there are five test domains and objectives. The list below aligns them with the appropriate AWS documentation. If you carefully read the entire list — the chance of winning increases.

1.1 Select the appropriate database services for specific types of data and workloads.
https://pages.awscloud.com/purpose-built-databases-ebook
https://www.youtube.com/watch?v=HaEPXoXVf2k&t=1s

1.2 Determine strategies for disaster recovery and high availability.
https://aws.amazon.com/blogs/database/implementing-a-disaster-recovery-strategy-with-amazon-rds/
https://aws.amazon.com/blogs/database/how-to-use-amazon-dynamodb-global-tables-to-power-multiregion-architectures/
https://aws.amazon.com/dynamodb/global-tables/
https://aws.amazon.com/rds/details/read-replicas/
https://aws.amazon.com/rds/details/multi-az/
https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-multi-master.html

1.3 Design database solutions for performance, compliance, and scalability.

Performance:
https://aws.amazon.com/blogs/database/best-storage-practices-for-running-production-workloads-on-hosted-databases-with-amazon-rds-or-amazon-ec2/
https://aws.amazon.com/blogs/database/boosting-application-performance-and-reducing-costs-with-amazon-elasticache-for-redis/
https://aws.amazon.com/blogs/database/caching-for-performance-with-amazon-documentdb-and-amazon-elasticache/
https://aws.amazon.com/blogs/database/optimizing-amazon-dynamodb-scan-latency-through-schema-design/
https://aws.amazon.com/blogs/database/amazon-dynamodb-auto-scaling-performance-and-cost-optimization-at-any-scale/

Compliance:
https://aws.amazon.com/blogs/database/applying-best-practices-for-securing-sensitive-data-in-amazon-rds/
https://aws.amazon.com/blogs/database/best-practices-for-securing-sensitive-data-in-aws-data-stores/
https://aws.amazon.com/blogs/database/securing-data-in-amazon-rds-using-aws-kms-encryption/
https://aws.amazon.com/blogs/database/how-lifeomics-jupiterone-simplifies-security-and-compliance-operations-with-amazon-neptune/

Scalability:
https://aws.amazon.com/blogs/database/autodesk-builds-on-amazon-aurora/
https://aws.amazon.com/blogs/database/sharding-with-amazon-relational-database-service/
https://aws.amazon.com/blogs/database/scaling-your-amazon-rds-instance-vertically-and-horizontally/
https://aws.amazon.com/blogs/database/amazon-aurora-as-an-alternative-to-oracle-rac/
https://aws.amazon.com/blogs/database/how-to-scale-aws-database-migration-service-dms-replication-instances/

Costs:
https://aws.amazon.com/blogs/database/reduce-database-cost-and-improve-availability-when-you-migrate-to-the-aws-cloud/
https://aws.amazon.com/blogs/database/reducing-aurora-postgresql-storage-i-o-costs/
https://aws.amazon.com/blogs/database/using-aws-cost-management-products-to-help-save-costs-on-amazon-rds-reserved-instances/
https://aws.amazon.com/blogs/database/how-cloudability-boosted-performance-simplified-tuning-and-lowered-costs-with-amazon-aurora/

2.1 Automate database-solution deployments.
https://aws.amazon.com/blogs/database/part-1-role-of-the-dba-when-moving-to-amazon-rds-responsibilities/
https://aws.amazon.com/blogs/database/automating-table-mappings-creation-in-aws-dms/
https://aws.amazon.com/blogs/database/create-aws-cloudformation-templates-for-aws-dms-tasks-using-microsoft-excel/

2.2 Determine data preparation and migration strategies.
https://aws.amazon.com/blogs/database/automating-database-migration-and-refreshing-activities-with-aws-dms/
https://aws.amazon.com/blogs/database/database-migration-what-do-you-need-to-know-before-you-start/
https://aws.amazon.com/blogs/database/how-to-solve-some-common-challenges-faced-while-migrating-from-oracle-to-postgresql/
https://aws.amazon.com/blogs/database/best-practices-for-migrating-an-oracle-database-to-amazon-rds-postgresql-or-amazon-aurora-postgresql-source-database-considerations-for-the-oracle-and-aws-dms-cdc-environment/

2.3 Execute and validate data migration.
https://aws.amazon.com/dms/resources/?nc=sn&loc=5
https://docs.aws.amazon.com/dms/latest/userguide/Welcome.html
https://aws.amazon.com/blogs/database/validating-database-objects-after-migration-using-aws-sct-and-aws-dms/

3.1 Determine maintenance tasks and processes.
https://aws.amazon.com/premiumsupport/knowledge-center/rds-common-dba-tasks/

3.2 Determine backup and restore strategies.
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html#Overview.BackupDeviceRestrictions
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_CommonTasks.BackupRestore.html
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/BackupRestore.html
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/PointInTimeRecovery.html

4.1 Determine monitoring and alerting strategies.
https://docs.aws.amazon.com/en_pv/AmazonRDS/latest/UserGuide/CHAP_Monitoring.html
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Monitoring.OS.html
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Events.html
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_LogAccess.html

4.2 Troubleshoot and resolve common database issues.
https://docs.aws.amazon.com/en_pv/AmazonRDS/latest/UserGuide/CHAP_Troubleshooting.html
https://docs.aws.amazon.com/redshift/latest/dg/queries-troubleshooting.html
https://docs.aws.amazon.com/redshift/latest/mgmt/troubleshooting-connections.html
https://docs.aws.amazon.com/redshift/latest/dg/t_Troubleshooting_load_errors.html
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Programming.Errors.html
https://docs.aws.amazon.com/dynamodb-encryption-client/latest/devguide/troubleshooting.html
https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-handling-errors.html

4.3 Optimize database performance.
https://aws.amazon.com/blogs/database/best-storage-practices-for-running-production-workloads-on-hosted-databases-with-amazon-rds-or-amazon-ec2/
https://aws.amazon.com/blogs/database/boosting-application-performance-and-reducing-costs-with-amazon-elasticache-for-redis/
https://aws.amazon.com/blogs/database/caching-for-performance-with-amazon-documentdb-and-amazon-elasticache/
https://aws.amazon.com/blogs/database/optimizing-amazon-dynamodb-scan-latency-through-schema-design/
https://aws.amazon.com/blogs/database/amazon-dynamodb-auto-scaling-performance-and-cost-optimization-at-any-scale/

5.1 Encrypt data at rest and in transit.
https://aws.amazon.com/blogs/database/securing-data-in-amazon-rds-using-aws-kms-encryption/
https://docs.aws.amazon.com/en_pv/AmazonRDS/latest/UserGuide/USER_ShareSnapshot.html

5.2 Evaluate auditing solutions.
https://aws.amazon.com/blogs/database/how-to-automate-the-audit-of-operational-best-practices-for-your-aws-account/
https://aws.amazon.com/blogs/database/audit-amazon-aurora-database-logs-for-connections-query-patterns-and-more-using-amazon-athena-and-amazon-quicksight/
https://aws.amazon.com/blogs/database/auditing-an-amazon-aurora-cluster/

5.3 Determine access control and authentication mechanisms.
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAMDBAuth.html
You got this

For now, I need only to wait until the AWS finishes the beta period and announces the exam results. If I pass, I will later update this blog post with the new badge. Otherwise, this will serve as a letter to my future self that could help me if I need to retake the exam. There is no cost associated with retaking beta exams.
