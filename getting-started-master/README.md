# Instructions for the student

## Installing the OpenShift Client on your IBM laptop / desktop

1. Download the appropriate client for your operating system from here: https://mirror.openshift.com/pub/openshift-v4/clients/oc/4.6/
2. Unpack and place the resulting binaries on the PATH of your operating system.
3. Validate that the PATH has been set correctly by typing "oc". If you get a command help for the "oc" command, things are working correctly.

##  Where will the labs be conducted?
All classroom excercises / labs guided by the instructors will be executed in the lab environment provided through the DO288 course available through your Red Hat subscription.

Most of the homework assignments are graded. You will need to use a cluster (see next section) on the IBM Cloud for that. 

##  Cluster information

Log into the [cluster](https://console-openshift-console.do288training-159361736-f72ef11f3ab089a8c677044eb28292cd-0000.us-east.containers.appdomain.cloud/dashboards) via a browser using your intranet id. If you are not able to login, then your id has not been authorized yet. Please contact one of the instructors to fix this.

Once logged in, at the top right, click on your user name. You will get a drop down like [this](login-drop-down.png). Click on the "Copy Login Command" option. This will open up a new window with a link saying "display token". Click on this link. Copy the "oc login" command shown, and run that from the command line. You will get output that looks something like this:

```[zaphod@oc3027208274 getting-started]$ oc login --token=1LB7BMPzq34onydFfbGXXh2_ANJs8ms9HslX3RgKxR4 --server=https://c100-e.us-east.containers.cloud.ibm.com:30596
Logged into "https://c100-e.us-east.containers.cloud.ibm.com:30596" as "IAM#kstephe@us.ibm.com" using the token provided.

You have access to 81 projects, the list has been suppressed. You can list all projects with 'oc projects'

Using project "default".
[zaphod@oc3027208274 getting-started]$
```

You are now logged into the cluster.
## Before Proceeding to other assignments
### switch to your project (Assigned by cluster admin) using 'oc project <project name>
mgadagin@MAHANTESHs-MBP day3-simple-stuff % oc project mgadagin
Now using project "mgadagin" on server "https://c100-e.us-east.containers.cloud.ibm.com:31920".
mgadagin@MAHANTESHs-MBP day3-simple-stuff % oc new-app --name=simple https://github.com/mahagmath/day3-simple-stuff.git
--> Found container image 3e170c7 (6 weeks old) from docker.io for "docker.io/ibmcom/websphere-liberty:20.0.0.5-full-java11-openj9-ubi"

    Red Hat Universal Base Image 8 
    ------------------------------ 
    The Universal Base Image is designed and engineered to be the base layer for all of your containerized applications, middleware and utilities. This base image is freely redistributable, but Red Hat only supports Red Hat technologies through subscriptions for Red Hat products. This image is maintained by Red Hat and updated regularly.

    Tags: base rhel8

    * An image stream tag will be created as "websphere-liberty:20.0.0.5-full-java11-openj9-ubi" that will track the source image
    * A Docker build using source code from https://github.com/mahagmath/day3-simple-stuff.git will be created
      * The resulting image will be pushed to image stream tag "simple:latest"
      * Every time "websphere-liberty:20.0.0.5-full-java11-openj9-ubi" changes a new build will be triggered

--> Creating resources ...
    imagestream.image.openshift.io "websphere-liberty" created
    imagestream.image.openshift.io "simple" created
    buildconfig.build.openshift.io "simple" created
    deployment.apps "simple" created
    service "simple" created
--> Success
    Build scheduled, use 'oc logs -f bc/simple' to track its progress.
    Application is not exposed. You can expose services to the outside world by executing one or more of the commands below:
     'oc expose svc/simple' 
    Run 'oc status' to view your app.

## Dealing with Windows

Sadly, many IBM'ers use Windows as the OS on their laptop :-) . A half-way good alternative to getting the linux command line working correctly on Windows is to use Git Bash (which is to be found at most custer locations) or even better - [Cygwin](https://cygwin.com/install.html). All Windows installations come with PowerShell, and this works better than the common Dos terminal, but its still not perfect. The best solution is to use the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10).Note that without using one of these options, you will have varying degree of breakage when it comes to handling quotes, double-quotes, and back-slashes in commands that you will need to use.

Mac users tend to have less problems when using their terminals to run the commands needed.

## Other software

"curl" is a common tool that you will have to use. If your operating system does not provide it, one option is to install Git Bash from [here](https://git-scm.com/downloads). There are many other tools that are the equivalent of "curl", but since the EX288 exam will not provide you with access to arbitrary tools, you should become very familiar with "curl".

ssh-keygen is a tool that is available that is part of openssh which is needed for the course. If your operating system does not have this tool already, installing Git Bash will provide you with this tool

