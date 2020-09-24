# LAB06. 애플리케이션 확장해보기
애플리케이션의 워크로드가 증가하면,  Pod의 복제본 수를 수동으로 늘릴 수 있습니다. 복제본은 Replica Set 으로 관리 됩니다.    
Replicat Set 을 설정하는 방법은 `kubernetes 대시보드` 또는 `kubectl` 명령어를 이용합니다.   
두 가지 중, 하나의 방법으로 실행해 보세요.    
( 실습에 여러 사람이 몰리는 경우, kubernetes 대시보드가 실행되지 않는 경우가 발생할 수 있습니다. 이 경우 다시 한번 대시보드를 실행해보거나 kubectl 명령어를 이용하는 방법으로 진행합니다. )   

## 1. Kubernetes 대시 보드를 이용하여 애플리케이션 확장하기
1. Cloud Portal 의 왼쪽 상단에 있는 햄버거마크를 눌러 Kubernetes 클러스터 페이지로 이동합니다.   
![](https://gblobscdn.gitbook.com/assets%2F-MDXHogCOGHdFvq3uZkw%2F-MELqlmA0MuUwvRlG92T%2F-MEQiMRltiTyIYxQpr9X%2Fimage.png?alt=media&token=45fe67f7-e3ef-4dfe-a53f-14c6970a52c2)  

2. Kubernetes 클러스터 리스트가 보이면, 본인의 클러스터를 선택하여 클릭합니다. 
![image](https://user-images.githubusercontent.com/15958325/94113755-57c5b600-fe82-11ea-8ffd-6347407cf3af.png)  

3. 오른쪽 상단의 `Kubernetes 대시보드`를 클릭합니다. 
![image](https://user-images.githubusercontent.com/15958325/94113952-a07d6f00-fe82-11ea-8a7f-1578fd939d7a.png)  

4. 좌측 상단의 네임스페이스를 default에서 본인이 생성한 eduxx 네임스페이스로 이동합니다.  
![image](https://user-images.githubusercontent.com/15958325/94143875-62e10c00-feab-11ea-8865-a55fceb4e184.png)


5. 대시 보드의 디플로이먼트 섹션에서, 본인 앱의 디플로이먼트 오른쪽 :  표시를 클릭하고 `스케일`을 선택합니다.   
![image](https://user-images.githubusercontent.com/15958325/94147319-19df8680-feb0-11ea-9e01-6be7ad85bad8.png)  

6. 리소스 스케일하기 화면이 뜨면,  의도한 레플리카의 수를 3으로 설정하고 스케일을 클릭합니다.   
![image](https://user-images.githubusercontent.com/15958325/94147412-34b1fb00-feb0-11ea-8687-70b3257917fe.png)  


7. 파드가 정상적으로 3개로 복제 되었는지 확인하실 수 있습니다.   
![image](https://user-images.githubusercontent.com/15958325/94147505-51e6c980-feb0-11ea-8581-78e23357a452.png)  

8. 애플리케이션의 워크로드가 감소하면,  복제본의 수도 다시 줄일 수 있습니다.  위와 동일한 방법으로 디플로이먼트 스케일 메뉴를 선택하여 **의도한 레플리카의 수를 1**로 설정하고 **스케일**을 클릭합니다.   
![image](https://user-images.githubusercontent.com/15958325/94147573-6aef7a80-feb0-11ea-95de-3b56cb515c11.png)    

9. 디플로이먼트의 파드수가 1/1 로 변경된 것을 확인하실 수 있습니다.   
![image](https://user-images.githubusercontent.com/15958325/94147645-85295880-feb0-11ea-876d-4813a04cfc61.png)  

## 2. Kubectl 명령어를 이용하여 애플리케이션 확장하기  
1. 다음의 명령어를 실행하여 애플리케이션 Pod 의 현재 수를 확인합니다. 
~~~sh
$ kubectl get pods -n <eduxx>
~~~
![image](https://user-images.githubusercontent.com/15958325/94143667-1eee0700-feab-11ea-89e5-e531d315b558.png)    


2. 애플리케이션 pod 의 복제본 수를 3으로 설정합니다.   
`<deployment name>` 을 알기 위해서는 `kubectl get deployments` 를 실행하세요.   
~~~sh
$ kubectl scale deployment <deployment name>--replicas=3 -n <eduxx> 
~~~  
![image](https://user-images.githubusercontent.com/15958325/94147907-e5b89580-feb0-11ea-88bb-283285d5acaf.png)  

3. 애플리케이션 Pod 의 상태를 확인합니다. 
~~~sh
$ kubectl get pods -n <eduxx>
~~~
![image](https://user-images.githubusercontent.com/15958325/94147980-0385fa80-feb1-11ea-9463-126dcbcc79d8.png)    

4. 애플리케이션의 워크로드가 감소하면,  복제본의 수도 다시 줄일 수 있습니다.  위와 동일한 방법으로 --replicas=1 로 설정한 뒤, Pods 의 상태를 확인해 보세요.  
~~~sh
$ kubectl scale deployment <deployment name> --replicas=1 -n <eduxx>
$ kubectl get pods -n <eduxx>
~~~

![image](https://user-images.githubusercontent.com/15958325/94148229-519afe00-feb1-11ea-9ac5-9b01a1b1dab4.png)  

# NEXT STEP
-> [LAB07. 리소스 삭제하기]()  

