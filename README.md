# jetsonnano
rf. https://developer.nvidia.com/embedded/learn/getting-started-jetson

nvidia 계정 생성 후 젯슨나노에 Os를 깔아준다. Os는 Micro SD 카드를 컴퓨터에 포멧시키고 etcher( https://www.balena.io/etcher/)를 이용해 이미지를 구워즐 수 있다. Jetson Nano Developer Kit SD Card Image를 NVIDIA에서 제공한다.(Jetpack461)
이미지를 구우면  Micro SD 카드를 젯슨나노에 옮기고 컴퓨터 모니터와 HDMI선 및 키보드, 마우스 선을 연결한다.
조립된 젯슨나노를 싱글보드 컴퓨터로 만들어 줄 수 있다.

젯슨나노는 GUI(그래픽 사용자 인터페이스)를 사용하며 계산에는 GPU가 사용된다.

우분투에 reboot를 마치면 초록색 화면이 뜨고 터미널을 연다.

```
sudo apt-get upgrade //업그레이드를 해주고
sudo apt install python3-pip //파이썬을 설치한다.
sudo sh -c 'echo 128 > /sys/devices/pwm-fan/target_pwm'
```

jtop 명령어로 쿨링펜의 온도를 확인하고 온도를 낮춰준다.
카메라 조립 후 젯슨나노에 연결한다.

```
dli@dli-desktop:~$ git clone https://github.com/jetsonhacks/USB-Camera.git
dli@dli-desktop:~$ ls
dli@dli-desktop:~$ cd CSI-Camera
dli@dli-desktop:~/CSI-Camera$ ls
dli@dli-desktop:~/USB-Camera$ python3 CSI-Camera.git //카메라를 작동시킨다.
```
DLI docker이미지를 설치하고, 개발 환경은 젯슨에 모니터를 연결하지 않는 Headless 모드로 동작 시킨다. 
GUI에서 Headless 모드로 바꾸려면 윈도우 power shell에 들어가 도커를 실행해준다.

```
PS C:\> ssh dli@192.168.55.1 //젯슨 나노의 주소는 192.168.55.1로 정해져있다.
dli@dli-desktop:~$ ./docker_dli_run.sh
```

 
