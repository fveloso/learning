kubectl get pod  
kubectl get service  
kubectl apply -f .  
kubectl port-forward blue 8080:8080  
kubectl logs blue  
kubectl exec -ti web /bin/sh  
kubectl top pods  
kubectl get pod web -o yaml > web.yaml  
$ kubectl create configmap website --from-file-index.html --dry-run -o yaml > website.yaml  
kubectl api-resources  
