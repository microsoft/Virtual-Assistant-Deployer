# Virtual Assistant Deployer

This solution accelerator provides a way to deploy a [Microsoft Virtual Assistant Solution](https://microsoft.github.io/botframework-solutions/overview/virtual-assistant-solution/) without needing to install all the prerequisite tools on your own machine. It uses a preconfigured docker container to create and deploy the virtual assistant with minimal effort and time.

Once completed, you will have a Virtual Assistant deployed into Azure as well as the code available to make modifications and deploy updates.

## Deploying your Virtual Assistant
There are two options to quickly getting your Virtual Assistant up and running.
* [Deploy with Visual Studio Online](docs/visualstudioonline.md) - This is the simplest and will all happen online. The only thing you need is an Azure Subscription.
* [Deploy with Visual Studio Code locally](docs/visualstudiocode.md) - This option uses your locally installed VS Code and Docker to do the work.

## How to talk to your assistant
After you have deployed the Virtual Assistant, you can test out!
1. Open the Azure portal and navigate to the Resource Group that has the name of your bot
2. Open the Web App Bot resource
3. Select the Test in Web Chat tab
4. Chat with your bot! 
NOTE: the first time you open the tab it may take a few moments as the entire app needs to start up for the first time

## Customizing your assistant
Now that you have an environment for developing a Virtual Assistant, you may want to review the [Next Steps](https://microsoft.github.io/botframework-solutions/virtual-assistant/tutorials/customize-assistant/csharp/5-next-steps/) section of the Virtual Assistant documentation for tutorials on some common customizations.

## How to delete your assistant
When you are done with your assistant
1. Delete the Azure resource group
2. Delete the application from Azure Active Directory. It has the same name as your bot.

# Additional Notes
The Virtual Assistant Deployer clones the [Bot Framework Solutions repo](https://github.com/microsoft/botframework-solutions) when you start it up. This ensures that your assistant will be based on the latest version of the sample assistant.

You can find the manual creation/deployment instructions in the  [Bot Framework Solutions documentation](
https://microsoft.github.io/botframework-solutions/virtual-assistant/tutorials/create-assistant/csharp/1-intro/)


## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
