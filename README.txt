************************************************************************************************************************
* Updating Your App
* https://asciinema.org/a/qitap2VrFkFVB9BrX2qUHuwFt
*
************************************************************************************************************************
$ kubectl get deployments
$ kubectl create deployment test-web-server --image=docker.io/deniskosolapov/test-web-server:1.0
$ kubectl get pods
$ kubectl get deployments
$ kubectl expose deployment test-web-server  --type=LoadBalancer --port=80
$ kubectl get services
$ minikube service test-web-server
$ kubectl set image deployments/test-web-server test-web-server=docker.io/deniskosolapov/test-web-server:2.0
$ kubectl set image deployments/test-web-server test-web-server=docker.io/deniskosolapov/test-web-server:3.0
$ kubectl set image deployments/test-web-server test-web-server=docker.io/deniskosolapov/test-web-server:2.0
************************************************************************************************************************
* Scaling Your App
* https://asciinema.org/a/12Op9S1mytnRwBS0eFKhmL4Fe
*
************************************************************************************************************************
$ kubectl get pods
$ kubectl create deployment test-web-server --image=docker.io/paulbouwer/hello-kubernetes:1.7
$ kubectl expose deployment test-web-server  --type=LoadBalancer --port=8080
$ kubectl scale deployments/test-web-server --replicas=2
$ minikube service test-web-server
$ kubectl get pods
$ kubectl scale deployments/test-web-server --replicas=4
$ kubectl get pods
$ kubectl scale deployments/test-web-server --replicas=1
$ kubectl get pods
************************************************************************************************************************
* Upload owen image withowt docker.io
* https://asciinema.org/a/FcOlSHM29dWJENrKo4jqDOcQA
*
************************************************************************************************************************
$ docker build --tag hello-web-server:5.0 .
$ docker save -o hello.tar paulbouwer/hello-kubernetes:1.7

Get minikube ip
$ minikube ip

The default login is, username: “docker“, password: “tcuser“. 
$ scp /home/denis/hello-kubernetes/hello.tar docker@192.168.99.100:/home/docker

$ minikube ssh
$ docker images
$ docker load -i hello.tar
$ kubectl create deployment hello-world  --image=paulbouwer/hello-kubernetes:1.7
$ kubectl expose deployment hello-world  --type=LoadBalancer --port=8080
$ minikube service hello-world

