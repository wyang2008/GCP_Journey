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
