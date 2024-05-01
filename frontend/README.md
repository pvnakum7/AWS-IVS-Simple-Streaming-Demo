# Simplifying live streaming contribution - run locally.

This sample demo app, captures the video and use a proxy in node.js to transwrap the stream to  Amazon IVS

Here are simplified steps to deploy and run the live streaming contribution app locally:

## 1. Install and configure AWS Amplify by running the following commands:
```sh
npm install -g @aws-amplify/cli
amplify configure
```
##  more detailed instructions, please refer to the official Amplify documentation for React. 
[Amplify Doc for React](https://docs.amplify.aws/start/getting-started/installation/q/integration/react#option-2-follow-the-instructions)

## 2. Clone the repository and navigate to the frontend directory:
```sh
git clone https://github.com/pvnakum7/AWS-IVS-Simple-Streaming-Demo.git
cd AWS-IVS-Simple-Streaming-Demo/frontend/
```

# 3. Install the necessary dependencies:
```sh
npm install
```

# 4. Initialize the Amplify project:
```sh
amplify init
```
# When prompted, enter "dev" as the environment name, choose your preferred default editor, and select "AWS profile" as the authentication method.

## 5. Push the project to create the necessary resources:
```sh
amplify push
```
## This command will deploy API Gateway, DynamoDB, and Lambda functions required for the app.

# 6. Run the solution in your local environment:
```sh
npm start
```

## above These steps will deploy and run the live streaming contribution app locally on your machine.



## Set Up Your Account
To get started, go to the authentication page. Here, you can create your user account and sign in.
## Connect Your Streaming Service
If you're using Amazon IVS, you'll need to add the **ingestEndpoint**, **streamKey**, and **playbackUrl** to your interface. If you don't have an Amazon IVS account yet, you can create one by following the provided steps.
In your local environment http://127.0.0.1:3000 (http://127.0.0.1:3000/) the following application will be loaded.

## Run the Server Locally

```sh
cd backend/
npm install
npm run startDev
```
**Note:** if you are running locally in HTTPS, the socket needs to be HTTPS as well, [please follow this instruction instead.](../backend/README_HTTPS.md)

### Test your streaming directly from your browser

<img src="../doc/7_app_live.png" alt="Application" />

### [Optional]: Cleanup, removing the provisioned AWS resources. 

```sh 
cd ../frontend
amplify delete
```

## Choose your next adventure:
* [**Backend: Transwraping Amazon ECS container:**](/backend/README.md)Install  the remote video transwrap server.
* [**Create a IVS Channel using a shell script**](/backend/CREATEIVS.md)
* [**Customize the web app and compatibility discussions**](BROWSER.md)
