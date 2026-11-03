# Section 4.1 Alert List

{% hint style="info" %}
**Persona for this section:** Sections 4.1-4.2 are written from the perspective of an IT Ops operator, not an administrator. Before starting, impersonate **Amelia Bryant** (the ITOM engineer persona seeded on this lab instance).

1. Select your user icon in the top-right corner, then select **Impersonate user**.
2. Search for and select **Amelia Bryant**, then select **Impersonate user** to confirm.

<img src="../.gitbook/assets/5.0-impersonate-search-amelia.png" alt="" data-size="original">

You'll know it worked when your user icon in the top-right shows "AB" and a banner confirms you're impersonating Amelia Bryant.

Stay impersonated as Amelia Bryant through the end of Section 4.2.
{% endhint %}

{% hint style="info" %}
The alerts in this lab were captured ahead of time and pre-loaded onto your instance, so they are not recent, and some or all of them may already be **Closed** by the time you launch. This section shows you how to widen the list so you can still find them. Use the **List** module (not the Express List icon) for every step in 4.1 and 4.2.
{% endhint %}

The operator reviews alerts to identify issues, assess their impact, and determine how to resolve them. In this section, you will act as an operator.

Typically, an operator would see alerts reported by monitoring tools in the list in near real time. For this lab, alerts have been captured and pre-loaded onto your instance. As a result, the alert times might not be recent enough to appear in the default window, so let's expand the window.&#x20;

1. Close any popups that appear when you first login. The left navigation rail in Service Operations Workspace now shows, top to bottom: Home, AIOps configuration, Inbox, **List**, Insights, Applications, Devices, DEX Administration, Service Dashboard, and an overflow "**...**" menu.

<figure><img src="../.gitbook/assets/5.1-nav-rail.png" alt=""><figcaption></figcaption></figure>

2. Click the **List** icon. In its sidebar, find the **Alerts** category and select **All Alerts** (other entries here include Top Priority, Top Severity, Open Alerts, Acknowledged Alerts, and Assigned to you).
3. Close the pop-up window that appears, if any.
4.  In the top right-hand drop-down, select the **widest date range available** (for example, **Last 90 days**). The default window, and "Last week", will probably show few or no alerts.

    <figure><img src="../.gitbook/assets/2026-08-10 14.04.36.png" alt=""><figcaption></figcaption></figure>
5. Make sure **Closed** alerts are included. If the list is filtered to open alerts only, remove that filter (or add State **is** Closed). Closed alerts are expected here and are fine to analyze.
6. Now you should see the pre-loaded alerts in the list. You may need to scroll or sort by **Created** to find them.

<figure><img src="../.gitbook/assets/5.1-amelia-all-alerts.png" alt=""><figcaption>Confirmed live as Amelia Bryant. Your alert numbers and states may differ.</figcaption></figure>

**But first, a quick sidebar…**

> What are alerts? In ServiceNow, the raw payloads from monitoring tools are called events. Many of these events are just noise, meaning they include information that an operator wouldn't act on. These could be informational events, ones that haven’t met a specific threshold, or haven’t occurred enough times to be concerning. These noisy events can be ignored, and ServiceNow can reduce the noise by never displaying those events to the operator.
>
> \
> Events that are important enough for an operator to investigate and act against are called alerts. The Alerts list shows alerts to the operator.<br>
>
> There are times when alerts are related to each other. For example, if there is a web server that is timing out on connections because the server it is hosted on is out of memory or compute resources, there may be alerts coming in against both the web server for those transaction failures and the host system generating its own alert about running out of memory or compute resources.
>
> \
> In the Alerts list, alert groups are identified by a circled number next to the alert number. To view other alerts within the group, click the arrow on the left side of the primary alert's number.

Let's focus on the Alert Analysis, transforming potentially obscure machine-generated output into clear, natural language. Code to text!<br>

<br>
