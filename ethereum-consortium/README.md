# FST Ethereum Blockchain on Azure

### Deploy using Azure Portal

Clicking on the button below, will launch our azure template to create blockchain network in your Azure subscription.

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Ffstnetwork%2Fazure-templates%2Fmaster%2Fethereum-consortium%2FmainTemplate.json)

### Blockchain Network Setup

1. **Create an account**
    * Navigate to [My Ether Wallet](http://myetherwallet.com)
    * Type in a password that will be used to secure the file generated
    * Download the Keystore file. We'll use this later.
    * Copy the address ex. 0x0000000000000000000000000000000000000000

2. **Generate the a genesis private account json content**
    * Replace the privateKey and address of the json below with the account that you generated from the step above.

            {
              "privateKey": "1806dca5a69b6ef7b73cfd244ce7be2b6bdc8d6d28845fbfb7fba7aa2eba50df",
              "address": "cd2051a37cdc02db5da21d61415de21af4058a5e"
            }

3. **Deploy the template**  

    **SSH Public Key**  
    ssh public key(s) for connecting to VMs
      
      - [Create SSH Key pair from linux based system](https://github.com/MicrosoftDocs/azure-docs/blob/master/articles/virtual-machines/linux/mac-create-ssh-keys.md#create-an-ssh-key-pair)

       - [Create SSH Key pair from windows system](https://github.com/MicrosoftDocs/azure-docs/blob/master/articles/virtual-machines/linux/ssh-from-windows.md#create-ssh-keys-with-puttygen)

    **Genesis Private Account**  
    Paste the json contents from Step 2 into the text box

    **Ethereum Network Id**  
    This is a shared secret that all ethereum nodes need to be started with in order to communicate. This should be a numerical value. **Default value: 54321**

    **Dashboard Secret**  
    This is a shared secret between the dashboard and it's clients. **Default value: 12345**

    **Tx Nodes**  
    Number of transaction nodes

    **Mining Nodes**  
    Number of miners to create for this members

4. **Completed Deployment**
    * Once the deployment completes you will find a Dashboard IP address in the output of
    of the template. You may also find it as a resource calle {consorsortium name}-dashboard-ip.
        * Port 3000 - Eth Stats Dashboard, this is useful to see the nodes, their blocks, etc.
        * Port 3001 - Boot node registrar
