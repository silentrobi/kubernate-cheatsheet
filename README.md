# Kubernate-cheatsheet
**pod** 
* Smallest unıt of K8s
* Usually one application per pod.
* Has own IP address. However IP get changed on container restart.

**service**
* Provides static IP (Doesn't change on container crash / restart)
* Types: 
  -  External (To communcate with external sources.  `http://<my-service-ip>:<port>`)
  -  Internal (To communicate with internal services)
  
**Ingres**
* provides https and domain name based url for service. `http://my-app.com`

**ConfigMap**
* set-up external configuration for your application. Example, set up db url for the application. `DB_URL=postgreSQL`

**Secret**
* Used to store secret data. (password, certificate etc...)
* base64 encoded

**Volumes**
- To persist container data. Example: make data persistent in DB.
- Normally, k8s doesn't manage data persistance. 

**Deployment**
- In real case, you don't create pods. you create deployment where you define how many pods to create.
- To deploy stateless apps

**StatefulSet**
- To avoid data inconsistance `StatefulSet` is used by DB container services.
- Deploying `StatefulSet` is not easy in k8s.
- **DB are often hosted outside of k8s cluster.**

## Kubernate Architecture
Consists of master node and slave nodes.

Each node should have three processes running on.
1. **Container Runtime**
2. **Kubelet**: interect with both container and node. start a pod with container inside, allocate resounces to pod
3. **Kube proxy**: forward request between node service.

**How do you interect with k8s cluster?**
- schedule pods
- monitor
- re-schedule / self-restart
- join new nodes

All these managing processes are done by `Master Nodes`
## Kubernate on local machine
