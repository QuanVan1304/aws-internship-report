---
title: "Event 3"
date: 2026-08-01
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# OAWS FCAJ Agent Forge - Deepdive - August 2026

### Event Objectives

- Experience the direct onboarding process, get familiar with the working environment and culture at the AWS office.
- Clarify the essence of Agentic AI systems and distinguish the levels of autonomy in software operations.
- Deep dive into the Amazon Bedrock Agent Core architecture: Runtime, Identity, and Gateway.
- Share operational strategies (Best Practices) and security measures to deploy large-scale AI systems (production-ready).

### Speakers

- **Mr. Nghia** - Host & Speaker, an expert leading and sharing the theoretical foundation of Agentic AI architecture.
- **Hai Anh** - Lab Instructor, directly coordinating and guiding the practical session (Hands-on Lab).

### Key Highlights

#### The Essence of Agentic AI
- **Topic:** "Definition and levels of autonomy"
- Explained that Agentic AI is a software system capable of reasoning, planning, and executing complex tasks.
- Clearly distinguished the difference between **Deterministic workflow** (a process predefined by developers, ensuring high stability) and **Multi-agent system** (a system of multiple agents that automatically divide and coordinate work).

#### Component Layers in Amazon Bedrock Agent Core
- **Topic:** "Solving the large-scale deployment problem (Production-ready)"
- **Runtime Environment:** Provides an auto-scaling serverless environment. Uses Firecracker MicroVM technology to completely isolate user sessions, combined with bidirectional streaming for real-time responses.
- **Identity & Access Management:** Acts as the authentication and authorization manager. Uses a smart token exchange mechanism (from JWT to Workload Access Token) to prevent information leakage.
- **Gateway:** A middleware layer managing connections between agents and tools. Integrates Semantic Search (selecting tools via semantic description) and the Human-in-the-loop moderation mechanism.

#### Best Practices for Enterprises
- **Topic:** "Security strategies and safe operations"
- Recommended using **AWS PrivateLink** to establish secure connections from on-premises systems to the Cloud, bypassing the public Internet.
- Emphasized the importance of strict Versioning management to easily roll back when the system encounters errors in the live environment.

### Key Takeaways

#### System Design & Security Mindset
- Deeply realized that AI security is not only applied at the application layer but must be established from the network layer (PrivateLink) and virtualization layer (Firecracker MicroVM).
- Understood that **Human-in-the-loop** is a mandatory safeguard to control business risks for sensitive tasks such as finance and refunds.

#### Technical Mindset
- Mastered how the 3 layers—Runtime, Identity, and Gateway—coordinate synchronously within the Bedrock Agent Core ecosystem.
- Understood the superiority of using Semantic Search to call tools flexibly, replacing the traditional, rigid hard-coded API approach.

### Applying to Work

- **Designing Safe Features:** Immediately apply the Human-in-the-loop moderation mechanism when building critical data processing modules during the upcoming internship.
- **Lifecycle Management Integration:** Form a habit of applying the Versioning strategy to all updates for easy restoration (roll-back) when necessary.
- **Workflow Optimization:** Research and test how to set up a Multi-agent system to automate repetitive tasks.
- **Workplace Integration:** Quickly get accustomed to the office space, and practice a professional demeanor to collaborate effectively with engineers at AWS.

### Event Experience

Attending the Onboarding and in-depth training event at the AWS office on August 1, 2026, was a valuable practical experience, helping me take the first steps in getting familiar with an international corporate environment. Some highlight experiences include:

#### Learning from Theory to Practice
- The perfect combination of Mr. Nghia's in-depth theoretical lecture and Hai Anh's Hands-on Lab helped me digest the knowledge very quickly.
- Directly configuring the system made abstract technical concepts (like Gateway, Runtime) extremely visual and easy to grasp.

#### Experiencing a Professional Workspace
- Directly felt the open working culture and accessed modern technology infrastructure right at the AWS headquarters.
- Impressed by the professionalism in event organization and the highly understandable knowledge transfer provided by the engineering team.

#### Lessons Learned
- To build a successful Agentic AI system, a smart LLM model is not enough. More importantly, the surrounding software architecture (middleware, identity, runtime) must be truly solid, secure, and easy to control.


> Overall, this combined Onboarding and in-depth training event not only equipped me with "hardcore" technical knowledge about Agentic AI but also helped me integrate, better understand the engineering culture, and clearly shape a professional working style at AWS.