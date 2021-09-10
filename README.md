

# This is Realtimes RTSO-1001 xavier carrierboard install guide

## 설치 환경
   * ubuntu 18.04


## 설치 전 준비해야할 것
   * Realtime에서 제공하는 BSP파일
   * 해당 BSP파일 버전과 호환되는 nvidia Tegra driver
   * 해당 driver에 넣을 tegra_linux_sample file
   * 키보드, 마우스, host pc와 연결할 usb

## Install Guide
    먼저 특정 폴더를 지정하여 위의 준비해야할 file들중 BSP, Tegra driver을 다운로드 합니다. 
       (ex. xavier 폴더 생성후 해당 폴더 안에 BSP, Tegra driver)
       
    첫번째로 Tegra driver를 해제하고 생성된 Linux_for_Tegra폴더에서 rootfs폴더로 접근합니다.
      
      cd your_forder_name
      tar -xvf your_Tegraxxx_tar_name
      cd Linux_for_Tegra/rootfs
      
      

