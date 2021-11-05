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

## Volumes
- To persist container data. Example: make data persistent in DB.
- Normally, k8s doesn't manage data persistance. 

**Deployment**
In real case, you don't create pods. you create deployment where you define how many pods to create.
To avoid data inconsistance `StatefulSet` is used by DB container services.
## Kubernate on local machine
