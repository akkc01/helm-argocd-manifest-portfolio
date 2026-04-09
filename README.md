# helm-argocd-manifest-portfolio
I have created this repo foor the testing of deploymnet image tag change by Argocd image updater.

Steps-

Install Argo CD--

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

Install Image Updater--

kubectl apply -n argocd-image-updater \
-f https://raw.githubusercontent.com/argoproj-labs/argocd-image-updater/v0.13.0/manifests/install.yaml

 RBAC (Permissions)---

kubectl create clusterrolebinding argocd-image-updater \
--clusterrole=cluster-admin \
--serviceaccount=argocd-image-updater:argocd-image-updater


