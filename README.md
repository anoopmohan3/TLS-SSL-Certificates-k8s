# TLS-SSL-Certificates-k8s


**The basic requirement for ingress TLS is a TLS/SSL certificate. You can obtain these certificates in the following ways.**

Self-Signed Certificates or Use Letsencrpt Certificate

**NOTE**

**SSL is handled by the ingress controller, not the ingress resourc**e. Meaning, when you add TLS certificates to the ingress resource as a kubernetes secret, the ingress controller access it and makes it part of its configuration.
********





**Ingress TLS/SSL Work**
1) Create a Kubernetes secret with server.crt certificate and server.key private key file.
2) Add the TLS block to the ingress resource with the exact hostname used to generate cert that matches the TLS certificate.
3)  point domain with ingress ip


**Steps**

1) kubectl create -n dev
2) create secret
3) kubectl create secret tls hello-app-tls \
    --namespace dev \
    --key server.key \
    --cert server.crt
4) Execute the deployment and ingress file
5) get into pod and execute curl https://domain.com -kv





