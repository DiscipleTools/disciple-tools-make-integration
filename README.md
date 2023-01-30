## Make's Custom App Development Workflow

> The following steps are to be used as a guide, whilst setting up and extending the Make D.T. Custom App.

1. Clone [disciple-tools-make-integration](https://github.com/DiscipleTools/disciple-tools-make-integration) repository.

    ```sh
    git clone git@github.com:DiscipleTools/disciple-tools-make-integration.git
    ```

    - This repository is to be used as a staging area for the exporting/importing of Make's custom apps.


2. Install [Visual Studio Code](https://code.visualstudio.com/)


3. Generate Make API Keys.
    - [Generation of your API key](https://docs.integromat.com/apps/apps-sdk/generation-of-your-api-key)


4. Start Visual Studio Code IDE and open recently cloned `disciple-tools-make-integration` folder.


5. Configure Visual Studio Code IDE Environment.
    - [Configuration of VS Code](https://docs.integromat.com/apps/apps-sdk/configuration-of-vs-code)
        - Install [Make Apps SDK](https://marketplace.visualstudio.com/items?itemName=Integromat.apps-sdk) extension.
    - [VS Code environment](https://docs.integromat.com/apps/apps-sdk/vs-code-environment)


6. Once the Make Apps SDK has been configured and successfully connected to your Make.com environemt, you can now proceed with any of the following actions:
    - Export/Import custom apps, using the cloned [disciple-tools-make-integration](https://github.com/DiscipleTools/disciple-tools-make-integration) repository.
        - To export, right-click on custom app and select `Export App`.
            - A zip file will be generated conttaining all custom app files and configuration.
            - If custom app is to be shared with the wider team, ensure zip file is exported to cloned [disciple-tools-make-integration](https://github.com/DiscipleTools/disciple-tools-make-integration) repository directory.
        - To import, select the `Import App` option within the `MY APPS` menu section.
            - Select a zip file previously exported by Make Apps SDK extension and import.
    - [Creating an app in VS Code](https://docs.integromat.com/apps/apps-sdk/creating-an-app-in-vs-code)