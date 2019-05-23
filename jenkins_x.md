# Jenkins x

## Install jx command line tool in Linux

Refer to the guide on [https://jenkins-x.io/getting-started/install/](https://jenkins-x.io/getting-started/install/) 

    mkdir -p ~/.jx/bin 
    curl -L https://github.com/jenkins-x/jx/releases/download/v2.0.157/jx-linux-amd64.tar.gz | tar xzv -C ~/.jx/bin 
    export  PATH=$PATH:~/.jx/bin 
    echo  'export PATH=$PATH:~/.jx/bin' >> ~/.bashrc
After the installation, use `jx version` to check if the installation is completed successfully and it will notify you to upgrade to the newest version(if there is any).

## Install Jenkins on Kubernetes Cluster
Before installing jenkins x on your cluster, you can validate your cluster performance.

    jx compliance run
This will take up to 60 minutes for the checking. 
![jx compliance run & status](https://github.com/wyang2008/GCP_Journey/blob/master/jx_compliance.jpg) 

When the checking is completed, use below command to check the result

    jx compliance results
Here is the sample results

    STATUS TEST       TEST-CLASS
    FAILED [k8s.io] Kubelet when scheduling a busybox Pod with hostAliases should write entries to /etc/hosts [LinuxOnly] [NodeConformance] [Conformance]                                        Kubernetes e2e suite
    PASSED [k8s.io] Container Lifecycle Hook when create a pod with lifecycle hook should execute poststart exec hook properly [NodeConformance] [Conformance]                                   Kubernetes e2e suite
    PASSED [k8s.io] Container Lifecycle Hook when create a pod with lifecycle hook should execute prestop exec hook properly [NodeConformance] [Conformance]                                     Kubernetes e2e suite
    PASSED [k8s.io] Container Lifecycle Hook when create a pod with lifecycle hook should execute prestop http hook properly [NodeConformance] [Conformance]                                     Kubernetes e2e suite        
    ...

Specify the provider for the installation.                                                                                                                                                                

    jx install --provider=gke
jenkins x will asks for your input during the installation:

    ? Select Jenkins installation type: Serverless Jenkins X Pipelines with Tekton
    Please enter the name you wish to use with git:  *******
? Please enter the email address you wish to use with git:  ********
? No existing ingress controller found in the kube-system namespace, shall we install one? Yes
? Domain ***.***.***.***.nip.io
nginx ingress controller installed and configured
? Would you like to enable Long Term Storage? A bucket for provider gke will be created Yes
? Google Cloud Zone: ****-****-*
? GitHub user name: ********
? API Token: ****************************************
Select the CI/CD pipelines Git server and user
? Do you wish to use GitHub as the pipelines Git server: Yes
Creating a pipelines Git user for GitHub server
To be able to create a repository on GitHub we need an API Token
Please click this URL https://github.com/settings/tokens/new?scopes=repo,read:user,read:org,user:email,write:repo_hook,delete_repo

Then COPY the token and enter in into the form below:

? API Token: ****************************************
Setting the pipelines Git server https://github.com and user name ********.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI2NTA5MzYxNCwtMTAwNDg4NTA1MSwtMT
g0NTExOTAwN119
-->