# Section 2.3 Wrap your Agent in an agentic workflow

1. Click the **Create and Manage** tab
2. Under the **Agentic workflows** tab, click **New**
3. Click on the “**Generate details**” in the **Define key requirements** page, copy and paste this into the dialog

{% code overflow="wrap" expandable="true" %}
```
This workflow will be the “Incident Solution Agent workflow” . This use case provides recommendations to resolve incidents”. Provide a recommendation on how to resolve a given incident using an easy-to-follow numbered step-by-step list format
```
{% endcode %}

4. Click on “**Generate**.” Scroll down and see how it's filled in the fields for you!
5. Click **Recommend AI Agernts** button, then find the AI Agent you created previously

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

6. Click “**+**” button under **Add AI agent** then click **Save and Continue**
7. You will get prompted for possible duplicates. Click “**Ignore and continue**. “In Define user access, click “Save and continue” on the following two steps
   1. Select “**Any Authenticated user**’ from the User access drop-down
   2. Select the **Dynamic user**, search and select ‘**itil**’ and “**admin**” from the approved roles
8. In the **Add Trigger** page, click **Add Trigger**, and fill in the following fields:
   1. **Select Trigger**: Created
   2. **Trigger name:** “\[Your initials] Incident Created and Objective: “Help me resolve $(number)”
   3. Trigger is toggled ‘**on**’
   4. **Table**: “Incident”
   5. **Conditions**: Active is True AND Assigned to is not empty
   6. **Sys\_user**: “Assigned to \[task]”
   7. **Channel**: “Now Assist panel”
   8. **Show alert to users**: “no”
9. Click “Save and continue”
10. On the **Select channel and status page**, make sure the Now Assist Panel Display toggle is set to **On**
11. Click **Save and Test**

Now let’s test your new workflow!

Let’s continue to use the same incident record as we’ve used previously – INC0010248. In the Task box enter

{% code overflow="wrap" expandable="true" %}
```
Help me resolve INC0010248
```
{% endcode %}

You may be prompted by the AI Agent for more informatio&#x6E;**.** Enter **'Load Balancer'** if that happens

**Click Continue to Test Chat response**

<figure><img src="../.gitbook/assets/2026-08-10 10.05.16.png" alt=""><figcaption></figcaption></figure>
