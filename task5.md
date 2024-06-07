# Azure Container Instance: Create and Deploy a Simple Docker Application 📦

## Table of Contents 📋
1. [Create an Azure Account](#create-an-azure-account)
2. [Create an Azure Container Instance](#create-an-azure-container-instance)
3. [Deploy a Simple Docker Application](#deploy-a-simple-docker-application)
4. [Create Container Groups](#create-container-groups)
5. [Test Functionality](#test-functionality)
6. [Additional Resources](#additional-resources)

## Create an Azure Container Instance 🖥️

1. **Navigate to the Azure Portal**:
   - Go to [portal.azure.com](https://portal.azure.com/) and sign in with your Azure account.
   
2. **Create a Container Instance**:
   - In the Azure portal, click on "Create a resource" in the left-hand menu.
   - Search for "Container Instance" and select it.
   - Click "Create".

3. **Configure the Container Instance**:
   - Basics: Select your subscription, resource group, and give your container a name (e.g., MyContainerInstance).
   - Region: Select the region close to your users (e.g., East US).
   - Image source: Select "Docker Hub" or "Azure Container Registry" depending on where your image is stored.
   - Image: Enter the image name (e.g., `nginx` for a simple web server).
   - Size: Choose a size for your container instance.
   - Networking: Choose a DNS name label to create a FQDN (e.g., mycontainerinstance).
   - Click "Review + create" and then "Create".

## Deploy a Simple Docker Application 🚀

1. **Deploy an Nginx Container**:
   - If you selected Docker Hub as the image source, you can deploy a simple Nginx web server:
     ```sh
     docker pull nginx
     docker run -d -p 80:80 --name mynginx nginx
     ```

2. **Push Your Custom Docker Application to Docker Hub**:
   - If you have a custom Docker application, build and push it to Docker Hub:
     ```sh
     docker build -t harsh/myapp:latest .
     docker push harsh/myapp:latest
     ```

3. **Use the Custom Image in Azure Container Instance**:
   - In the Image field, enter `hk/myapp:latest`.

## Create Container Groups 🗃️

1. **Navigate to Container Groups**:
   - In the Azure portal, search for "Container Instances".
   - Click on "Container groups" and then "Add".

2. **Configure the Container Group**:
   - Basics: Select your subscription, resource group, and provide a name for your container group.
   - Containers: Add multiple containers as needed by clicking "Add container" and providing the necessary details (e.g., image name, port).
   - Networking: Configure networking settings as needed.
   - Click "Review + create" and then "Create".

## Test Functionality 🔧

1. **Verify Container Instance**:
   - Once the container instance is created, navigate to its overview page in the Azure portal.
   - Note the FQDN (Fully Qualified Domain Name) of your container instance.
   - Open a browser and navigate to the FQDN to see your application running.

2. **Verify Container Group**:
   - Once the container group is created, navigate to its overview page in the Azure portal.
   - Note the FQDN and access each container using its specific path or port.

3. **Check Logs and Metrics**:
   - Go to the "Logs" and "Metrics" sections of your container instance or group to monitor performance and check for any issues.
