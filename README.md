

# This is Realtimes RTSO-1001 xavier carrierboard install guide

## 설치 환경
   * ubuntu 18.04


## 설치 전 준비해야할 것
   * Realtime에서 제공하는 BSP파일
   * 해당 BSP파일 버전과 호환되는 nvidia Tegra driver
   * 해당 driver에 넣을 tegra_linux_sample file
   * 키보드, 마우스, host pc와 연결할 usb

## Install Guide
1. 먼저 특정 폴더를 지정하여 위의 준비해야할 file들중 BSP, Tegra driver을 다운로드 합니다.  
(ex. xavier 폴더 생성후 해당 폴더 안에 BSP, Tegra driver)
       
2. Tegra driver를 해제하고 생성된 Linux_for_Tegra폴더에서 rootfs폴더로 접근합니다.
      
        cd your_forder_name
        tar -xvf your_Tegraxxx_tar_name
        cd Linux_for_Tegra/rootfs
3. rootfs 폴더에 Tegra_Linux_Sample~~ 파일을 다운해줍니다.  
   그리고 해당 파일을 풀어줍니다. (반드시 sudo를 사용해야합니다.)
   
          sudo tar -jxpf Tegra_Linux_Sample~~

4. 다시 root 폴더로 돌아옵니다. Realtimes BSP파일을 풀어줍니다. 
           
           cd
           cd your_forder_name
           tar -xvf realtimes_L4T_3XXX
5. Realtimes_XX 폴더가 생성되었을텐데 해당폴더로 들어가 install.sh을 실행합니다.
           
           cd Realtimes_XX
           sudo ./install.sh
6. 그리고 다시 Linux_for_Tegra 폴더로 들어가서 apply_binary.sh, realtimes-flash.sh을 실행시킵니다. 

           cd ../Linux_for_Tegra
           sudo ./apply_binary.sh
           sudo ./realtimes-flash.sh  
           typing 1, typing 1
           
           
7. 마지막으로 xavier을 recovery mode로 변경하고 flash 시켜줍니다.  
  
    ps.리커버리 하는 방법은 맨 안쪽 버튼을 누른상태에서 가운데 리셋버튼을 한번 누르고 처음 누른 버튼을 3초뒤에 땝니다.
  
           sudo ./flash.sh jetson-xavier mmcblk0p1


flash가 끝나면 xavier에서 자동으로 booting이 이루어집니다. 
host computer와 xavier의 usb를 해제하고 마우스와 키보드를 해당 c타입 단자에 연결해줍니다.
ubuntu 설치를 진행하고 설치가 끝나면 reboot을 진행해주면 끝납니다.

주의) xavier에서 절대 sudo apt upgrade를 하시면 안됩니다. sudo apt upgrade를 진행하면 BSP에서 가져왔던 binary 파일들이  
      최신데이터로 덮어지면서 usb단자들이 일부 정상작동 하지 않게 됩니다. 

           
      
      

