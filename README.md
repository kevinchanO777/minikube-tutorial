# Using Minikube to depoly a Kubernetes cluster locally running MacOS silicon

## Referencing:

- https://minikube.sigs.k8s.io/docs/start/
- https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/
- https://kubernetes.io/docs/tutorials/kubernetes-basics/deploy-app/deploy-intro/


## Install the following to begin:

- Minikube
    - `brew install minikube`

- kubectl (using brew)
    - `brew install kubectl`
###### Enable shell autocompletion by adding `source <(kubectl completion zsh)` to `~./zshrc`

- kubectl (Manually)
    ```
     curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/arm64/kubectl"
     chmod +x ./kubectl
     sudo mv ./kubectl /usr/local/bin/kubectl
     sudo chown root: /usr/local/bin/kubectl
     kubectl version --client --output=yaml
     rm kubectl kubectl.sha256
    ```


## The only Minikube commands we need:

#### Start a cluster
- `minikube start`

#### Status of cluster
- `minikube status`

#### Delete the cluster
- `minikube delete --all`



## Useful kubectl commands:

#### 

