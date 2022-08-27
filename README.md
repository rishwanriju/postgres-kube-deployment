# postgres-kube-deployment

before you start :

get minikube if you are running in local

or get kubernetes with all the configuration done

how to start the project :

build the Dockerized-Golang-Postgres-Mysql-API using docker build command

tag the project using docker tag and push it into your docker hub registry

create the secret required for the project using kubectl apply -f postgres-secret.yaml 

create the persitant volume and claim created volume using kubectl apply -f postgres-db-pv.yaml and postgres-db-pvc.yaml respectively

start the deployment using kubectl apply -f postgres-db-deployment.yaml 

note : you can addtionally change the image from the postgres-db-deployment.yml file from the image tag(since I used my docker image)

start the service using kubectl apply -f postgres-db-service.yaml 

now start the app using kubectl apply -f app-postgres-deployment.yaml

start the service using app-postgres-service.yaml

you can get the link of the app using minikube service fullstack-app-postgres --url if you are using minikube

additionally if you encouter any error try kubectl describe pod command and kubectl logs to debug
