QUESTION 1
You need to start a set of virtual machines to run year-end processing in a new GCP project. How can you enable the Compute API in the fewest number of steps?
A. Open Cloud Shell, configure authentication, run `gcloud services enable compute.googleapis.com`
B. Do nothing. It is enabled by default.
C. Open Cloud Shell, configure authentication, select the “defaults” project, run `gcloud enable compute service`
D. Navigate to the Compute section of the console.
E. Open Cloud Shell, run `gcloud services enable compute`

EXPLANATION:
There is no such thing as a “defaults” project. Each API must be enabled before it can be used. Some APIs are enabled by default, but GCE is not. Navigating to the Compute Engine of the console automatically enables the GCE API. You do not have to configure authentication to be able to use Cloud Shell, but regardless, using Cloud Shell would take more steps than simply navigating to the GCE console. [D]

QUESTION 3
What is the easiest way to delete a project?
A. There is no general way to delete a project. Projects are immutable.
B. Simply ignore the monthly project renewal email and the project will automatically be deleted in 15 days.
C. Run `gcloud projects delete oldprojid`
D. Open a support request to delete the project and wait 2-5 days for them to complete the task.
E. In the monthly project budget email, click the link to “Delete Project and Unsubscribe”.

EXPLANATION:
You do not need to involve Support to delete a project; you just do that, yourself. Project budgets do not include any way to delete the project. If you rack up charges, you're liable for them even if you delete the project or it gets suspended. [C]

QUESTION 6
You already installed and configured `gcloud` for use on your work computer (not Cloud Shell). What do you need to so you can also use `gsutil` and `bq`?
A. Run `gcloud config export storage` and `gcloud config export query`.
B. Run `gcloud config export gsutil` and `gcloud config export bq`.
C. Run `gsutil config import gcloud` and `bq config import gcloud`.
D. Configure those tools independently.
E. Nothing

EXPLANATION:
These tools all share their configuration, which is managed by gcloud. [E]

QUESTION 8
Which of the following are Google-recommended practices for creating new projects?
A. Use projects to limit blast radius.
B. Create a project for each user of your system.
C. Create separate projects for systems owned by different departments in your organization.
D. Add more systems into a project until you hit a quota limit, then make a new one.
E. New projects should only be created when your organization can handle at least one hour of downtime.
F. Because quotas are shared across all projects, it doesn't matter how many you make.
G. Create a new project each time you deploy your system.
H. Create a project for each environment for your system--such as Dev, QA, and Prod.

EXPLANATION:
Creating new projects does not involve any downtime. Projects can be shared between all persons working with them; they do not have to be individual, and usually aren't. The system(s) in one project normally get deployed multiple times and serve many users. It's a good idea to use projects to separate different systems and environments from each other, partly for organization and partly to prevent them from interacting badly with each other. [A,C,H]

QUESTION 11
Which of the following are true about a newly-created project?
A. Since BigQuery is enabled by default, charges will immediately accrue until you shut it off
B. The free tier lasts one year
C. It cannot be used until the organization owner has completed the approval form
D. None of the other statements is true
E. The free tier lasts 30 days

EXPLANATION:
Projects are separate from billing accounts and their free tier. BigQuery is enabled by default, but it starts empty and has no charge until you use it. There is no approval form for new projects. [D]

QUESTION 14
You have previously installed the Google Cloud SDK on your work laptop and configured it. You now run the command `gcloud compute instances create newvm` but it does not prompt you to specify a zone. Which of the following could explain this?
A. Your gcloud configuration includes a value for compute/zone
B. Your gcloud configuration includes a value for compute/region
C. Only one of the other options is correct.
D. In Cloud Shell, you previously set a zone as the default one GCE should use.
E. The project configured for gcloud is located in a particular zone.

EXPLANATION:
Projects are global and and are not “located” in any region or zone. The gcloud family of tools save their default zone information locally where they’re installed, and these are separate from console settings. The gcloud tool _can_ pull the values set in the console if you rerun `gcloud init`, but gcloud does not push its configuration to the place the console uses. [A,C]

QUESTION 24
When should new projects be created?
A. Whenever the new project is needed
B. On the weekends, to minimize the effects of downtime
C. When the new project owner is available enter their credentials on your computer
D. At the end of the billing cycle of the linked billing account
E. On weekdays so that Google Support personnel can respond to your queries

EXPLANATION:
Project creation does not involve any downtime. Google Support does not need to be involved in creating new projects. You can create a project and transfer ownership of it, if you need. Billing accounts can be linked and unlinked from projects and do not have to sync up with project lifetimes. [A]

QUESTION 25
You need to store some recently recorded customer focus sessions into a new GCP project. How can you enable the GCS API in the fewest number of steps?
A. Open Cloud Shell, configure authentication, select the “defaults” project, run `gcloud enable storage service`
B. Open Cloud Shell, configure authentication, run `gcloud services enable storage.googleapis.com`
C. Do nothing. It is enabled by default.
D. Open Cloud Shell, run `gcloud services enable storage`
E. Navigate to the Storage section of the console.

EXPLANATION:
There is no such thing as a “defaults” project. Each API must be enabled before it can be used. Some APIs are enabled by default, and that includes GCS. You do not have to configure authentication to be able to use Cloud Shell, but regardless, using Cloud Shell would take more steps than doing nothing. :-) [C]

QUESTION 31
In Cloud Shell, you run the command `gcloud compute instances list`, and the response that you see is `HTTPError 403: Access Not Configured.`. What is a likely explanation for this error message?
A. The startup script for this Cloud Shell instance has not yet finished running.
B. The GCE API has not yet been enabled for this Cloud Shell instance.
C. Your user account does not have read access to any of the currently running instances.
D. This Cloud shell instance does not have read access to any of the currently running instances.
E. The GCE API has not yet been enabled for this project.
F. The GCE API has not yet been enabled for this account.

EXPLANATION:
APIs must be enabled at the project level, and 403 can indicate that that has not yet been done. [E]

QUESTION 41
Google has just released a new XYZ service and you would like to try it out in your pre-existing skunkworks project. How can you enable the XYZ API in the fewest number of steps?
A. Open Cloud Shell, run `gcloud services enable xyz`
B. Open Cloud Shell, run `gcloud services enable xyz.googleapis.com`
C. Since you have Gold-level support on this project, phone support to enable XYZ
D. Open Cloud Shell, configure authentication, run `gcloud services enable xyz.googleapis.com`
E. Since you have Silver-level support on your linked billing account, email support to enable XYZ
F. Open Cloud Shell, configure authentication, select the “defaults” project, run `gcloud enable xyz service`
G. Do nothing. It is enabled by default.

EXPLANATION:
Google does not generally enable new services by default for existing projects. Cloud Shell does not require you to configure authentication. GCP Support does not get involved with things like enabling APIs for you; that's something you simply do for yourself. The API URL in the gcloud command to enable it includes `googleapis.com`. [B]

QUESTION 2
You need to view both request and application logs for your Python-based App Engine app. Which of the following options would be best?
A. Use the built-in support to view request logs in the App Engine console and install the Stackdriver agent to get app logs to Stackdriver.
B. Use the built-in support to get both request and app logs to Stackdriver.
C. Install the Stackdriver agent to get request logs to Stackdriver; use the Stackdriver Logging API to send app logs directly to Stackdriver.
D. None of the other options is appropriate.

EXPLANATION:
Google App Engine natively connects to Stackdriver and sends both request logs and any application logs you give it (via the GAE SDK). [B]

QUESTION 7
You are designing the logging structure for a non-containerized Java application that will run on GAE. Which of the following options is recommended and will use the least number of steps to enable your developers to later access and search logs?
A. Have the developers write log lines to stdout and stderr
B. Have the developers write log lines to a file named application.log, install the Stackdriver agent on the VMs, configure the Stackdriver agent to monitor and push application.log
C. Have the developers write logs using the App Engine Java SDK
D. Have the developers write log lines to a file named stackdriver.log, install and run the Stackdriver agent beside the application
E. Have the developers write log lines to stdout and stderr, install and run the Stackdriver agent beside the application
F. Have the developers write log lines to a file named stackdriver.log

EXPLANATION:
In App Engine Standard, you should log using the App Engine SDK and the connection to Stackdriver (i.e. agent installation and configuration) is handled automatically for you. [C]

QUESTION 12
You are designing the logging structure for a containerized Java application that will run on GAE Flex. Which of the following options is recommended and will use the least number of steps to enable your developers to later access and search logs?
A. Have the developers write log lines to a file named application.log, install the Stackdriver agent on the VMs, configure the Stackdriver agent to monitor and push application.log
B. Have the developers write log lines to a file named stackdriver.log, install and run the Stackdriver agent beside the application
C. Have the developers write log lines to stdout and stderr, install and run the Stackdriver agent beside the application
D. Have the developers write log lines to a file named stackdriver.log
E. Have the developers write logs using the App Engine Java SDK
F. Have the developers write log lines to stdout and stderr

EXPLANATION:
In App Engine Flex the connection to Stackdriver (i.e. agent installation and configuration) is handled automatically for you. In GAE Flex, you _could_ write logs using the App Engine SDK--and that would work--but it’s best practice for containers to log to stdout and stderr, instead: “Containers offer an easy and standardized way to handle logs because you can write them to stdout and stderr. Docker captures these log lines and allows you to access them by using the docker logs command. As an application developer, you don't need to implement advanced logging mechanisms. Use the native logging mechanisms instead.” [F]

QUESTION 23
You run the command `kubectl describe pod mypodname` in Cloud Shell. What should you expect to see?
A. A “command not found” error
B. An authentication failure
C. An authorization failure
D. A syntax error
E. A configuration error
F. Information about the named pod

EXPLANATION:
This is a valid command and Cloud Shell will automatically configure kubectl with the required authentication information to allow you to interact with the GKE cluster through it. [F]

QUESTION 32
You have a GKE cluster that has fluctuating load over the course of each day and you would like to reduce costs. What should you do?
A. Run `gcloud container clusters resize mycluster --size=auto` .
B. In the GCE console, add the nodes to an unmanaged instance group.
C. In the GKE console, edit the cluster and enable cluster autoscaling.
D. Write a script to recreate the cluster as demand changes.
E. In the GCE console, add the nodes to a managed instance group.

EXPLANATION:
Clusters are editable, not immutable, and should not be recreated because of changes in demand. You cannot manage GKE nodes with your own instance groups--and you can’t migrate nodes into a managed instance group, anyway. You cannot enable cluster autoscaling with the `resize` command, but you can turn that option on in the console or using the command `gcloud container clusters update CLUSTER_NAME --enable-autoscaling`. [C]

QUESTION 38
You have a GKE cluster that currently has six nodes but has lots of idle capacity. What should you do?
A. Nothing. GKE is always fully managed and will scale down by default.
B. Clusters are immutable so simply create a new cluster for the smaller workload.
C. In the GCE console, delete one of the nodes.
D. In the GCE console, terminate one of the nodes.
E. Run `gcloud container clusters resize mycluster --size=5` .

EXPLANATION:
Clusters are editable, not immutable, and should not be recreated because of changes in demand. Cluster autoscaling is an optional setting. You do not manage nodes via GCE, directly--you always manage them through GKE, even though you can see them via GCE. [E]

QUESTION 39
You have a GKE cluster that currently has six nodes but will soon run out of capacity. What should you do?
A. Clusters are immutable so simply create a new cluster for the larger workload.
B. Run `gcloud compute instances create anyname --gke`
C. In the GKE console, edit the cluster and specify the new desired size.
D. Run `gcloud compute instances create gke-7`
E. Nothing. GKE is always fully managed and will scale up by default.

EXPLANATION:
Clusters are editable, not immutable, and should not be recreated because of changes in demand. Cluster autoscaling is an optional setting. You do not manage nodes via GCE, directly--you always manage them through GKE, even though you can see them via GCE. [C]

QUESTION 40
You are designing the logging structure for a containerized Java application that will run on GKE. Which of the following options is recommended and will use the least number of steps to enable your developers to later access and search logs?
A. Have the developers write log lines to a file named application.log, install the Stackdriver agent on the VMs, configure the Stackdriver agent to monitor and push application.log
B. Have the developers write log lines to stdout and stderr
C. Have the developers write log lines to a file named stackdriver.log
D. Have the developers write log lines to stdout and stderr, install and run the Stackdriver agent beside the application
E. Have the developers write logs using the App Engine Java SDK
F. Have the developers write log lines to a file named stackdriver.log, install and run the Stackdriver agent beside the application

EXPLANATION:
The App Engine SDKs only work for apps running on App Engine. Stackdriver does not automatically send files named stackdriver.log . “Stackdriver Logging is enabled by default when you create a new cluster using the gcloud command-line tool or Google Cloud Platform Console.” Logging to stdout and stderr on GKE _is_ the recommended way to log: “Containers offer an easy and standardized way to handle logs because you can write them to stdout and stderr. Docker captures these log lines and allows you to access them by using the docker logs command. As an application developer, you don't need to implement advanced logging mechanisms. Use the native logging mechanisms instead.” [B]

QUESTION 45
You have a StatefulSet and a DaemonSet deployed in your GKE cluster which currently has seven nodes. What will happen if you scale the cluster down to six nodes?
A. Clients connecting to any Services will experience a momentary service interruption.
B. All pods that were running on the terminated node will be restarted on other nodes.
C. The number of pods for the DaemonSet will shrink.
D. The size of any deployments will be decreased by one.
E. You will be unable to access the data from one StatefulSet pod.

EXPLANATION:
A DaemonSet runs one pod per GKE node. [C]

QUESTION 50
You are designing the logging structure for a non-containerized Java application that will run on GCE. Which of the following options is recommended and will use the least number of steps to enable your developers to later access and search logs?
A. Have the developers write log lines to stdout and stderr, install and run the Stackdriver agent beside the application
B. Have the developers write log lines to a file named application.log, install the Stackdriver agent on the VMs, configure the Stackdriver agent to monitor and push application.log
C. Have the developers write log lines to a file named stackdriver.log
D. Have the developers write log lines to stdout and stderr
E. Have the developers write log lines to a file named stackdriver.log, install and run the Stackdriver agent beside the application
F. Have the developers write logs using the App Engine Java SDK

EXPLANATION:
The App Engine SDKs only work for apps running on App Engine. Stackdriver does not automatically send files named stackdriver.log . Stackdriver is not installed by default on GCE. Logging to stdout and stderr on GCE is not the recommended way to get logs to Stackdriver; configuring a custom log file location is. [B]

QUESTION 4
You navigate to the Activity Log for a project containing a GKE cluster you created. If you filter the Resource Type to “GCE VM Instance”, which of the following will you see?
A. You will see lines of the form “DEFAULT_GCE_SERVICE_ACCOUNT created GKE_NODE_INSTANCE_NAME”
B. You will see lines of the form “YOUR_EMAIL created GKE_NODE_INSTANCE_NAME”
C. You will not see any lines because the instances are owned by GKE.
D. None of the other options is correct.

EXPLANATION:
Log lines for GKE node creation will show up in the activity log. But the creation is not attached to your account--you only created the GKE cluster. Neither is it the GCE default service account that creates such instances--that account is meant to be used by applications running _on_ GCE instances, not GKE management like this. Instead, log lines will use the passive voice “GKE_NODE_INSTANCE_NAME was created” to indicate that this was an automatic action taken by GCP because you had previously configured/requested it do that. [C]

You have a GCE instance using the default service account and access scopes. What will happen if an attacker compromises this instance and runs their own program on it?
A. If they use the credentials outside of GCP, they will have the same access as the GCE instance as long as they spoof that machine’s MAC address.
B. If they use the credentials outside of GCP, they will be unable to access any GCP services.
C. They will be unable to access any credentials because of the “Metadata-Flavor: Google” protection.
D. If they use the credentials outside of GCP, they will be able to access everything allowed by the access scopes.
E. If they use the credentials outside of GCP, they will be able to access everything allowed by the service account.
F. None of the other options is correct.

EXPLANATION:
Requiring the “Metadata-Flavor: Google” header protects against a different type of attack than the one described in this question, so it will not help in this case. The access token will be available to the attacker’s program and it will work the same way from outside of GCP as it does from within it. [F]

QUESTION 9
Which of the following roles has the highest level of access?
A. Project Owner
B. Compute Administrator
C. Project Editor
D. Controller
E. Organization Superuser
F. Organization Auditor

EXPLANATION:
There are no such roles as Organization Superuser, Organization Auditor, nor Controller. The Project Owner has all of the capabilities of the other two (Project Editor and Compute Administrator), and more. (There is, however, a “Super Admin” role for an organization that can control everything.) [A]

How should you enable a GCE instance to read files from a bucket in the same project?
A. Log into Cloud Shell and run `gcloud services enable storage.googleapis.com`
B. When launching the instance, remove the default service account so it falls back to project-level access
C. Do not change the default service account setup and attachment
D. Log onto the instance and run `gcloud services enable storage.googleapis.com`
E. Grant bucket read access to the default compute service account
F. Only one of the other options is correct

EXPLANATION:
By default, both the default service account and te default scopes can read from GCS buckets in the same project, so you should just leave those alone and it will work. [C,F]

QUESTION 22
You are working together with a contractor from the Acme company and you need to allow GCE instances running in one of Acme’s GCP projects to write to a Cloud Pub/Sub topic you own. Which of the following pieces of information are enough to let you enable that access?
A. The Acme GCP project’s project ID
B. The email address of the Acme project service account
C. The Acme GCP project’s project number
D. The Acme GCP project’s name
E. The email address of the Acme contractor

EXPLANATION:
You need to grant access to the service account being used by Acme’s GCE instances, not the contractor, so you don’t care about the contractor’s email address. If you are given the service account email address, you’re done; that’s enough. If you need to use the pattern to construct the email address, you’ll need to know the Project Number (not its ID, unlike for App Engine!) to construct the email address used by the default GCE service account: `PROJECT_NUMBER-compute@developer.gserviceaccount.com` . If Acme wants to use a different service account than the default one, they’d need to give you more than is listed in the response options--both the Project ID (not its number, this time!) and also the name they gave to the service account: SERVICE_ACCOUNT_NAME@PROJECT_ID.iam.gserviceaccount.com [B,C]

QUESTION 30
You are working together with a contractor from the Acme company and you need to allow App Engine running in one of Acme’s GCP projects to write to a Cloud Pub/Sub topic you own. Which of the following pieces of information are enough to let you enable that access?
A. The email address of the Acme contractor
B. The Acme GCP project’s project number
C. The Acme GCP project’s name
D. The Acme GCP project’s project ID
E. The email address of the Acme project service account

EXPLANATION:
You need to grant access to the service account being used by Acme’s App Engine app, not the contractor, so you don’t care about the contractor’s email address. If you are given the service account email address, you’re done; that’s enough. If you need to use the pattern to construct the email address, you’ll need to know the Project ID (not its number, unlike for GCE!) to construct the email address used by the default App Engine service account: `PROJECT_ID@appspot.gserviceaccount.com` . [D,E]

QUESTION 36
You are planning out your usage of GCP. Which of the following things do you need to consider about Service Accounts?
A. To use service accounts, you must enable the Service Account API.
B. The default service account is restricted in what it can do by the default access scopes.
C. Access scopes are related to service APIs and not service accounts.
D. None of the other statements is true.
E. The default access scopes allow full access to all services.

EXPLANATION:
The scopes that restrict what can be done through a service account are somewhat limited, by default. [B]

QUESTION 43
You are designing the object security structure for sensitive customer information. Which of the following should you be sure to include in your planning?
A. Hash and salt all data, to limit the blast radius of any potential breach.
B. Use both ACLs and roles, to achieve defense in depth.
C. Assign only limited access, to achieve least privilege.
D. Randomize object names, to support security through obscurity.
E. None of the other options is appropriate.
F. Ensure there is a honeypot, to support penetration testing.

EXPLANATION:
Least privilege is a paramount concern for data security, and you definitely do want to restrict access as much as possible to support this. Hashing and salting _passwords_ is important, but if you hash information you need to view (not just compare), then hashing will make it unusable. ACLs and roles can both be used, but they will not create multiple layers of security that an attacker would need to go through: any allow in either of them will suffice to view the data. Hashing and salting _passwords_ is important, but if you hash information you need to view (not just compare), then hashing will make it unusable. Security through obscurity is not an effective strategy for securing data (or anything, really); you must assume that every attacker knows what you know and still ensure data safety. Penetration testing can be used as a part of your overall security strategy, but it doesn’t require a honeypot and is not your primary consideration. [C]

QUESTION 46
You need to make sure a GCE instance can access other services in GCP. Which of the following are Google-recommended practices for enabling this?
A. Securely log onto the account to enter the required credentials.
B. Access the token via the metadata service.
C. Hash and salt all passwords transferred to the instance.
D. Generate an SSH key for the instance using gcloud or keygen.
E. Grant a service account access to the required resources.
F. Use Account Cross Access to authorize requests that originate from the instance.

EXPLANATION:
Using Service Accounts is definitely a best practice, and those are accessed from the instance via the metadata service. “Account Cross Access” isn’t a real thing. You don’t need SSH or SSH keys to enable this scenario. It’s a good idea to hash and salt passwords, but this has nothing to do with a GCE instance accessing GCP. [B,E]

QUESTION 48
How should you enable a GCE instance in Project A (having project ID `project-a-id`) to read files from a bucket in a Project B (having project ID `project-b-id`)?
A. When launching the instance, remove the default service account so it falls back to project-level access
B. Log into Cloud Shell in Project A and run `gcloud services enable storage.googleapis.com --project-id project-b-id`
C. In Project B, grant bucket read access to Project A’s default compute service account.
D. Log into Cloud Shell in Project B and run `gcloud services enable storage.googleapis.com --project-id project-a-id`
E. Only one of the other options is correct
F. Do not change the default service account setup and attachment
G. Log onto the instance and run `gcloud services enable storage.googleapis.com --project-id project-b-id`

EXPLANATION:
Since the default scopes allow reading from GCS, all that remains to get this situation working is for Project B (which owns and controls access to the bucket) to grant access to the service account being used. APIs are enabled for a project and do not differ between internal and external access. [C,F]

QUESTION 10
Which of the following statements is true?
A. You must specify a Service Account when creating an instance or none will be attached.
B. None of the other statements is true.
C. Every instance must have a Service Account attached to it.
D. Service Accounts should be used by GKE nodes and pods but not by GCE instances.

EXPLANATION:
If you don't do (or specify) anything, the default service account will be attached by default to each new GCE instance. However, you can stop that from happening by either deleting the default service account or opting out of attaching it when you are creating a new GCE instance. [B]

QUESTION 15
What will happen if a running GKE Deployment encounters a fatal error?
A. You can tell GKE to restart the deployment in an available pod.
B. None of the other options is correct.
C. GKE will automatically restart that deployment on an available node.
D. GKE Deployments are configuration information and do not directly encounter fatal errors.
E. GKE will automatically restart the deployment in an available pod.
F. GKE will automatically restart that deployment on an available GCE host.

EXPLANATION:
GKE Deployments are a declaration of what you want. Functionally, a Deployment uses ReplicaSets to make sure that the right configuration and number of pods are deployed to the cluster. [D]

QUESTION 16
What will happen if a running GKE pod encounters a fatal error?
A. If it is a part of a node, GKE will automatically restart that pod on an available GCE host.
B. GKE pods are tiered and cannot encounter fatal errors.
C. You can tell GKE to restart the pod in an available deployment.
D. If it is a part of a deployment, GKE will automatically restart that pod on an available node.
E. If it is a part of a host, GKE will automatically restart the pod in an available deployment.

EXPLANATION:
GKE tries to ensure that the number of pods you’ve specified in your deployment are always running, so it will restart one if it fails. All the other options are using terms in ways that don’t make sense (such as “an available deployment”). From the documentation: `Pods do not 'heal' or repair themselves. For example, if a Pod is scheduled on a node which later fails, the Pod is deleted. Similarly, if a Pod is evicted from a node for any reason, the Pod does not replace itself.` [D]

QUESTION 21
You need to very quickly set up Nginx Plus on GCP. Which of the following is the fastest option to get up and running?
A. Cloud Launcher
B. App Engine Standard
C. Kubernetes Engine
D. Cloud Functions

EXPLANATION:
Nginx cannot run on Cloud Functions, nor on App Engine Standard. Setting it up on Kubernetes Engine would take rather more time/effort than using the marketplace. The Cloud Launcher was renamed to be the GCP Marketplace--so these refer to the same thing--and this is a quick way to deploy all sorts of different systems, including Nginx Plus. [A]

QUESTION 26
You need to very quickly set up Nginx on GCP. Which of the following is the fastest option to get up and running?
A. GCP Marketplace
B. Compute Engine
C. Cloud Dataprep
D. Cloud Dataflow
E. None of the other options would work

EXPLANATION:
Nginx cannot run on Cloud Dataprep, nor on Cloud Dataflow. Setting it up on Compute Engine would take a lot more time/effort than using the marketplace. The Cloud Launcher was renamed to be the GCP Marketplace--so these refer to the same thing--and this is a quick way to deploy all sorts of different systems, including Nginx. [A]

QUESTION 28
You are monitoring a GKE cluster and see that a pod is being terminated. What will happen?
A. The ports used in the StatefulSet will be opened.
B. The processes used in the PersistentSet will remain locked.
C. The memory used by the containers will be freed.
D. The domains used in the deployment will be reduced.

EXPLANATION:
There are such things as deployments and StatefulSets, but they don’t have domains or ports, respectively. GKE doesn’t have such a thing as a PersistentSet, but it does have DaemonSets. [C]

QUESTION 29
You are thinking through all the things that happen when a Compute Engine instance starts up with a startup script that installs the Stackdriver agent and runs gsutil to retrieve a large amount of data from Cloud Storage. Of the following steps, which is the last one to happen?
A. The service account is created
B. The gcloud command to start the instance completes
C. The instance goes into the Running state
D. Space is reserved on a host machine

EXPLANATION:
Whether or not it is the default service account, the service account must exist before it can be attached to the instance. After a request to create a new instance has been accepted and while space is being found on some host machine, that instance starts in the Provisioning state. After space has been found and reserved on a host machine, the instance state goes to Staging while the host prepares to run it and sorts out things like the network adapter that will be used. Immediately when the VM is powered on and the OS starts booting up, the instance is considered to be Running. That's when gcloud completes, if it was run without `--async`. [B]

QUESTION 34
You are thinking through all the things that happen when a Compute Engine instance starts up with a startup script that installs the Stackdriver agent and runs gsutil to retrieve a large amount of data from Cloud Storage. Of the following steps, which is the first one to happen?
A. The gcloud command to start the instance completes
B. The service account is created
C. Space is reserved on a host machine
D. The instance goes into the Running state

EXPLANATION:
Whether or not it is the default service account, the service account must exist before it can be attached to the instance. After a request to create a new instance has been accepted and while space is being found on some host machine, that instance starts in the Provisioning state. After space has been found and reserved on a host machine, the instance state goes to Staging while the host prepares to run it and sorts out things like the network adapter that will be used. Immediately when the VM is powered on and the OS starts booting up, the instance is considered to be Running. That's when gcloud completes, if it was run without `--async`. [B]

QUESTION 35
You want to create a new GCS bucket in Iowa. How could you go about doing this?
A. Make sure the project is homed in the Iowa region then just create the bucket.
B. Only one of the other options will work.
C. Begin creating the bucket and set the location to Iowa when prompted.
D. At the top of the GCP console, drop the zone selector and choose us-central1-a, us-central1-b, us-central1-c, or us-central1-f, then create the bucket.
E. First create the bucket in Cloud Shell and then set its location to Iowa using the console.
F. At the top of the GCP console, drop the region selector and choose us-central1, then create the bucket.

EXPLANATION:
GCP does not have top-level location selectors like AWS does. GCP is global by default and it’s only individual resources that live in certain locations. When you’re creating a bucket in the console, the wizard asks you where you want to put it. Also, you cannot move a bucket after its region has been chosen during creation. [B,C]

QUESTION 49
Which of the following is NOT a part of having a Java program running on a GCE instance access the Cloud Tasks API in a Google-recommended way?
A. The program should pass “Metadata-Flavor: Google” to the SDK
B. The access scopes should include access to the Cloud Tasks API
C. The GCE instance should be using a service account
D. The service account should have access to the Cloud Tasks API
E. The program should use the Google SDK
F. The Cloud Tasks API should be enabled

EXPLANATION:
Java programs can use the SDK to access GCP services, and the SDK will take care of the details of retrieving the access token from the metadata service and communicating with the service. As such, your program need not concern itself with the “Metadata-Flavor: Google” header; the SDK will handle that. [A]

QUESTION 13
You are planning to use Persistent Disks in your system. In the context of what other GCP service(s) will you be using these Persistent Disks?
A. BigTable
B. Cloud Storage
C. You can only use Persistent Disks with one of the other listed options
D. Compute Engine
E. Kubernetes Engine

EXPLANATION:
Persistent Disks attach to GCE instances, but they can also be used through GKE. Cloud Storage and BigTable are completely separate types of storage. [D,E]

QUESTION 17
You need to process batch data in GCP and reuse your existing Hadoop-based processing code. Which of the following is a managed service that would best handle this situation?
A. Cloud Dataflow
B. Cloud Dataproc
C. Cloud Storage Processing
D. Compute Engine
E. Kubernetes Engine

EXPLANATION:
Google does not have a service called “Cloud Storage Processing”. Cloud Dataflow is for newly-built processing that can take advantage of Apache Beam. Compute Engine and Kubernetes Engine could both be used to run the processing, but they are not managed services to serve the described situation. Cloud Dataproc is made for running Hadoop/Spark work. [B]

QUESTION 18
You need to store thousands of 2TB objects for one year and it is very unlikely that you will need to retrieve any of them. Which of the following options would be the most cost-effective?
A. Multi-Regional Cloud Storage bucket
B. Coldline Cloud Storage bucket
C. Bigtable
D. Nearline Cloud Storage bucket
E. Regional Cloud Storage bucket

EXPLANATION:
Bigtable is not made for storing large objects. Since Coldline’s minimum storage duration of 90 days is easily met, it makes it less expensive than Nearline, Regional, and Multi-Regional. [B]

QUESTION 20
You need to host a legacy accounting process on SUSE Linux Enterprise Server 12 SP3. Which of the following is the best option for this?
A. CF
B. GKE
C. GCE
D. BQ
E. GAE

EXPLANATION:
If you aren’t familiar with all the common service abbreviations, you could get tripped up. You cannot choose the OS on Cloud Functions, App Engine, or Kubernetes Engine. BigQuery is not a compute service. Note that the linked flowchart is a little out of date in that GKE does now support GPUs. [C]

QUESTION 27
When comparing `n1-standard-8`, `n1-highcpu-8`, and `n1-highmem-16`, which of the following statements are true?
A. They all cost the same amount
B. The `n1-highmem-16` has twice as much RAM as the `n1-highcpu-8`
C. The `n1-highcpu-8` is the least expensive
D. The `n1-standard-8` is the least expensive
E. The `n1-highmem-16` has twice as many CPUs as the `n1-highcpu-8`

EXPLANATION:
The number at the end of the machine type indicates how many CPUs it has, and the type tells you where in the range of allowable RAM that machine falls--from minimum (highcpu) to balanced (standard) to maximum (highmem). The cost of each machine type is determined by how much CPU and RAM it uses. Understanding that is enough to correctly answer this question. [C,E]

QUESTION 33
You currently have 850TB of Closed-Circuit Television (CCTV) capture data and are adding new data at a rate of 80TB/month. The rate of data captured and needing to be stored is expected to grow to 200TB/month within one year because new locations are being added, each with 4-10 cameras. Archival data must be stored indefinitely, and as inexpensively as possible. The users of your system currently need to access 250TB of current-month footage and 100GB of archival footage, and access rates are expected to grow linearly with data volume. Which of the following storage options best suits this purpose?
A. Store new data as Multi-Regional and then use Lifecycle Management to transition it to Nearline after 30 days.
B. Immediately store all data as Coldline, because the access volume is low.
C. Store new data as Multi-Regional and then use Lifecycle Management to transition it to Regional after 30 days.
D. Always keep all data stored as Multi-Regional, because access volume is high.
E. Store new data as Regional and then use Lifecycle Management to transition it to Coldline after 30 days.

EXPLANATION:
Data cannot be transitioned from Multi-Regional to Regional through Lifecycle Management; that would change the location. The access rate for new data is 250/80--so quite high--but archival data access is very low (100/850000). Because of this, we need to start with Regional or Multi-Regional and should transition to Coldline to meet the “as inexpensively as possible” requirement. [E]

QUESTION 37
You need to process data streamed from Cloud Pub/Sub. Which of the following is a managed service that would handle this situation?
A. Cloud Storage
B. Cloud Storage Processing
C. Cloud Dataflow
D. Cloud Dataproc
E. App Engine

EXPLANATION:
Google does not have a service called “Cloud Storage Processing”. App Engine is not made to handle processing of this type. Cloud Dataproc is made for running Hadoop/Spark clusters but does not support streaming jobs. Cloud Dataflow is for newly-built processing that can take advantage of Apache Beam and supports both batch and streaming. [C]

QUESTION 42
You are planning a log analysis system to be deployed on GCP. Which of the following would be the best way to store the logs, long-term?
A. BigTable
B. Cloud Pub/Sub
C. Cloud Storage
D. Activity Log
E. Stackdriver Logging

EXPLANATION:
Stackdriver Logging only retains logs for 30 days, but it can then send the logs on to GCS for long-term storage (in whichever storage class is desired). Cloud Pub/Sub is not long-term storage. [C]

QUESTION 44
You are currently creating instances with `gcloud compute instances create myvm --machine-type=n1-highmem-8`. This is good but you would just like a bit more RAM. Which of the following replacements would be the most cost effective?
A. `gcloud compute instances create myvm --machine-type=n1-highmem-16`
B. `gcloud compute instances create myvm --custom-cpu=8 --custom-memory=60`
C. `gcloud compute instances create myvm --machine-type=n1-highmem-10`
D. `gcloud compute instances create myvm --custom-cpu=10 --custom-memory=60`
E. `gcloud compute instances create myvm --custom-cpu=1 --custom-memory=10`
F. `gcloud compute instances create myvm --machine-type=n1-highcpu-16`
G. `gcloud compute instances create myvm --custom-cpu=2 --custom-memory=10`

EXPLANATION:
For reference, the n1-highmem-8 has 8 CPUs and 52 GB of memory, but you do NOT need to remember this. Just remember that predefined machine types are named by their CPU counts and those are always powers of two--so `n1-highmem-10` is invalid. Custom machine types let you tweak the predefined types, but you can’t add more RAM per CPU than you get with the `highmem` machine types unless you use “Extended Memory”. But since the 8-CPU custom type option does not include `--custom-extensions`, it doesn’t get Extended Memory and the command won’t work. Since you’ll need to add more CPUs, you could go to `n1-highmem-16`--but a custom machine type with only 10 CPUs will be less expensive than that. [D]

QUESTION 47
You are planning a log analysis system to be deployed on GCP. Which of the following would be the best service for processing streamed logs?
A. Cloud Dataflow
B. Stackdriver Logging
C. BigTable
D. Cloud Dataproc
E. Cloud Pub/Sub

EXPLANATION:
Cloud Dataflow uses the Apache Beam framework and can process streamed data. Cloud Dataproc is for Spark/Hadoop and doesn’t handle streamed data. Stackdriver Logging doesn’t do custom log processing for a system like this. Cloud Pub/Sub can accept and deliver large volumes of data, but it’s not a processing service. BigTable can handle lots of data, but it’s for storage, not processing [A]

```js
// qwiklabs docs
[
  ...document.querySelectorAll(
    "h1.lab-preamble__title, #markdown-lab-instructions"
  )
].map(el => {
  document.body.classList = "";
  return document.body.appendChild(el);
});

[
  ...document.querySelectorAll(
    ["body > *:not(#markdown-lab-instructions):not(h1)"].join(",")
  )
].map(el => el.parentNode.removeChild(el));

[...document.querySelectorAll("*")]
  .filter(el => {
    return el.tagName.indexOf("QL-") === 0;
  })
  .map(el => el.parentNode.removeChild(el));

[
  ...document.querySelectorAll(
    [".l-lab-main-body", "#markdown-lab-instructions"].join(",")
  )
].map(el => {
  el.style.margin = 0;
  el.style.padding = 0;
});

[
  ...document.querySelectorAll(["h1", "h2", "h3", "h4", "h5", "h6"].join(","))
].map(el => {
  el.style.margin = "1.25rem 0";
  el.style.padding = 0;
});

// paste md and replace \n\n([^a-zA-Z#]) with \n$1
```
