# TCP/IP_1

- [x] TCP/IP의 정의
- [x] 역사 및 배경
- [x] TCP/IP 구조
  - [x] 응용 계층
  - [x] 전송 계층
  - [x] 인터넷 계층
  - [x] 네트워크 인터페이스 계층
- [x] TCP/IP 흐름
- [x] 페이로드와 패킷
- [x] 참고 자료

본 자료는 [냐옹아멍멍해봐](https://better-together.tistory.com/82?category=887984)님의 자료를 기반으로 **그림으로 쉽게 이해하는 웹/HTTP/네트워크**의 내용을 덧붙혀서 작성했습니다.

---

## TCP/IP의 정의

---

<br/>

- 인터넷 프로토콜 스위트라고 하며, 인터넷에서 컴퓨터들이 서로 정보를 주고 받는데 사용하는 프로토콜의 집합이다.
- TCP는 Transmission Control Protocol의 약자로, 스트림 전송 서비스를 제공하는 **연결 지향적** 프로토콜이다.
  - 데이터 전송 중 발생할 수 있는 오류를 처리하고, 패킷의 **순서**가 바뀌는 것을 방지하며, 네트워크의 혼잡도를 관리한다.
- IP는 Internet Protocol의 약자로, 데이터 패킷을 소스에서 목적지로 라우팅하는 비연결형 프로토콜이다. IP주소 시스템을 사용해서, 식별하고 통신할 수 있다.

<br/>

- TCP/IP는 데이터를 패킷으로 나누어서 전송한다. 각 패킷은 독립적으로 네트워크를 통해 전송되며, 최종 목적지에서 다시 원래의 **순서**대로 조립된다.
- 또한 서로 다른 하드웨어 또는 네트워크 구조에서도 동작이 가능해, 다양한 네트워크를 하나의 네트워크로 통합할 수 있다.
- 여러 계층으로 구성이되어있기에, 계층마다 특정 기능에만 집중할 수 있게 한다.

<br/>

## 역사 및 배경

---

<br/>

- TCP/IP는 1960년대 미국 방위성 연구 프로젝트(ARPANET)의 일환으로 개발되었다.
- 인터넷의 성장과 함께 표준화되었으며, 1983년에는 ARPANET의 공식 프로토콜로 채택되었다.
- TCP는 기존 전쟁으로 인해 통신이 회선 교환 방식으로만 이루어 졌던게 패킷 교환으로 바꾼 사례이다.
- 기존에는 회선 교환 방식으로 하나의 선으로 통신을 주고 받았는데, 전쟁으로 미사일이나 폭탄으로 선이 끊어질 경우, 통신이 불가능 하다.
- TCP는 하나의 선이 아닌 서로 연결가능한 선들이 단 1개 라도 존재하면 통신이 끊어지지 않고 계속될 수 있게 된다.

<br/>

## TCP/IP 구조


---

<br/>

![image](https://user-images.githubusercontent.com/56383948/257676190-28a3d12b-e160-45b3-add3-82d1623162ee.png)


### 응용 계층

<br/>

- 사용자와 네트워크 사이에서 인터페이스를 제공하며, 사용자가 네트워크를 통해 서비스를 이용하고 응용 프로그램을 실행할 수 있게 한다.
  - 응용 계층에서 사용자와 가장 가까운 계층으로 다양한 사용자의 요구와 응용 프로그램에 대응하기 위해 설계되었다.
  - 응용 계층에서 다양한 프로토콜이 동작하며, 각각의 프로토콜은 특정한 서비스나 기능을 담당한다.

- 응용 계층의 다양한 프로토콜로는 HTTP, FTP, SMTP, DNS, SSH가 존자한다.
  - `HTTP` : 웹 브라우징을 가능하게 하는 프로토콜로, 서버와 클라이언트 간에 HTML 문서 등의 자원을 전송하는 프로토콜이다. (80)
  - `FTP` : 파일 전송을 관리하는 프로토콜로, 서버와 클라이언트 사이에서 파일을 업로드하고 다운로드한다. (20, 21)
  - `SMTP` : 이메일 전송을 담당하는 프로토콜로, 이메일 서버 간의 메시지 전송과 중계를 처리한다. (25)
  - `DNS` : 도메인 이름을 IP 주소로 변환하는 서비스로, 사용자가 기억하기 쉬운 도메인 이름을 사용한다. (53)
  - `SSH` : 암호화된 네트워크 연결을 제공해서, 원격 서버에 안전하게 접속할 수 있게 해주는 프로토콜이다. (22)

<br/>

![image](https://user-images.githubusercontent.com/56383948/261039093-d6500aee-ea5f-4270-a1fd-d3a9e65cd170.png)


<br/>

### 전송 계층

<br/>

- 전송 계층에서는 데이터를 어떻게 전송할지에 따라, 2개의 프로토콜로 나뉘게된다.
- 데이터를 전송할 때, 신뢰해야하고, 순서가 보장되며, 데이터를 정확하게 전달하기 위해, 전송 속도를 조절하거나, 데이터가 올바르게 왔는지 여부를 알고 재요청을 하는 기능이 포함된 TCP 프로토콜이 존재한다.
- 데이터의 일부가 유실되어도, 순서가 보장되지 않아도, 빠르고 효율적으로 데이터를 전송하는 UDP 프로토콜이 존재한다.
- 웹, 이메일과 같이 데이터의 신뢰성, 순서가 중요한 경우 TCP를 사용하며, 동영상 스트리밍 처럼, 데이터가 일부 유실되더라도 원할하게 볼 데이터의 경우 UDP를 사용한다.

- TCP
  - `신뢰성` : 패킷 손실이 발생하는 경우, 요청이 들어오고 다시 재전송을 한다.
  - `흐름 제어` : 수신자와 송신자 사이 데이터 전송 속도를 조절해서 혼잡도를 낮춘다.
  - `순서 보장` : 패킷이 도착한 순서대로 재조립된다.
  - `연결 지향성` : 전송 전에 송신자와 수신자 간의 연결을 설정한다.
- UDP
  - `비연결 지향성` : 연결을 설정하지 않고 데이터를 뿌린다.
  - `신뢰성` : 패킷 손실이 발생해도 다시 전송하지 않는다.
  - `속도` : TCP와 달리 오버헤드가 적어 빠르게 전송이 가능하다.

- 전송 계층은 데이터의 전달과 네트워크의 자원을 효율적으로 활용하기 위해 설계되었다.

<br/>

![image](https://user-images.githubusercontent.com/56383948/261040787-9bac46f0-68cd-4c84-8ea6-6117425cd721.png)


<br/>

### 인터넷 계층

<br/>

- 인터넷 계층은 데이터 패킷을 **송신지**에서 **수신지**까지 전달하는 역할을 담당한다.
- `라우팅`, `주소 지정`, `패킷 분할 및 재조립` 기능을 제공한다. 

> 네트워크와 네트워크를 연결하여 직접 연결되지 않은 컴퓨터 간에 데이터 통신을 구현하는 역할을 한다. 그리고, 인터넷 계층에서 네트워크를 연결하고 데이터를 전송하기 위해 반드시 필요한 네트워크 장비가 `라우터`이다.

- 인터넷에 연결된 네트워크 기기인 노드에서 컴퓨터를 호스트라고 한다. 그리고 호스트와 호스트사이에 존재하는 노드를 중간 노드일 때, 인터넷 계층은 호스트에서 호스트까지 데이터가 전송되는 경로를 책임진다. (라우팅은 라우터에서 라우터까지 데이터가 최적의 경로를 찾아가는 연쇄적인 과정이다.)
- 호스트를 식별하기 위해 IP를 사용하며, IP를 기반으로 경로를 찾아간다.


<br/>

![image](https://user-images.githubusercontent.com/56383948/261044054-de0cab9f-bddb-4c72-b4be-e6fd47266431.png)


<br/>

### 네트워크 인터페이스 계층

<br/>

- 네트워크 인터페이스 계층은 물리적 네트워크와 연결되어 있으며, 데이터를 프레임화, MAC 주소 지정, 오류 검출 등을 담당한다.
- 이름 그대로, 인접한 네트워크 **기기**간 전송 매체로 연결되어, 전기 신호나 전파가 도달하는 범위에서 데이터를 전송하게 된다.
- 대표적인 네트워크 인터페이스 계층의 프로토콜로 **이더넷**이 존재한다.
- 사실 네트워크 인터페이스 계층의 프로토콜은 모든 프로토콜을 지원하지만, 대표적으로 **이더넷**을 사용한다. 또한 유일하게 모든 프로토콜을 지원하기 때문에 통신하는 상대방과 같은 프로토콜을 사용할 필요가 없다. 무선 LAN, 유선 LAN이 서로 통신이 가능한 대표적인 이유이다.
- 무선 LAN과 이더넷 프로토콜(CSMA/CD)이 사용하는 물리 주소를 MAC 주소라고 한다.
- IP 주소와 MAC 주소를 매핑하며 관리하는 것을 ARP라고 한다.
  - `프레임화` : 데이터를 네트워크에서 전송할 수 있는 형식으로 변환한다.
  - `MAC` : 데이터 링크 계층의 주소 체계로 사용되는 MAC 주소를 할당한다.
  - `오류 검출` : CRC를 사용해서 데이터 오류를 검출한다.

<br/>

![image](https://user-images.githubusercontent.com/56383948/261046662-6226d616-f56b-4617-b9ec-462e1c4aeadf.png)

<br/>

## TCP/IP 흐름

---

<br/>

![image](https://user-images.githubusercontent.com/56383948/261050845-a31ade0a-5953-4032-82d0-12476e66d9e6.png)


<br/>

## 페이로드와 패킷

---

<br/>

- `패킷` : 패킷은 네트워크에서 데이터를 전송하기 위해 구조화된 형식이다. 패킷은 헤더와 페이로드로 구성되어 있으며, 헤더는 패킷이 어떻게 처리되어야 하는지에 대한 정보를 포함하고 있다.

- `페이로드` : 페이로드는 패킷 내의 실제 데이터 부분을 말한다. 패킷의 헤더가 패킷의 송수신에 필요한 메타데이터를 담고 있다면, 페이로드는 실제 전송하고자 하는 데이터 자체를 담고 있다.

- 즉, 각 계층의 단위인, 메시지, 세그먼트, 데이터 그램, 프레임 등은 패킷으로 분류해도 된다. 네트워크 계층에서 데이터 링크의 패킷은 페이로드이다. 

<br/>

## 참고 자료

---

<br/>

> [TCP/IP 흐름](https://docs.oracle.com/cd/E38901_01/html/E38894/ipov-29.html#ipov-100), [냐옹아멍멍해봐](https://better-together.tistory.com/89), [그림으로 쉽게 이해하는 네트워크](https://www.yes24.com/Product/Goods/118547742), [TCP헤더](https://evan-moon.github.io/2019/11/10/header-of-tcp/), [TCP/IP 특징](https://codedragon.tistory.com/4092)

<br/>