# Ostad-Docker
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Install the latest PowerShell for new features and improvements! https://aka.ms/PSWindows

PS C:\windows\system32> cd Ostad-Docker
PS C:\windows\system32\Ostad-Docker> ls


    Directory: C:\windows\system32\Ostad-Docker


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          7/1/2025   4:47 PM                .github
d-----          7/1/2025   4:47 PM                OstadServer
d-----          7/1/2025   4:47 PM                OstadUI
-a----          7/1/2025   4:47 PM             35 .dockerignore
-a----          7/1/2025   4:47 PM             15 .gitignore
-a----          7/2/2025  12:10 PM            708 mongo-deployment.yaml
-a----          7/2/2025  12:10 PM            837 mongo-express-deployment.yaml
-a----          7/1/2025   4:52 PM             62 namespace.yaml
-a----          7/2/2025  12:09 PM            739 ostad-server-deployment.yaml
-a----          7/2/2025  12:08 PM            630 ostad-ui-deployment.yaml
-a----          7/1/2025   4:47 PM           1941 readme.md


PS C:\windows\system32\Ostad-Docker> kubectl config set-context --current --namespace=rahat-ns
Context "docker-desktop" modified.
PS C:\windows\system32\Ostad-Docker> kubectl apply -f ostad-ui-deployment.yaml
deployment.apps/ostad-ui unchanged
service/ostad-ui unchanged
PS C:\windows\system32\Ostad-Docker> kubectl get pods -n rahat-ns
NAME                            READY   STATUS             RESTARTS        AGE
mongo-59bc9f49f4-zrn8f          1/1     Running            1 (2m51s ago)   24m
mongo-express-d5f69c9dd-npmk8   1/1     Running            1 (2m51s ago)   23m
ostad-server-74d5bcdd8b-pzcvw   0/1     ImagePullBackOff   0               24m
ostad-ui-66bcc7b4cb-nqkvf       0/1     ImagePullBackOff   0               24m
PS C:\windows\system32\Ostad-Docker> kubectl get pods -n ingress-nginx
NAME                                        READY   STATUS             RESTARTS      AGE
ingress-nginx-admission-create-gb445        0/1     Completed          0             18m
ingress-nginx-admission-patch-2hq9r         0/1     Completed          0             18m
ingress-nginx-controller-5b94446ddb-8dfmd   0/1     CrashLoopBackOff   4 (44s ago)   18m
PS C:\windows\system32\Ostad-Docker> PS C:\windows\system32\Ostad-Docker> kubectl get pods -n ingress-nginx
Get-Process : A positional parameter cannot be found that accepts argument 'C:\windows\system32\Ostad-Docker>'.
At line:1 char:1
+ PS C:\windows\system32\Ostad-Docker> kubectl get pods -n ingress-ngin ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Get-Process], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.GetProcessCommand

PS C:\windows\system32\Ostad-Docker> NAME                                        READY   STATUS             RESTARTS      AGE
NAME : The term 'NAME' is not recognized as the name of a cmdlet, function, script file, or operable program. Check
the spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ NAME                                        READY   STATUS            ...
+ ~~~~
    + CategoryInfo          : ObjectNotFound: (NAME:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\windows\system32\Ostad-Docker> ingress-nginx-admission-create-gb445        0/1     Completed          0             18m
ingress-nginx-admission-create-gb445 : The term 'ingress-nginx-admission-create-gb445' is not recognized as the name
of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included,
verify that the path is correct and try again.
At line:1 char:1
+ ingress-nginx-admission-create-gb445        0/1     Completed         ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (ingress-nginx-admission-create-gb445:String) [], CommandNotFoundExcepti
   on
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\windows\system32\Ostad-Docker> ingress-nginx-admission-patch-2hq9r         0/1     Completed          0             18m
ingress-nginx-admission-patch-2hq9r : The term 'ingress-nginx-admission-patch-2hq9r' is not recognized as the name of
a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included,
verify that the path is correct and try again.
At line:1 char:1
+ ingress-nginx-admission-patch-2hq9r         0/1     Completed         ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (ingress-nginx-admission-patch-2hq9r:String) [], CommandNotFoundExceptio
   n
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\windows\system32\Ostad-Docker> ingress-nginx-controller-5b94446ddb-8dfmd   0/1     CrashLoopBackOff   4 (44s ago)   18m
44s : The term '44s' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the
spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:75
+ ... ntroller-5b94446ddb-8dfmd   0/1     CrashLoopBackOff   4 (44s ago)    ...
+                                                               ~~~
    + CategoryInfo          : ObjectNotFound: (44s:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\windows\system32\Ostad-Docker> PS C:\windows\system32\Ostad-Docker>
PS : Cannot find a process with the name "C:\windows\system32\Ostad-Docker>". Verify the process name and call the
cmdlet again.
At line:1 char:1
+ PS C:\windows\system32\Ostad-Docker>
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (C:\windows\system32\Ostad-Docker>:String) [Get-Process], ProcessCommand
   Exception
    + FullyQualifiedErrorId : NoProcessFoundForGivenName,Microsoft.PowerShell.Commands.GetProcessCommand

PS C:\windows\system32\Ostad-Docker> kubectl logs -n ingress-nginx ingress-nginx-controller-5b94446ddb-8dfmd
>>
exec /usr/bin/dumb-init: exec format error
PS C:\windows\system32\Ostad-Docker> kubectl delete -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.9.1/deploy/static/provider/cloud/deploy.yaml
>>
namespace "ingress-nginx" deleted
serviceaccount "ingress-nginx" deleted
serviceaccount "ingress-nginx-admission" deleted
role.rbac.authorization.k8s.io "ingress-nginx" deleted
role.rbac.authorization.k8s.io "ingress-nginx-admission" deleted
clusterrole.rbac.authorization.k8s.io "ingress-nginx" deleted
clusterrole.rbac.authorization.k8s.io "ingress-nginx-admission" deleted
rolebinding.rbac.authorization.k8s.io "ingress-nginx" deleted
rolebinding.rbac.authorization.k8s.io "ingress-nginx-admission" deleted
clusterrolebinding.rbac.authorization.k8s.io "ingress-nginx" deleted
clusterrolebinding.rbac.authorization.k8s.io "ingress-nginx-admission" deleted
configmap "ingress-nginx-controller" deleted
service "ingress-nginx-controller" deleted
service "ingress-nginx-controller-admission" deleted
deployment.apps "ingress-nginx-controller" deleted
job.batch "ingress-nginx-admission-create" deleted
job.batch "ingress-nginx-admission-patch" deleted
ingressclass.networking.k8s.io "nginx" deleted
networkpolicy.networking.k8s.io "ingress-nginx-admission" deleted
validatingwebhookconfiguration.admissionregistration.k8s.io "ingress-nginx-admission" deleted
PS C:\windows\system32\Ostad-Docker> kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.9.1/deploy/static/provider/baremetal/deploy.yaml
namespace/ingress-nginx created
serviceaccount/ingress-nginx created
serviceaccount/ingress-nginx-admission created
role.rbac.authorization.k8s.io/ingress-nginx created
role.rbac.authorization.k8s.io/ingress-nginx-admission created
clusterrole.rbac.authorization.k8s.io/ingress-nginx created
clusterrole.rbac.authorization.k8s.io/ingress-nginx-admission created
rolebinding.rbac.authorization.k8s.io/ingress-nginx created
rolebinding.rbac.authorization.k8s.io/ingress-nginx-admission created
clusterrolebinding.rbac.authorization.k8s.io/ingress-nginx created
clusterrolebinding.rbac.authorization.k8s.io/ingress-nginx-admission created
configmap/ingress-nginx-controller created
service/ingress-nginx-controller created
service/ingress-nginx-controller-admission created
deployment.apps/ingress-nginx-controller created
job.batch/ingress-nginx-admission-create created
job.batch/ingress-nginx-admission-patch created
ingressclass.networking.k8s.io/nginx created
networkpolicy.networking.k8s.io/ingress-nginx-admission created
validatingwebhookconfiguration.admissionregistration.k8s.io/ingress-nginx-admission created
PS C:\windows\system32\Ostad-Docker>
PS C:\windows\system32\Ostad-Docker> kubectl get pods -n ingress-nginx
NAME                                        READY   STATUS             RESTARTS      AGE
ingress-nginx-admission-create-dvcst        0/1     Completed          0             49s
ingress-nginx-admission-patch-hh9q6         0/1     Completed          1             49s
ingress-nginx-controller-7d49889486-kssbk   0/1     CrashLoopBackOff   2 (23s ago)   49s
PS C:\windows\system32\Ostad-Docker> kubectl logs -n ingress-nginx ingress-nginx-controller-7d49889486-kssbk
exec /usr/bin/dumb-init: exec format error
PS C:\windows\system32\Ostad-Docker> git add .
>> git commit -m "Update Kubernetes YAMLs"
>> git push
>>
warning: LF will be replaced by CRLF in namespace.yaml.
The file will have its original line endings in your working directory
[main 31a4c4d] Update Kubernetes YAMLs
 5 files changed, 155 insertions(+)
 create mode 100644 mongo-deployment.yaml
 create mode 100644 mongo-express-deployment.yaml
 create mode 100644 namespace.yaml
 create mode 100644 ostad-server-deployment.yaml
 create mode 100644 ostad-ui-deployment.yaml
remote: Permission to mdarifahammedreza/Ostad-Docker.git denied to rahatkutubi.
fatal: unable to access 'https://github.com/mdarifahammedreza/Ostad-Docker/': The requested URL returned error: 403
PS C:\windows\system32\Ostad-Docker> git remote set-url origin https://github.com/rahatkutubi/Ostad-Docker.git
PS C:\windows\system32\Ostad-Docker> git push -u origin main
To https://github.com/rahatkutubi/Ostad-Docker.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/rahatkutubi/Ostad-Docker.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
PS C:\windows\system32\Ostad-Docker> git pull origin main --rebase
warning: no common commits
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), done.
From https://github.com/rahatkutubi/Ostad-Docker
 * branch            main       -> FETCH_HEAD
 + d032840...adc1597 main       -> origin/main  (forced update)
First, rewinding head to replay your work on top of it...
Applying: Update Kubernetes YAMLs
PS C:\windows\system32\Ostad-Docker> git push -u origin main
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 12 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (7/7), 1.29 KiB | 1.29 MiB/s, done.
Total 7 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/rahatkutubi/Ostad-Docker.git
   adc1597..d691a3c  main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
PS C:\windows\system32\Ostad-Docker> git push -u origin main --force
Everything up-to-date
Branch 'main' set up to track remote branch 'main' from 'origin'.
PS C:\windows\system32\Ostad-Docker>
