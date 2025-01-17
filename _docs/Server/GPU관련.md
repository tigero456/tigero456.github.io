---
title: GPU관련
category: Server
order: 6
---
> **nouveau blacklist setting**  
    - nouveau : 리눅스에 기본으로 탑재된 nvidia용 그래픽 드라이버
    - 누보가 로딩되어 있으면 nvidia 드라이버와 충돌이 발생해 설치가 제대로 되지 않음
    # echo -e "blacklist nouveau" > /etc/modprobe.d/blacklist.conf
    # echo -e "options nouveau modeset=0" >> /etc/modprobe.d/blacklist.conf
	- nouveau 모듈을 비활성화 하기 위한 작업 (설치전에 해두면 설치과정에서 오류 메시지가 안보임)
    # dracut -f
	- initramfs 초기 램 디스크 이미지 생성
    # grub2-mkconfig -o /boot/efi/EFI/redhat/grub.cfg
	- grub.cfg 파일 재빌드
    #reboot
  
> **check**
    # lsmod | grep nouveau
	**lsmod : 현재 시스템에 설치되어 있는 모듈들의 목록을 보여줌
	- cat /proc/modules와는 비슷하지만 lsmod가 더 깔끔한 형식
  
> **permit 추가**  
    # chmod +x ./NVIDIA-Linux-x86_64-550.90.12.run
    # chmod +x ./cuda_12.6.2_550.90.12_linux.run

> **nvidia driver 설치**  
    # ./NVIDIA-Linux-x86_64-550.90.12.run
    yes / enter / enter / rebuild / enter
  
> **cuda 설치**  
    # ./cuda_12.4.1_550.54.15_linux.run
    accept / driver 체크 해제 / install
  
> **cudnn 설치**  
    # echo -e "export PATH=/usr/local/cuda-12.4/bin:$PATH" >> /etc/bashrc
    # echo -e "export LD_LIBRARY_PATH=/usr/local/cuda-12.4/lib64:$LD_LIBRARY_PATH" >> /etc/bashrc
    # nvcc --version
    - PATH의 cuda 버전은 설치한 cuda 버전과 동일해야 한다
    - PATH 수정 경로 : /etc/bashrc
  
> **cudnn install with tar file**  
    # tar -xvf ./cudnn-linux-x86_64-9.5.0.50_cuda12-archive.tar.xz
    # cd ./cudnn-linux-x86_64-9.5.0.50_cuda12-archive
    # cp include/cudnn*.h /usr/local/cuda/include 
    # cp -P lib/libcudnn* /usr/local/cuda/lib64 
    # chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*
  
> **check install cudnn**  
    # cat /usr/local/cuda/include/cudnn_version.h | grep CUDNN_MAJOR -A 2

Driver 다운로드  
### NVIDIA  

  
### cuda  

  
### cudnn  

   