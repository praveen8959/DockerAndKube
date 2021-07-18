# DockerAndKube
####Required minikube and kubectl

###This project is a simple mongodb test project using kunbernate clusters with minikube and kubectl.

1) #### The mongodb node which will have two pods
    1) Mongo express
    2) Mongo Db

2) #### Contains 2 services for communication between pods
    1) mongo-express-service
    2) mongodb-service

3) #### Contains mongo-configmap which contains external configurations.

4) #### Contains mongo-secret which contains username and password

Steps to create mongo test project:

1) Create mongodb configuration as mongodb.yaml.
2) If you want to secure the username and password then create a mongo-secret.yaml
3) Create mongodb service in same file.(in order to avoid confusion)
4) Run "kubectl apply -f mongo-secret.yaml" and then run for mongodb.yaml
5) Create mongoexpress configuration as mongoexpress.yaml
6) Create mongoexpress service in same file
7) Create mongo configmap.yaml which can contain external configurations such as database url
8) Run "kubectl apply -f mongo-configmap.yaml" and then run for mongoexpress.yaml
9) Run "minikube service mongo-express-service" which will assign the external IP.
