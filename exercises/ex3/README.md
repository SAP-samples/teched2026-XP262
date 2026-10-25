# 3 Third Roadblock: Authorization Exists but Joule Still Fails

## 3.1 Exercise: Reaching out to the **Financial Closing Assistant** again
Let's check if now with the correct policy assignments it will work: 

1. Return to your Joule Work UI  https://747238487.eu10.sapdas.cloud.sap/new/ 

2. Try the same prompt again: *Create journal entry proposals for company code 1010*
<br>![](/exercises/ex1/images/Ex1_2.png)

4. Notice that the answer is still not quite complete.
<br>![](/exercises/ex3/images/Ex3_8.png)

The reason for this is because the information from back-end was not synchronized in the SAP Cloud Identity Services centrally. SAP offers now SAP-managed functionality for achieving this, without having to change your IAM flows. The next chapter will explain how. 

## 3.2 SAP-Managed Provisioning

The SAP-managed experience is introduced for example when activating Joule for SAP S/4HANA Cloud, or for SAP SuccessFactors — without yet requiring a landscape-wide consolidation of identities.

Each line-of-business application continues to keep its own users. What makes this stage managed rather than merely isolated is that every user is cached (hidden) in the Identity Directory of SAP Cloud Identity Services from the connected applications. This allows the SAP Business AI Platform to use SAP Cloud Identity Services as its Identity and Access Management interface and as a central user and role store for filtering agentic communication.

Authentication for the scoped experience runs through SAP Cloud Identity Services for the SAP Business AI Platform (and SAP Joule WORK). Each connected SAP business application remains with the configured authentication and user lifecycle flows; each of those tenants acts in this scenario like an IdP. The successful authentication within one of the business applications is enough to initiate the session in Cloud Identity for the Business AI Platform. Authorization for the application remains defined and assigned within that application's domain.


### 3.2.1 Flow
1. The customer activates the SAP-managed experience (for example Joule) for one or more line-of-business applications.
2. The application is integrated with SAP Cloud Identity Services. All roles or groups from the connected application get replicated as (visible) application-groups into the Identity Directory.
3. Each application user gets (hidden) cached in the Identity Directory with the assigned application-groups.
4. The user interacts with the scoped experience; identity and authentication are governed by SAP Cloud Identity Services, while authorization stays within the application.

## 3.3 Demo: SAP-Managed Provisioning

With the activation of SAP

1. In the Provisioning tab we can see that the **SAP-Managed Provisioning** is not enabled. Let's try to enable it. 
<br>![](/exercises/ex3/images/Ex3_1.png)


2. What is happening: The wizard has detected a group conflict that must be resolved before SAP-Managed Provisioning can be enabled
<br>![](/exercises/ex3/images/Ex3_2.png)
The user must either:

- Map the local group to the corresponding application group (by filling in the right column), or
- Delete it permanently from the Identity Directory (trash icon)

We will map the local group to the corresponding one

3.  A second nested dialog has opened on top. This is the group mapping picker — triggered when the user clicked the copy/map icon in the right column next to S4HC_Cust_SMJ_Z_FINANCIAL_AGENTS. The dialog shows the available groups from the SAP S/4HANA Cloud – Sales Demo Customizing Tenant SMJ application side, with a search field at the top and one result: **Z_FINANCIAL_AGENTS** 
This is the corresponding group on the S/4HANA application side that the local Identity Directory group (S4HC_Cust_SMJ_Z_FINANCIAL_AGENTS) should be mapped to. The user selects Z_FINANCIAL_AGENTS to establish the mapping between the two groups, resolving the conflict and allowing the SAP-Managed Provisioning enablement to proceed.
<br>![](/exercises/ex3/images/Ex3_3.png)

4. The group mapping is now complete. The conflict has been resolved:
<br>![](/exercises/ex3/images/Ex3_4.png)
The right column now shows Z_FINANCIAL_AGENTS filled in — the local Identity Directory group has been successfully mapped to its corresponding group on the S/4HANA application side. The "Next Step" button is now active (blue), indicating the conflict is resolved and the wizard can proceed.

The user clicks Next Step to move to Step 2 — **Choose Preferred Name**.

5. What is happening: The user must decide which group name should be used as the preferred/canonical name for the provisioned groups going forward. Two options are presented:
<br>![](/exercises/ex3/images/Ex3_5.png)

Local Identity Directory is currently selected (radio button filled). This means the existing local group name in IdDS will be kept as the preferred name for the application-specific group after SAP-Managed Provisioning is enabled.

The "Review" button is active (blue) — hovering over it shows the tooltip "Review" — and the user clicks it to proceed to Step 3 — Summary to review all choices before finalising the switch to SAP-Managed Provisioning.

6. The wizard is now on Step 3 — Summary, the final review step before SAP-Managed Provisioning is activated.

What is shown:
<br>![](/exercises/ex3/images/Ex3_6.png)
The group mapping confirmed in Step 1 is displayed here for final review.

The preference chosen in Step 2 is confirmed — the group name from the Local Identity Directory will be used as the canonical name going forward.

The "Enable" button is now active (blue) at the bottom. Clicking it will finalise the switch to SAP-Managed Provisioning for the SAP S/4HANA Cloud – Sales Demo Customizing Tenant SMJ application, applying the group mapping and preferred name choice in one action.

7. The wizard is now closed and the result is visible on the application's Provisioning tab for SAP S/4HANA Cloud – Sales Demo Customizing Tenant.
<br>![](/exercises/ex3/images/Ex3_7.png)

SAP-Managed Provisioning has been successfully switched on — the toggle is now blue/active. Central Store-Based Provisioning is turned off (the two are mutually exclusive).


## Summary

Now that you learned how to enable SAP-Managed Provisioning — by resolving group conflicts through the mapping wizard, linking local Identity Directory groups to their corresponding S/4HANA application groups, choosing a preferred group name, and activating the provisioning toggle — you understand how group memberships in the Identity Directory are synchronized with application-side authorizations, ensuring that users and their business role assignments stay consistent across the SAP landscape.

Continue to - [Success: The AFC Assistant Is Working](../ex4/README.md)
