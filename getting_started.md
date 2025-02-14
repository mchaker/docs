# Getting started

## installing the openlab command line interface

## uploading and downloading files 

## running a service 

## running a token-gated service

## contributing a new service
OpenLab is currently in version 0.1 and only supports running nexftflow containers on our centralized compute infrastructure build on AWS. We are currently preparing the release of the complete backend infrastructure to allow more nodes to join the network. 

In order to add a tool to the openlab exchange, you have to go through multiple steps. We start with the basics because it is important to us that community members from all experience-levels know how to contribute tools to the ecosystem.

0. Make sure your tool can be launched from the command line and does not need any manual change to variables within your scripts to run. You can define variables for [python scripts](https://www.tutorialspoint.com/python/python_command_line_arguments.htm) and [R scripts](https://www.r-bloggers.com/2015/09/passing-arguments-to-an-r-script-from-command-lines/) easily from the command line.
1. Make sure your tool is on github, ideally in a *public* repository (this will make it easier for community members to help you).
2. Dockerize your tool. [Docker](https://www.docker.com/) is a popular container framework that enables high reproducibility for running code. You can think of it as a lightweight virtual machine that makes sharing code very easy (no more missing packages/libraries!). The key element of every docker container is the dockerfile. Tutorials on how to dockerize [python](https://medium.com/swlh/dockerize-your-python-command-line-program-6a273f5c5544) and [R](https://www.r-bloggers.com/2019/02/running-your-r-script-in-docker/) command line tools exist. It is good practice to add docker-related files to your project's git reposority. 
3. Wrap your tool in an [NF-core workflow](https://nf-co.re/tools/#creating-a-new-pipeline). After creating a container that enables your tool to run in various contexts, it is important to also share the instructions that you pass to the container in a standardized way. This is where [nextflow](https://www.nextflow.io/), and its core library, [NF-core](https://nf-co.re/pipelines) come in. At the end of this step you should have a nextflow template workflow that points to your dockerfile and add it to the repository.
