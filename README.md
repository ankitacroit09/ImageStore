																	*****************Docker-Minikube******************
Create the Docker Image and expose to minikube and generate the URL
																	
																	
Step 1>			
docker file dir> docker build -t appdemo:v1 .

Step 2>			
kubectl run appdemosample10 --image=appdemo:v1 --port=8080

Step 3>	
kubectl expose deployment appdemosample10 --type=NodePort

Step 4>	
minikube service appdemosample10 --url							

----------------------------------------------------------

Command for check the status:
Docker images
kubectl get pods
kubectl get deployment
			
																	*****************MYSQL DATABSE******************
																	

Step 1: 
kubectl create secret generic mysql-pass --from-literal=password=password

Step 2: Deploy the contents of the YAML file
kubectl create -f /mysql/mysql-pv.yaml
kubectl create -f /mysql-deployment.yaml

Step 3: Debug

kubectl get pods | grep mysql  it outputs podname
kubectl exec -it <podname> bash

mysql -u root -h mysql -ppassword
password
show databases;
use mysql;
show tables;

CREATE TABLE ImageBlob (imagename varchar(255) NOT NULL ,imgae LONGBLOB NOT NULL , albumname varchar(255) NOT NULL);
ALTER TABLE ImageBlob ADD CONSTRAINT pk_image PRIMARY KEY (imagename,albumname);
SELECT imagename,albumname from ImageBlob;


																	*****************Access URl******************

For Show the images:
http://192.168.99.100:30183/welcome.html
																
For upload the Image:
http://192.168.99.100:30183/upload.html			

For Delete the single file:
http://192.168.99.100:30183/delete.html

For Delete the folder of files:
http://192.168.99.100:30183/deleteFolder.html												






