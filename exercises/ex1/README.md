# First Roadblock: No authorization, No Access

In this exercise, we will meet the Financial Closing Agent. 

## 1.1 Meet the Financial Closing Agent


1. Click on https://747238487.eu10.sapdas.cloud.sap/new/ 
<br>![](/exercises/ex1/images/Ex1_0.png)

Your Username is xp262-0XX@bestrunsap.com, where XX is your seat number. 
Your Password is Init1234. Reset it to something easy to memorize. 

2. Start a new conversation and choose from the drop-down menu the **Financial Closing Assistant**
<br>![](/exercises/ex1/images/Ex1_1.png)

3. Try the following prompt: *Create journal entry proposals for company code 1010*

<br>![](/exercises/ex1/images/Ex1_2.png)

4. Notice that the answer is not quite useful ..
<br>![](/exercises/ex1/images/Ex1_3.png)

What could be the reason ? 

## 1.2 Agent Access Governance – Three Layers of Access Assessment

<br>![](/exercises/ex1/images/Ex1_4.png)

The picture illustrates three complementary layers of **authorization** for AI agents. Each layer answers a different question: Is the action allowed by the application? May the user invoke the agent? And may the agent call the required API? Together, these checks address different access risks rather than replacing one another.

 1. Application authorizations: Is the business action allowed?

The target application remains responsible for enforcing its own authorization rules. These can include ABAP roles, restrictions on specific business objects or instances, and attribute-based checks. Even when a request comes through an agent, the application checks whether the action is permitted and rejects unauthorized requests at the application level. 

 2. Agent access: May this user invoke the agent?

This layer controls access to the agent itself. The agent gateway checks every incoming request to determine whether the user has permission to invoke that agent. The diagram describes these access controls as automatically generated at deployment time. If the user lacks permission, the gateway blocks the request before it reaches the agent. 

 3. Scoped access: May the agent call this API?

This layer limits which APIs the agent can call and which HTTP operations it can perform. The gateway checks the permissions carried in the agent’s token against the requested API and HTTP verb. If the required permission is missing, it immediately returns a `403 Forbidden` response—following the principle “fail early, fail cheap.” 

### How the layers work together

Permission to use an agent does not automatically grant permission to use every API, and permission to call an API does not override the target application’s business authorization rules. The diagram therefore separates user-to-agent access, agent-to-API permissions, and application-level authorization into distinct controls. Its “1st,” “2nd,” and “3rd” labels should not be confused with runtime execution order: the gateway checks block unauthorized requests before they reach the agent or target application, while application-specific checks take place in the target application itself. 

## Checking application authorizations 

Let's check your user in the SAP Cloud Identity Services : 
<br>![](/exercises/ex1/images/Ex1_8.png)

And now in the back-end system: 
<br>![](/exercises/ex1/images/Ex1_5.png)

We notice that your user does not have back-end authorizations. 
<br>![](/exercises/ex1/images/Ex1_6.png)


Let's assign them in the back end: 
<br>![](/exercises/ex1/images/Ex1_7.png)



## Summary

Now that you learned about the three layers of Agent Access Governance — application authorizations that enforce business-level permissions, agent access controls that determine whether a user may invoke an agent, and scoped access that restricts which APIs an agent can call — you understand why your first interaction with the Financial Closing Agent failed and how assigning the correct back-end authorizations in SAP Cloud Identity Services might resolves the issue.

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

