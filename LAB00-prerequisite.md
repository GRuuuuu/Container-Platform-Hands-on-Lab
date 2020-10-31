# LAB00. Prerequisite
본 실습을 위해서는 로컬 환경에 다음 항목이 필요합니다.   
원할한 실습을 위하여 실습이전에 환경을 구성하세요.   
- IBM Cloud CLI : IBM Cloud API와 상호작용하기 위한 명령행 인터페이스입니다.
    - IBM Cloud Kubernetes Service 플러그인(`kubernetes-service`)
    - Container Registry 플러그인(`container-registry`)
- Docker 엔진 : 컨테이너라고 하는 패키지로 소프트웨어를 제공하고 실행합니다. 
- `kubectl`: Kubernetes 클러스터에 대한 명령을 실행하기 위한 명령행 인터페이스입니다.
- `helm`: Kubernetes 애플리케이션 관리를 도와줍니다. Helm Charts는 가장 복잡한 Kubernetes 애플리케이션을 정의하고, 설치하고, 업그레이드하는 데 도움을 줍니다.

## 1. IBM Cloud CLI 설치

### Mac & Linux
~~~sh
$ curl -sL https://ibm.biz/idt-installer | bash
~~~

### Windows 10 Pro
**관리자 권한**의 **Powershell**에서 실행하세요.
~~~sh
$ [Net.ServicePointManager]::SecurityProtocol = "Tls12, Tls11, Tls, Ssl3"; iex(New-Object Net.WebClient).DownloadString('https://ibm.biz/idt-win-installer')
~~~

### 참고
위 방법이 제대로 동작하지 않는다면 아래 링크에서 Installer를 받아 실행하세요.  
[IBM-Cloud/ibm-cloud-cli-release](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/)  


### 설치 확인
~~~sh
$ ibmcloud -v
~~~

## 2. IBM Cloud Plugin 설치
### 2.1 Kubernetes command-line tool
**Mac**  
~~~sh
$ curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
~~~

**Linux**  
~~~sh
$ curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
~~~

**Windows**   
~~~sh
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
~~~

### 2.2 IBM Cloud Kubernetes Service & Container Registry CLI plug-in
~~~sh
$ ibmcloud plugin install container-service
~~~

~~~sh
$ ibmcloud plugin install container-registry
~~~

설치를 완료하고 나서 list명령어로 확인해줍니다.  
~~~sh
$ ibmcloud plugin list
~~~
![image](https://user-images.githubusercontent.com/15958325/94016418-0b7a6780-fde9-11ea-8509-2303f1cfb88d.png)




# NEXT STEP
-> [LAB01. IKS 클러스터 연결 및 구성](https://github.com/GRuuuuu/Container-Platform-Hands-on-Lab/blob/master/LAB01-connect-cluster.md)