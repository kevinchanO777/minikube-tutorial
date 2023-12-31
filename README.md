# Using Minikube to depoly a Kubernetes cluster locally running MacOS silicon


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

## To start the cluster and the app
```
minikube start
minikube service webapp-service
```
###### ⚠ Known issue - Minikube IP not accessible using ```minikube ip```
###### If you can't access the NodePort service webapp with MinikubeIP:NodePort, execute the following command:
``` minikube service webapp-service ```

The application is supposed to be listened at minikubeip:nodePort


## The only Minikube commands we need:

#### Start a cluster
- ```minikube start```

#### Status of cluster
- ```minikube status```

#### Dashboard
- ```minikube dashboard```

#### Delete the cluster
- ```minikube delete --all```


## Useful kubectl commands:

#### Retrieve all the resources (pods, services, deployments ...) in K8s cluster
- ```kubectl get all```
- ```kubectl get configmap```
- ```kubectl get secret```

#### Applying a config/depolyment/service file 
- ```kubectl apply -f <file.yaml>```

#### Instpecting individual resouces or errors:
- ```kubectl describe pod podname```


## Referencing:

- https://gitlab.com/nanuchi/k8s-in-1-hour/-/blob/master/README.md?ref_type=heads
- https://www.youtube.com/watch?v=s_o8dwzRlu4&t=151s&ab_channel=TechWorldwithNana
- https://minikube.sigs.k8s.io/docs/start/
- https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/
- https://kubernetes.io/docs/tutorials/kubernetes-basics/deploy-app/deploy-intro/

