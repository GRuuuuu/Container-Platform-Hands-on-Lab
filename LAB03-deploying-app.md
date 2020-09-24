# LAB03. IKS클러스터에 애플리케이션 배포하기
Registry 에 푸시한 이미지를 이용하여 IKS 클러스터에 배포합니다. 

## 1. Deployment.yaml파일 수정

IKS 에 배포하기 위해 deployment.yaml 파일을 생성합니다.    
아래 샘플 파일을 다운로드 받아,  애플리케이션 디렉토리 아래에 복사해서 넣습니다.   

[Deployment.yaml]()

deployment.yaml 파일을 열어 Kubernetes 의 오브젝트 ( Deployment & Service ) 의 이름 및 애플리케이션 이미지 위치를 설정합니다.   

### 수정 해야 하는 부분
- < app 이름 >  -> eduxxkubeapp          
(xx 는 01 ~ 16 번사이의 자신에게 부여된 번호 이며, 수정할 부분은 모두 8군데 입니다. )  
- < docker ID> -> 자신의 Docker Hub ID  
( 수정할 부분은 모두 1군데 입니다. )  

![](https://gblobscdn.gitbook.com/assets%2F-MDXHogCOGHdFvq3uZkw%2F-ME6oc8PC6pTEw5vputC%2F-ME6tJXzcQSxK5JIKDdy%2Fimage.png?alt=media&token=8dff21b9-0600-4312-8063-170b7b75854f)  

## 2. Namespace 생성
부여받은 번호를 edu뒤에 붙여 유니크한 네임스페이스를 생성해줍니다.  
~~~sh
$ kubectl create namespace < eduxx >
~~~

## 2. 애플리케이션 배포
애플리케이션 배포를 위해 생성한 YAML 파일을 이용하여,  클러스터에 애플리케이션을 배포합니다.   

~~~sh
$ kubectl create -f deployment.yaml -n < eduxx >
~~~

### Deployment 확인
~~~sh
$ kubectl get deployments -n <eduxx>
~~~
![image](https://user-images.githubusercontent.com/15958325/94143637-14337200-feab-11ea-9a1b-f388eb46bb68.png)
  

### pod 확인
~~~sh
$ kubectl get pods -n <eduxx>
~~~
![image](https://user-images.githubusercontent.com/15958325/94143667-1eee0700-feab-11ea-89e5-e531d315b558.png)
   


### service 확인
~~~sh
$ kubectl get services -n <eduxx>
~~~
![image](https://user-images.githubusercontent.com/15958325/94143717-2dd4b980-feab-11ea-991c-5e1c2d5f8217.png)
   


# NEXT STEP
-> [LAB04. Kubernetes 대시보드에서 리소스 확인하기](https://github.com/GRuuuuu/Container-Platform-Hands-on-Lab/blob/master/LAB04-dashboard.md)  
