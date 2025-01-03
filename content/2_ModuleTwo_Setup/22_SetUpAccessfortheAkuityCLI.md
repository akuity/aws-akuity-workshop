---
title: "Deploying Resources into the Cluster with Akuity Platform" # MODIFY THIS TITLE
chapter: true
weight: 2 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

<!-- MORE SUBMODULES CAN BE ADDED TO DIVIDE UP THE SETUP INTO SMALLER SECTIONS -->
<!-- COPY AND PASTE THIS SUBMODULE FILE, RENAME, AND CHANGE THE CONTENTS AS NECESSARY -->


# Deploying Resources into the Cluster with Akuity Platform :high_brightness: <!-- MODIFY THIS SUBHEADING -->
<ol>
<li> Create an account on the <a href="https://training.akuity.cloud/">Akuity Platform</a>.

![Akuity Login Page](/aws-modernization-workshop-base-main/static/images/akuitylogin.png)
</li>
<li>  You have the option to use either GitHub SSO or Google SSO to sign up.
</li>

<li> Create an organization on the Akuity Platform by clicking "Organization", then create.

![Akuity Login Page](/aws-modernization-workshop-base-main/static/images/akuitylogin.png)
</li>
<li> Name your organization following the rules listed below the Organization Name field.
</li>

</ol>

# Set Up Access for the Akuity CLI :computer:
<ol>
<li> Select the Organization you want to create an API key for, from the pull down menu on your Organization.

</li>

<li> Select the API Keys tab.

</li>

<li> Click the + New Key Button on the lower right side of the page.

![Akuity APIKey Page](/aws-modernization-workshop-base-main/static/images/APIkeycreation.png)
</li>

<li> Set the description for the key as <code>Akuity EKS Workshop</code>.
</li>

<li> Assign the <code>Owner</code> Role to the key.
</li>

<li> Click the create button once you're done.
</li>

<li> An API Key prompt will pop up once you hit create, so go ahead and click the Copy to Clipboard button. Then go ahead and paste and run the command in the terminal.

![Akuity APIKey Page](/aws-modernization-workshop-base-main/static/images/Keycreated1.png)
</li>

</ol>