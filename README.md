# 3-Tier DevSecOps Project

This repository contains a simple Node.js API and a React client used for a user management demo. Follow the steps below to get the project running locally.

## Setup


1. Install Node.js (version 18 or later is recommended).
2. Install dependencies for both the API and client:

   ```bash
   cd api && npm install
   cd ../client && npm install
   ```

3. Start the API server:

   ```bash
   cd api
   npm start
   ```

4. In a separate terminal, start the React client:

   ```bash
   cd client
   npm start
   ```

5. Open `http://localhost:3000` in your browser to use the application.

6. For ingress controler folow below processs require MetelLB deployed on on prime setup

```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update

helm install nginx-ingress ingress-nginx/ingress-nginx \
  --namespace prod \
  --set controller.ingressClassResource.name=nginx \
  --set controller.ingressClassResource.controllerValue="k8s.io/ingress-nginx" \
  --set controller.service.type=LoadBalancer \
  --set controller.service.externalTrafficPolicy=Local
 ```

The client now displays an animated banner welcoming you to **DevOps Shack**.
