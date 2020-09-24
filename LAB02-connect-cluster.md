# LAB02. IKS 클러스터 연결 및 구성
## 1. WEB으로 클러스터 액세스하기

1. IBM Cloud Portal 에서 사용자 계정을 "1653185 - IBM" 로 변경 합니다.    
![image](https://user-images.githubusercontent.com/15958325/94113628-23ea9080-fe82-11ea-8a4d-8da4f79f92b0.png)   


2. 왼쪽 상단의 햄버거 마크를 눌러 `Kubernetes >> 클러스터` 로 이동합니다.   
![](https://gblobscdn.gitbook.com/assets%2F-MDXHogCOGHdFvq3uZkw%2F-ME5mp8nm5PAnZH_Yr50%2F-ME6AGAcuXLotqajLqzT%2Fimage.png?alt=media&token=92ed6eae-eda3-4561-baf8-9fca077e68f9)  

3. 실습을 위해 생성된 클러스터를 확인하실 수 있습니다.  클러스터 이름을 클릭하세요.  
![image](https://user-images.githubusercontent.com/15958325/94113755-57c5b600-fe82-11ea-8ffd-6347407cf3af.png)  


4. 클러스터의 요약 정보 및 상태를 확인 합니다.   
![image](https://user-images.githubusercontent.com/15958325/94113834-75931b00-fe82-11ea-85b6-c5c8c66e1fdb.png)  


5. Kubernetes 내의 리소스 관련 정보는 오른쪽 상단의 Kubernetes 대시보드 를 클릭합니다.  
![image](https://user-images.githubusercontent.com/15958325/94113952-a07d6f00-fe82-11ea-8a7f-1578fd939d7a.png)  

이상으로 웹으로 IKS 클러스터를 접속해 보았습니다. 

## 2. CLI으로 클러스터 액세스하기

1. 로컬 환경의 명령창을 열고 Cloud 에 로그인하여,  `1653185 - IBM` 계정으로 연결합니다.   
~~~sh
$ ibmcloud login
~~~  
- Email : ibmcloudeduXX@gmail.com
- password : ibmcloudeduXX 계정의 패스워드
- 계정선택 : `1653185 - IBM` 선택  

![image](https://user-images.githubusercontent.com/15958325/94114122-e1758380-fe82-11ea-9a2e-5b206872a9b9.png)   

2. 클러스터의 이름을 확인 합니다.   
~~~sh
$ ibmcloud ks cluster ls
~~~
![image](https://user-images.githubusercontent.com/15958325/94114423-4f21af80-fe83-11ea-94f5-b45fca9fcf9a.png)  

3. 다음 명령어를 실행하여 클러스터의 구성을 다운로드 합니다. 
~~~sh
$ ibmcloud ks cluster config --cluster < 클러스터 이름 >
~~~
![image](https://user-images.githubusercontent.com/15958325/94114561-78dad680-fe83-11ea-91b1-ba1efc74fd77.png)  

4. 클러스터 요약 정보를 확인합니다.   
~~~sh
$ ibmcloud ks cluster get --cluster < 클러스터 이름 >
~~~
![image](https://user-images.githubusercontent.com/15958325/94114646-9740d200-fe83-11ea-80d0-89bd8ad1a16d.png)  


5. 클러스터의 작업자 노드를 확인해 봅니다. 작업자 노드 확인은 ibmcloud ks 명령어 또는 kubectl 명령어를 사용할 수 있습니다.    
~~~sh
$ ibmcloud ks workers --cluster < 클러스터 이름 >
$ kubectl get nodes
~~~
![image](https://user-images.githubusercontent.com/15958325/94129807-cc0a5480-fe96-11ea-9126-62373a94b5d1.png)  


이제 로컬 환경에서 IBM Cloud 에서 생성된 kubernetes 클러스터에 액세스 할 수 있습니다.    

# NEXT STEP
-> [LAB03. IKS클러스터에 애플리케이션 배포하기]()  
