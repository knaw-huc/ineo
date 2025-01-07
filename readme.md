# INEO 

This repository contains the code to deploy the INEO stack using `docker compose`. 
There are three other repositories that are used in this stack:
- [indexer](https://github.com/knaw-huc/ineo_indexer) contains the code to add data into indexer and its sample data. 
- [service](https://github.com/knaw-huc/ineo_service) contains the middleware in between the indexer and the front end.
- [frontend](https://github.com/knaw-huc/ineo_frontend) contains the frontend code.

They contain the docker file to build individual images if needed. Please refer to their respective repositories for more information.

Once the images are built, the compose file in this repository can be used to deploy the stack.
- For production, please use `docker-compose.yml` file.
- For development, please use `docker-compose-dev.yml` file.

During development, the front end code and service code can be mounted to the container to see the changes in real time. 
And the frontend image is just the official `node` image with the code copied into it. 
So, the changes in the code will be reflected in the container.

When publishing the images for production, ALL the images should be built and available in the registry. 
Then the path and name of the image can be updated in compose file can be used to deploy the stack.

## NOTES:
- **ALL** the images used in the compose files should be prebuilt and available in local or remote registry depends on the environment.
