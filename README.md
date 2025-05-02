# EHR-FHIR Data Extractor

A comprehensive solution for automated extraction and conversion of Electronic Health Record (EHR) 
data into FHIR (Fast Healthcare Interoperability Resources) standard format and then to use for data visulisation.

## Problem Statement

Healthcare providers face significant challenges with their legacy EHR systems:

- Data extraction from EHRs is predominantly manual, time-consuming, and error-prone
- Integration of new EHR in the system is manual and also harcoded values in lambda functions such as client id, client secret etc.
- Multiple data formats create interoperability issues between healthcare systems
- Lack of standardization impedes comprehensive patient care and reporting
- Manual data entry introduces risks of human error affecting patient care
- Resource allocation for data management takes away from patient care time

## Proposed Solution

EHR-FHIR Data Extractor provides an automated system that:

1. Extracts patient data from legacy EHR systems
2. Validates and transforms this data to meet FHIR standards
3. Enables seamless integration with FHIR-compliant systems
4. Reduces manual intervention through automation
5. Ensures data integrity through validation processes
6. Standard Lambda functions which are compatible with any EHR. 

## New System Overview

The EHR-FHIR Data Extractor is a cloud-based solution that creates a bridge between legacy EHR systems and modern FHIR-compatible systems. It automates the entire process from data extraction to transformation and validation, providing healthcare providers with clean, standardized data without manual intervention.

## Key Functionality

### For Healthcare Providers
- **Automated Data Extraction**: Schedule and run automated extractions from EHR systems
- **Data Transformation**: Convert legacy data formats to FHIR-compliant resources
- **Validation Engine**: Ensure data meets FHIR standards before integration
- **User Dashboard**: Monitor extraction processes and data quality metrics
- **Error Handling**: Receive alerts and resolve data extraction issues

### For Administrators
- **User Management**: Control access and permissions
- **System Configuration**: Set up connections to EHR systems
- **Audit Trails**: Track all data transformations for compliance
- **Reporting**: Generate usage and performance reports
- **Backup & Recovery**: Ensure data preservation during extraction

### For Technical Users
- **API Integration**: Connect with other healthcare systems via APIs
- **Custom Mapping**: Define custom data mapping rules for specific needs
- **Batch Processing**: Handle large volumes of patient data efficiently
- **Logging & Monitoring**: Track system performance and errors

## System Architecture

![System Architecture Diagram](https://github.com/klsavaj/EHR-FHIR-Data-Extractor/blob/main/docs/images/architecture.png)

The system follows a three-tier architecture:

1. **Presentation Layer**: Web interface for user interaction
2. **Application Layer**: Core processing modules including:
   - Extraction Engine
   - Transformation Service
   - Validation Module
   - Scheduling Service
   - Error Handling Service
3. **Data Layer**: Storage for mappings, configurations, and temporary data

## Technical Stack

- **Frontend**: React.js, Bootstrap hosted on AWS Amplify
- **Backend**: AWS Lambda (Python runtime), API Gateway
- **Database**: Amazon RDS (PostgreSQL), DynamoDB
- **Cloud Infrastructure**: 
  - AWS VPC for network isolation
  - AWS IAM for access control
  - AWS Step Functions for flow of lambda functions
  - AWS Healthlake for Conversion in FHIR format 
- **Authentication**: Amazon Cognito, OAuth 2.0
- **Monitoring**: Amazon CloudWatch

## AWS Components in Detail

Based on the SDD, the system utilizes these key AWS services:

- **AWS Amplify**: For hosting the Frontend
- **AWS API Gateway**: For Routing Get/Post API request via front end to lambda Functions
- **Amazon RDS**: For storing Clinc/hospital contact details, EHR details, Fetch History data
- **Amazon S3**: For storing EHR data exports and FHIR resources
- **AWS Lambda**: For event-driven processing and transformations
- **AWS Secrets Manager**: For secure credential storage
- **AWS Healthlake**: For converting Json data to fhir Data
- **AWS Cognito**:For Authentication of user login
- **AWS IAM**: User access Control

## Security & Compliance

- HIPAA Compliance: The system implements all required controls for HIPAA compliance
- Data Encryption: All PHI data is encrypted at rest and in transit
- Access Control: Fine-grained IAM permissions for all system components
- Audit Logging: Comprehensive logging via CloudTrail and CloudWatch
- Network Security: VPC isolation with security groups and network ACLs

## Documentation
Comprehensive documentation is available in the /docs directory:

- Software Design Document (SDD)
- Software Requirements Specification (SRS)
- Software Testing Documentation (STD)

Comprehensive code explanation is available in the /code directory:
- Deployment.md file to set up AWS architecture
- /lambda_functions,  all functions have proper objective in the start of the function.

### Contributors
Jaynesh, Jaimin, Nitin, Rajath

