# Google Cloud Deployment

This is a repository to show the deployment of a docker image. Here the docker image of a web api is made. The image is built and then pushed into google container registry. The datetime of the image creating is given as the tag of the docker image. The image is then deployed into google kubernetes engine.

### Things to Add

The below details should be added as variables in the worflow.yml file.

    PROJECT_ID: your_project_id
    GCR_LOCATION: asia.gcr.io
    GKE_CLUSTER: your_cluster_name
    GKE_ZONE: asia-south1-a
    DEPLOYMENT_NAME:  your_deployment_name
    IMAGE: your_docker_image_name


### Github Secret

For authentication with google cloud, you need a service account with the necessary permissions. For pushing and deployment, you need permissions like storage admin and kubernetes engine admin. Make a key for the service account and save it in a safe location. Then make a github secrets and name it "SERVICE_ACCOUNT_KEY" and copy paste service key contents into the secret.

### Deployment Configuration Files

Use kustomization.yml to add service and deployment details. The service.yml file contains the google kubernetes service details and the deployment.yml contains the various details regarding the deployment. Change the values according to need. 