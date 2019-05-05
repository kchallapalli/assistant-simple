<h1 align="center" style="border-bottom: none;">🚀 Watson Assistant (formerly Conversation) Sample Application</h1>
<h3 align="center">This Node.js app demonstrates the Watson Assistant service in a simple interface engaging in a series of simple simulated banking tasks.</h3>
<p align="center">
  <a href="http://travis-ci.org/watson-developer-cloud/assistant-simple">
    <img alt="Travis" src="https://travis-ci.org/watson-developer-cloud/assistant-simple.svg?branch=master">
  </a>
  <a href="#badge">
    <img alt="semantic-release" src="https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg">
  </a>
</p>
</p>

![Demo](readme_images/demo.gif)

You can view a [demo][demo_url] of this app.

Please note this app uses the [Watson Assistant V2 API](https://cloud.ibm.com/apidocs/assistant-v2#introduction). To access a version of the V1 app, you can go to [v1.4.1](https://github.com/watson-developer-cloud/assistant-simple/releases/tag/v1.4.1).

If you need more information about the V1 API, you can go to the [Watson Assistant V1 API page](https://cloud.ibm.com/apidocs/assistant#introduction).


## Prerequisites

1. Sign up for an [IBM Cloud account](https://cloud.ibm.com/registration/).
1. Download the [IBM Cloud CLI](https://cloud.ibm.com/docs/cli/index.html#overview).
1. Create an instance of the Watson Assistant service and get your credentials:
    - Go to the [Watson Assistant](https://cloud.ibm.com/catalog/services/conversation) page in the IBM Cloud Catalog.
    - Log in to your IBM Cloud account.
    - Click **Create**.
    - Click **Show** to view the service credentials.
    - Copy the `apikey` value, or copy the `username` and `password` values if your service instance doesn't provide an `apikey`.
    - Copy the `url` value.

## Configuring the application

1. In your IBM Cloud console, open the Watson Assistant service instance

2. Navigate to the **Skills** tab
  
3. Select the **Create skill** button
  
4. By default the Dialog skill is selected, if not select it and click **Next**

5. Navigate to the **Import skill** tab

6. Click the **Choose JSON File** button. Specify the location of the workspace JSON file in your local copy of the app project: (NOTE: Assuming that you have downloaded this whole git project to your local workstation)

    `<project_root>/training/bank_simple_workspace.json`

7. Select **Everything (Intents, Entities, and Dialog)** and then click **Import**. The car dashboard workspace is created.

8. If you are within the skill, click on **Skills /** link at the top. Else go to next step.

9. Navigate to the **Assistants** tab

10. Select the **Create assistant** button.  Give it a name (Eg: Assistant-Simple) and a description (optional).

11. Scroll down from within the Assistant-Simple assistant and select the **Add dialog skill** button. Then select the skill imported earlier from the tile. 

12. In the Assistant-Simple assistant page, select the burger menu at the top right and then select **Settings**

13. Navigate to the **API Details** tab and copy the Assistant ID 

14. In your local workstation application folder, copy the *.env.example* file and create a file called *.env*

    ```
    cp .env.example .env
    ```

15. Open the *.env* file and add the service credentials that you obtained in the previous step. The Watson SDK automatically locates the correct environmental variables for either `username`, `password`, and `url` or the `apikey` and `url` credentials found in the *.env* file.

    Example *.env* file that configures the `apikey` and `url` for a Watson Assistant service instance hosted in the US East region:

    ```
    ASSISTANT_IAM_APIKEY=X4rbi8vwZmKpXfowaS3GAsA7vdy17Qh7km5D6EzKLHL2
    ASSISTANT_URL=https://gateway-wdc.watsonplatform.net/assistant/api
    ```

    - If your service instance uses `username` and `password` credentials, add the `ASSISTANT_USERNAME` and `ASSISTANT_PASSWORD` variables to the *.env* file.

    Example *.env* file that configures the `username`, `password`, and `url` for a Watson Assistant service instance hosted in the US South region:

    ```
    ASSISTANT_USERNAME=522be-7b41-ab44-dec3-g1eab2ha73c6
    ASSISTANT_PASSWORD=A4Z5BdGENrwu8
    ASSISTANT_URL=https://gateway.watsonplatform.net/assistant/api
    ```
    However, if your credentials contain an IAM API key, copy the `apikey` and `url` to the relevant fields.
    ```JSON
      {
        "apikey": "ca2905e6-7b5d-4408-9192-e4d54d83e604",
        "iam_apikey_description": "Auto generated apikey during resource-key ...",
        "iam_apikey_name": "auto-generated-apikey-62b71334-3ae3-4609-be26-846fa59ece42",
        "iam_role_crn": "crn:v1:bluemix:public:iam::::serviceRole:Manager",
        "iam_serviceid_crn": "crn:v1:bluemix:public:iam...",
        "url": "https://gateway-syd.watsonplatform.net/assistant/api"
      }
    ```
    ```
    ASSISTANT_IAM_APIKEY=ca2905e6-7b5d-4408-9192-e4d54d83e604
    ```

16. Add the `ASSISTANT_ID` to the previous properties (see step 13)

    ```
    ASSISTANT_ID=522be-7b41-ab44-dec3-g1eab2ha73c6
    ```

## Running locally

1. Install the dependencies

    ```
    npm install
    ```

2. Run the application

    ```
    npm start
    ```

3. View the application in a browser at `localhost:3000`

## Deploying to IBM Cloud as a Cloud Foundry Application

1. Login to IBM Cloud with the [IBM Cloud CLI](https://cloud.ibm.com/docs/cli/index.html#overview)

    ```
    ibmcloud login
    ```

2. Target a Cloud Foundry organization and space.

    ```
    ibmcloud target --cf
    ```

3. Edit the *manifest.yml* file. Change the **name** field to something unique.  
  For example, `- name: my-app-name`.

4. Deploy the application

    ```
    ibmcloud app push
    ```

5. View the application online at the app URL.  
For example: https://my-app-name.mybluemix.net


## License

This sample code is licensed under Apache 2.0.  
Full license text is available in [LICENSE](LICENSE).

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md).

## Open Source @ IBM

Find more open source projects on the
[IBM Github Page](http://ibm.github.io/).


[demo_url]: https://assistant-simple.ng.bluemix.net/
[doc_intents]: https://cloud.ibm.com/docs/services/conversation/intents-entities.html#planning-your-entities
[docs]: https://cloud.ibm.com/docs/services/assistant/index.html#index
[docs_landing]: (https://cloud.ibm.com/docs/services/assistant/index.html#index)
[node_link]: (http://nodejs.org/)
[npm_link]: (https://www.npmjs.com/)
[sign_up]: https://cloud.ibm.com/registration
