# apps-helm

Steps to install:

1. Get a running Kubernetes cluster (e.g. minikube or any cloud provider). Make sure access is correctly setup.

2. Install app with Helm

    ```bash
    helm dependency update
    helm install apps-helm ./
    ```

3. Once installed by Helm, get the IP of the load balancer and add a record in the local hosts file pointing to `apps-example.local`

    `kubectl get ingress apps-helm --output jsonpath='{.status.loadBalancer.ingress[0].ip}'`

4. Browse the [home page](http://apps-example.local/)
