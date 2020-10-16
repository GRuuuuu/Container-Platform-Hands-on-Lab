# Container-Platform-Hands-on-Lab

## 실습의 목표

- 애플리케이션을 IKS 클러스터에 배치합니다.
- 클러스터의 상태 및 로그를 모니터합니다.
- Kubernetes 팟(Pod)을 스케일링합니다.


## 사용되는 서비스 
본 실습에서는 아래와 같은 서비스를 사용합니다.  
[Kubernetes Service](https://cloud.ibm.com/kubernetes/catalog/cluster?CAMPAIGN_CODE)  
[DockerHub](https://hub.docker.com/)  
[IBM Cloud Container Registry](https://www.ibm.com/kr-ko/cloud/container-registry)(예정)  


## 구성 아키텍처
![](https://gblobscdn.gitbook.com/assets%2F-MDXHogCOGHdFvq3uZkw%2F-MDXHsfiuIK38O12zw2m%2F-MDXL_clCAMD3lxQPvy_%2Fimage.png?alt=media&token=13ee08ba-9b08-44e0-a77d-ff6cacd2f4c5)  

1. IBM Cloud CLI를 통해 생성된 쿠버네티스 클러스터에 접근합니다.
2. 샘플 이미지를 Docker Hub에서 pull받아, 태그 변경 후 자신의 Docker Hub에 Push합니다.
3. 애플리케이션을 쿠버네티스 클러스터에 배치합니다.
4. 사용자가 애플리케이션에 액세스합니다.


# NEXT STEP
-> [LAB00. Prerequisite](https://github.com/GRuuuuu/Container-Platform-Hands-on-Lab/blob/master/LAB00-prerequisite.md)