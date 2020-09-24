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


## 3. Docker 설치 및 Docker Hub 계정 생성
다음 링크를 참조하여 설치와 도커 계정을 생성해줍니다.    
--> [Get Started with Docker](https://www.docker.com/get-started)

도커 설치 확인 :   
~~~sh
$ docker -v
~~~

![image](https://user-images.githubusercontent.com/15958325/94016909-b5f28a80-fde9-11ea-951f-01cb1565c96d.png)  


## 4. IBM Cloud Login
### 4.1 WEB으로 로그인하기
1. IBM Cloud 웹사이트로 이동합니다  ( https://cloud.ibm.com )

2. 강사로 부터 전달받은 계정 정보를 넣고 로그인 합니다.  
    - 계정 : ibmcloudeduXX@gmail.com
    - 패스워드 : XXXXXXXX

3. 왼쪽 상단의 관리를 클릭하고, 계정 메뉴를 선택합니다.  

![](https://gblobscdn.gitbook.com/assets%2F-MDXHogCOGHdFvq3uZkw%2F-ME1xLfJqKeikXdauZJV%2F-ME2BFnezEBZl3mxCkrK%2Fimage.png?alt=media&token=7a233aba-04c6-4106-85c6-93ba51eab19d)

4. 왼쪽 메뉴 패널에서 "Cloud Foundry 조직" 을 클릭하면 오른쪽 화면에 본인의 조직정보를 확인 하실 수 있습니다.  
( 일반적으로 계정 이메일과 동일) 조직의 이름을 클릭하세요.    

![](https://gblobscdn.gitbook.com/assets%2F-MDXHogCOGHdFvq3uZkw%2F-ME1xLfJqKeikXdauZJV%2F-ME2CHcnwinLrTItoEHk%2Fimage.png?alt=media&token=85f646a8-f61b-4459-8b35-c21653fbdc25)  

5. 조직의 위치 정보를 확인합니다.   

![](https://gblobscdn.gitbook.com/assets%2F-MDXHogCOGHdFvq3uZkw%2F-ME1xLfJqKeikXdauZJV%2F-ME2CpKsvNszVTgTFBDX%2Fimage.png?alt=media&token=d8afcff2-b0e1-498a-97b7-565d8cbec41f)  

>**[참조] 지역 정보**
>지역(`region`)은 IBM Cloud 리소스가 프로비저닝된 지리적 위치입니다.  
>예를 들어, 허용되는 값은 `us-south`, `us-east`, `au-syd`, `eu-gb`, `eu-de` 및 `jp-tok`입니다.

6. 리소스 그룹을 확인 합니다.   

![](https://gblobscdn.gitbook.com/assets%2F-MDXHogCOGHdFvq3uZkw%2F-ME2JncXnzj0iaLjLbMs%2F-ME2L-nueFgjlIwW-T__%2Fimage.png?alt=media&token=d624fcab-56fb-48f9-a6f6-54a942b488df)  

### 4.2 CLI로 로그인하기
1. 명령창 ( Mac OS : 터미널 ) 을 실행하여 ibmcloud 명령어를 실행합니다  
~~~sh
$ ibmcloud login 
~~~

- Email : ibmcloudeduXX 계정 이메일
- Password : 패스워드
- 계정선택 : EducationXX IBM Cloud's Account 선택
- region : 4.1에서 확인한 본인의 조직이 생성된 지역을 선택합니다. 

> 로그인 할 때 설정된 지역은 추후에 아래 커맨드로 변경이 가능합니다.  
>~~~sh
>$ ibmcloud -r [region] 
>~~~ 

2. 리소스 그룹을 설정합니다.   
( 4.1 에서 확인한 본인의 리소스 그룹을 넣으세요 `default` 또는 `Default` 입니다.)   
~~~sh
$ ibmcloud target -g < resource-group >
~~~

3. 액세스가 정상적으로 되었는지 확인 합니다. 
~~~sh
$ ibmcloud target
~~~

# NEXT STEP
-> [LAB01. 이미지 Pull 받아서 Docker Hub에 Push하기]()