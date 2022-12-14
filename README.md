[![CircleCI](https://circleci.com/gh/CtripleU/mlops-project.svg?style=svg)](https://circleci.com/gh/CtripleU/mlops-project)


## Project Overview

In this project, I operationalized a Machine Learning Microservice API. 

The pre-trained, `sklearn` model has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. The data was initially taken from Kaggle - [the data source site](https://www.kaggle.com/c/boston-housing). The Python flask app in `app.py` serves out predictions (inference) about housing prices through API calls. 

### Requirements
- Python 3.7 or 3.8 
- Docker
- Hadolint
- Minikube
- Kubectl
- A Dockerhub account

### Project Steps
- Test Dockerfile using Hadolint
- Complete Dockerfile to containerize application
- Deploy the containerized application and make a prediction
- Improve the logging in the source code
- Upload container to Dockerhub
- Configure Kubernetes and create a Kubernetes cluster
- Run the deployed application in a Kubernetes cluster and make a prediction
- Integrate continuous integration using CircleCI


**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

- Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
- Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone: `python app.py`
2. Run in Docker: `./run_docker.sh`
3. Run in Kubernetes: `./run_kubernetes.sh`

### Kubernetes Steps

- Setup and Configure Docker locally 
- Setup and Configure Kubernetes locally
- Create Flask app in Container
- Run via kubectl `kubectl run mlopsproject --image=$dockerpath`


### Explanation of files in the Repository

| Directory/File| Description  |
| ------------- | ------------- |
| .circleci  | Contains config.yml file for circleci  |
| model_data  | Model data for housing prices  |
| output_txt_files | Folder containing docker and kubernetes log outputs |
| app.py | API endpoint in flask |
| Dockerfile | Dockerfiles for image creation |
| make_predictions.sh | Script to log output predictions from the endpoint |
| Makefile | Makefile for installation of project dependencies and lint |
| requirements.txt | Python dependencies for project |
| run_docker.sh | Script to build the docker file |
| run_kuberbetes.sh | Script to run docker image in kubernetes | 
| upload_docker.sh | Script to upload docker image to Dockerhub | 
