[![CircleCI](https://circleci.com/gh/pckhib/devops-ml-microservice.svg?style=svg)](https://circleci.com/gh/pckhib/devops-ml-microservice)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API.

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:

- Test your project code using linting
- Complete a Dockerfile to containerize this application
- Deploy your containerized application using Docker and make a prediction
- Improve the log statements in the source code for this application
- Configure Kubernetes and create a Kubernetes cluster
- Deploy a container using Kubernetes and make a prediction
- Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

### Files Overview

- `.circleci`: Configuration directory for CircleCI.
- `app.py`: Python flask application that returns predictions about housing prices.
- `Dockerfile`: Dockerfile to build the application image.
- `make_prediction.sh`: Sends a request to the flask application and receives a prediction.
- `Makefile`: Includes instructions on environment setup and lint tests.
- `requirements.txt`: Contains a list of all requirements that will be installed using `pip`.
- `run_docker.sh`: Script to create a Docker image and run the container.
- `run_kubernetes.sh`: Script to run the application as a Kubernetes cluster.
- `upload_docker.sh`: Script to upload the Docker image to Docker HUB.

---

## Setup the Environment

- Create a virtualenv and activate it (`make setup`)
- Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone: `python app.py`
2. Run in Docker: `./run_docker.sh`
3. Run in Kubernetes: `./run_kubernetes.sh`

### Make Prediction

Once the application is running, you can send a request to it by running `./make_prediction.sh`.

### Upload Docker image

To upload the Docker image created based on the `Dockerfile`, run `./upload_docker.sh`.

### Lint `app.py` and `Dockerfile`

Lint the `Dockerfile` using **hadolint** and the application using **pylint**.

- `make lint`
