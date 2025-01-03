---
title: "Configure Your Instance" # MODIFY THIS TITLE
chapter: true
weight: 4 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

<!-- MORE SUBMODULES CAN BE ADDED TO DIVIDE UP THE SETUP INTO SMALLER SECTIONS -->
<!-- COPY AND PASTE THIS SUBMODULE FILE, RENAME, AND CHANGE THE CONTENTS AS NECESSARY -->

# Configure Your Instance :hammer:
<ol>
<li>
On the dashboard for the Argo CD Instance, click Settings.
</li>

<li>
On the left side, under "Security & Access" select System Accounts.
</li>


<li>
Enable the "Admin Account" by clicking the toggle and clicking Confirm when prompted.
</li>


<li>
For the <code>admin</code> user, set a password.

![Set Admin PW](/aws-modernization-workshop-base-main/static/images/adminpw.png)
</li>

{{% notice warning %}}
Put a pin:pushpin:on this...you'll need your password to access your applications later.
{{% /notice %}}

<li>
Your instance URL is listed in the URL field on your Argo CD instance page. It will look something like this: <code>instance-id.cd.akuity.cloud</code>
</li>

<li>
For username, enter <code>admin</code>, and the password you set previously. Wait for the blue cogwheel next to your instance's name to stop, and you should be able to access your instance.
</li>

</ol>

Congratulations, you now have a fully-managed Argo CD instance! :tada: