---
title: iscsi
category: Server
order: 5
---
### iSCSI란 (Internet Small Computer System Interface)  
SCSI 프로토콜을 인터넷 프로토콜을 사용해 전송하는 기술  
즉, 인터넷을 통해 데이터를 전송하고 보관하게 됨  
  
### iSCSI 관련 개념  
- Target : Server, 스토리지 제공자 (targetcli 설치 필요)  
- Initiator : Client 스토리지 소비자 (iscsi-initiator-utils 설치 필요)  
- IQN : iSCSI Qualified Name, iSCSI Target/Initiator의 고유 이름 포맷 중 하나  
- targetcli : LinuxIO를 위한 general management 플랫폼  
  
### iSCSI Target 구조 & targetcli 명령  
1.  Backstores : iSCSI 서비스로 제공되는 스토리지 리소스, 스토리지 종류 설정
    - block : 디스크를 파티션 한 파티션장치 (논리 볼륨도 가능)
        ex) backstores/block create name=[이름] dev=[디스크 경로]
    - fileio : 파일 시스템 중 일부 공간
        ex) backstores/fileio create name=[이름] file_or_dev=[생성할 파일 경로] size=  [할당할 사이즈]
    - pscsi : 물리적인 SCSI 장치
    - ramdisk : RAM 공간의 일부
  
2. iscsi : target에 지정된 이름(iqn)
    - iscsi/ create [iqn포맷 이름] -> 자동으로 해당 iqn에 대한 tpg가 생성
    - tpg : target portal group. initiator들이 target에 연결될 수 있도록 하는 설정들의 그룹
        - ACL
            - iSCSI Target에 접속을 허용할 Initiator 리스트
            - Access Control List
            - iscsi/[target iqn이름]/tpg1/acls/ create [허용할 initiator iqn이름]
        - LUN
            - iSCSI Target이 제공하는 논리적 SCSI 장치. Backstore랑 매핑됨
            - Logical Unit Number
            - iscsi/[target iqn이름]/tpg1/luns/ create [매핑할 backstores 경로]
            - scsi/iqn.2021-04.com.haejang:target/tpg1/luns/ create /backstores/fileio/file1
        - Portal : iSCSI Target의 네트워크 주소 - 기본적으로 0.0.0.0:3260으로 설정되어 있음
            - portal 등록 : iscsi/[target iqn이름]/tpg1/portals/ create [ip주소] [포트(기본값 3260)]
            - portal 삭제 : iscsi/[target iqn이름]/tpg1/portals/ delete [ip주소] [포트]
 
   
### Target 서버 구축
iSCSI Target 데몬과 관련 패키지 설치 & 데몬 활성화  

    ▶ targetcli 설치
       # yum install targetcli

    ▶ target 데몬 enable 후 활성화
       # systemctl enable --now target

    ▶ target 데몬 상태 확인
       # systemctl is-active target

  
### Initator 서버 구축