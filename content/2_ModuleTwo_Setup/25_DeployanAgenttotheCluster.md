---
title: "Deploy an Agent to the Cluster" # MODIFY THIS TITLE
chapter: true
weight: 5 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

<!-- MORE SUBMODULES CAN BE ADDED TO DIVIDE UP THE SETUP INTO SMALLER SECTIONS -->
<!-- COPY AND PASTE THIS SUBMODULE FILE, RENAME, AND CHANGE THE CONTENTS AS NECESSARY -->

# Deploy an Agent to the Cluster :octopus:

<ol>
<li>
Back on the Akuity Platform, in the top left of the dashboard for the Argo CD instance, click Clusters.
</li>

<li>
Click <code>+ Connect a Cluster </code> to add a Kubernetes cluster.
</li>

<li>
Enter the eks name as the <code>Cluster Name</code>.

![Connect Cluster](/aws-modernization-workshop-base-main/static/images/connect.png)</li>

<li>
In the bottom right, click Connect Cluster.
</li>

<li>
To get the agent install command, click Copy to Clipboard. Then, in the bottom right, Done.
</li>

<li>
Open your terminal and check that your target is the correct cluster by running <code>kubectl config current-context.</code>
The output should look similar to the following:<br>
<pre><code>
arn:aws:eks:us-east-1:338615488317:cluster/cluster-name
</code></pre>
</li>

<li>
Paste and run the command against the cluster. The command will create the <code>akuity</code> namespace and deploy the resources for the Akuity Agent.
</li>

<li>
Check the pods in the <code>akuity</code> namespace. Wait for the Running status on all pods. <br>
<pre><code>
% kubectl get pods -n akuity
NAME                                                        READY   STATUS    RESTARTS   AGE
akuity-agent-<replicaset-id>-<pod-id>                       1/1     Running   0          65s
akuity-agent-<replicaset-id>-<pod-id>                       1/1     Running   0          65s
argocd-application-controller-<replicaset-id>-<pod-id>      2/2     Running   0          65s
argocd-notifications-controller-<replicaset-id>-<pod-id>    1/1     Running   0          65s
argocd-redis-<replicaset-id>-<pod-id>                       1/1     Running   0          65s
argocd-repo-server-<replicaset-id>-<pod-id>                 1/1     Running   0          64s
argocd-repo-server-<replicaset-id>-<pod-id>                 1/1     Running   0          64s
</pre></code>
</li>
</ol>


# Using the Akuity Agent Add-On :hammer:
You can install the Akuity Agent on an Amazon EKS cluster by installing the Agent as an Amazon EKS add-on. <br>
Unlike regular Agent installation, there is a big difference when installing as an add-on. During EKS add-on installation, images must be pulled *only* from the EKS repository, which cannot be changed by the user.

## Prerequisites
- An Akuity Platform account with an Argo CD instance
- An AWS EKS cluster
- Subscription to the Akuity Agent EKS add-on
- kubectl installed
- (Optional) AWS CLI

1. Navigate to your Clusters tab on your Argo CD instance.
   ![Clusters Tab](/aws-modernization-workshop-base-main/static/images/Clustab.png)
2. Click <code>+ Connect a Cluster </code> to add a Kubernetes cluster.
3. Enter the eks cluster name as the <code>Cluster Name</code>
4. Expand the <code>Advanced Settings </code> section
5. Click on <code>Add Ons</code> tab.
6. Click on the <code>+ Add</code> button under AWS EKS.
![Connect Cluster](/aws-modernization-workshop-base-main/static/images/connect.png)
7. Click <code>Connect Cluster</code>
Once you click connect, an Akuity Agent pop-up screen should appear. It looks something like this:
![Akuity Agent installer](/aws-modernization-workshop-base-main/static/images/EKS1.png)
8. You can install the agent via the **AWS Console** or the **CLI**.
