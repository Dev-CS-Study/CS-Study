# Internet Protocol Suite


: 인터넷 프로토콜 스위트

- 인터넷에서 컴퓨터들이 서로 정보를 주고받는 데 쓰이는 프로토콜의 집합

- 이를 TCP/IP 4계층 모델로 설명하거나, OSI 7계층 모델로 설명하기도 함

- TCP/IP(Transmission Control Protocol/Internet Protocol) 4계층 모델을 중심으로 설명하며, 이 계층 모델은 네트워크에서 사용되는 통신 프로토콜의 집합으로 계층들은 프로토콜의 네트워킹 범위에 따라 4개의 추상 계층으로 구성됨

![](https://velog.velcdn.com/images/sw_smj/post/983d3dad-d4fc-44fe-a05d-9471f1f95caa/image.png)


## OSI 7계층


: 네트워크에서 통신이 일어나는 과정을 7단계로 나눈 것

![](https://velog.velcdn.com/images/sw_smj/post/eda28c65-b845-4c1b-9227-2ff032a75d42/image.png)

> 📌 **OSI 7계층을 나눈 이유?**
> : 통신이 일어나는 과정을 단계별로 파악할 수 있기 때문!
> - 흐름을 한 눈에 알아보기 쉬움
> - 특정한 곳에 이상이 생기면, 다른 단계의 장비/소프트웨어를 건드리지 않고 이상이 생긴 단계만 고치면 되기 때문!


<br>

### **1계층 - 물리계층 (Physical Layer)**


: 주로 전기적, 기계적, 기능적인 특성을 이용해서 통신 케이블로 데이터를 전송하는 단계
- 통신 단위 : 비트 (1, 0으로 나타내어짐)
- 단지 데이터를 전달만 할 뿐, 송수신하는 데이터가 무엇인지, 어떤 에러가 있는지 등에는 전혀 신경 쓰지 않는다.
- 데이터를 전기적인 신호로 변환해서 주고받는 기능만 할 뿐
- 대표적인 통신 장비 : 통신 케이블, 리피터, 허브 등
  ![](https://velog.velcdn.com/images/sw_smj/post/bd6b1c3f-ec11-4f93-b491-2998a74f3c64/image.png)

<br>

### 2계층 - 데이터링크 계층 (DataLink Layer)


: Point to Point간 신뢰성 있는 전송을 보장하기 위한 계층


- 물리계층을 통해 송수신되는 정보의 오류와 흐름을 관리하여, 안전한 정보의 전달을 수행할 수 있도록 도와주는 역할을 함

- 통신에서의 오류를 찾아주고, 재전송도 해줌

- MAC주소를 가지고 통신
  > 📌 **MAC 주소란?**
  > MAC 주소는 사람의 이름처럼 네트워크 카드마다 붙는 고유한 이름이다. 즉, LAN카드 별로 MAC주소를 각각 부여한다.
  > (컴퓨터 네트워크 카드의 MAC 주소는 윈도우 명령창에서 ipconfig /all 명령을 실행해 확인할 수 있다.)

- 통신 단위 : 프레임

- CRC 기반의 오류 제어와 흐름 제어가 필요하다. 네트워크 위의 개체들 간 데이터를 전달하고, 물리 계층에서 발생할 수 있는 오류를 찾아 내고, 수정하는 데 필요한 기능적, 절차적 수단을 제공함

- 주소 체계는 계층이 없는 단일 구조

- 데이터 링크 계층 프로토콜의 예 : 이더넷, HDLC·ADCCP 등의 포인트 투 포인트 프로토콜, 패킷 스위칭 네트워크, LLC·ALOHA 같은 근거리 네트워크용 프로토콜

- 대표적 통신 장비 : 브릿지, 스위치 (MAC주소 사용)

<br>

### 3계층 - 네트워크 계층(Network Layer)


: 여러개의 노드를 거칠때마다 경로를 찾아주는 역할을 하는 계층

- 이 계층에서 가장 중요한 기능은 데이터를 목적지까지 가장 안전하고 빠르게 전달하는 기능(라우팅)

- 논리적인 주소 구조(IP) 부여
  > 📌 **IP**
  > 네트워크 관리자가 직접 주소를 할당하는 구조. 계층적임

- 다양한 길이의 데이터를 네트워크들을 통해 전달하고, 그 과정에서 전송 계층이 요구하는 서비스 품질(QoS)을 제공하기 위한 기능적, 절차적 수단을 제공

- 라우팅, 흐름 제어, 세그멘테이션(segmentation/desegmentation), 오류 제어, 인터네트워킹(Internetworking) 등을 수행

- 대표적 통신 장비 : 라우터, Layer 3 스위치
  
   > 📌 **IP 계층이란?**
   > TCP/IP 상에서 IP계층이란, 네트워크의 주소(IP주소)를 정의하고, IP 패킷의 전달 및 라우팅을 담당하는 계층
   > - OSI 7계층의 네트워크 계층
   > - 하위계층인 데이터링크 계층의 하드웨어적인 특성에 관계 없이 독립적인 역할을 수행
   > - 주요 프로토콜<br>
   >  - IP : 패킷의 전달
   >  - ICMP :패킷 전달 에러의 보고 및 진단
   >  - 라우팅 프로토콜 : 복잡한 네트워크에서 인터네트워킹을 위한 경로를 찾게 해줌
  
  > 📌 **IP 프로토콜(Internet Protocol)이란?**
  >  : TCP/IP 기반의 인터넷 망을 통하여 데이타그램의 전달을 담당하는 프로토콜
  > - 주요 기능
  >   - Routing : IP 계층에서 IP 패킷의 라우팅 대상이 됨
  >   - Addressing : IP 주소 지정
  > - 비연결성 데이터그램 방식으로 전달됨<br>
  >   ➡ 패킷의 완전한 전달을 보장하지 않음
  > - IP 패킷 헤더 내 수신 및 발신 주소를 포함 - IPv4 헤더, IPv6 헤더, IP 주소
  > - 경우에 따라, 단편화가 필요함
  > - TCP, UDP, ICMP, IGMP 등이 IP 데이타그램에 실려서 전송

<br>

### 4계층 - 전송 계층(Transport Layer)


: 통신을 활성화하기 위한 계층

- 보통 TCP프로토콜을 이용함

- 포트를 열어서 응용프로그램들이 전송을 할 수 있게 함

- 양 끝단(End to end)의 사용자들이 신뢰성있는 데이터를 주고 받을 수 있도록 해 주어, 상위 계층들이 데이터 전달의 유효성이나 효율성을 생각하지 않도록 해줌

- 패킷들의 전송이 유효한지 확인하고 전송 실패한 패킷들을 다시 전송

- 종단간(end-to-end) 통신을 다루는 최하위 계층으로 종단간 신뢰성 있고 효율적인 데이터를 전송

- 기능 : 오류검출 및 복구,  흐름제어, 중복검사 등

  > 📌 **TCP 프로토콜(Transmission Control Protocol)이란?**
  > : 전송 계층의 통신 프로토콜의 하나
  > - 양종단 호스트 내 프로세스 상호 간에 신뢰적인 연결지향성 서비스를 제공
  > - 신뢰적인 전송을 보장
      >   - TCP 하위계층인 IP 계층의 신뢰성 없는 서비스에 대해 다방면으로 신뢰성을 제공
  >   - 패킷 손실, 중복, 순서바뀜 등이 없도록 보장
  > - 연결지향적 (Connection-oriented)
      >   - 연결 관리를 위한 연결설정 및 연결해제 필요

  > 📌 **TCP의 연결 성립, 연결 해제 과정**
  >
  > **3-way handshaking** - 연결 과정
  > : 신뢰성을 확보하기 위한 작업
  > ![](https://velog.velcdn.com/images/sw_smj/post/8388a9e8-2b65-4822-9bde-a6a8b5ba7270/image.png)
  > 1. **SYN 단계**
       >   A클라이언트는 B서버에 접속을 요청하는 SYN 패킷을 보낸다. 이때 A클라이언트는 SYN을 보내고 SYN/ACK 응답을 기다리는 SYN_SENT 상태가 된다.
  > 2. **SYN + ACK 단계**
       >   B서버는 SYN요청을 받고 A클라이언트에게 요청을 수락한다는 ACK 와 SYN flag 가 설정된 패킷을 발송하고 A가 다시 ACK으로 응답하기를 기다린다. 이때 B서버는 SYN_RECEIVED 상태가 된다.
  > 3. **ACK 단계**
       >   A클라이언트는 B서버에게 ACK을 보내고 이후로부터는 연결이 이루어지고 데이터가 오가게 되는것이다. 이때의 B서버 상태가 ESTABLISHED 이다.
  >
  > ➡ 위와 같은 방식의 통신이 신뢰성 있는 연결을 맺어 준다는 TCP의 3 Way handshake 방식이다.
  > <br><br>
  > **4-way handshaking** - 연결 해제 과정
  > : 세션을 종료하기 위해 수행되는 절차
  > ![](https://velog.velcdn.com/images/sw_smj/post/60cb4414-82a3-4b85-8da9-a8a3e7e0dc59/image.png)
  > 1. 클라이언트가 연결을 종료하겠다는 FIN플래그를 전송
  > 2. 서버는 일단 확인메시지를 보내고 자신의 통신이 끝날때까지 기다리는데 이 상태가 TIME_WAIT상태다.
  > 3. 서버가 통신이 끝났으면 연결이 종료되었다고 클라이언트에게 FIN플래그를 전송한다.
  > 4. 클라이언트는 확인했다는 메시지를 보낸다.
  > 
  >
  > - **지연 패킷** : 패킷이 뒤늦게 도달하고, 이를 처리하지 못한다면 데이터 무결성 문제가 발생함
  > - **TIME_WAIT** : 소켓이 바로 소멸되지 않고, 일정 시간 유지되는 상태. 지연 패킷 등의 문제점을 해결하기 위해 쓰임. 두 장치가 연결이 닫혔는지 확인하기 위해서도 필요함. (참고 - 윈도우는 4분, 우분투는 60초)
  > - **데이터 무결성(Data Integrity)** : 데이터의 정확성과 일관성을 유지하고 보증하는 것
  
  > 👉 **TCP - 가상회선 패킷 교환 방식**
  > 가상회선 : 데이터를 전송하기 전에 설정되는 논리적 연결(연결 지향형)
  > - 각 패킷에는 가상회선 식별 번호(VCI)가 포함되고, 모든 패킷을 전송하면 가상회선이 해제되고 패킷들은 전송된 순서대로 도착한다.
  > - 패킷마다 라우터가 경로를 선택하는 것이 아니라, 경로를 설정할 때 한 번만 수행한다.
    > ![](https://velog.velcdn.com/images/sw_smj/post/d8eec3f7-bd52-4a88-b753-ff5f9ae82795/image.png)
  
  > 📌 **UDP 프로토콜(User Datagram Protocol)이란?**
  > : 전송 계층의 통신 프로토콜의 하나 (TCP에 대비됨)
  > - 비연결성이고, 신뢰성이 없으며, 순서화되지 않은 Datagram 서비스 제공
  > - 실시간 응용 및 멀티캐스팅 가능
  >   - 빠른 요청과 응답이 필요한 실시간 응용에 적합
  >   - 여러 다수 지점에 전송 가능 (1:多)
  > - 헤더가 단순함
  >   - UDP는 TCP처럼 16 비트의 포트 번호를 사용하나, 헤더는 고정크기의 8 바이트(TCP는 20 바이트) 만 사용. (헤더 처리에 많은 시간과 노력을 요하지 않음)

  > 👉 **UDP - 데이터그램 패킷 교환 방식**
  > 데이터그램 : 데이터를 전송하기 전에 논리적 연결이 설정되지 않으며 패킷이 독립적으로 전송되는 것
  > - 패킷을 수신한 라우터는 최적의 경로를 선택하여 패킷을 전송하는데 하나의 메시지에서 분할된 여러 패킷은 서로 다른 경로로 전송될 수 있다.(비연결 지향형)
  > - 송신 측에서 전송한 순서와 수신 측에 도착한 순서가 다를 수 있다.
  > ![](https://velog.velcdn.com/images/sw_smj/post/6f1e2c66-f6e5-4b81-a415-348828a5e43a/image.png)
  
  > 👉 **정리**
  > - 가상 회선 방식 : 정해진 시간 안이나 다량의 데이터를 연속으로 보낼 때 적합
  > - 데이터그램 방식 : 짧은 메시지의 일시적인 전송에 적합

<br>

### 5계층 - 세션 계층(Session Layer)


: 양 끝단의 응용 프로세스가 통신을 관리하기 위한 방법을 제공하는 계층

- 데이터가 통신하기 위한 논리적인 연결을 함

- 동시 송수신 방식(duplex), 반이중 방식(half-duplex), 전이중 방식(Full Duplex)의 통신과 함께, 체크 포인팅과 유휴, 종료, 다시 시작 과정 등을 수행

- TCP/IP 세션을 만들고 없애는 책임을 짐

- 통신하는 사용자들을 동기화하고 오류복구 명령들을 일괄적으로 다룬다.

- 통신을 하기 위한 세션을 확립/유지/중단 (운영체제가 해줌)

<br>

### 6계층 - 표현 계층(Presentation Layer)


:코드 간의 번역을 담당하여 사용자 시스템에서 데이터의 형식상 차이를 다루는 부담을 응용 계층으로부터 덜어 주는 계층

- MIME 인코딩이나 암호화 등의 동작이 이 계층에서 이루어짐

- ex: EBCDIC로 인코딩된 문서 파일을 ASCII로 인코딩된 파일로 바꿔 주는 것, 해당 데이터가 TEXT/JPG/PNG/GIF인지의 구분 등


<br>

### 7계층 - 응용 계층(Application Layer)


: 최종 목적지로써, 응용 프로세스와 직접 관계하여 일반적인 응용 서비스를 수행하는 계층

- HTTP, FTP, SMTP, POP3, IMAP, Telnet 등과 같은 프로토콜이 있다.
    - FTP : 장치와 장치간의 파일을 전송하는 데에 사용되는 표준 통신 프로토콜
    - SSH : 보안되지 않은 네트워크에서 네트워크 서비스를 안전하게 운영하기 위한 암호화 네트워크 프로토콜
    - SMTP : 전자 메일 전송을 위한 인터넷 표준 통신 프로토콜
  
  > 모든 통신의 양 끝단은 HTTP와 같은 프로토콜이지 응용프로그램이 아니다.

  > 📌 **HTTP 프로토콜(HyperText Transfer Protocol)이란?**
  > : 웹 상에서 웹 서버 및 웹브라우저 상호 간의 데이터 전송을 위한 응용계층 프로토콜
  > - 처음에는, WWW 상의 하이퍼텍스트 형태의 문서를 전달하는데 주로 이용. 현재에는, 이미지,비디오,음성 등 거의 모든 형식의 데이터 전송 가능
  > - 요청 및 응답의 구조 - 동작형태가 클라이언트/서버 모델
  > - 메세지 교환 형태의 프로토콜
  > - 트랜잭션 중심의 비연결성 프로토콜
      >   - 종단간 연결이 없음 (Connectionless)
  >   - 이전의 상태를 유지하지 않음 (Stateless)

<br>

## 계층간 데이터 송수신 과정

![](https://velog.velcdn.com/images/sw_smj/post/ad6ddb80-92b0-4394-977e-94fe72cc1a51/image.png)


**캡슐화 (encapsulation)** : 상위 계층의 헤더와 데이터를 하위 계층의 데이터 부분에 포함시키고, 해당 계층의 헤더를 삽입하는 과정

**비캡슐화 (decapsulation)** : 하위 계층에서 상위 계층으로 가며, 각 계층의 헤더 부분을 제거하는 과정

**PDU (Protocol Data Unit)** : 한 계층에서 다른 계층으로 데이터가 전달될 때, 한 덩어리의 단위

![](https://velog.velcdn.com/images/sw_smj/post/516bb062-3f62-4c83-849a-d9ca95572cd8/image.png)

- 애플리케이션 계층 - 데이터, 메시지
- 전송계층 - 세그먼트
- 네트워크 계층 - 패킷
- 데이터링크 계층 - 프레임
- 물리 계층 - 비트


<br><br>

---

**참고자료**

- [OSI 7계층이란? OSI 7계층을 나눈 이유 - 티스토리 블로그](https://shlee0882.tistory.com/110)

- [[네트워크] 가상회선 패킷 교환 vs 데이터그램 패킷 교 - github 블로그](https://woovictory.github.io/2018/12/28/Network-Packet-Switching-Method/)

- [[ 네트워크 쉽게 이해하기 22편 ] TCP 3 Way-Handshake & 4 Way-Handshake = 티스토리 블로그](https://mindnet.tistory.com/entry/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-22%ED%8E%B8-TCP-3-WayHandshake-4-WayHandshake)

- [[네트워크] 캡슐화와 역캡슐화 - 티스토리 블로그](https://davinchicoder.tistory.com/entry/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%BA%A1%EC%8A%90%ED%99%94%EC%99%80-%EC%97%AD%EC%BA%A1%EC%8A%90%ED%99%94)