# 5 More on SAP AI Governance

## 5.1 Knowing What's Running: Governing AI Agents with SAP AI Agent Hub

The SAP AI Agent Hub (built on SAP LeanIX, now GA) gives you a single command center view of your entire AI agent landscape. Here is what you can see:

What you can see in SAP AI Agent Hub
1. **Agent Inventory:** — all agents in your landscape
A unified registry of every agent operating in your environment, regardless of origin:

SAP-built agents (Joule agents, S/4HANA agents, SuccessFactors agents, etc.),
custom agents built in Joule Studio or elsewhere,
third-party agents from Microsoft, Google, AWS, Databricks, ServiceNow, and others. 
For each agent you see: identity (name, description, provider), service endpoint, classification, status, and ownership. 

2. **Business context:** where agents are deployed
Which business capabilities or process steps each agent supports
Which applications or systems the agent is connected to
mapping agents to your architecture and business landscape.
3. **Models & MCP Servers:**
Beyond agents you also get visibility into LLMs and Model Context Protocol (MCP) servers running in your landscape, all in the same registry.

4. **Performance & Observability:** 
How agents are performing (goal completion, policy conformance, business impact)
Agent behavior and usage patterns
Identify redundancies or underperforming agents.
5. **Governance & Risk:**
Policy conformance across agents
Ownership tracking who is responsible for each agent
Foundation for access control and audit of agent activity.

## 5.2 Exercise: Finding the Financial Closing Assistant in SAP AI Agent Hub 

Now let's check our Assistant in SAP Ai Agent Hub

1. Navigate to https://de-6.leanix.net/SolutionExperience7ce8f
Your Username is xp262-0XX@bestrunsap.com, where XX is your seat number. 
Your Password is Acce$$teched26.
<br>![](/exercises/ex5/images/Ex5_1.png)

2. Press on **Ask Me Later**
<br>![](/exercises/ex5/images/Ex5_2.png)

3. Navigate to the upper right corner: 
<br>![](/exercises/ex5/images/Ex5_3.png)

4. Start tipping the name of your Assistant *Financial* and select the correct entry.
<br>![](/exercises/ex5/images/Ex5_4.png)

5. On the Fact Sheet you will notice your instance as well the link to the SAP Cloud Identity Services associated with it.
<br>![](/exercises/ex5/images/Ex5_5.png)

## 5.3 Other related TechEd sessions 

[BT102V | From AI sprawl to AI governance with SAP AI Agent Hub](URL "https://www.sap.com/events/teched/virtual/flow/sap/tev26/catalog/page/catalog/session/1788452327509003AspI")
Today, agents are built across enterprise systems, business functions, and vendors, and nobody has the full picture. This creates real exposure: compliance gaps, blind spots, and risk you can't see coming. Experience live how the SAP AI Agent Hub solution takes you from AI sprawl to a real governance practice.


[XP112 | How SAP secures enterprise AI agents with identity propagation](URL "https://www.sap.com/events/teched/berlin/flow/sap/te26/catalog/page/catalog/session/1787664725605001QBue")
Enterprise AI agents need the same identity governance as human users. See how SAP Cloud Identity Services manages both in a single directory, propagates user context with token exchange, and enforces authorization at every hop. Microsoft, Google, and partner agents take the same flow through the agent gateway. No agent holds back-end credentials.


[XP100 | Evolving the identity lifecycle for an AI-first future](URL "https://www.sap.com/events/teched/berlin/flow/sap/te26/catalog/page/catalog/session/1786632565262001KJNp")
Learn how SAP Cloud Identity Services provide the foundation for secure authentication, identity lifecycle management, and smooth access across SAP landscapes. See how agent identity concepts and SAP-managed identity and access management scenarios simplify secure communication, reduce operational complexity, and strengthen enterprise security.

## Summary

You have successfully completed this material. 

Thank you for choosing our session today ! 

