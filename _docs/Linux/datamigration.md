---
title: migration
category: Linux
order: 3
---

### dd
dd if=[입력 대상] of=[출력 대상]

> 디스크 복제 [*목적지 디스크 언마운트]  
  dd if=/dev/sdb1 of=/dev/sdc1 bs=1024  
  if= 입력대상 of= 출력대상 bs= 읽고 쓸 최대 크기  

> 디스크 파티션 삭제  
  dd if=/dev/zero of=/dev/sda count=1 bs=512  
  if= 입력대상 of= 출력대상 읽고 쓸 최대 크기 count= 지정 수 많큼 복사  

> 디스크 초기화 # dd if=/dev/zero of=/dev/sdb1  
  if= 입력대상[/dev/zero는 고정] of= 출력대상  