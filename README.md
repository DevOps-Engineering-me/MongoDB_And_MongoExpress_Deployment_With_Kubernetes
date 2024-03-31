
# MongoDB_And_MongoExpress_Deployment_With_Kubernetes

## This an Complete Deployment Project with MongoDB and MongoExpress with minikube
### The Pods Work flow 
![Screenshot from 2024-03-29 15-06-20](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/08ab149e-d4de-4153-8b45-c655b082a79c)




## Steps

### Step-1 

- Create mongo-secret.yaml file and write the Deployment Code
- Run this command to create Pod
```bash
  kubectl apply -f mongo-secret.yaml
```
- for confirm use this command
```bash
  kubectl get secret
```
![sec](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/b8d5c859-a3eb-4cc3-a2c1-bd9beb20e9b1)
- here Mongo Secret pod will created and we use secret for database secret like username and password



### Step-2 Create MongoBD Deployment

- Create mongo.yaml file and write the Deployment Code
- Run this command to create Pod
```bash
  kubectl apply -f mongo.yaml
```
![3](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/bd1ecbaf-87c9-4159-83a8-b6d7e6ce37d5)

- Run this command to get all Pod
```bash
  kubectl get all
```
![4](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/cb2326ae-2e6b-4416-971f-252621d4f2c8)

- Run this command to get Pods
```bash
  kubectl get pod
```
![5](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/c1f7e735-150d-45a7-8f87-3a98cd17b45e)

- Run this command to get Service
```bash
  kubectl get service
```
![6](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/a1234a66-3153-4590-922d-2f8ba0268b55)

- Run this command to checking the service information using service name which can fin by previous command
```bash
  kubectl describe service mongodb-service
```
![7](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/5a16b60b-bb3f-4c06-a133-d15fe80ac681)

### Step-3 Creating Config Map
- Create mongo-configmap.yaml file and write the Deployment Code
- Run this command to create Pod
```bash
  kubectl apply -f mongo-configmap.yaml
```
- #### Here this config map use to maping Mongo Express and MongoBD pod ,like maping database_url,database_password,database_user etc
![8](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/3788f393-0c1c-4b13-ac43-a295b67c8e5e)

### Step-4 Creating MongoExpress Deployment
- Create mongo-express.yaml file and write the Deployment Code
- Run this command to create Pod
```bash
  kubectl apply -f mongo-express.yaml
```
![9](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/863d2c44-b70b-42f2-8288-2da8e5f294c9)

- use this command to find the mongo-express delpoyment name
```bash
  kubectl get pod
```
![10 1](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/d3d914c5-34f2-4fa2-925b-5a4f650adb86)
- using this mongo-express pod name let's logs this pod,it's connetion etc (use your pod name which find by 'kubectl get pod')
```bash
  kubectl logs <mongo-express pod mane>
```
![10](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/5a1bd709-7410-4439-9461-97f7f556d637)

### Step-5 
- Get the minikube service address / Browser address.
```bash
  minikube service mongo-express-service
```
![13](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/78561512-7ed9-4209-86f3-a0ea099254f6)

- Open Url on your Browser
![last](https://github.com/MdShafiqulSaymon/System_Design/assets/68004638/82acabde-5417-48d4-b27a-8f893f8f572a)




