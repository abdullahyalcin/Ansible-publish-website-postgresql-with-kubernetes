# Project-207 : Web Page Application (Postgresql-Nodejs-React) deployed on EC2's with Ansible and Docker

## Description

The Clarusway Web-Page Application aims to deploy web-page written Nodejs and React Frameworks on AWS Cloud Infrastructure using Ansible.This app's will be launched on local. Web-page has 3 main components which are postgresql, nodejs, and react. Each component is serving in Docker container. Postgresql is serving as Database of web-page. Nodejs controls backend part of web-side and react controls frontend side of web-page.
## Problem Statement

![Project_007](ansible.png)

- Web-page allows users to collect their infos. Registration data should be kept in separate PostgreSQL database located in local. Nodejs framework controls backend and serves on port 5000, it is als connected to the PostgreSQL database on port 5432. React framework controls the frontend and it is also connected to the Nodejs server on port 5000. React server broadcasts web-page on port 3000. 

- The Web Application will be deployed using Nodejs and React framework.

- The Web Application should be accessible via web browser from anywhere on port 3000.

- Postgresql, Nodejs and React parts has to be placed in docker container. 

In the architecture, you can configure your architecture with these conditions,

  - All process has to be controlled into the `control Node` (or you can use minikube)

  - Dynamic inventory has to be used for inventory file.
  
  - Docker should be installed in all worker nodes using ansible.

  - `todo-app-pern` file should be pulled from Github Repo at the beginning.

  - For PostgreSQL worker node

    - PostgreSQL files (Dockerfile and init.sql) should be sent into it from control node using ansible

    - Docker image should be created for PostgreSQL container and init.sql file should be placed under necessary folder.

    - Create PostgreSQL container. Do not forget to set password as environmental variable. This password has to be protected with ansible vault.

    - To keep database's data, volume has to be created with docker container and necessary file(s) should be kept under this file.

  - For Nodejs worker node

    - Please make sure to correct or create `.env` file under `server` folder based on PostgreSQL environmental variables
    
    - Nodejs's `server` folder should be sent into it from control node using ansible. This file will use for docker image. You don't need any extra file for creating Nodejs image.

    - Docker image should be built for Nodejs container

    - Create Nodejs container and publish it on port 5000

  - For React worker node

    - Please make sure to correct `.env` file under `client` folder based on Nodejs environmental variables 
    
    - React's `client` folder should be sent into it from control node using ansible. This file will be used for docker image. You don't need any extra file for creating react image.

    - Docker image should be created for React container

    - Create React container and publish it on port 3000

  - Last Step 

## Expected Outcome

![Todo Web Page](./todo_web.png)

