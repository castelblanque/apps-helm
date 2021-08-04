# apps-helm

## Goal

This Helm chart deploys the "apps" application into your Kubernetes cluster.

Projects deployed:

- **apps-manager** (Backend)
  - [GitHub](https://github.com/castelblanque/apps-manager)
  - [Docker hub](https://hub.docker.com/r/castelblanque/apps-manager)
- **apps-frontend** (Backend)
  - [GitHub](https://github.com/castelblanque/apps-frontend)
  - [Docker hub](https://hub.docker.com/r/castelblanque/apps-frontend)
- Nginx ingress to access both services with the domain `apps-example.local`

## Installation

1. Get a running Kubernetes cluster (e.g. minikube or any cloud provider). Make sure access is correctly setup.

2. Checkout this project

    ``

3. Install app with Helm

    ```bash
    helm dependency update
    helm install apps-helm ./
    ```

4. Once installed by Helm, get the IP of the load balancer with

    `kubectl get ingress apps-helm --output jsonpath='{.status.loadBalancer.ingress[0].ip}'`

5. Add a record in the local hosts file pointing the obtained IP to `apps-example.local`

6. Browse to the [home page](http://apps-example.local/)
