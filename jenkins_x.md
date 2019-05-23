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

                                                                                                                                                                   


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcxNjYwOTM1MiwtMTAwNDg4NTA1MSwtMT
g0NTExOTAwN119
-->