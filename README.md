# apps-helm

Steps to install:

1. Get a running Kubernetes cluster (e.g. minikube or any cloud provider). Make sure access is correctly setup.

2. Install app with Helm

    ```bash
    helm dependency update
    helm install apps-helm ./
    ```

3. Once installed by Helm, get the IP of the load balancer with

    `kubectl get ingress apps-helm --output jsonpath='{.status.loadBalancer.ingress[0].ip}'`

4. Add a record in the local hosts file pointing the obtained IP to `apps-example.local`

5. Browse to the [home page](http://apps-example.local/)
