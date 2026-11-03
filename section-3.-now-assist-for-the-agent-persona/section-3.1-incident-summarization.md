# Section 3.1 Incident Summarization

{% hint style="info" %}
**Persona for this section:** Sections 3.1-3.5 are written from the perspective of an IT agent, not an administrator. Before starting, impersonate **Ravi Kapoor** (one of the IT agent personas seeded on this lab instance) so that what you see matches an agent's real day-to-day access — not the unrestricted admin view.

1. Select your user icon in the top-right corner, then select **Impersonate user**.

<img src="../.gitbook/assets/3.0-impersonate-menu.png" alt="" data-size="original">

2. Search for and select **Ravi Kapoor**, then select **Impersonate user** to confirm.

<img src="../.gitbook/assets/3.0-impersonate-search-ravi.png" alt="" data-size="original">

You'll know it worked when your user icon in the top-right shows "RK" and a banner confirms you're impersonating Ravi Kapoor.

<img src="../.gitbook/assets/3.0-impersonating-ravi.png" alt="" data-size="original">

Stay impersonated as Ravi Kapoor through the end of Section 3 (Section 3.5) — you'll switch personas again for Section 5.\
\
**NOTE THAT THE NOW ASSIST EXPLORER MAY NOT WORK ON ALL LAB INSTANCES. IF YOU DO NOT SEE THE SPARKLE AS SHOWN IN THE SCREENSHOT BELOW, PLEASE SKIP. WE APOLOGIZE**
{% endhint %}

1. Once you impersonate **Ravi Kapoor** Service Operations Workspace is the homepage. Refresh the page once you land there after Impersonating, otherwise you probably won't see any data the page.&#x20;

<figure><img src="../.gitbook/assets/2026-08-10 10.14.50.png" alt=""><figcaption></figcaption></figure>

2. Make sure to click on the **In Progress** donut on the left side
3. Let’s get to know **Service Operations Workspace** a little. We are going to search for a specific incident to work with. First, select the list view, then under incidents, select All to see a list of incidents.
4. In that list view, select the **“+ Explore”** button (tooltip “Explore with AI”) near the top-right of the list toolbar — this is the Gen-AI feature; the plain “Filter” button next to it is just the traditional filter-condition builder and has no AI input.

<figure><img src="../.gitbook/assets/2026-08-10 10.17.04.png" alt=""><figcaption><p>Confirmed live as Ravi Kapoor — the "Explore with AI" button.</p></figcaption></figure>

5. This opens a small floating panel with an **“Ask Now Assist a question about data…”** input. **Select and copy the following** into that input and submit it:

{% code overflow="wrap" expandable="true" %}
```
Any incident that has a description that contains Versioning errors
```
{% endcode %}

<figure><img src="../.gitbook/assets/2026-08-10 10.18.14.png" alt=""><figcaption></figcaption></figure>

6. Close that window and then Click on **Show different distribution**

<figure><img src="../.gitbook/assets/2026-08-10 10.19.42.png" alt=""><figcaption></figcaption></figure>

6. Now you can scroll through even more detailed analysis of the unassigned incidents and breakdown, which may further help Ravi prioritize his work&#x20;

<figure><img src="../.gitbook/assets/2026-08-10 10.20.59.png" alt=""><figcaption></figcaption></figure>

7. Let's go BACK to the In progress donut, and select and open **INC0010005 "Blocked: Password reset portal....** (if your instance shows two incidents numbered INC0010005, open the one titled "Blocked: Password reset portal…")

<figure><img src="../.gitbook/assets/2026-08-10 10.24.34.png" alt=""><figcaption></figcaption></figure>

Once that is open, click the Generate button in the AI Summary area

<figure><img src="../.gitbook/assets/2026-08-10 10.25.33.png" alt=""><figcaption></figcaption></figure>

The summarization skill analyzes the short description, description, work notes, and related records before generating the issue, SLAs, impacted services, and actions taken up to that point.

<figure><img src="../.gitbook/assets/2026-08-10 10.26.23.png" alt=""><figcaption></figcaption></figure>

As an agent, this is extremely helpful if there are multiple updates to the work notes and the text is dense; when a ticket is assigned to the agent, the Agent must spend 15 minutes reading all the work notes. Instead, they can quickly read the Now Assist summarization.

{% hint style="info" %}
Your incident summarization may look slightly different from the screenshot shown above
{% endhint %}

8. Notice the icons at the bottom. As well ask '**Ask Now Assist to...** that will open the Now Assist Panel and kick on the ability to call any Now Assist Agentic workflows. You can also copy the text to the clipboard and regenerate the summary.
9. **Edit the summary by adding a bulleted item** like the one below and then select **Save to work notes**.
10. Expand the work note activity stream to see that your edits were copied

{% hint style="info" %}
Bonus: Return to the Incident list and try the summarization skill with ANY in-progress incident. Try it a few times!
{% endhint %}

**Congratulations**, you have created an incident summary! Please don't close the Service Operations workspace or the incident tab; we will use it in the next section
