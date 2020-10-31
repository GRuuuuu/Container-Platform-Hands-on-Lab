# LAB04. 애플리케이션 실행하기
Kubernetes 에 배포된 애플리케이션을 실행해 보도록 하겠습니다.   
외부에서 해당 서비스를 호출하는 방법으로는 `Nodeport` 를 사용해볼 예정이며,  배포된 애플리케이션의 서비스를 호출하기 위한 IP 및 포트 정보는 아래와 같이 두가지 방법을 이용하여 검색해 볼 수 있습니다.  

두 가지 방법 중 하나를 이용하여 애플리케이션을 실행해 보겠습니다.  


1. kubectl 명령어 이용
2. Kuberentes 대시보드 이용  

## 1. Kubectl 명령어 이용
실행되고 있는 애플리케이션의 Pod 를 찾아 가는 방법은 Pod 에 연결되어 있는 서비스를 검색하여, 서비스를 호출할 수 있습니다.   

1. 애플리케이션 Pod 의 이름을 검색 합니다.  
~~~sh
$ kubectl get pods -n <eduxx>
~~~
![image](https://user-images.githubusercontent.com/15958325/94143667-1eee0700-feab-11ea-89e5-e531d315b558.png)  

2. Pod 의 public IP 를 확인합니다. `ibmcloud ks cluster ls` 로 클러스터의 이름을 확인 후,  Worker Node 의 정보를 확인합니다. (WorkerNode 중 아무거나 선택)    
~~~sh
$ ibmcloud ks cluster ls
$ ibmcloud ks workers --cluster < cluster name > 
~~~
![image](https://user-images.githubusercontent.com/15958325/94144441-16e29700-feac-11ea-94ce-8853106888ff.png)  


3. 서비스의 Nodeport 를 검색합니다. 
~~~sh
$ kubectl get services -n <eduxx>
~~~
![image](https://user-images.githubusercontent.com/15958325/94144683-6f199900-feac-11ea-846c-68babd7ce4d1.png)  

4. 위에서 확인한 Pubic IP 와 Node port 를 이용하여 애플리케이션을 실행해 봅니다.  
브라우저를 열어 `https:// <Node External IP>:<Node port>`  를 실행하세요.  

![image](https://user-images.githubusercontent.com/15958325/94144892-b142da80-feac-11ea-97af-0f976a73ee57.png)  


## 2. Kubernetes 대시보드 이용
실행되고 있는 애플리케이션의 Pod 를 찾아 가는 방법은 Pod 에 연결되어 있는 서비스를 검색하여, 서비스를 호출할 수 있습니다.   

1. 좌측 상단의 네임스페이스를 default에서 본인이 생성한 eduxx 네임스페이스로 이동합니다.  
![image](https://user-images.githubusercontent.com/15958325/94143875-62e10c00-feab-11ea-8865-a55fceb4e184.png)

2. 아래로 조금 스크롤을 하면 **파드** 섹션이 보입니다.  
자신의 애플리케이션 파드를 클릭합니다.   
또는 대시보드 왼쪽 메뉴 중,  **워크로드** 섹션의 **파드**를 클릭해도 동일한 정보를 찾으실 수 있습니다.   
![image](https://user-images.githubusercontent.com/15958325/94145120-0383fb80-fead-11ea-9e4c-cf26f8b6e8de.png)  

3. 파드의 자세한 정보 페이지가 보이면,  리소스 정보 영역에서 파드가 실행되고 있는 Node 의 IP를 찾아 클릭합니다.  
![image](https://user-images.githubusercontent.com/15958325/94145187-1bf41600-fead-11ea-8fdb-bee77c0f5360.png)  

4. 노드 정보 페이지가 열리면, 리소스 정보 영역에서 ExternalIP 의 정보를 확인합니다.   
![image](https://user-images.githubusercontent.com/15958325/94145442-8442f780-fead-11ea-8069-6493a03950be.png)  

5.  대시보드 왼쪽 메뉴 중,  Service 섹션의 서비스를 클릭하면 애플리케이션 서비스 정보를 확인 할 수 있습니다.   
본인의 애플리케이션 서비스를 찾아 내부 앤드포인트 부분의 Node Port 정보를 확인하세요.   
( Node Port 는 3XXXX 의 값입니다. )  
![image](https://user-images.githubusercontent.com/15958325/94145641-d5eb8200-fead-11ea-9527-c5c641a76c02.png)  


6. 웹 브라우저를 열어 `https:// <Node External IP>:<Node port>` 를 실행하세요.   
![image](https://user-images.githubusercontent.com/15958325/94145773-04695d00-feae-11ea-8dcb-138dfb350aa0.png)  

# NEXT STEP
-> [LAB05. 애플리케이션 확장해보기](https://github.com/GRuuuuu/Container-Platform-Hands-on-Lab/blob/master/LAB05-scale-out.md)  
