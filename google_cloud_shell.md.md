---


---

<h1 id="jenkins-x">Jenkins x</h1>
<h2 id="install-jx-command-line-tool-in-linux">Install jx command line tool in Linux</h2>
<p>Refer to the guide on <a href="https://jenkins-x.io/getting-started/install/">https://jenkins-x.io/getting-started/install/</a></p>
<pre><code>mkdir -p ~/.jx/bin 
curl -L https://github.com/jenkins-x/jx/releases/download/v2.0.157/jx-linux-amd64.tar.gz | tar xzv -C ~/.jx/bin 
export  PATH=$PATH:~/.jx/bin 
echo  'export PATH=$PATH:~/.jx/bin' &gt;&gt; ~/.bashrc
</code></pre>
<p>After the installation, use <code>jx version</code> to check if the installation is completed successfully and it will notify you to upgrade to the newest version(if there is any).</p>
<h2 id="install-jenkins-on-kubernetes-cluster">Install Jenkins on Kubernetes Cluster</h2>
<p>Before installing jenkins x on your cluster, you can validate your cluster performance.</p>
<pre><code>jx compliance run
</code></pre>
<p>This will take up to 60 minutes for the checking.<br>
<img src="https://github.com/wyang2008/GCP_Journey/blob/master/jx_compliance.jpg" alt="jx compliance run &amp; status"></p>

