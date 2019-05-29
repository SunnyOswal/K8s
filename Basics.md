Kubernetes provides a **declarative approach to deployments**, backed by a robust set of **APIs for management operations**.

+ **API OBJECTS**
  + **PODS**:  
Pods are responsible for running your containers. Every Pod holds at least one container, and controls the execution of that container. When the containers exit, the Pod dies too.

  + **CONTROLLERS**:  
Define desired state. Respond to pod state and health.

    + **REPLICA SET**:  
A ReplicaSet ensures that a set of identically configured Pods are running at the **desired replica count**. If a Pod drops off, the ReplicaSet brings a new one online as a replacement.

    + **DEPLOYMENTS**:  
A Deployment is a higher-order abstraction that controls deploying and maintaining a set of Pods. Behind the scenes, it uses a ReplicaSet to keep the Pods running, but it offers sophisticated **logic for deploying, updating, and scaling a set of Pods** within a cluster.

  + **SERVICES**:  
is a network and abstraction for access to the services that pods actually provide, and so what Kubernetes does for us is it persistently allocates an IP and DNS name for the application services that are provided by the collection of pods that we want to front end with a service.  
We can also leverage services to scale our application by adding or removing pods based on the demands of that application, and services also provide load balancing to distribute application load across those pods providing the application service.

  + **STORAGE**:
    + **Persistent volume**  
    is pod-independent storage that's defined by the administrator at the cluster level, and so when a pod wants access to that storage, it defines what's called a persistent volume claim. This technique effectively decouples the pod from the storage inside of the cluster.

+ **CLUSTER COMPONENTS**
  + **MASTER**
    + API SERVER + CLUSTER STORE(etcd) + SCHEDULER + CONTROLLER MANAGER
    
  + **NODE**  
    + KUBELET + KUBE-PROXY + CONTAINER RUNTIME 
    
  + **SCHEDULED/ADD ONS**  
    + DNS + INGRESS + DASHBOARD

+ **SECRETS**:  
Secrets are used to store non-public information, such as tokens, certificates, or passwords. Secrets can be attached to Pods at runtime so that sensitive configuration data can be stored securely in the cluster.

+ **DAEMONSETS**:  
DaemonSets provide a way to ensure that a copy of a Pod is running on every node in the cluster. As a cluster grows and shrinks, the DaemonSet spreads these specially labeled Pods across all of the nodes.

+ **INGRESSES**:  
Ingresses provide a way to declare that traffic ought to be channeled from the outside of the cluster into destination points within the cluster. One single external Ingress point can accept traffic destined to many different internal services.

+ **CRONJOBS**:  
CronJobs provide a method for scheduling the execution of Pods. They are excellent for running periodic tasks like backups, reports, and automated tests.

+ **CRDs**:  
CustomResourceDefinitions, or CRDs, provide an extension mechanism that cluster operators and developers can use to create their own resource types.

+ **NAMESPACES**:  
object is the logical isolation boundary like virtual cluster within a cluster used for separation.
