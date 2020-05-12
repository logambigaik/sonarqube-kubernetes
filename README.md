# sonarqube-kubernetes

Encode USERNAME and PASSWORD of Postgres using following commands:
--------

    echo -n "postgresadmin" | base64
    echo -n "admin123" | base64
    
Create the Secret using kubectl apply:
-------
  
    kubectl apply -f postgres-secrets.yml

Check secrets:
-------

    kubectl get secrets

Create PV and PVC for Postgres using yaml file:
-----

    kubectl apply -f postgres-storage.yaml

Check pv and pvc:
----
  
    kubectl get pv
    kubectl get pvc
    
Deploying Postgres with kubectl apply:
-----------

    kubectl apply -f postgres-deployment.yaml
    kubectl apply -f postgres-service.yaml
    
Check Deployments, Pods and Services:
-------

    kubectl get deploy
    kubectl get pods
    kubectl get svc
 
Create PV and PVC for Sonarqube:
--------------

    kubectl apply -f sonar-pv-data.yml
    kubectl apply -f sonar-pv-extensions.yml
    kubectl apply -f sonar-pvc-data.yml
    kubectl apply -f sonar-pvc-extentions.yml
    
Create configmaps for URL which we use in Sonarqube:
--------

    kubectl apply -f sonar-configmap.yaml
    
Deploy Sonarqube:
-------------

    kubectl apply -f sonar-deployment.yml
    kubectl apply -f sonar-service.yml
    
Now Goto Loadbalancer and check whether service comes Inservice or not, If it comes Inservice copy DNS Name of Loadbalancer and check in web UI

Default Credentials for Sonarqube:
-------

    UserName: admin
    PassWord: admin
 
    
