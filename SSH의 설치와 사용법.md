SSH의 설치와 사용법
==================
- - -
## 0. 기본 개념
### - IP
**IP(Internet Protocol)** 는 컴퓨터 네트워크에서 장치들이 서로를 인식하고 통신하기 위해 사용하는 번호이다. 이는 **내부IP**와 **외부IP**로 나뉘어진다.

>##### 내부IP (사설IP)
- 인터넷 상에서 확인 및 사용할 수 없음
- 네트워크 안에서 내부적으로 사용되는 고유한 주소
- 하나의 네트워크 안에서 유일

>##### 외부IP (공인IP)
- 인터넷 상에서 사용됨
- 전 세계에서 유일

### - 포트 (Port)
**포트(Port)** 는 모뎀과 컴퓨터 사이에 데이터를 주고받을 수 있는 통로 역할을 한다. 특히 IP를 사용할 때 클리언트 프로그램이 네트워크 상의 특정 서버 프로그램을 지정하는 방법으로 사용된다.

>000.000.000.000:**22**의 표기에서 000.000.000.000은 IP 주소를 의미하며 **22는 포트 번호를 의미한다.**

### - 포트 포워딩 (Port Forwarding)
특정 포트에서 다른 포트로 포워드 시키는 것을 말한다.
> 공유기에서 예를 들자. 내 컴퓨터가 외부 ip로 000.000.000.000, 내부 ip로 192.168.0.5를 가진다고 해보자. 이 컴퓨터를 서버로 쓰기 위해 22번 포트에 SSH라는 것을 설정해 놓았다. 이는 내부에서 192.168.0.5:22로 접근이 가능하다. 하지만 외부에서는 192.168.0.5:22를 알지 못하고 집의 ip가 000.000.000.000이라는 것만 알고 있다. 이 때, **공유기 포트포워딩** 설정을 통해 000.000.000.000:12345로 들어오는 신호는 192.168.0.5:22로 보내라고 설정할 수 있다. 이를 통해 외부에서 내부 서버로 접근하도록 할 수 있다.

## 1. SSH란?
**시큐어 셸(Secure Shell, SSH)** 은 네트워크 상의 다른 컴퓨터에 로그인하거나 원격 시스템에서 명령을 실행하고 다른 시스템으로 파일을 복사할 수 있도록 해 주는 응용 프로그램 또는 그 프로토콜을 가리킨다. 강력한 인증 방법 및 안전하지 못한 네트워크에서 안전하게 통신을 할 수 있는 기능을 제공한다.

## 2. SSH의 설치
SSH 클라이언트는 보통 기본적으로 설치되어 있다.  
>**sudo apt-get install openssh-server** 서버 설치  
>**sudo apt-get install ssh** 서버+클라이언트 설치

![install-ssh 1](https://i.imgur.com/SJ9HKBR.png)

명령어와 패스워드를 입력하고, Do you want to continue? 문구가 뜰 경우 y를 입력하자.

![install-ssh 3](https://i.imgur.com/exLUe15.png)  


## 3. SSH 서버 설정
SSH 서버는 /etc/ssh/sshd_config 파일에서 설정을 변경할 수 있다.
>**sudo vim /etc/ssh/sshd_config** 설정 파일 열기

![ssh_config 1](https://i.imgur.com/Fg2FbkB.png)

![ssh-config 2](https://i.imgur.com/qk4TyS4.png)

만약 vim이 설치되어 있지 않다면 설치해 주도록 하자.
>**sudo apt install vim** vim 설치

![install-vim 1](https://i.imgur.com/z7WxX6g.png)
