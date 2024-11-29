---
title: MultiPath
category: Linux
order: 1
---

### 멀티패스란
 **SAN 스위치**와 **스토리지 사용 환경**에서 하나의 볼륨이 다중 경로로 표시될 때, **논리적으로 하나의 볼륨으로 묶어주는 기능**이다.  
**하나의 저장소**가 컴퓨터에서 **여러개로 인식**되는 상황에서 그것들을 다시 **하나로 만들어주는 기능**

![MultiPath Image1](/images/multipath.png "구성 예시")

  
위와 같이 연결되어 스토리지에서 서버에 볼륨을 할당해주면 서버는 총 4개의 path로 해당 스토리지 볼륨을 조회하게 된다.  
동일 볼륨을 4가지 경로로 바라복 되는 것이다.
  
![MultiPath Image2](/images/multipath2.png "경로(path) 에시")  
<!--
    <img src="https://url/image.png" width="50" height="50"/>
-->
SAN 스위치를 사용해서 이더넷이 아닌 HBA로 연결하게 되면 디스크를 추가했을 때처럼 인식된다.  
패스 하나당 하나의 볼륨으로 인식되기 때문에 위와 같이 패스가 4개라면 1개의 볼륨이 4개의 볼륨으로 인식된다.  
  
  멀티패스는 동일 볼륨의 경우 하나의 논리적 볼륨으로 인식하게 해주는 기능인데 과거에는 주로 스토리지에서 제공하는 기능이었으나 요즘은 OS에서 멀티패스 설정이 가능하다.  
  
<br></br>




> Signing up with Facebook automatically starts syncing contacts.

To sync your contacts:

1. Open your *User Settings*
2. Select the **Connect Facebook** button
3. Authorise ChatApp

![](//placehold.it/800x600)
