[![CircleCI](https://circleci.com/gh/svk100/Udacity-DevOps-Project4.svg?style=svg)](https://circleci.com/gh/svk100/Udacity-DevOps-Project4/tree/main)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

Files

* /.circleci/config.yml: CircleCI configuration file
* /model_data : Housing model data from [here] (https://www.kaggle.com/c/boston-housing)
* /output_txt_files
*  docker_out.txt: Output of run_docker.sh
*  kubernetes_out.txt: Output of run_kubernetes.sh and make_prediction.sh
* Dockerfile : Docker config for building the pythn app image
* Makefile : Instructions on environment setup and lint tests
* Readme.md: This file
* app.py : The main python code that makes predictions
* make_prediction.sh : Used to test the app by sending a request to localhost:8000
* requirements.txt : List of dependencies for the python app
* run_docker.sh : Script to create docker image
* run_kubernetes.sh : Script to create kubernetes pod
* upload_docker.sh : Script to push docker image to docker hub

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
deactivate to exit the virtual environment
```
* Run `make install` to install the necessary dependencies
* IF higher verson of python is used you may get issues installing dependencies, so use python 3.7

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally by installing Docker Desktop in case of Windows
* Setup and Configure Kubernetes locally by installing Docker Desktop in case of Windows and enabling Kubernetes service
* Create Flask app in Container  by running run_docker.sh
* Run via kubectl by running run_kubernetes.sh

Note: Durng testig you may end up with several docker containers, use the command below to delete them all
* USE CAUTION RUNNING THE COMMAND BELOW, IT DELETES ALL CONTAINERS
* docker rm -f $(docker ps -a -q)
