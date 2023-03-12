[![Sbaiden94](https://circleci.com/gh/Sbaiden94/udacity-project-4.svg?style=svg)](https://app.circleci.com/pipelines/github/Sbaiden94/udacity-project-4)

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

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
1. Download and install Docker for your operating system by following the official Docker installation guide.
2. Once Docker is installed, verify that it is running by running the following command in your terminal:
```bash
docker --version
```
3. Optionally, create a Docker Hub account to store and share Docker images.

* Setup and Configure Kubernetes locally
1. Install Minikube
2. Start the Kubernetes cluster by running minikube start.
3. Verify that the cluster is running by running `kubectl cluster-info`

* Create Flask app in Container
1. Create a new directory for your Flask app and navigate to it in your terminal.
2. Create a new file called app.py and add code to it.
3. Create a new file called Dockerfile and add code to it.
4. Create a requirements.txt file.
5. Build the Docker image by runningdocker build --tag=microproject .

* Run via kubectl
1. Verify that the Docker image was created by running docker images.
2. Deploy the Docker container to the Kubernetes cluster by running kubectl run microproject --image=sammyb94/mircroproject:v1.0.0 --port=80 --labels app=microproject
