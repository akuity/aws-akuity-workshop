---
title: "Create an App of Apps" # MODIFY THIS TITLE
chapter: true
weight: 1 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Create an App of Apps :octopus:
Let's utilize the [app of apps pattern](https://youtu.be/2pvGL0zqf9o)! Argo CD can take plain Kubernetes manifests from a directory and deploy them. <br>
The <code>Application</code> manifests are Kubernetes resources. Thus, an Application pointing to a folder in Git containing such manifests will create an application in our <code>argocd</code> namespace.

<ol>
<li>
On the Applications dashboard in the Argo CD UI, click New App.
</li>

<li>
In the top right, click "Edit as YAML."
</li>


<li>
Navigate to your repository you cloned. In the root, there should be a YAML file called: <code>app-of-apps.yaml</code>. Go ahead and copy the contents:
<pre><code>
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: bootstrap
  namespace: argocd
spec:
  destination:
    name: in-cluster
  project: default
  source:
    path: apps
    repoURL: https://github.com/<username>/intro-argo-cd-tutorial # Update to your repo URL.
    targetRevision: HEAD
</pre></code>
This Application will watch all the YAML files in the <code>apps/</code> directory in the repository. 
</li>

<li>
Click Save.
</li>


<li>
Then, in the top left, click Create.
</li>


<li>
Click on the Application card titled <code>argocd/bootstrap</code>.
At this point, the Application will be out-of-sync. The diff will show the addition of the <code>argocd.argoproj.io/tracking-id</code> label to the existing <code>guestbook-dev</code> Application, which indicates that the "App of Apps now manages it".
<pre><code>
  kind: Application
  metadata:
++  annotations:
++    argocd.argoproj.io/tracking-id: 'bootstrap:argoproj.io/Application:argocd/guestbook-dev'
    generation: 44
    labels:
      ...
      path: guestbook
      repoURL: 'https://github.com/<username>/intro-argo-cd-eks-tutorial'
    syncPolicy:
      automated: {}
</pre></code>
</li>

<li> To apply any changes, click Sync, then Synchronize.
</li>


</ol>