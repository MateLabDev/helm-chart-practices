# helm-chart-practices
Practices how to use helm charts

## Practice Steps

1. Create a new namespace called 'challenge'
   - "kubectl create ns challenge"
  
2. Install the Bitnami-hosted Metrics Server Helm chart
   - "helm install challenge-metrics-server bitnami/metrics-server --set apiService.create=true -n challenge" 
  
3. Ensure the release name is challenge-metrics-server
   - "kubectl get all -n challenge"
  
4. Cleanup
   - "helm delete challenge-metrics-server -n challenge"
   - "kubectl delete ns challenge"

## Create Helm chart

1. Create a chart
    - "helm create first-chart"
  
2. Delete tepmlates directory then recreate manually to be empty
3. Create configmap.yaml
4. Install the chart
   - "helm install first-chart ."

5. Check the configmap
   - "kubectl get configmap"
   - "kubectl describe cm first-chart-configmap"

6. Create secret.yaml
   - convert username and password to base64: "echo -n 'admin' | base64" and "echo -n 'adminadmin' | base64"

7. Upgrade helm chart
   - "helm upgrade first-chart ."

8. Check the secret
   - "kubectl get secrets"
   - "kubectl describe secret first-secret"