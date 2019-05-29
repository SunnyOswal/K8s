+ **HIGH LEVEL FLOW**
  + k8s users communicate with **API server** and apply **desired state**.
  + **Master node** actively **enforce** desired state **on worker nodes**.
  + Worker nodes support communication between containers.
  + Worker nodes support communication from the internet.

+ **SCENARIO** :  
  + Let's say we deployed some pods in a replica set with three replicas with **kubectl**.  
  + That request is going to be **submitted into the API server** and it's the responsibility of the API server to **store that information persistently in a cluster store**.  
  + With that, it's then the responsibility of the controller manager to **spin up those three requested replicas of that ReplicaSet**. So it's going to start up those three pods.  
  + That request is going to be submitted to the scheduler. The **scheduler is then going to mark on the API server that these pods need to be scheduled on these nodes**. Which nodes do those pods get scheduled on? Well, that's dependent upon the resources requested in the pods and the resources available on the nodes in the cluster.  
  + The **kubelet is going to ask the API server**, hey, do you have any work for me, and then it's going to start spinning up the pods that are requested in the ReplicaSet. 
  + **Controller manager** is monitoring the state of the replicas and everybody's reporting that they're in the desired state.
  + **If desired state changes**, controller manager is going to submit for a new pod to be created and scheduledto bring our ReplicaSet back into compliance with the desired state of three replicas. 
