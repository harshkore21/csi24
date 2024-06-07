# Azure App Service: Create and Deploy a Web App 📖

## Table of Contents 📋
1. [Create an Azure Account](#create-an-azure-account)
2. [Create an App Service Plan](#create-an-app-service-plan)
3. [Provision a Web App in the App Service Plan](#provision-a-web-app-in-the-app-service-plan)
4. [Deploy a Simple Welcome Page](#deploy-a-simple-welcome-page)
5. [Additional Resources](#additional-resources)

## Create an App Service Plan 👨‍💻

1. **Navigate to the Azure Portal**:
   - Go to [portal.azure.com](https://portal.azure.com/) and sign in with your Azure account.
   
2. **Create an App Service Plan**:
   - In the Azure portal, click on "Create a resource" in the left-hand menu.
   - Search for "App Service Plan" and select it.
   - Click "Create".

3. **Configure the App Service Plan**:
   - Basics: Select your subscription and resource group. Provide a name for your App Service Plan (e.g., MyAppServicePlan).
   - Operating System: Choose Windows or Linux based on your preference.
   - Region: Select a region close to your users (e.g., East US).
   - Pricing tier: Click on "Change size" and select a pricing tier based on your needs. The "Free" tier (F1) is suitable for testing.
   - Click "Review + create" and then "Create".

## Provision a Web App in the App Service Plan 🔗

1. **Navigate to the Web App**:
   - In the Azure portal, click on "Create a resource" in the left-hand menu.
   - Search for "Web App" and select it.
   - Click "Create".

2. **Configure the Web App**:
   - Basics: Select your subscription, resource group, and give your Web App a name (e.g., MyWebApp12345). This name must be unique across all of Azure.
   - Publish: Choose "Code".
   - Runtime stack: Select the runtime stack you prefer (e.g., .NET, Node.js, PHP).
   - Operating System: Choose the same OS you selected for your App Service Plan.
   - Region: Select the same region as your App Service Plan.
   - App Service Plan: Click "Create new" and select the existing App Service Plan you created earlier.
   - Click "Review + create" and then "Create".

## Deploy a Simple Welcome Page ⚙️

1. **Navigate to the Deployment Center**:
   - Go to your Web App's overview page in the Azure portal.
   - In the left-hand menu, under "Deployment", click on "Deployment Center".

2. **Configure Deployment**:
   - Select your source. For simplicity, choose "Local Git" and follow the instructions to set up a local Git repository.
   - Alternatively, you can choose "GitHub" if you have your code in a GitHub repository.

3. **Clone the Repository and Add Code**:
   - Open a terminal on your local machine.
   - Clone the repository using the provided URL: `git clone https://github.com/harshkore21/git-repo`
   - Navigate to the cloned directory: `cd https://github.com/harshkore21/git-repo`

4. **Create a Simple Welcome Page**:
   - Create an `index.html` file with the following content:

     ```html
     <!DOCTYPE html>
     <html>
     <head>
         <title>Welcome to My Web App</title>
     </head>
     <body>
         <h1>Welcome to My Web App</h1>
         <p>This is a simple welcome page.</p>
     </body>
     </html>
     ```

5. **Push the Changes to Azure**:
   - Add the file to the repository: `git add index.html`
   - Commit the changes: `git commit -m "Add welcome page"`
   - Push the changes to the remote repository: `git push`

6. **Verify the Deployment**:
   - Once the deployment is complete, navigate to the URL of your Web App (e.g., `https://MyWebApp12345.azurewebsites.net`).
   - You should see your simple welcome page.
