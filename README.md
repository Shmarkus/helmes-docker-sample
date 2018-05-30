# Usage

* Add new registry in [Azure](https://portal.azure.com/#blade/HubsExtension/Resources/resourceType/Microsoft.ContainerRegistry%2Fregistries)
    * When registry is ready, open the instance and look for *Access keys* menu. There you'll find **Login server**, **Username** and **Password**
* Use docker shell on your local machine: ```docker login <Login Server> -u <Username>``` and enter password when prompted, eg. ```docker login helmesregistrytest.azurecr.io -u helmesRegistryTest```
* Build the current application ```./gradlew build``` and then create docker image ```./gradlew buildDocker```
* Create tag of this image ```docker tag sample helmesregistrytest.azurecr.io/samples/sample```
* Push image to registry ```docker push helmesregistrytest.azurecr.io/samples/sample```

> To remove the image, use command: ```docker rmi helmesregistrytest.azurecr.io/samples/sample```
* Create AppService for containers
* Select Azure registry and fill all the fields with references to built image (eg. sample)

> When using different port than 80, you must provide WEBSITES_PORT value under **Application settings** 