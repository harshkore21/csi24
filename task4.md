# Azure Container Registry: Create and Use a Container Image

## Table of Contents
1. [Create an Azure Account](#create-an-azure-account)
2. [Create an Azure Container Registry (ACR)](#create-an-azure-container-registry-acr)
3. [Push an Image to ACR](#push-an-image-to-acr)
4. [Create a Container Instance from ACR Image](#create-a-container-instance-from-acr-image)
5. [Additional Resources](#additional-resources)

## Create an Azure Container Registry (ACR)

1. **Navigate to the Azure Portal**:
   - Go to [portal.azure.com](https://portal.azure.com/) and sign in with your Azure account.
   
2. **Create an ACR**:
   - In the Azure portal, click on "Create a resource" in the left-hand menu.
   - Search for "Container Registry" and select it.
   - Click "Create".

3. **Configure the ACR**:
   - Basics: Select your subscription, resource group, and give your ACR a name (e.g., MyContainerRegistry).
   - Region: Select a region close to your users (e.g., East US).
   - SKU: Select a SKU based on your needs (e.g., Basic).
   - Click "Review + create" and then "Create".

## Push an Image to ACR

1. **Install Docker**:
   - Ensure Docker is installed on your local machine. If not, download and install it from the [Docker website](https://www.docker.com/products/docker-desktop).

2. **Login to ACR**:
   - Open a terminal and log in to your ACR: `az acr login --name MyContainerRegistry`
   
3. **Tag Your Image**:
   - Assuming you have a Docker image locally (e.g., `myapp:latest`), tag it for ACR:
     ```sh
     docker tag myapp:latest MyContainerRegistry.azurecr.io/myapp:latest
     ```

4. **Push the Image to ACR**:
   - Push the tagged image to your ACR:
     ```sh
     docker push MyContainerRegistry.azurecr.io/myapp:latest
     ```

## Create a Container Instance from ACR Image

1. **Navigate to the Azure Portal**:
   - Go to [portal.azure.com](https://portal.azure.com/) and sign in with your Azure account.
   
2. **Create a Container Instance**:
   - In the Azure portal, click on "Create a resource" in the left-hand menu.
   - Search for "Container Instance" and select it.
   - Click "Create".

3. **Configure the Container Instance**:
   - Basics: Select your subscription, resource group, and give your container a name (e.g., MyContainerInstance).
   - Region: Select the region where your ACR is located.
   - Image source: Select "Azure Container Registry".
   - Registry: Select your ACR (e.g., MyContainerRegistry).
   - Image: Enter the image name (e.g., MyContainerRegistry.azurecr.io/myapp:latest).
   - Size: Choose a size for your container instance.
   - Click "Review + create" and then "Create".

4. **Verify the Container Instance**:
   - Once the container instance is created, navigate to its overview page in the Azure portal.
   - Note the FQDN (Fully Qualified Domain Name) of your container instance.
   - Open a browser and navigate to the FQDN to see your application running.
