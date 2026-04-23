# DevOps Directive Kubernetes Course

This is the companion repo to: [Complete Kubernetes Course -- From BEGINNER to PRO
](https://www.youtube.com/watch?v=2T86xAtR6Fo)

[![thumbnail](./readme-assets/thumbnail.jpg)](https://www.youtube.com/watch?v=2T86xAtR6Fo)

## Using this repo

Each directory within the repo corresponds to one section of the course. You should fork the repo and follow along with the lessons and use/update/modify the code samples as needed.

There are a number of software tools used throughout the course. Instructions on the best way to set them up can be found in [03-installation-and-setup](03-installation-and-setup/README.md).

## Technologies
[Civo](https://dashboard.civo.com/) is used for hosting K8s cluster on a Cloud.

## Using devbox on Windows
From root of a project, please run:
* ```wsl -d Ubuntu```.
* ```devbox shell```.

During first time when those commands will be executed - whole process might take some time.
However, later it will last fewer amount of time due to caching.

Devbox is used for ensuring that while following tutorial same dependencies as an author will be used.
Those dependencies are defined within ./devbox.json.

```devbox shell``` will list all installed dependencies by Devbox.



## Useful commands
Taskfile.yaml files specifies very commonly used tasks across the project 
(associated with deploying and managing K8s clusters).

[//]: # (```tl``` - alias for t=task l=list-all &#40;listing all tasks&#41; )

Using key from Civo:
    ```civo apikey current <KEY_NAME>```
    I have used ```beginner-to-pro```