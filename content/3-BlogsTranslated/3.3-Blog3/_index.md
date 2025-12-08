---
title: "Blog 3"
date: "2025-09-10"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
# Artificial Intelligence
## Building a Just-in-Time Knowledge Base with Amazon Bedrock

**Author:** Steven Warwick  
**Date:** 07 JUL 2025  
**Source:** Amazon Bedrock, Amazon Bedrock Knowledge Bases, Cloud Cost Optimization, AI, SaaS  

---

# Summary

Multi-tenant SaaS systems often need to process a large volume of documents, but traditional RAG approaches consume excessive resources because they ingest and store embeddings for documents that may never be queried.

The **Just-in-time Knowledge Base** architecture solves these challenges by:

- Processing documents only when needed (on-demand ingestion)  
- Automatically removing unused data using **DynamoDB TTL**  
- Reducing OpenSearch Serverless costs  
- Supporting multi-tenant isolation and strong data separation  
- Enabling tier-based pricing depending on tenant configuration  

This solution allows SaaS providers to scale flexibly, reduce operational overhead, and maintain high query performance.

---

# Architecture Overview

The solution uses the following AWS services:

- **Amazon Bedrock** – Document processing, querying, and RAG content generation  
- **Amazon OpenSearch Serverless** – Vector indexing and search  
- **Amazon S3** – Storing raw files  
- **Amazon DynamoDB** – Storing metadata, TTL, and tenant document tracking  
- **AWS Lambda** – Automatically cleaning expired documents  
- **AWS CDK** – Infrastructure provisioning  

These components work together to ensure only necessary documents are ingested, while outdated data is automatically removed.

---

# Workflow

## 1. User login and tenant assignment
When a user logs in, the system assigns a **tenantId** to define the data boundary and access scope.

## 2. Create a project
Each project contains a list of files the user wants to query.  
The system initializes metadata linking **user – tenant – project**.

## 3. Upload files
Users upload files via pre-signed URLs.  
Files are stored in S3 and metadata is recorded in DynamoDB.

## 4. Just-in-time ingestion
Documents are only ingested into the Knowledge Base **when the user starts chatting with the project**.

Each file receives a **TTL based on the tenant’s subscription tier**.

## 5. Refreshing TTL during queries
Frequently-queried documents → TTL is extended → remain active.  
Unused documents → TTL expires → removed automatically.

## 6. Automatic document deletion
DynamoDB Streams detect TTL expiration → Lambda deletes the document from the Knowledge Base and OpenSearch.

---

# Example: Ingesting tenant-specific TTL documents

```python
# Ingesting files with tenant-specific TTL values
def ingest_files(user_id, tenant_id, project_id, files):
    tenants = json.loads(os.environ.get('TENANTS'))['Tenants']
    tenant = find_tenant(tenant_id, tenants)
    ttl = int(time.time()) + (int(tenant['FilesTTLHours']) * 3600)

    for file in files:
        file_id = file['id']
        s3_key = file.get('s3Key')
        bucket = file.get('bucket')

        knowledge_base_files_table.put_item(
            Item={
                'id': file_id,
                'userId': user_id,
                'tenantId': tenant_id,
                'projectId': project_id,
                'documentStatus': 'ready',
                'createdAt': int(time.time()),
                'ttl': ttl
            }
        )
Nếu bạn muốn mình dịch ngắn hơn, dịch kiểu academic, dịch kiểu technical A