Name: Muhammad Marwan Bin Mohd Bukhori

Q1:
Create a deployment named nginx in the qq2 namespace using the nginx image with 3 replicas.

Q2:
Create a new deployment name lab-deployment in the qq2 namespace. With one replica in the manifest then scale the deployment to 4 replicas.

Q3:
Create a deployment names nginx-deployment in the qq3 namespace. Perform a rolling update to the deployment by setting the image to nginx:alpine.

Q4:
Create ConfigMap name it q5 and Secret name credentials in the default namespace.

The secret file should contain username and password

and the config map

does not need to have any certain data but it should be functional

Create a pod named apache using the httpd image in the default namespace containing the following:

Environment variable named CONTENT containing the key content from the q5 ConfigMap Environment variable named USERNAME containing the key username from the credentials Secret Environment variable named PASSWORD containing the key password from the credentials Secret

Q:5
Create a StatefullSet with 3 replicas named limit using the redis image in the qq3 namespace with the following resource limits and requests:

RequestsCPU: 0.5Memory: 500MiLimitsCPU: 1Memory: 1Gi

Q6:
Create a Deployment named web in the ca1 namespace with an image of nginx:latest. Create a new Service named web-svc that sits in front of this deployment. Expose the new service publicly by using the exact port of 8080. The Ingress's host field must be set to the host key value stored in an existing ConfigMap named webapp-host-fqdn, also located in the ca1 namespace. All changes should be performed in the ca1 namespace.

Q7:

Execute the following requirements in the prod namespace. Create a new Deployment named app01 using the nginx:latest container image and have it listen on port 80. The deployment should consist of 2 replicas. Create a new Service named app01-svc and expose the newly created deployment using a NodePort. Confirm that you can access the nginx home (index) page using the NodePort service.

Q8:
Create a new Deployment named cloud-app01 in the ca2 namespace consisting of 2 replicas. The deployment should use image nginx:1.23.3-alpine. Create a new Service resource named cloud-app-svc to expose the cloud-app01 deployment on port 80 in the same namespace. Finally use the following kubectl run command to spin up a utility pod which tests HTTP connectivity through the new service. Confirm that the following command returns an HTTP 200 response code:

kubectl run -n ca2 -i --tty --restart=Never --rm netutil --image cloudacademydevops/networkutils:v2 -- curl -I cloud-app-svc

Q9:
Create a StorageClass named class configured with the following settings:

provisioner = rancher.io/local-path
name = gp2
volume type = retain
Reclaim policy = do not allow for volume expansion

Q10:
Create a PersistentVolume named pv. The PersistentVolume must be configured with the following settings:

storageClassName: gp21Gi of storage capacityallow a single Node read-write accessuse a hostPath of /mnt/data
The PersistentVolume must be claimed by a PersistentVolumeClaim named pvc. The PersistentVolume must request 1Gi of storage capacity.

Q11:

Create a Pod named pod with one nginx container in the qq2 namespace. The Pod must use the podpvc PersistentVolumeClaim to mount a volume at /data. The pod must have read-only access to the pvc.

Q12:

Create a StorageClass names state. Assign a persistent volume with 3Gi to it and create a StatefulSet with a following configuration:

Image = mysql:oraclelinux9
Claims = 2Gi
Takes MYSQL_ROOT_PASSWORD and MYSQL_PASSWORD from the secret names mysqlsecret
Takes MYSQL_DATABASE and MYSQL_USER from the configmap names mysqlconfig
Namespace: datastorage

Q13:

Scale up the StatefullSet in previous question to 6 and show the output

Q14:

Create a deployment names nginx-deployment in the qq3 namespace. Perform a rolling update to the deployment by setting the image to nginx:alpine.

Q15:
Create a new deployment name apache-deployment with an image of caleed httpd:latest

in the qq3 namespace. Perform rolling update to the image httpd:bookworm and then a rollback of the deployment to restore the original image.

Q16:
Deploy postgres by using Deployment with the following image:

https://hub.docker.com/_/postgres

Use proper ConfigMap, Secret, Persistent Volume/StorageClass, PersistenVolumeClaim , Service

Q17:

Then use elastio/pgadmin to create a database and change for the previous question

https://hub.docker.com/r/elestio/pgadmin
