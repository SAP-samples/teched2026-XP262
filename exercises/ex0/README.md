# Agent Identity

The Agent Identity is a foundational concept within the SAP AI Agent Governance framework. It represents the identity artifacts required to authenticate, authorize, and govern AI agents operating within an SAP landscape. Just as human users require identity records to access enterprise systems, AI agents—whether built on SAP technology or by third parties—require a dedicated identity that defines their boundaries, permissions, and allowed interactions.

SAP Cloud Identity Services acts as the central identity hub for both human identities and agent identities. By storing agent identities alongside human identities in the Identity Directory, enterprises gain a unified governance model that leverages existing IAM infrastructure—including authentication, federation, identity provisioning, and authorization management—for the new class of autonomous AI actors.


## Architecture

The following diagram shows the major components of the SAP Joule integration from an IAM perspective at a leadership level. SAP Cloud Identity Services (SCI) act as the central interface containing the SAP-landscape-relevant human identities and agent identities. SCI integrates with the SAP applications in scope in an SAP-managed way. This architecture is a key pillar in the Agent Governance framework for an SAP landscape.

The Agent Identity is a mandatory requirement to ensure the secure authentication and authorization of AI Agents in an SAP landscape.


<br>![](/exercises/ex0/images/Ex0_1.png)

## Key Architectural Concepts

### SAP Cloud Identity Services as the Agent Identity Store
SAP Cloud Identity Services serves as the single source of truth for both human and agent identities within the SAP landscape:

* Identity Directory stores agent identities and human identities, each with a Global User ID that enables cross-application identity linking.
* Identity Authentication handles the authentication of agents (and humans) using protocols such as OIDC, including federation with third-party identity providers.
* Identity Provisioning synchronizes agent identity records and their associated role/group assignments across connected SAP applications.
* Authorization Management defines and enforces what each agent identity is permitted to do, expressed through application groups and policies.

### Joule as the Engagement Layer

SAP Joule is the brand which contains several SAP Business AI aspects like the conversational AI interface through which business users interact with AI agents:

1. The user accesses SAP Joule through an application client (mobile or desktop).
2. SAP Joule authenticates the user via SAP Cloud Identity Services (with optional federation to a corporate Identity Provider).
3. The Joule orchestrator determines which agents and functions the user is authorized to invoke.
4. Conversations are routed to the appropriate agents, with each interaction governed by the user's identity and the agent's permitted scope.

### Agent Gateway for A2A Communication
The SAP Agent Gateway is a technical component wihtin the customer landscape but besides the A2A external endpoint transparent for the customer and fully SAP-managed. It provides the communication fabric for agent interactions:
 
* **External (A2A interface for third parties)**: Third-party agents connect to the Agent Gateway using the A2A protocol. Before any interaction, the third-party agent must authenticate through SAP Cloud Identity Services. The gateway enforces policy checks to validate whether the external agent's identity is authorized to communicate with the target SAP agent.

* **Internal (SAP-managed agent communication)**: When the Joule orchestrator dispatches work to agents on SAP technology, the Agent Gateway wraps the communication. It applies policy checks and authorization verification at each step, ensuring agents only invoke permitted APIs or tools on the target SAP applications (cloud or private cloud).

* **Policy enforcement points exist at multiple levels**: at the gateway entry (it checks if the calling user (human/agent) has access to call the dedicated agent), before agent-to-agent hand-off , and at the target application (The policy enforcement point between an agent and the API/tools/MCP will be released in H2/2026). The authZ check in the SAP Cloud application is built on the well established authorization concepts of SAP applications. This layered approach ensures unauthorized requests are rejected early, minimizing unnecessary network traffic and processing.

### Other Services & Components
* **SAP AI Agent Hub	Agent Governance** — cataloging and managing agent landscapes
* **SAP Cloud ALM	Agent Lifecycle Governance** — managing the lifecycle of agents from development to decommissioning
* **SAP4ME**	Provisioning of agent identities and configurations across the SAP landscape

## Summary

Now that you learned about Agent Identity, how SAP Cloud Identity Services acts as the central identity hub for authenticating and authorizing AI agents, and how the Agent Gateway enforces policy checks for both external A2A and internal SAP-managed agent communication, you have the foundational understanding to proceed with the next chapter.

Continue to - [Exercise 1 - Exercise 1 Description](../ex1/README.md)
