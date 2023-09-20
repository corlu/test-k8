Deploy:

1. kubectl create -f sp-deployment.yaml 
2. kubectl create -f test-auth.yaml 
3. kubectl create -f sp-service.yaml 
  
  check 
    kubectl get all
  to see the external ip of the service load balancer. it may take a while
  if all pending, delete the deployment, service and pod (kubectl delete) and start over.
  
  the test-auth will create roles and rolebindings.

  If already created it will complain. always check 

    oc get rolebinding

    oc describe rolebinding shinyproxy-rolebinding
    
  to see that the desired service account (default) has the correct role
  (masterrole) in the appropriate namespace in the bottom Sujects list.
  
  test.
