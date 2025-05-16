

INSTALCION MANUAL

minikube profile [nombre_clouster]

minikube service [Nombre-svc] (Abre navebador apuntando alos puertos corectos)

minikube status (checar si status minikube)

minikube dashboard (docker dashboard)

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

Listar diferentes componentes 
kubectl get deploy,pods,rs

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

ver especificaciones del pod
kubectl get pod [NombrePod] -o yaml

Crear o configurar un pod(Util al modificar el fichero)
kubectl apply -f [nombreArchivo].yaml

ver labels de un pods 
kubectl get pods -o wide --show-labels
kubectl get pod [NombrePod] -o wide --show-labels
kubectl get pod [NombrePod] -o wide --show-labels -L [Label] (agrega una colupna con un etiqueta labels)

Agrega Etiquetas
kubectl label pod [NombrePod] [Etiqueta]=[Propiedad]
Modificar Etiquetas 
kubectl label --overwrite pod/[NombrePod] [EtiquetaLabel]=[Propiedad]
Eliminar Etiquetas 
kubectl label pod/[NombrePod] responsable-

borrar pods
 kubectl delete pod [NombrePod]
 kubectl delete pod/[NombrePod]
 kubectl delete pod [NombrePod], [NombrePod] ... 
 kubectl delete pod [NombrePod] --grace-period=5 (borra despuedes de un periodo de tiempo)
 kubectl delete pod [NombrePod] --now (borra sin espera a terminar procesos)
 kubectl delete pod --all (Borra todos los pods)

 Multiples container
  kubectl logs -f [NombrePod] -c [NombreContainer] (ver Logs del container dentro)
  kubectl exec [NombrePod] -c [NombreContainer]  -- date (dia del segundo container)

SELECTORES
sececionar pod con una etiqueta=propiedad
kubectl get pods -o wide --show-labels -l [Etiqueta]=[Propiedad]
kubectl get pods -o wide --show-labels -l [Etiqueta]!=[Propiedad]
kubectl get pods -o wide --show-labels -l '[Etiquetas] in([Propiedad],[Propiedad])'  (que este presente)
kubectl get pods -o wide --show-labels -l '[Etiquetas] notin([Propiedad],[Propiedad])' (que no este presente)

kubectl get pod [NombrePod] -o jsonpath={.metadata.annotations} (ver propiedades en esta caso anotaciones de un pod)

Crear un Deployment 
kubectl create deployment [nombrePod] --image=[Imagen]

ver deployments
kubectl get deploy

ver Repli caset????
kubectl get rs

ver descripcion de deploy 
kubectl describe deployment/[NombreDeploymet]


 kubectl edit deploy nginx-d(modificar de manera dianamica)
 kubectl get deploy nginx-d -o yaml (optener yaml de undeploy)

Reescalar un deploy
kubectl scale deploy -l [EtiquetaDeploy]=[Propiedad] --replicas=[CantidadReplicas]

optener los endpoins de minikube
kubectl get endpoints

ver a detalle un endponts
kubectl get endpoints [NombreEndpoints] -o yaml
 



