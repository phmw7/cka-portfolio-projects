# Project 1: Service Account with Cluster-Wide Pod Listing Permissions

## Goal
Create a ServiceAccount with cluster-wide permissions to list pods across all namespaces.

## What You Did
- Created a Namespace: `cka-namespace`
- Created a ServiceAccount: `pod-reader`
- Created a ClusterRole with list, get, watch permissions on pods
- Created a ClusterRoleBinding to bind the ServiceAccount to the ClusterRole
- Validated access by impersonating the ServiceAccount and running:
  ```
  kubectl auth can-i list pods --as=system:serviceaccount:cka-namespace:pod-reader --all-namespaces
  ```

## Files
- `serviceaccount.yaml`: Contains Namespace, ServiceAccount, ClusterRole, ClusterRoleBinding manifests

## Apply with:
```
kubectl apply -f serviceaccount.yaml
```
