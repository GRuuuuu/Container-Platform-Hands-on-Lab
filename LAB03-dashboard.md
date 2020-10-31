# LAB03. Kubernetes 대시보드에서 리소스 확인하기
지금까지 IBM Cloud CLI 환경으로 애플리케이션 배포 및 생성된 리소스 상태 확인을 해보았습니다.   
이번 단계에서는 Kubernetes 대시보드를 이용하여 리소스 상태를 확인해 보겠습니다. 

1. IBM Clod Portal 에서 사용자를 클러스터 사용 계정으로 변경합니다.   
`1653185 - IBM`  

2. 왼쪽 상단의 탐색메뉴 ( 햄버거표시 )  -> Kubernetes -> 클러스터 메뉴를 선택합니다. 
![](https://gblobscdn.gitbook.com/assets%2F-MDXHogCOGHdFvq3uZkw%2F-ME6vn9xoFvVyF8Zrt6d%2F-MEA_AnKesgGrLWmlFnt%2Fimage.png?alt=media&token=3b0c03d2-0934-43cb-bbba-05a4b0c17053)  

3. Kubernetes 클러스터 리스트가 보이면, 본인의 클러스터를 선택하여 클릭합니다. 
![image](https://user-images.githubusercontent.com/15958325/94113755-57c5b600-fe82-11ea-8ffd-6347407cf3af.png)  

4.  오른쪽 상단의 Kubernetes 대시보드를 클릭합니다. 
![image](https://user-images.githubusercontent.com/15958325/94113952-a07d6f00-fe82-11ea-8a7f-1578fd939d7a.png)    


5. 대시보드는 Overview 페이지로 시작됩니다.      
현재 클러스터의 노드 리소스 상태 ( Memory / CPU ) 및 클러스터내 워크로드 ( 디플로이먼트, 파드, 레플리카셋 ) 의 전체 상태를 확인 하실 수 있습니다.  
![image](https://user-images.githubusercontent.com/15958325/94130469-aa5d9d00-fe97-11ea-9ab3-6857f2e9dce5.png)  

6. 좌측 상단의 네임스페이스를 default에서 본인이 생성한 eduxx 네임스페이스로 이동합니다.  
![image](https://user-images.githubusercontent.com/15958325/94143875-62e10c00-feab-11ea-8865-a55fceb4e184.png)

7. 아래로 스크롤 하면 애플리케이션의 디플로이먼트, 파드 및  레플리카셋의 정보 및 상태를 확인하실 수 있으며, 각 오브젝트를 클릭하면 자세한 정보를 볼 수 있습니다.  
![image](https://user-images.githubusercontent.com/15958325/94143975-873ce880-feab-11ea-8a7a-10e9f0b0758a.png)  



# NEXT STEP
-> [LAB04. 애플리케이션 실행하기](https://github.com/GRuuuuu/Container-Platform-Hands-on-Lab/blob/master/LAB04-application.md)  
