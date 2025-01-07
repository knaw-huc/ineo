
# INEO 

This repository provides the code and configurations to deploy the **INEO stack** using `docker compose`. 

## Overview

The INEO stack is composed of the following components, each hosted in its own repository:

1. **[Indexer](https://github.com/knaw-huc/ineo_indexer)**  
   - Handles adding data to the indexer.  
   - Includes sample data.

2. **[Service](https://github.com/knaw-huc/ineo_service)**  
   - Acts as middleware between the indexer and the frontend.  
   - Contains the Docker file for building its image.

3. **[Frontend](https://github.com/knaw-huc/ineo_frontend)**  
   - The user-facing frontend application.  
   - Contains a Docker file to build its image.

> Each repository contains the necessary Docker configurations for building individual images. Refer to the respective repositories for detailed documentation.

## Deployment

This repository includes `docker-compose` files to simplify deployment of the stack.  

### Compose Files
- **Production Deployment:** Use the `docker-compose.yml` file.  
- **Development Deployment:** Use the `docker-compose-dev.yml` file.  

### Development Tips
- During development, the **frontend** and **service** code can be mounted directly into the containers for real-time updates.  
- The **frontend image** is based on the official `node` image with the application code copied into it. Any changes in the code will reflect immediately in the container.

### Production Notes
1. Ensure **all images** are prebuilt and available in the relevant registry (local or remote, depending on your environment).  
2. Update the image paths and names in the `docker-compose.yml` file as needed.  
3. After updating, use the `docker-compose.yml` file to deploy the production stack.

---

## Notes

- **ALL** images used in the compose files must be built and available in the registry before deployment.  

---
