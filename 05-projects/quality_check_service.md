# Quality Check Service

## Project Overview

Quality Check Service is an enterprise-grade backend microservice designed to automate document quality verification during underwriting workflows.

The service consumes OCR-extracted Key-Value Pairs (KVPs) generated from documents uploaded through the Information Request Service (IRS). It evaluates the extracted data against configurable business validation rules and generates an automated quality analysis that assists underwriters in making faster and more consistent decisions.

When additional documentation is required, the service integrates back with the Information Request Service to initiate an Additional Document Required (ADR) request, creating a complete end-to-end document collection and verification lifecycle.

---

# Business Problem

Before this service was introduced, document verification was largely performed manually by underwriters.

The process involved:

- Reading uploaded documents manually.
- Verifying extracted information field by field.
- Comparing document values against business requirements.
- Identifying missing or incorrect information.
- Recording observations manually.

This resulted in:

- High manual effort
- Longer turnaround time
- Human errors
- Inconsistent validation
- Increased underwriting workload
- Poor scalability

---

# Solution

The Quality Check Service automates document verification by consuming OCR-extracted Key-Value Pairs (KVPs) and validating them using configurable business rules.

Instead of manually reviewing every uploaded document, underwriters receive an automated analysis highlighting:

- Missing information
- Invalid values
- Rule validation failures
- Quality observations
- Overall document assessment

The validation engine is configurable, allowing different clients and document types to use different validation rules without changing application code.

---

# Business Impact

The service became a key component of the end-to-end underwriting workflow.

It enabled:

- Automated quality analysis
- Faster underwriting decisions
- Standardized validation
- Reduced manual verification effort
- Consistent business rule execution
- Better document processing efficiency
- End-to-end integration with the Information Request Service

Whenever additional documents are required, underwriters can generate an ADR request that is routed back to the Information Request Service, enabling customers to upload additional documents and continue the verification cycle.

---

# Project Type

- Enterprise Backend Microservice
- Rule-Based Validation Service
- Greenfield Project (Built from Scratch)

---

# My Role

**Role:** Backend Engineer

I was responsible for the end-to-end backend ownership of the service, including:

- Requirement analysis
- Technical design
- Database design
- Backend architecture implementation
- REST API development
- Business logic implementation
- Rule engine development
- PostgreSQL integration
- Spring Data JPA implementation
- Production support
- Bug fixing
- Feature enhancements
- API testing
- Ongoing maintenance

The Tech Lead provided architectural guidance whenever required, while the implementation and day-to-day ownership of the backend service remained primarily with me.

---

# Team Structure

- 1 Backend Engineer (Myself)
- 1 Frontend Developer
- 1 QA Engineer
- 1 Tech Lead

---

# Technology Stack

## Programming Language

- Java 17

## Backend Framework

- Spring Boot

## Persistence

- Spring Data JPA
- Hibernate

## Database

- PostgreSQL

## Build Tool

- Maven

## Version Control

- Git

## API Testing

- Postman

## IDE

- IntelliJ IDEA
- Visual Studio Code

---

# System Architecture

The Quality Check Service is a downstream validation microservice within the enterprise document processing pipeline.

Documents are uploaded through the Information Request Service.

A dedicated OCR Service extracts Key-Value Pairs (KVPs) from uploaded documents.

The Quality Check Service consumes these extracted values, evaluates them against configurable business rules, and generates an automated quality analysis.

Underwriters review this analysis and, if additional documentation is required, create an ADR request which is sent back to the Information Request Service to continue the document collection process.

The service intentionally delegates OCR processing to a dedicated OCR microservice and focuses solely on business rule evaluation.

---

# High-Level Workflow

Customer

↓

Uploads Documents

↓

Information Request Service (IRS)

↓

OCR Service

↓

Extracted Key-Value Pairs (KVPs)

↓

Quality Check Service

↓

Configurable Rule Engine

↓

Automated Quality Analysis

↓

Underwriter Review

↓

ADR Required?

├── No → Continue Underwriting

└── Yes

↓

Information Request Service

↓

Customer Uploads Additional Documents

↓

Workflow Continues

---

# Service Integration

## Information Request Service (IRS)

- Receives uploaded documents.
- Sends ADR requests back to IRS.
- Supports an iterative document collection workflow.

## OCR Service

- Extracts Key-Value Pairs (KVPs).
- Provides extracted document data.
- Quality Check Service consumes OCR output.

## Underwriter Portal

- Displays automated analysis.
- Allows review of validation results.
- Enables ADR generation.

---

# Core Responsibilities

- Consume OCR-extracted Key-Value Pairs.
- Execute configurable business validation rules.
- Generate automated document analysis.
- Produce validation results for underwriters.
- Support multiple clients through configurable validation logic.
- Maintain production stability.
- Implement new business requirements.
- Resolve production issues.
- Enhance rule evaluation capabilities.

---

# Project Duration

Approximately 3 months for initial development.

Currently under active ownership for:

- Production support
- Bug fixes
- Feature enhancements
- Business requirement implementation
- Backend maintenance

---

# Ownership

This is one of my primary ownership areas.

Current responsibilities include:

- Production issue resolution
- Backend feature development
- Requirement analysis
- Bug fixing
- Business rule implementation
- Long-term service ownership
- Continuous improvements

---

# Engineering Notes

## Architecture Decision

OCR processing is intentionally separated into a dedicated OCR microservice.

The Quality Check Service focuses exclusively on business validation by evaluating OCR-extracted Key-Value Pairs (KVPs).

This separation follows the Single Responsibility Principle and allows OCR and validation logic to evolve independently.

---

# Related Services

- Information Request Service
- OCR Service
- Underwriter Portal

---

# APIs

(To be documented)

---

# Database Design

(To be documented)

---

# Request Flow

(To be documented)

---

# Authentication

(To be documented)

---

# Configuration

(To be documented)

---

# Business Rules

(To be documented)

---

# Challenges Faced

(To be documented)

---

# Production Incidents

(To be documented)

---

# Optimizations

(To be documented)

---

# Resume Ready Bullet Points

(To be documented)

---

# STAR Stories

(To be documented)

---

# Interview Questions

(To be documented)

---

# Learnings

(To be documented)

---

# Future Improvements

(To be documented)