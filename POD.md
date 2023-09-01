We configured the Kubernetes Cluster and opened a session for the Master Node .
Our Aim is to create a multi-container POD and launch operations on this arrangement.
We used the following commands for the operations:-
kubectl get pod

(For getting the number of active PODs)

Post this we took a duplicate session of our Command line session by holding the previous one to watch for any POD activity using the command

watch kubectl get pod.

After this we made a .yml file naming dave.yml

using the command 
 
vim dave.yml

and defined it as follows:-

apiVersion: v1
kind: POD
metadata:
  name: dave1234
 spec:
  containers:
   -  name: 1st
      image: mysql
      
   - name: 2nd
     image: mysql
     

. After that we ran the command to demonstrate the working of a POD with two similar images in containers.

 kubectl apply -f dave.yml
 
 which gives us an error . Hence it ran only 1 image.
 
 This could be verified by reading the entire build structure of the POD using the command
 
 kubectl describe pod dave1234
 
 . The pause container can be seen  in the worker node 
