​		Google Assoicate Cloud Engineering

### Table of Content

1. [Compute](#Compute)

2. [Storage](#Storage)

3. [Operations](#Operations)

4. [Tools](#Tools)

5. [BigData](#BigData)

6. [Cloud Shell](#shell)

7. [Resoure Hierarcy](#ResourceHierarcy)

8. [Identity and Access Management (IAM)](#iam)

9. [Instance Group](#instancegroup)

10. [Kubernetes](#Kubernetes)

11. [Cloud Function](#cloudfunction)

12. [What to know for Google Assoicate Cloud Engineering certification ](#knowabout)

    

## Compute Service <a name="Compute"></a> 

* **App Engine :** 
  * Platform-as-service
  * Minimal Configuration requirements
* **Compute Engine:**
  * Maximum control and comnfigurability
  * Shiedlded VMS  & Sole Tenancy
* **Kubernetes Engine:**
  * Managed cluster
  * Containerized applications
* **Cloud Functions:**
  * Responfing to events in GCP

## Storage <a name="Storage"></a>

Classification:

* NOSQL DB
* Relational DB
* File System
* Object System

Storage Services:

* Bigtable : Column, NOSQL DB
* Datastore: Document, NOSQL DB
* FIrestore: Document, NOSQL DB
* SQL: Relational DB
* Spanner: Relational DB
* Storage: Stores any sort of data, Unstructured data

## Operations <a name="Operations"></a>

* Monitoring
* Debugging
* Trace
* Logging

## Tools <a name="Tools"></a>

* Cloud Build
* Cloud Tasks
* Container Registry
* Deployment Manager

## BitData <a name="BitData"></a>

* Dataproc
* Dataflow
* BigQuery
* Pub/Sub

## Cloud Shell <a name="shell"></a>

* gcloud
* gsutil : for cloud storage (object storage system)
* bq: command line utility for BigQuery
* cbt: command line utility for big table

## Resource Hierarcy <a name="ResourceHierarcy"></a>

Provide attach points and inheritance for access control and organization policie

**Components**

* Organization 

* Folders

* projects

* Resources (vms, buckets, sql, etc)

  ![Resources-hirercy](./images/Resources-hirercy.png)

## Identity and Access Management (IAM) <a name="iam"></a> 

Represents a user or entity that has privileges to perform actions in GCP.

**4 Types:**

* **Google Account:** Represents person(developer, admin) associated with email

* **Cloud Identity or GSuit Account:** Gsuit is a member of organisation, Cloud Identity is like GSuit domain but without access to Gsuit service

* **Google Group**: Collection of identities. useful for assigning roles to multiple users.

* **Service Account** : Account associated with an application or instance rather than a user, can create as many as needed.

  

### Access Control Concepts

* Resources
* Permissions
* Roles
  * Predefined(created by google)
  * Custom
  * Primitive

### Policies

Collection of statements that define whihc users have access to some resources

Attcahed to a resource

Roles attached to identities, Policies attached to resources, Policies are hierarchy.

## Instance Group <a name="instancegroup"></a>

Collection of instances that are managed as a single entity

2 Types

* Managed instance group
* Unmanaged instance group

Cool Down period is time allowed for instances tp finish initializing

Stabilization period is time autoscaler uses to calculate MIGs recommended target size

Avoids thrashing, i.e. rapidly adding and removing instances

![MIG](./images/MIG.png)

![UMIG](./images/UMIG.png)

## Kubernetes

Managed service, Provides Kubernetes Clusters.

Kubernetes runs containers on cluster of virtual or physical machines.

Known as container orchestration

**Features:**

* Load balancing of workloads
* Node pools to segment nodes within a cluster
* Automatic scaling and updating
* Autohealing
* Stackdriver monitoring

**Process Objects:**

* Pods
* Deployments
* Services

**Storage Objects**

* Persistent Volumes
* Persistent Volume Claims

**kubectl**

## App Engine

* App Engine Standard 
* App Engine Flexible

## Cloud Function

* Serverless compute service
* Execute code in response to events based on triggers
* Availanle for events in:
  * Cloud storgare
  * Cloud Pub/Sub
  * HTTP
  * Firebase
  * Stackdriver Logging

### Cloud Function components

* Events
* Trigger
* Functions

## What to know for Google Assoicate Cloud Engineering certification <a name="knowabout"></a>

![Appengine](./images/Appengine.png)

![Computeengine](./images/Computeengine.png)

![Kubengine](./images/Kubengine.png)

![functions](./images/functions.png)