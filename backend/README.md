# Here's a simplified version of the instructions for running the live streaming contribution app in an Amazon ECS container:

1. To deploy the backend environment, the app uses two containers: a NodeJS web server and FFmpeg. They run on AWS Fargate, a serverless compute engine for containers.

2. In Amazon ECS, you have three important components: 
- Task definition: It's like a blueprint that specifies the Docker images to use and the resources needed for each container.
- Task: It's an instance of a task definition, where the containers are actually running. 
- Service: It launches and maintains a defined number of task instances in your cluster.

## For this app, the service consists of two tasks, each with its own public IP address to receive the video stream via WebSocket.

3. To keep track of each task's public IP, we use the following AWS services: 

- Amazon EventBridge: It's a serverless event bus that simplifies building event-driven applications. We use it to track the start and stop status of our tasks and trigger an AWS Lambda function. 

- AWS Lambda: It's a serverless compute service that lets you run your code without managing servers. We create a Lambda function that updates the public IP of the tasks in an Amazon DynamoDB table when triggered by the EventBridge.

In simpler terms, the app runs in containers on AWS Fargate. Each container has its own configuration and runs tasks. Amazon EventBridge and AWS Lambda work together to track the tasks' status and update their public IP addresses in DynamoDB.

These simplified instructions give an overview of how the live streaming contribution app runs in an Amazon ECS container.


- Amazon DynamoDB: It's a database that offers fast performance and can handle large-scale applications. It's managed by AWS and provides features like security, backups, and caching. In this case, we use DynamoDB to store task metadata, including the public IP addresses of the tasks.

The backend deployment is managed through a shell script. By navigating to the "backend" directory and running the script, it uses AWS CLI commands to build the environment. Run the following commands in the terminal: ```sh
    cd simple-streaming-webapp/backend
    ./install_ivs_backend.sh deploy all
```

### HTTPS considerations: 
The ECS container uses a self-signed certificate for HTTPS. This means your browser may show a warning about it not being a trusted certificate. You can either allow your browser to accept the self-signed certificate, add an Amazon CloudFront distribution to handle HTTPS, or add your own valid certificate to the container.

##  To find the external IP address of your transwrap server, run the following command:

 ```sh
./get_container_domain.sh
```
 This will provide the domain for your server. Open it in your web browser by adding "https://" in front of the domain and accept the self-signed certificate.

Note: These steps are for testing purposes only and you got ssl self sign error.





## For Cleanup  : Cleanup, removing the provisioned AWS resources. 

## For removing the Transwrap proxy server, you can use below script uninstall_ivs_backend.

```sh
./uninstall_ivs_backend.sh clean all
```

## After it completes, you can clean files also

```sh
./uninstall_ivs_backend.sh clean files
```


