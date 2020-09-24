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
~~~sh
$ docker tag kongru/kubeapp:latest {DockerID}/kubeapp:v1.0.0
~~~

## 4. Registry에 이미지 Push
~~~sh
$ docker push {DockerID}/kubeapp:latest
~~~

# NEXT STEP
-> [LAB02. IKS 클러스터 연결 및 구성](https://github.com/GRuuuuu/Container-Platform-Hands-on-Lab/blob/master/LAB02-connect-cluster.md)