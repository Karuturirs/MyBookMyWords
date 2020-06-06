# Kubernetes cluster local setup

### * [Installation steps](https://medium.com/faun/install-minikube-with-kubernetes-in-windows-and-deploy-a-sample-application-64de17083fa9)



### Day to Day commands

- Use command ***minikube start\***. Typically, it takes 3–5 mins.
- Then to set vm-driver as virtual box ***minikube config set vm-driver virtualbox\***. This step is optional.
- Use the context of minikube
  ***kubectl config use-context minikube\***
- See cluster-info of minikube in your local machine.
  **kubectl cluster-info**
- Next, open the dashboard of minikube which navigates to the Kubernetes dashboard.
  ***minikube dashboard\***

>Note: any errors in minikube, just delete the minikube vm in local and start again.
>
>```minikube delete```

