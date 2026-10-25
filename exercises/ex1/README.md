# 1 First Roadblock: No authorization, No Access

In this exercise, we will meet the Financial Closing Agent. 

## 1.1 Exercise: Meet the Financial Closing Agent


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


The following diagram illustrates the three layers of access assessment​.
<br>![](/exercises/ex1/images/Ex1_4.png)

The layers are complementary and represent the **authorization** for AI agents.
 Each layer answers a different question: Is the action allowed by the application? May the user invoke the agent? And may the agent call the required API? Together, these checks address different access risks rather than replacing one another.

 1. Application authorizations: Is the business action allowed?

The target application remains responsible for enforcing its own authorization rules. These can include ABAP roles, restrictions on specific business objects or instances, and attribute-based checks. Even when a request comes through an agent, the application checks whether the action is permitted and rejects unauthorized requests at the application level. 

 2. Agent access: May this user invoke the agent?

This layer controls access to the agent itself. The agent gateway checks every incoming request to determine whether the user has permission to invoke that agent. The diagram describes these access controls as automatically generated at deployment time. If the user lacks permission, the gateway blocks the request before it reaches the agent. 

 3. Scoped access: May the agent call this API?

This layer limits which APIs the agent can call and which HTTP operations it can perform. The gateway checks the permissions carried in the agent’s token against the requested API and HTTP verb. If the required permission is missing, it immediately returns a `403 Forbidden` response—following the principle “fail early, fail cheap.” 

### 1.2.1 How the layers work together

Permission to use an agent does not automatically grant permission to use every API, and permission to call an API does not override the target application’s business authorization rules. The diagram therefore separates user-to-agent access, agent-to-API permissions, and application-level authorization into distinct controls. Its “1st,” “2nd,” and “3rd” labels should not be confused with runtime execution order: the gateway checks block unauthorized requests before they reach the agent or target application, while application-specific checks take place in the target application itself. 

## 1.3 Demo: Checking application authorizations 

Let's check your user in the SAP Cloud Identity Services : 
<br>![](/exercises/ex1/images/Ex1_8.png)

We notice that your user does not have policies to use the assistant. As the  [documentation](URL "https://help.sap.com/docs/AUTONOMOUS_FINANCE_DOMAIN/b233792a00de4edc8d668bf422fd59a3/08d7065ec74f470eb6b484ae706467a1.html?locale=en-US") indicates, we need to assign the user to policies corresponding to the following agents connected to the assistant : 

- Journal Entry Agent
- Accounting Accruals Agent
- Receivables and Payables Clearing Agent
- Analytical Business Insights Agent
- Financial Consistency Analysis Agent
- Asset Accounting Anomaly Detection Agent
- Financial Closing Orchestration Agent


First, to be efficient, we will create a user group that will contain all the users that need access to the agent(s).Afterwards will add this user groups to all the agents. 

This is how the assignment will work:

1. In the SCI console, navigate to *Users & Authoriozations* -> *Greoups* and press on **Create**. Fill in the **Name** and **Display Name** fields. Press on **Next Step**
<br>![](/exercises/ex1/images/Ex1_9.png)

2. Do not add and **Application** here, as we want to create a *user group*.
<br>![](/exercises/ex1/images/Ex1_10.png)

3. Check the **Summary** and press on **Finish**
<br>![](/exercises/ex1/images/Ex1_11.png)

4. To the newly created user group, add your user: 
<br>![](/exercises/ex1/images/Ex1_12.png)

5. Navigate to *Users & Authoriozations* -> *Agents* and search for the first agent : 
<br>![](/exercises/ex1/images/Ex1_13.png)

6. Press on **Manage Access** and search for the newly created user group.
<br>![](/exercises/ex1/images/Ex1_14.png)

7. Review your change and press **Save**.
<br>![](/exercises/ex1/images/Ex1_15.png)



## Summary

Now that you learned about the three layers of Agent Access Governance application authorizations that enforce business-level permissions, agent access controls that determine whether a user may invoke an agent, and scoped access that restricts which APIs an agent can call you understand why your first interaction with the Financial Closing Agent failed and how assigning the agent policies in SAP Cloud Identity Services *might* resolves the issue.

Continue to - [Second Roadblock: Business Roles in the back end](../ex2/README.md)

