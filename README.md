

INSTALCION MANUAL
minikube profile [nombre_clouster]
minikube service [Nombre-svc] (Abre navebador apuntando alos puertos corectos)
minikube status (checar si status minikube)
minikube logs  (Genara toda la informacion de miniKube)
minikube ip (ver ip)
minikube ssh (entrar a minikube)
minikube profile list (ver un alista de los cluster)
minikube start --driver=docker -p [NOMBRE-CLUSTER] --nodes=2 (crear un cluster con un cantidad especifica de nodos entre mas nodos mas recursos)
minikube delete -p
kubectl get nodes 

Hacer Un posh en docker Hup
$ docker push [Usuario de docker]/nginx:v1


Crear un pod:	
kubectl run [NombrePod] --image=[Imagen]  --port=[Puertodelpod 80]

Crear un pod desde Yaml :
kubectl apply -f [NombreArchivo].yaml (estar en ruta file)

Listar pods:
kubectl get pods

Listar pods mas info:	
kubectl get pods -o wide

Describir componesntes:	
kubectl describe [componeste]/[Nombrecomponentes] Example: kubectl describe pod/nginx2

Entrar de modo interactivo:	
kubectl exec [NombrePod] -it -- bash

Crear un pod apache; 
kubectl run apache --image=httpd --port=8080

ver los logs:
kubectl logs [nombrePod] 

se queda en logs:	
kubectl logs -f [nombrePod]

monitoria kubernetes desdes navegador:	
kubectl proxy example http://localhost:8001/api/v1/namespaces/default/pods/srapache

crear un pod expuesto fuera del cluser:	
kubectl expose pod [Nombredelpodaexponer]--port=80 --name=[Nombre] --type=LoadBalancer 

ver el servicio creado:	
kubectl get svc

hacer local un puerto de un contenedorpod de minikube: 
kubectl port-forward [NombrePod] 9999:80


