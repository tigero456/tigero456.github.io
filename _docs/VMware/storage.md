---
title: storage
category: VMware
order: 4
---

### Storage 개요
![스토리지](/images/storage1.png/)  
> 가상화 환경에서 스토리지는 가상 머신(VM) 및 가상 환경에서 데이터를 저장하고 관리하는 시스템을 의미하고 있다.  
(1) Fibre Channel  
- 주로 SAN (스토리지 영역 네트워크)에서 스토리지 장치를 연결하는 데 사용되는 고속 네트워킹 기술을 의미한다.  
  
(2) FCoE (Fibre Channel over Ethernet)  
- FCoE는 Fibre Channel 프로토콜을 이더넷 네트워크에서 전송할 수 있도록 해주는 기술이다. 기존의 Fibre Channel 스토리지 네트워크를 이더넷 기반의 데이터 네트워크로 통합하여 효율성을 높인 기술이다.  
  
(3) iSCSI (Internet Small Computer Systems Interface)  
- iSCSI는 SCSI 프로토콜을 TCP/IP 네트워크를 통해 전송하는 기술로, 스토리지 장치와 서버 간의 연결을 제공한다.  
  
(4) NAS (Network Attached Storage)  
- NAS는 네트워크에 직접 연결된 스토리지 장치로, 여러 클라이언트가 파일 수준에서 데이터를 공유할 수 있도록 해주는 시스템을 말한다.  
  
### 스토리지 프로토콜의 주요 기능들
![기능](/images/storage2.png/)  
(1) SAN을 통한 부팅 지원  
- SAN(스토리지 영역 네트워크)을 통한 부팅 지원은 가상 머신이나 물리적 서버가 SAN에 연결된 스토리지 장치에서 운영체제를 부팅할 수 있도록 하는 기능을 의미한다.  
  
(2) VMware vSphere Motion  
- VMware vSphere Motion은 가상 머신을 가동 중인 상태에서 다른 호스트로 이동할 수 있는 기능을 말한다.   
- vSphere는 VM의 메모리 상태와 디스크 상태를 실시간으로 복사하여, 사용 중인 VM을 중단 없이 다른 ESXi 호스트로 이동시킬 수 있는기능을 지원하고 있다.  
   
(3) HA (High Availability)  
- HA (High Availability)는 가상 머신의 고가용성을 제공하는 기능이다.  
- ESXi 호스트가 장애가 발생하면 HA가 자동으로 VM을 다른 호스트에서 재시작하여 가용성을 유지할 수 있다.  
  
(4) DRS (Distributed Resources Scheduler)  
- DRS는 가상 머신의 리소스를 자동으로 관리하고 최적화하는 기능이다.  
- DRS는 클러스터 내의 여러 ESXi 호스트의 CPU와 메모리 사용량을 모니터링하고, 부하가 높은 호스트에서 VM을 자동으로 이동시키거나 리소스를 재배분하는 등의 역할을 수행한다.  
  
(5) RDM  
- RDM (원시 디바이스 매핑 지원)은 가상 머신이 물리적 스토리지 장치에 직접 접근할 수 있도록 하는 기능이다.  
- RDM을 사용하면 VM은 SAN의 LUN이나 물리적 디스크에 직접 매핑되어, 마치 로컬 디스크처럼 작동한다.  
  