DevOps
------------------------
        Each commit must go to release.
        Cost reudction.
        Quality - REDFINED
        ==========================
==============================================
Prod - OnMobX        
Mgr - Mgrx.
=============================
Transition - 2 WEEK =====> 20 MINS.
==================================================
SDLC
----------------------------
Architect - JIRA - Confulence
Dev - 10 FEA - 10 DEV
            Code Integ - Gitlab
            Code Ana - 
                        PEER CODE REVIEW - 
                        Static Code Ana  - SonarQube
            Build - Maven - Gradle
            Unit TESTING - Junit
            Package mgmt -
                            SYSTEM
                            APP -
            Archive tool - Artifactory
            --------------------------------------
            OnMobX56.7 ----> 100 BOXES
            -------------------------------------
            50 L - 50 W
            50 N - 50 A
            25 T - 25 WL - 25 -JBs - 25 WS
            25 MY  - 25 MS - 25 OR - 25 PS
            100 PRO - 
            -------------------------------------
            1 DEP -> 9 mins.
            100 - DEP -> 9 mins?
                ---------------------
                HOW?- Parrell DEP
            -----------------------------------------
            Code -> Ansible -> Puppet- > Chef - >Salt
            GUI -> Octopus Dep - Udeploy
            -------------------------------------
            9 mins + 1 mins(100 SERVER) --- 10 MINS.
            =====================================================
            100000 INsarnce - 100 DIFF Config ---> 1 SEC.
            -----------
                Container -> Docker + Kubernetes

            AT

            Code Coverage - 
            ------------------------------
            =========================================================================
            PLAN->code->Ana->UT->Pack-Archie->Dep2QA->AT->CC
            JIRA_>GIt->SQ ->Junit>Jar->Art ->Ansible->SEL->Jacoco
            ------------------------------------------------------
                                JENKINS
                                cont - Integ
                                Auto Build
                                Auto Testing
                                Imm Feedback
            ======================================================
            ======================================================================
            Prod 
                    Dep2Prod
                    Monitoring -
                            INFRA - Zabbix
                            Log - ELK - 
                            Performance - NewRelic

https://www.devopsschool.com/path
===========================================================================================
Username: devops@rajeshkumar.xyz 
Pass: v78qbka7
============================================================================================
Onmobile-Dec-Docker-K8s-Bangalore-2019

http://bit.ly/2LCBCTF

========================================================
What is Docker?
    Container mgmt tool
    Free
    OS
    Version
            - Docker CE
            - DOCKER EE


What is Container?
    USER SPACE with their own
                        - NET NS
                        - mNT NS
                        - PMAP NS
                                    Powered by Docker

                    with a help of KERNAL NS.
 15  history
   16  clear
   17  ps -eaf | grep docker
   18  ps -eaf | grep docker | wc -l
   19  docker run -itd ubuntu
   20  docker run -itd ubuntu
   21  ps -eaf | grep docker | wc -l
   22  docker run -itd ubuntu
   23  ps -eaf | grep docker | wc -l
   24  clear
   25  ps -eaf | grep docker
   26  clear
   27  clear
   28  docker ps
   29  docker inspect 22719b53dc0e | grep -i ip
   30  docker inspect b2876a4c0ce0 | grep -i ip
   31  docker inspect 71aee8e1fa4c | grep -i ip
   32  clear
   33  ls
   34  docker ps
   35  docker exec 22719b53dc0e df -kh
   36  docker exec b2876a4c0ce0 df -kh
   37  docker exec 71aee8e1fa4c df -kh
   38  clear
   39  ls
   40  docker ps
   41  docker exec 22719b53dc0e touch /opt/rajesh.txt
   42  docker exec 22719b53dc0e ls /opt/
   43  docker exec b2876a4c0ce0 ls /opt/
   44  docker exec 71aee8e1fa4c ls /opt/
   45  clear
   46  ps -eaf
   47  clear
   48  docker ps
   49  docker exec 22719b53dc0e ps -eaf
   50  docker exec b2876a4c0ce0 ps -eaf

Docker Arch
Humen -> Docker Client --> Docker Deamon --> KERNAL
-----------------------------------------------------
                Docker Engine

Component of Docker?
    - Dokcker Engine    
            - Docker Client --> Docker Deamon
    - Docker Image
            - File system + Apps
    - Docker Container
            - What you have in image - you see in Container
    - Docker Registry and repo

=======================================
How to install Docker?
13.233.105.67
=====================
RHEL-7.5_HVM_GA-20180322-x86_64-1-Hourly2-GP2 (ami-5b673c34)

https://www.devopsschool.com/tutorial/docker/install-config/docker-install-commuityedition-centos-rhel.html

  1  sudo yum install -y yum-utils device-mapper-persistent-data lvm2
    2  sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    3  sudo yum install –y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
    4  sudo yum-config-manager --enable rhui-REGION-rhel-server-extras
    5  sudo yum install -y docker-ce
    6  docker -v
    7  sudo systemctl enable docker
    8  sudo systemctl start docker
    9  clear
   10  which docker
   11  ps -eaf | grep docker
   12  docker info
   13  clear
   14  ls
   15  history

Q1 - Validate it - DONE


WORKING WIth Container - Docker Workflow
=================================================
create -> start -> stop -> start -> restart -> pause -> unpause -> stop -> rm

 51  history
   52  clear
   53  docker ps
   54  docker stop 22719b53dc0e b2876a4c0ce0 71aee8e1fa4c
   55  docker ps
   56  docker ps -a
   57  docker rm 22719b53dc0e b2876a4c0ce0 71aee8e1fa4c
   58  clear
   59  docker -sA
   60  clear
   61  docker ps -a
   62  docker create jenkins
   63  clear
   64  docker ps
   65  docker ps -a
   66  docker start 0b6cbacb4750
   67  docker ps a
   68  docker ps -a
   69  docker stop 0b6cbacb4750
   70  docker ps -a
   71  clear
   72  docker ps -a
   73  docker start 0b6cbacb4750
   74  docker ps a-
   75  docker ps -a
   76  docker restart 0b6cbacb4750
   77  docker ps -a
   78  clear
   79  docker pause 0b6cbacb4750
   80  docker ps -a
   81  docker unpause 0b6cbacb4750
   82  docker ps -a
   83  docker stop 0b6cbacb4750
   84  docker ps -a
   85  docker rm 0b6cbacb4750
   86  docker ps -a



Pause vs stop
-----------------
When you pause - Containers stop getting CPU from Kernal.

 89  docker create jenkins
   90  docker ps -a
   91  docker start jenkins
   92  docker start f295775d912e
   93  clear
   94  docker ps
   95  docker stats f295775d912e
   96  docker top f295775d912e
   97  ps -eaf | grep 12847
   98  clear
   99  docker ps
  100  docker exec f295775d912e ls /
  101  clear
  102  ls
  103  docker ps
  104  docker inspect f295775d912e


 105  clear
  106  history
  107  clear
  108  docker ps
  109  docker pause f295775d912e
  110  docker ps -a
  111  docker inspect f295775d912e
  112  clear
  113  docker exec f295775d912e ls /
  114  docker top f295775d912e
  115  docker stats f295775d912e
  116  docker unpause f295775d912e
  117  clear
  118  docker ps
  119  docker stop f295775d912e
  120  docker inspect f295775d912e
  121  docker exec f295775d912e ls /
  122  docker top f295775d912e
  123  clear
  124  docker stats f295775d912e
  125  history


Pull vs create
-----------------



nginx
mysql
tomcat
redis
mongodb
solr
python
----------------------
jenkins
        JAVA
            WAR
        WEB SERVER - NODE
        8080            50000
        ------------------------------

PID 1 -  Concept of PID1
=================================================
How to access containers?
        How to get inside containers?
        
        exec - will executate an executables inside a container - if executable are found. - NEW SESSION
                        with -it and /bin/bash -you can go insdie a container.
        attach
                attach will attached to a session of PID1.

        How to come out without existing a session?
        ctrl + p + Q

        How to access from outside of the containers?
          97  docker inspect f295775d912e | grep -i ip
        98  curl http://172.17.0.2:8080

        docker run -d -p 8080:8080 jenkins
        docker run -d -p 8090:8080 jenkins

=====================================================
Docker Containers
https://www.devopsschool.com/tutorial/docker/commands/

 109  docker ps -a
  110  docker run -d -p 8080:8080 jenkins
  111  docker run -d -p 8080:8080 jenkins
  112  clear
  113  docker run -d -p 8090:8080 jenkins
  114  docker -s
  115  docker ps
  116  celar
  117  clear
  118  docker ps
  119  docker exec 245128cc6a0a ls /opt
  120  touch rajesh.txt
  121  ls
  122  docker cp rajesh.txt 245128cc6a0a:/opt
  123  docker exec 245128cc6a0a ls /opt
  124  ls
  125  rm rajesh.txt
  126  ls
  127  clear
  128  docker cp 245128cc6a0a:/opt/rajesh.txt .
  129  ls
  130  clear
  131  ls
  132  docker diff 245128cc6a0a
  133  clear
  134  docker ps -a
  135  docker port
  136  docker port 245128cc6a0a
  137  clear
  138  docker ps
  139  docker rename 245128cc6a0a dev1
  140  docker ps
  141  clear
  142  docker run -itd --name dev2 ubunutu
  143  docker run -itd --name dev2 ubuntu
  144  docker ps -a

======================
75  docker rmi nginx ubuntu jenkins
   76  clear
   77  ls
   78  ls
   79  docker images
   80  clear
   81  cd /var/lib/docker
   82  clear
   83  ls
   84  docker info
   85  clear
   86  ls
   87  cd overlay2
   88  clear
   89  ls
   90  du -sh
   91  docker pull ubuntu
   92  clear
   93  ls
   94  du -h --max-depth=1
   95  cd ./26d9bb40324dcea3989d1bff7d6f0e48728dbd7ba273b00cba86aa26f3960488
   96  clear
   97  ls
   98  cd diff/
   99  clear
  100  ls
  101  clear
  102  docker images
  103  docker inspect ubuntu
  104  clear
  105  docker images
  106  docker history ubuntu
  107  pwd
  108  clear
  109  ls
  110  cd ..
  111  ls
  112  cd ..
  113  ls
  114  clear
  115  df -kh
  116  clear
  117  ls
  118  cd ..
  119  ls
  120  cd containers/
  121  ;
  122  clear
  123  ls
  124  docker run -itd ubuntu
  125  docker
  126  clear
  127  docker ps
  128  ls
  129  cd ..
  130  ls
  131  cd overlay2/
  132  clear
  133  ls
  134  df -kh
  135  clear
  136  docker ps -a
  137  docker stop c81d57c032f0
  138  df -kh
  139  ls
  140  clear
  141  ls
  142  clear
  143  dcoker ps -a
  144  docker ps -a
  145  docker start c81d57c032f0
  146  clear
  147  ls
  148  docker ps
  149  docker attach c81d57c032f0
  150  clear
  151  cd ..
  152  ls
  153  clear
  154  ls
  155  find . -name rajesh.txt
  156  docker ps -a
  157  docker stop c81d57c032f0
  158  find . -name rajesh.txt
  159  docker rm c81d57c032f0
  160  find . -name rajesh.txt
  161  clear
  162  history


Docker Images
----------------------
Lazy way - using Exiting container

  171  docker history ubuntu
  172  docker ps
  173  docker ps
  174  docker exec 8290a26cb93a git
  175  clear
  176  docker ps
  177  docker commit -m"ub-git-up" -a"rajesh" 8290a26cb93a ub-git-up
  178  docker images
  179  docker history ubuntu
  180  docker history ub-git-up
  181  clear
  182  docker images
  183  docker run -itd ub-git-up
  184  docker ps
  185  docker exec 382aa014dfa7 git
  186  history


Best Way - Using Dockerfile

FROM ubuntu
MAINTAINER Rajesh Kumar <devops@rajeshkumar.xyz>
RUN apt-get update
RUN apt-get install git -y

 docker build -t ub1 .



Docker Netwokring

Docker volume

Docker regirty..
=======================================================================
What Docker Image
        - Collection of Layers.
What is layer
        - filesystems
        - UUID by SHA256
        - Each layer their Parents
What is Layer0?
        - base image
        - rootfs
======================================
What is Container?
        Whatever we in image we can see in container.
        - All the layer of images merge into ONE(RW) layer and attached to Rw empty layer(This is a container.)
        - Union Mounts.

========================================================
Jenkins
        openjdk:8-jdk
                buildpack-deps:stretch-scm
                        buildpack-deps:stretch-curl
                                        debian:stretch
                                                        scratch
=================================================================
Base Image
        JDK5 - TOMCAT 
        JDK6
        JDK7
        JDk8
        JDK9
        JDk9 - TOMCAT 5 Apace 2
                        Apche 3
             - TOMCAT 6   
==============================
CENTOS 7.6  - BASE IMAGE
OpenJDk 8 && Redis && mysql && tomcat ----- IMAGE
App---- - IMAGE

CENTOS 7.6  - BASE IMAGE
OpenJDk 8  - IMAGE
&& Redis && - IMAGE
 mysql &&  - IMAGE
 tomcat - IMAGE
App----
=============


How to create image?
        - Using Existing Container
        - Dockerfile
                - EACH LINE WOULD CRAETE ONE LAYER.
                - NEXT LAYER WOULD BE CREATED FROM A CONTAINER OF PREVIOUS LATYER
                

FROM ubuntu
MAINTAINER Rajesh Kumar <devops@rajeshkumar.xyz>
RUN apt-get update
RUN apt-get install git -y

======================
rootfs  - 1 Layer
        - openjdk  - - 2 Layer
                - Tomcat  - - 3 Layer
                                - APP   - - 4 Layer
=======================================================================================
DAY 2 - 13.233.49.156



FROM ubuntu 
MAINTAINER Rajesh Kumar <devops@rajeshkumar.xyz>        af2d9cefb7ef
RUN touch /opt/rajesh1.txt                              913e12e3b57e
RUN touch /opt/rajesh2.txt                              85b13f506baa

   1  docker pull ubuntu
    2  sudo systemctl enable docker
    3  sudo systemctl start docker
    4  docker pull ubuntu
    5  clear
    6  docker images
    7  docker inspect ubuntu
    8  clear
    9  docker history ubuntu
   10  clear
   11  cd
   12  ls
   13  vi doc1
   14  docker build -t dock1 -f doc1 .
   15  docker cleaer
   16  clear
   17  docker images
   18  docker history dock1
   19  docker inspect dock1
   20  clear
   21  docker history dock1
   22  docker help diff
   23  clear
   24  history

   CMD VS ENTRYPOINT
   ========================
   Mode of Execution.

CMD 
        CMD is a way to have PID1
                        if PID1 hold - container keep running.
                        if PID1 is not holdin - it get exited.
        CMD be can be replaced any time.

- Shell Mode 
echo "Rajesh Kumar"

- exec mode
/bin/echo fsdfs

ENTRYPOINT
        ENTRYPOINT is a way to have PID1
                        if PID1 hold - container keep running.
                        if PID1 is not holding - it get exited.
        ENTRYPOINT CAN NOT BE REPLACED and 
                        IF PARAMETER password to a ENTRPOINT - it get appended as param to the ENTRYPOINT.

/bin/tini -- /usr/local/bin/jenkins.sh 33333

Lab - 15 mins - https://www.devopsschool.com/tutorial/docker/docker-run-vs-cmd-entrypoint.html

====================================================
Registry        
        pub
                hub.docker.com
                        Regiter -> USERID n PASS
                google registry
        pvt
                Artifactory
                nexus
                ECR
                registry

docker login https://index.docker.io/v1/
docker login http//18.7.7.7.7/fdsfsf

docker push imagename
docker push http//18.7.7.7.7/fdsfsf

  64  docker images
   65  docker info
   66  clear
   67  docker images
   68  docker login
   69  docker push dock1
   70  docker images
   71  docker tag dock1 scmgalaxy/dock1
   72  docker images
   73  docker push scmgalaxy/dock1
   74  docker tag dock1 scmgalaxy/dock1:v1
   75  docker images
   76  docker push scmgalaxy/dock1:v1
   77  history

https://www.devopsschool.com/blog/how-to-setup-docker-repository-in-artifactory-and-push-pull-images/
https://www.devopsschool.com/blog/setup-artifactory-pro-6-1-0-using-docker-containtainer/
https://www.devopsschool.com/blog/how-to-setup-docker-registry-repository-using-jfrog-artifactory/
https://www.devopsschool.com/blog/artifactory-install-and-configurations-guide/
https://www.devopsschool.com/blog/artifactory-install-and-configurations-guide/


====================================================================================
====================================================================================
================================DAY 3====================================================
Master
        API server -> POD -> container - Images -> GR
        ETCD  -> POD -> container - Images -> GR
        Controller Mgr  -> POD -> container - Images -> GR
        Schedular  -> POD -> container - Images -> GR

        Kube proxy -> POD -> container - Images -> GR
        Kubelet - AGENT - TOOL
        Docker - - DEAMON - TOOL
Worker
        Kubelet - AGENT - TOOL
        Kube proxy
        Docker - - DEAMON - TOOL

Workstation
        kubectl -> config

ONE NODE CLUSTOR = minikube
                IS VM
                                API server -> POD ->
                                ETCD  -> POD
                                Controller Mgr  -> POD
                                Schedular  -> POD

                                Kube proxy
                                Kubelet - AGENT - TOOL
                                Docker - - DEAMON - TOOL
https://kubernetes.io/docs/setup/learning-environment/minikube/
minikube
kubectl
                $ minikube start
===================================================================
kubernetes clustor -
                PHYSICAL 

                VIRUAL BOXES
                        PRIVATE CLOUD
                               SELF MANAGED -
                                                OPEN STAKE
                                                VSPHE 
                        PUBLIC
                                HOSTED - MASTER IS PAAS
                                        AWS - EKS
                                        AZURE - AKS
                                        GC - GKE
                                SELF MANAGED - 
                                        MANUAL WAY using
                                        - Kubeadm without cloud Integ
                                        - Kops with cloud integ
https://www.devopsschool.com/tutorial/kubernetes/
============================================================================
hardway
https://github.com/kelseyhightower/kubernetes-the-hard-way                                        

54.152.249.148 
34.207.96.204

User –root
Pass – Onm0bile

Docker 
https://www.devopsschool.com/tutorial/docker/install-config/docker-install-commuityedition-centos-rhel.html

Kubeadm +++++
https://www.devopsschool.com/blog/setting-up-kubernetes-clusters-using-kubeadm-manual-way-in-rhel-7-centos7/

Your Kubernetes control-plane has initialized successfully!

To start using your cluster, you need to run the following as a regular user:

  mkdir -p $HOME/.kube
  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  sudo chown $(id -u):$(id -g) $HOME/.kube/config

You should now deploy a pod network to the cluster.
Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
  https://kubernetes.io/docs/concepts/cluster-administration/addons/

Then you can join any number of worker nodes by running the following on each as root:

kubeadm join 10.123.1.170:6443 --token 5ihfaf.bkf9nuwc5ynfp925 \
    --discovery-token-ca-cert-hash sha256:d003775646ed91e8eb60b208c9402a7b6b57d8ea14b38f695e8b8d7f1aa7d1d8


   32  kubectl
   33  kubectl cluster-info
   34  kubectlget nodes
   35  kubectl get nodes
   36  kubectl get pods
   37  kubectl get ns
   38  kubectl get pods -n=kube-system
   39  kubectl describe pod coredns-6955765f44-cggpd -n=kube-system
   40  kubectl get nodes
   41  kubectl describe node ip-10-123-1-41.ec2.internal
   42  kubectl get pods -n=kube-system
   43  kubectl describe pod coredns-6955765f44-cggpd -n=kube-system
   44  clear
   45  kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"
   46  clear
   47  kubectl get pods -n=kube-system
   48  kubectl get nodes
   49  history
   
   
   problems of containers :
scalability beyond hosts
containers running in multiple hosts.


kubernetes architechture

master and nodes

master : 4 components 
1)-> API SERVER : SERVER OF api's (600 OR MORE entire kubernetes )
   --->front end to control palne
   --->extrenal(from client) or internal(within nodes) communication is done by api server
   
2)->etcd : key and value based database  (similar to database)
---->cluster store (persistent storage)
---->etcd should have backup
----> 

3) Controller : how to monitor cluster : (controller of controllers)
---->watch for changes and if there any change report to api server
---->runs in loops

4) Scheduler : watches api server for new pods, assigns work to nodes.


node have 3 components:
1)kubelet : (minion)
  ---> is in each worker
  ---> the moment kubelet is up look for master in node
  ---> 10255 default port for kubelet.
  
2) container engine (docker)
3) kube-proxy :
	---> no -p options (-p is nat(network address transmission) ing)
	---> assign ip address to pods
	----> all containers in pod share single ip address.
	---> kind of bridge
	
	
human job is to express desired :

declarative model : yaml,json
desired state : we want pod (which we will give in manifest file) ---- send to api server.
pod - atomic unit of scheduling.
  kubernetes have pods
  pods are not created 
  pod is running because of container inside it which is running because of pid1.
  if one container fails in pod then pod is not running.
  any kind of container can be there in pod.
  best practise  (one pod one container)
  main container (first one) in pod.
  no pod is ever redeployed
  
  
multiple pod -- replication controller
  
  pause container ()
  
=>Services : 
to solve ip address problem of pods,

any pod labels (give any lable)
labels of pods if matches with service label automatically load balancer happens --- but there is some discovery services.
labels are more important 
services uses tcp by default.
random load balancing.

registry -public  --- 1)docker hub
2) google
and private ---- 1) Artifactory
2)nexus
3)ECR
4)registry

/etc/docker is containing config file

one repository have one image


DAY - 3
========================================
1) setting up cluster is platform specific

2) kubectl look for config file in current location 
1) ./.kube/conf if not then 
2) env kube conf
3) /.kube/conf

config file 
1) section name (clusters)
2) users 
3) context (which user belong to which cluster)
4) current context

after config file run kubectl.---- run commands

================================================
namespaces --- pods
subcluster 
-----> default subcluster those who dont belong to any group
-----> node subcluster -- logs and monitoring
-----> Kube system cluster

these subclusters are called as namespaces in pods
check describe pods for coredns ---- discovery services

wevnet is a driver to kube proxy
