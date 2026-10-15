# Exercise 1: L1 Service Desk AI Specialist Setup & Configurationf

> **Objective:** Configure and activate the L1 Service Desk AI Specialist so it can autonomously classify, triage, investigate, and resolve incidents on behalf of your IT Support team.
>
> ⏱️ **Total time:** \~15 minutes

***

### Navigate to AI Agent Studio

1.  In the filter navigator, type **AI Agent Studio** and select **AI Agent Studio > Overview**.

    > You'll land on the AI Agent Studio Overview page, where you can see ready-made AI automations and any AI Specialists already active in your organization.

***

### Open the L1 Service Desk AI Specialist for editing

1. On the AI Agent Studio Overview page, locate the **L1 Service Desk AI Specialist** card under _Ready-made AI automations > AI specialists_.
2. Select **View Details** on the card — this opens the full configuration experience directly. (

***

### Personalize the AI Specialist Profile

You are now on the **Profile** page for the L1 Service Desk AI Specialist. This is where you configure the AI Specialist's identity, capabilities, group membership, and roles.

1.  Change the **First name** to a name of your choice — make it your own! **Note:** Last name is a fixed, non-editable field on this page.

    > For example: First name: `Athena`
2. Scroll down to review the **Capabilities** section — this shows the types of work the AI Specialist can handle: `General inquiries`, `Laptop issues`.
3. Scroll down to the **Assignment groups** section.
4.  Confirm **IT Support** is listed. On a lab instance provisioned from the current ICE package, it's usually already there by default — a role-fix step run during provisioning adds it for you. If it's missing, type `IT S` and select **IT Support** from the dropdown to add it yourself.

    > Assignment groups determine which team's tickets the AI Specialist will pick up. Adding IT Support means the AI Specialist will begin handling incidents assigned to that group.
5.  Review the **Roles** section. The AI Specialist should already have the following roles assigned:

    <figure><img src="../../.gitbook/assets/2026-09-01 08.51.51.png" alt=""><figcaption></figcaption></figure>
6. Select **Save** in the top-right corner.

***

### Configure Tasks — Classify and assign (for this lab we will leave them as-is)

The **Tasks** section is where you configure how the AI Specialist makes decisions, takes action, and interacts within workflows. Select **Tasks** in the left-hand navigation.

1. Select **Classify and assign** from the task list.
2. In the Settings panel on the right, review the configuration:
   * **Table:** Incident
   * **Fields to classify on the record:** Category, Subcategory, Service, Service offering, Configuration item
3.  You can add or remove fields depending on what you'd like the AI Specialist to predict when triaging new incidents.

    > These are the fields the AI Specialist will automatically populate when it picks up a new incident. Tailor this list to match your organization's classification requirements.

***

### &#x20;Configure Tasks — Triage and diagnose

1. Select **Triage and diagnose** from the task list.
2. In the Settings panel, review the following:
   * **Fields to use (Task Fields):** Short description, Description
   * **Use attachment content:** Toggled **ON** — this allows the AI Specialist to review attached files as part of its triage process.
3.  Scroll down to **Map AI Specialist states to record states**. Confirm the following mappings:

    | AI Specialist State | → | Incident State |
    | ------------------- | - | -------------- |
    | New                 | → | New            |
    | Work in progress    | → | In Progress    |
    | Awaiting info       | → | On Hold        |
    | Solution proposed   | → | Resolved       |

    > **Note:** These state mappings may differ in your production instances if you've modified the out-of-the-box incident state model. Adjust the mappings to match your organization's workflow.

***

### Configure Tasks — Investigate and resolve

1. Select **Investigate and resolve** from the task list.
2. In the Settings panel, review and configure:
   * **Knowledge sources:** Confirm the following AI Search Profile is listed:
     * `ZTSD Search Profile`
   * Select **+ Add** to attach additional search profiles if needed. Do not add `Known Error Matcher` — it has no search sources configured on these lab instances and stalls the research step.
3.  Set the **Research depth** based on your preference:

    * **Low** – faster results, less detail
    * **Medium** – balanced results, moderate depth
    * **High** – slower results, more detail

    > Knowledge sources define where the AI Specialist looks for resolution information. Search profiles can include knowledge bases, known error databases, and other indexed content. The research depth controls how extensively the AI Specialist investigates before proposing a solution.

    > **Note:** Product Management has indicated the Research Depth setting is currently not applied by the AI Specialist and is expected to be removed in a future release. You can leave it at the default for now.
4. Leave **the pre-resolution condition** blank for this lab — this optional encoded query lets you validate the record against the table before the AI Specialist acts on it.
5. Set the **Execution mode**:
   * **Supervised** – The AI Specialist presents resolution notes as a draft for a human agent to review before posting to the caller.
   * **Autonomous** – The AI Specialist posts resolution notes directly to the caller without human review.
6.  For this lab, select **Autonomous**.

    > In a production rollout, many organizations start with **Supervised** mode to build confidence in the AI Specialist's responses, then graduate to **Autonomous** as accuracy improves. For today's lab, we'll go straight to Autonomous so you can see the full end-to-end flow.

***

### Configure Tasks — Response formatting

> **Note:** on current platform versions this task is labeled **Response formatting** — it's the same configuration area older guide versions called "Communicate updates," just renamed.

1. Select **Response formatting** from the task list.
2. In the Settings panel, review:
   * **Inbound channels:** Comments — how the AI Specialist receives messages from requesters.
   * **Outbound channels:** Comments — how the AI Specialist sends responses or notifications.
   * **Internal communication when confidence is low:** toggle — when on, the AI Specialist logs its proposed solution as a work note instead of responding directly to the requester when it isn't confident enough.
   * **Response templates:** Follow up, Propose a solution, and Reassign to human — these define how the AI Specialist phrases each type of update.

***

### Configure Tasks — Reassign

> **Note:** on current platform versions this task is labeled **Reassign** — it's the same configuration area older guide versions called "Escalate and reroute," just renamed.

1. Select **Reassign** from the task list.
2. In the Settings panel, review:
   * **Maximum number of interactions before reassignment:** `2` (default) — how many times the AI Specialist will contact the requester before sending the ticket to a human agent.
   * **Reassign on follow-up question:** Off by default — when on, any follow-up question from the requester sends the ticket straight to an agent instead of letting the AI Specialist handle it.
   * **Choose where to reassign records:** Reassign to **An assignment group** or **A specific person**, then pick the group/person.

***

### est the AI Specialist

Now let's see the AI Specialist in action on a real incident record.

1. Select **Test** in the left-hand navigation.
2. In the **Choose a record** field, search for an open incident by its short description — for example, one of the Zscaler-themed incidents seeded on this lab instance (e.g. **"Zscaler ZPA tunnel disconnected — Finance team unable to reach internal apps"**). Match on the description text, not the `INC00XXXXX` number — your instance's numbering may differ.
3. Select **Run**.
4.  Watch the AI Specialist process the incident in real time — it will classify, triage, investigate, and propose a resolution.

    > **Important:** This is not a simulation — the AI Specialist will take action on the selected record. Choose an appropriate test incident.
5.  Select **View Details** to see the result. **Do not** click into **My Solutions** — that's a different view and won't show you the run you just kicked off.

    > **Be patient:** the test takes about 5-7 minutes to complete. While it's running, **All Steps** keeps updating live, showing the AI Specialist's thought process — this is your window into how it's actually reasoning through the incident.

    <figure><img src="../../.gitbook/assets/2026-08-26 11.04.48.png" alt=""><figcaption></figcaption></figure>

***

### Review the Performance Dashboard

1. Select **Performance** in the left-hand navigation.
2. Explore the three dashboard tabs:
   * **Effectiveness** — Measure how well the AI Specialist resolves tickets, including incident outcomes by category and average exchanges for resolved tickets.
   * **Efficiency** — Track speed and throughput metrics.
   * **Value & Feedback** — Review the business impact and feedback from agents and callers.
3.  Use the **Assignment group** and **Date** filters to narrow the data.

    > The Performance dashboard is your command center for monitoring the AI Specialist over time. In a fresh lab instance, data will populate as the AI Specialist processes more incidents.

***

### Review the Activity Log

1. Select **Activity** in the left-hand navigation.
2. Review the **AI Specialist activity** list showing:
   * **Associated record** — The incident the AI Specialist worked (match by short description, not just number — your instance may have a different `INC00XXXXX` value)
   * **State** — Current state of the AI Specialist's task (e.g., Completed)
   * **State Reason** — Why the task is in that state
   * **Assigned to** — The AI Specialist who handled it
   * **Created** — Timestamp of when the activity was created
   * **Feedback** — Thumbs up/down icons for providing feedback on the AI Specialist's performance
3. Toggle **Turn on live updates** to watch new activity appear in real time as the AI Specialist processes incidents.

***

### Configure management of the L1 Service Desk AI Specialist

Select **Management** in the left-hand navigation. This is where you set access permissions, add copies of this AI Specialist, and activate it.

1. Under **Manage locations and approved users**, review **Where it's managed** (Service Operations Workspace) and set **User access role(s)** — this is where you grant the roles (default is `sn_sow_itsm_common.sn_service_desk_manager`) that determine who can see this AI Specialist's actions in Core UI.
2. The **Copies** section lets you clone this AI Specialist for other teams — not needed for this lab.
3. Under **Activate**, confirm **Activate this AI specialist** is toggled **Yes**, then set the **AI specialist manager** field to **Ravi Kapoor**.
4. Under **Publish**, confirm **Publish this AI specialist in a workspace** is toggled **Yes** — this makes the specialist available to the assigned managers/roles. It's usually already on for this lab. Without this step we will not be able to continue the next section.
5. Select **Save** in the top-right corner.

>

You've configured the profile, tasks, and settings. This specialist is now LIVE!

***

#### Checkpoint

You have successfully:

* Personalized the AI Specialist's profile and name
* Reviewed the Capabilities section
* Added the AI Specialist to the IT Support assignment group
* Configured classification fields for incident triage
* Mapped AI Specialist states to incident states
* Set up knowledge sources for investigation and resolution
* Enabled Autonomous execution mode
* Configured communication channels and response templates
* Set escalation and fallback assignment rules
* Tested the AI Specialist against a real incident
* Reviewed the Performance dashboard and Activity log
* Activated the AI Specialist

🎉 **Congratulations!** Your L1 Service Desk AI Specialist is now live and ready to autonomously resolve incidents. Next up — let's put it to work on a real incident queue.
