# Roche Interview

### Protool 2.0 archtiecture





![](<.gitbook/assets/image (8).png>)

In vat (Visual architecture team), I use react tech stack to replace markojs/ handlebar/ old jsp framework. &#x20;







### CI/CD

![](<.gitbook/assets/image (13).png>)



1. developer commit the code to github
2. github trigger web hooker to ask jenkins run pipline
3. in pipline, it would initial the testing environment, run unit test, run coverage/ regression,  run `sonar` code quality check, build docker image/ build jar, node package, upload the docker image/ libs to `nexus` repository.
4. In production, it would run jenkins job to deploy the latest version, sanity check, QA testing.



### Roche high level architecture

![](<.gitbook/assets/image (4).png>)



I need to highlight `KaaS` and `PaaS`. Because current environment is more about the `cloud native` ,  kubernetes (k8s) has dramatically simplify the deploy tasks.&#x20;



see also:

{% embed url="https://rancher.com/" %}
rancher
{% endembed %}

{% embed url="https://argo-cd.readthedocs.io/en/stable/" %}
argo cd
{% endembed %}

### Infrastructure layer

![](<.gitbook/assets/image (9).png>)



* production environment: Production environment is the cluster to deploy / run production version application.
* pre-production environment:  The PP environment is for QA/QE/Dev/Dev Ops do deploying and integration testing. It is just a small cluster compare with Production.
* Dev environment: The dev environment is based on open stack cluster. Each developer has 4 VM and could deploy anything they need.

### Platform layer

![](<.gitbook/assets/image (6).png>)

How to manage/scale the platform

![](<.gitbook/assets/image (14).png>)

### My raspberry Pi

How I use docker to manage my family:

![](<.gitbook/assets/image (11).png>)

![](<.gitbook/assets/image (15).png>)

### Finally

Wish roche could save more people who get caner.







