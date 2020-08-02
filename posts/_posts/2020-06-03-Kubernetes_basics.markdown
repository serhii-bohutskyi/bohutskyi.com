---
title: Kubernetes commands
description: kubernetes,basics,commands,cluster,node,pod,api,master,kubectl
---

```kubectl config get-clusters``` 

to get all clusters in your .kube/config file

```kubectl config get-contexts``` 

to get contexts

```kubectl config current-context``` 

to print current context


In order to change it use the next command:

```kubectl config use-conext <context_name>```


To get list of all objects of special kind verb ‘get’ is used:

```kubectl get pods```

```kubectl get deployments```

```kubectl get secrets```

```kubectl get services```

```kubectl get pdb```

```kubectl get hpa```


Additional switches that can be added to the above commands:

```-o wide``` - show more information

```--watch``` or ```-w``` - watch for changes


Useful ```get``` command:

```kubectl get <object_type> <object_name> -o yaml``` 
 
to print YAML manifest of requested resource

For ex. ```kubectl get po my-test-pod -o yaml```


The first troubleshooting verb is ```describe```, it shows detailed info about resource and latest events related to this resource:

```kubectl describe pod <pod_name>```

```kubectl describe deployment <deployment_name>```

```kubectl describe secret <secret_name>```

```kubectl describe service <service_name>```

```kubectl describe hpa <hpa_name>```

```kubectl describe pdb <pdb_name>```   


The second troubleshooting word is ```log```, it shows pod logs:

```kubeclt logs <pod_name>``` - to see all logs that were written by pod until now.


Useful flags:

```-f``` or ```--follow``` – to catch new logs in real-time

```--previous``` – to see logs of previous failed container (in case pod keeps failing)

```--tail <number>``` – print <number> latest log lines


The third verb is ```exec```:

```kubectl exec -it <pod_name> bash``` – this creates new bash session inside container inside pod you specified and provides it for you as standard terminal.


Editing resources on the fly:

```kubectl edit deploy <deploy_name>```

to edit your deployment manifest on the fly. Can be useful to tests app behavior with special configs, like new
/modified env variable, different amount of resource, etc.

```kubectl edit hpa <hpa_name>```

to edit HorizontalPodAutosacller resource. Can be useful to scale app to the maximum amount of pods.


In order to delete resource:

```kubectl delete pod <pod_name>```  

(it is one of the approaches to restart your application, delete pods one by one, but waiting for the new one before deleting
the next one)

```kubectl delete deploy <deploy_name>```

(in order to stop application on some specific environment) this can’t be restored automatically, only through CI/CD
job or using backuped .yaml file.


Another approach to stop app on specific env significantly SAFELY (read as USE THIS OPTION) is:

```kubectl scale deployment <deployment_name> --replicas=0```



```kubectl delete service <service_name>```

(in order to delete k8s service together with corresponding LoadBalancer in cloud), traffic to app will be stopped. 



[Kubernetes Documentation](https://kubernetes.io/docs/home/)
