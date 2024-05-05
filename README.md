Running command to build jenkins image. This file config mount jenkins local to jenkins container
After building, we have jenkins container has docker instance from machine

Step1:
docker image build -t <image_name> .

Step2:

docker run --name <container_name> -it -p 8080:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock -v jenkins_home:/var/jenkins_home <image_name>

<container_name> : type name do you want
-v /var/run/docker.sock:/var/run/docker.sock: mount docker from machine to jenkins container
-v jenkins_home:/var/jenkins_home: mount folder jenkins_home in container to local folder. This is folder restore configs, plugins ..., it will store data and auto apply configs when delete container or migrate and update container.
<image_name>: image name in step 1

Step3:
exec to container in step 2:

docker exec -it <container_name> bash

Step4:
switch to user jenkins then test docker

su jenkins

docker ps

if you see all container running in local machine. It done!
# jenkins
