# LAB06. 리소스 삭제하기
kubectl명령어를 사용하여 배포한 리소스를 삭제하겠습니다.  
두 가지 방법이 있습니다. 둘 중 하나의 방법을 사용해서 삭제해주시면 됩니다.  

## 1. 배포하는데 사용한 yaml파일로 삭제  
LAB03에서 deployment.yaml파일을 사용해서 쿠버네티스 클러스터에 deployments와 service를 배포했었습니다.  
파일에 정의된 리소스 정보를 통해 리소스를 삭제할 때도 쉽게 파일을 사용해 삭제할 수 있습니다.  

배포했을때는 `kubectl apply -f deployment.yaml`로 배포했다면,   
삭제할때는 `delete`를 사용합니다.  
~~~sh
$ kubectl delete -f deployment.yaml -n <eduxx>
~~~  

## 2. 리소스별 삭제  
리소스별로 삭제할수도 있습니다.   

~~~sh
$ kubectl delete service <deployment name> -n <eduxx>
$ kubectl delete deployments <deployment name> -n <eduxx>
~~~
![image](https://user-images.githubusercontent.com/15958325/94148906-31b80a00-feb2-11ea-8942-aa9849621282.png)  

**지금까지 Kubernetes 관련 실습을 모두 마치셨습니다.  수고하셨습니다.**

----