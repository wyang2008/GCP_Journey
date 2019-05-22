---


---

<h1 id="google-cloud-shell">Google Cloud Shell</h1>
<h2 id="set-your-google-project">Set your google project</h2>
<p>Once login, the session will be set to one of your project, you can use “<code>gcloud config set project [PROJECT_ID]</code>” to change to a different project.</p>
<h2 id="connect-to-k8s-cluster">Connect to k8s cluster</h2>
<pre><code>gcloud container clusters get-credentials [cluster-name] --zone [zone-name] --project [project-name]
</code></pre>
<h2 id="check-your-account">Check your account</h2>
<pre><code>gcloud auth list
</code></pre>

