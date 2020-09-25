# LAB01. 이미지 Pull 받아서 Docker Hub에 Push하기
지금부터는 샘플 application 이미지를 Pull받아서 자신의 Docker Hub에 Push하는 작업을 진행하겠습니다.  

## 1. Docker Login

~~~sh
$ docker login
~~~

## 2. Sample App이미지 Pulling
~~~sh
$ docker pull kongru/kubeapp
~~~

## 3. 이미지 태그 변경
자신의 도커 id로 태그를 변경해주세요.  
이미지의 이름은 부여받은 번호를 참고하여 edu**xx**kubeapp으로 지정해주세요. (ex. `edu16kubeapp`)  
~~~sh
$ docker tag kongru/kubeapp:latest {DockerID}/{eduxx}kubeapp:v1.0.0
~~~

확인 :  
~~~sh
$ docker images
~~~
![image](https://user-images.githubusercontent.com/15958325/94228843-e72da080-ff38-11ea-9b4c-86e30cd51b0d.png)  




## 4. Registry에 이미지 Push
~~~sh
$ docker push {DockerID}/{eduxx}kubeapp:latest
~~~

# NEXT STEP
-> [LAB02. IKS 클러스터 연결 및 구성](https://github.com/GRuuuuu/Container-Platform-Hands-on-Lab/blob/master/LAB02-connect-cluster.md)