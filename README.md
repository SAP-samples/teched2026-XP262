# XP262 - Governing AI with identity and access management

## Description

This repository contains the material for the SAP TechEd 2026 session called XP262 - Governing AI with identity and access management.


## Overview

In this hands-on TechEd session, you will follow a realistic end-to-end scenario that connects SAP Cloud Identity Services, SAP S/4HANA, and the SAP AFC Assistant (Joule). Starting from a blank slate, you will experience — and resolve — three progressive access failures, each exposing a different layer of the identity and authorization stack.

You will learn how user identities flow from the SAP Cloud Identity Services - Identity Directory (IdDS) into S/4HANA via the Identity Provisioning Service, how group memberships in IdDS translate into Business Role assignments in S/4HANA, and how SAP Managed Joule keep authorizations and users synchronized across the landscape. Finally, you will explore how access policies in the Identity Directory control which users can interact with AI-powered assistants like Joule.

By the end of this session, you will have a solid, practical understanding of the full authorization chain — from identity provisioning to assistant-level access control — and the troubleshooting skills to diagnose and fix issues at each layer.

## Requirements

N/A

## Chapters

- [Agent Identity](exercises/ex0/)
    - [Architecture](exercises/ex0/#architecture)
    - [Key Architectural Concepts](exercises/ex0/#key-architectural-concepts)
- [First Roadblock: No authorization, No Access](exercises/ex1/)
    - [1.1 Exercise: Meet the Financial Closing Agent](exercises/ex1/#11-exercise-meet-the-financial-closing-agent)
    - [1.2 Agent Access Governance – Three Layers of Access Assessment](exercises/ex1/#12-agent-access-governance--three-layers-of-access-assessment)
    - [1.3 Demo: Checking application authorizations](exercises/ex1/#13-demo-checking-application-authorizations)
- [Second Roadblock: Business Roles in the back end](exercises/ex2/)
    - [2.1 Exercise: Reaching out to the Financial Closing Assistant](exercises/ex2/#21-exercise-reaching-out-to-the-financial-closing-assistant)
    - [2.2 Demo: Checking back-end authorizations](exercises/ex2/#22-demo-checking-back-end-authorizations)
- [Third Roadblock: Authorization Exists but Joule Still Fails](exercises/ex3/)
    - [3.1 Exercise: Reaching out to the Financial Closing Assistant again](exercises/ex3/#31-exercise-reaching-out-to-the-financial-closing-assistant-again)
    - [3.2 SAP-Managed Provisioning](exercises/ex3/#32-sap-managed-provisioning)
    - [3.3 Demo: SAP-Managed Provisioning](exercises/ex3/#33-demo-sap-managed-provisioning)
- [Success: The AFC Assistant Is Working](exercises/ex4/)
    - [4.1 Exercise: Reaching out to the Financial Closing Assistant one last time](exercises/ex4/#41-exercise-reaching-out-to-the-financial-closing-assistant-one-last-time)
- [More on SAP AI governance](exercises/ex5/)
    - [5.1 Knowing What's Running: Governing AI Agents with SAP AI Agent Hub](exercises/ex5/#51-knowing-whats-running-governing-ai-agents-with-sap-ai-agent-hub)
    - [5.2 Exercise: Finding the Financial Closing Assistant in SAP AI Agent Hub](exercises/ex5/#52-exercise-finding-the-financial-closing-assistant-in-sap-ai-agent-hub)
    - [5.3 Other related TechEd sessions](exercises/ex5/#53-other-related-teched-sessions)


## License
Copyright (20xx-)20xx SAP SE or an SAP affiliate company and <your-project> contributors. Please see our [LICENSE](LICENSE) for copyright and license information. Detailed information including third-party components and their licensing/copyright information is available [via the REUSE tool](https://api.reuse.software/info/github.com/SAP/<your-project>).
