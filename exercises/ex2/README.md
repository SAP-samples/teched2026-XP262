# User Authorization Assignment: Business Roles in the back end

## Exercise: Reaching out to the **Financial Closing Assistant**
Let's check if now with the correct policy assignments it will work: 

1. Return to your Joule Work UI  https://747238487.eu10.sapdas.cloud.sap/new/ 

2. Try the same prompt again: *Create journal entry proposals for company code 1010*

<br>![](/exercises/ex1/images/Ex1_2.png)

4. Notice that the answer is still not quite useful ..
<br>![](/exercises/ex1/images/Ex1_3.png)

What could be the reason ? 

## Demo: Checking back-end authorizations 


Coming back to the three layers if access assessment, what we will assess next will be the application authorization assignments. 
<br>![](/exercises/ex2/images/Ex2_1.png)

For the scope of this session, we will assume that the second check (scoped-access risk) has been performed at agent deployment. 


Let's check our user in the back-end system: 
<br>![](/exercises/ex1/images/Ex1_5.png)

We notice that the user does not have authorizations. 
<br>![](/exercises/ex1/images/Ex1_6.png)

So we will proceed with the assignment in the back end: 
<br>![](/exercises/ex1/images/Ex1_7.png)


## Summary

Now that you learned how to verify and assign back-end application authorizations — by checking your user's business roles in the back-end system and assigning the missing permissions — you understand that having agent access alone is not sufficient, and that the application-level authorization layer must also be fulfilled before the Financial Closing Assistant can successfully process your requests.

Continue to - [Third Roadblock: Authorization Exists but Joule Still Fails](../ex3/README.md)
