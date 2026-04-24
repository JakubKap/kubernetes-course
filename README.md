[# DevOps Directive Kubernetes Course

This is the companion repo to: [Complete Kubernetes Course -- From BEGINNER to PRO
](https://www.youtube.com/watch?v=2T86xAtR6Fo)

[![thumbnail](./readme-assets/thumbnail.jpg)](https://www.youtube.com/watch?v=2T86xAtR6Fo)

## Using this repo

Each directory within the repo corresponds to one section of the course. You should fork the repo and follow along with the lessons and use/update/modify the code samples as needed.

There are a number of software tools used throughout the course. Instructions on the best way to set them up can be found in [03-installation-and-setup](03-installation-and-setup/README.md).

## Technologies
[Civo](https://dashboard.civo.com/) is used for hosting K8s cluster on a Cloud.
GKE provided by Google Cloud is used for cluster experience.

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

```devbox list``` will list all available dependencies.

```t civo:06-clean-up``` & ```gcp:09-clean-up``` cleanup infrastructure. It is crucial to clean it, 
because **otherwise there will be charged fee while cluster(s) will be running**.

```kubectx``` - swiching context between clusters

```kubectl explain <RESOURCE_TYPE>``` - explains fields and its description regarding
specific resources. For instance: ```kubectl explain Namespace```

```kubectl get rs``` - showing amount of replicaSets for a pod

## Setting aliases
```alias k=kubectl```
```alias tl='task --list-all'```

[//]: # (```tl``` - alias for t=task l=list-all &#40;listing all tasks&#41; )

Using key from Civo:
    ```civo apikey current <KEY_NAME>```
    I have used ```beginner-to-pro```


## Possible problems
In case of an error:

ERROR: (gcloud.services.enable) FAILED_PRECONDITION: Billing account for project '1011180695086' is not found. Billing must be enabled for activation of service(s) 'compute.googleapis.com,container.googleapis.com,secretmanager.googleapis.com,artifactregistry.googleapis.com,containerregistry.googleapis.com,dns.googleapis.com' to proceed.
Help Token: AVnrbflP19n5Wy9MfQZ5vux1HVlVuWM_B4v8fMvfVZHx4Q1pt_mQ-d1yjhpWJzaKckLFWFsLqw83iDmRjImcklvHTFVtvrfn0KtgvxpCcb3FVtgO
- '@type': type.googleapis.com/google.rpc.PreconditionFailure
  violations:
    - subject: ?error_code=390001&project=1011180695086&services=compute.googleapis.com&services=container.googleapis.com&services=secretmanager.googleapis.com&services=artifactregistry.googleapis.com&services=containerregistry.googleapis.com&services=dns.googleapis.com
      type: googleapis.com/billing-enabled
- '@type': type.googleapis.com/google.rpc.ErrorInfo
  domain: serviceusage.googleapis.com/billing-enabled
  metadata:
  project: '1011180695086'
  services: compute.googleapis.com,container.googleapis.com,secretmanager.googleapis.com,artifactregistry.googleapis.com,containerregistry.googleapis.com,dns.googleapis.com
  reason: UREQ_PROJECT_BILLING_NOT_FOUND
  task: Failed to run task "gcp:02-enable-apis": exit status 1

- Please run gcloud billing projects link 1011180695086 --billing-account=012269-BAED37-84FA49


## Screenshots
**GKE cluster:**
![GKE cluster](./readme-assets/gke_cluster.png)

Civo cluster:**
![Civo cluster](./readme-assets/civo_cluster.png)