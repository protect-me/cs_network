> [KOCW | 컴퓨터네트워크 | 한양대학교 | 2015-2 | 이석복](http://www.kocw.net/home/cview.do?mty=p&kemId=1169634)
[KOCW | 컴퓨터네트워크 | 한양대학교 | 2018-2 | 이석복](http://www.kocw.net/home/cview.do?mty=p&kemId=1169634)
>
__위 강의를 수강하며 정리한 내용임을 밝힙니다.__
네트워크 계층을 Top-Down 방식으로 위에서부터 한 겹씩 까보면서 디테일하게 알아보는 강의

<br>
<br>

# 컴퓨터 네트워크 01 소개 | KOCW 한양대 이석복

`OSI 7layer` && `TCP/IP 4layer`
![](https://images.velog.io/images/protect-me/post/0921a125-7567-44fb-a49e-285ddcae3298/image.png)


## Network Structure
(네트워크 구성요소)
1. network edge : applications and hosts
2. network core : routers
3. access networks, physical media : communication links 라우터들을 연결시켜주는 링크

## Network edge
1. end systems (hosts) : run application programs
eg) Web, email
2. client/server model : client host requests, receives service from always-on server
(서버는 항상 연결되어 있으며 클라이언트의 요청을 기다림)
eg) web browser/server; email client/server
3. peer-peer model : minimal use of dedicated servers
eg) Skype, BitTorrent

## Network core
라우터간의 연결들의 집합 

## 데이터 통신방식 
### 1. __connection-oriented service: TCP (Transmission Control Protocol)__
- reliable, in-order byte-stream data transfer : 신뢰할 수 있는, 순차적인 데이터 전송
- flow control : 수신자 혹은 네트워크의 능력 고려하여 받을 수 있는 만큼 전송
- congestion control : 네트워크 막힘 현상시 속도를 낮춰서 전송
사용: HTTP, FTP, Telnet, SMTP(email)

### 2. __connectionless: service UDP (User Datagram Protocol)__
- connectionless: 연결되어있지 않음
- unreliable data transfer: 유실이 있을 수 있음, 순차적이지 않을 수 있음
- no flow control: 받을 수 있던지 말던지 일단 양껏 때려 부음
- no congestion control: 네트워크 현재 상태 그런거 모름
사용: Streaming media, DNS, real time voice
속도가 빠르다는 장점(양 상관없이 때려 부으니까)

*Protocol이란? 데이터 통신을 원활하게 하기 위해 필요한 통신 규약(약속)

## 네트워크를 통한 데이터 전송방식
### 1. __circuit switching__
출발지에서 목적지까지 가는 길을 미리 설정(길을 사용할 edge도 미리 배정)
단점: 동시에 사용 가능한 인원이 적음. 실제 사용자 입장에서는 요청을 하지 않고 머무르는 시간이 더 길 수 있기 때문에 낭비되는 자원이 많음.
ex) 유선전화 / bandwidth 가 1Mpbs이고 1명의 유저당 active 상태에서 100kb/s 사용시 최대 10명의 유저만 사용가능

### 2. __packet-switching__
패킷 순서가 정해져 있지 않으며 패킷을 요청시 공유(statistical multiplexing)
장점: circuit switching처럼 낭비되는 자원이 없음
단점: 패킷 딜레이 발생

## 패킷 딜레이(4가지)
1) nodal processing: check bit errors(패킷 검사)
2) queueing: 큐 순서 대기(라우터에는 큐를 저장하기 위한 버퍼가 존재)
*queue를 초과하는 경우 packet이 유실(__Packet Loss__). 대부분의 packet 유실은 queue 초과로 발생
3) Transmission delay: 큐 순서 도달 후, packet의 첫 bit가 나가기 시작한 순간부터 마지막 bit가 나가기까지 걸리는 총 시간 
4) Propagation delay: 패킷이 다음 목적지까지 가는데 걸리는 전송 시간(광속이기 때문에 케이블의 길이에 비례)

## 패킷 딜레이를 줄이는 방법
1) processing delay: 라우터 성능 업그레이드
2) queueing delay: 사용자 수와 사용량에 의해 결정되므로 제어 불가
3) transmission delay: 케이블 업그레이드(bandwidth를 넓힘)
4) propagation delay: 광속이므로 제어 불가


<br>
<br>


📚 참고
---
[[TCP/UDP] TCP와 UDP의 특징과 차이](https://mangkyu.tistory.com/15)
[[Network] 1. 네트워크 기본 : Network 구성요소, TCP vs UDP, 서킷 스위칭 vs 패킷 스위칭, 패킷 딜레이](https://developyo.tistory.com/243)
[[Network] 2. Application layer : HTTP, Cookie, Web Cache, Conditional GET, SMTP](https://developyo.tistory.com/244?category=746382)
[[네트워크] 한양대 컴퓨터 네트워크 이석복 교수님 2015년 - 1. 컴퓨터 네트워크 기본](https://velog.io/@injoon2019/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%95%9C%EC%96%91%EB%8C%80-%EC%BB%B4%ED%93%A8%ED%84%B0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%9D%B4%EC%84%9D%EB%B3%B5-%EA%B5%90%EC%88%98%EB%8B%98-2015%EB%85%84-1.-%EC%BB%B4%ED%93%A8%ED%84%B0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B8%B0%EB%B3%B8)
[[네트워크] 한양대 컴퓨터 네트워크 이석복 교수님 2015년 - 2. 컴퓨터 네트워크 기본2
](https://velog.io/@injoon2019/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%95%9C%EC%96%91%EB%8C%80-%EC%BB%B4%ED%93%A8%ED%84%B0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%9D%B4%EC%84%9D%EB%B3%B5-%EA%B5%90%EC%88%98%EB%8B%98-2015%EB%85%84-2.-%EC%BB%B4%ED%93%A8%ED%84%B0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B8%B0%EB%B3%B82)


---

<br>
<br>
<br>
<br>


# 컴퓨터 네트워크 02 애플리케이션 계층 | KOCW 한양대 이석복

<br>
<br>

> __TCP/IP 4 Layer__
Application / Transport / Internet / Network Access
강의에서는 아래와 같이 나눔
Application / Transport / Network / Link

- 앱 개발자가 프로그래밍할 때는 application 계층만 신경쓰기 때문에 transport이하 계층을 신경 쓸 필요가 없음
- Client-Server architecture
client는 필요할 때만 요청을 보내고, server는 24시간 같은 장소에서 작동(고정된 주소를 가짐)



## Sockets
![](https://images.velog.io/images/protect-me/post/3f1535a7-281e-4528-90ae-8fbe9d98e0cc/image.png)
- __프로세스는 socket을 통해 message를 주고 받음__
- 소켓이란 OS에서 제공해주는 API 중 하나
- 인터넷상에 존재하는 컴퓨터는 고유한 주소를 갖고 있어야하는데 이를 IP주소라 함.
- IP는 인터넷상에 존재하는 컴퓨터를 찾기 위한 것이고, 그 컴퓨터 안의 프로세를 찾기 위한 것이 port

## What transport service does an app need?
- application layer 는 transport layer에 종속적이며,
transport layer에서 application layer에 다음과 같은 것들 보장받길 원하지만 보장해주지 않음.

1. data integrity: 데이터 무결성(손실이 없음을 보장) => TCP는 이를 보장함
2. timing: 제한 시간 내에 보냄
3. throughput: 처리량
4. security: 보안

TCP를 사용할 경우 `1번`은 보장함. 따라서 나머지 요소들을 Application에서 알아서 처리해야함

## HTTP 
- hypertext transfer protocol: 하이퍼텍스트를 주고 받는데 사용하는 규약(약속)
- WEB's application layer protocol
- request/response로 주고받음
- TCP를 기반 
- default 80번 port 사용
- __stateless__ : 클라이언트의 상태를 저장하지 않음(cookie 사용)

* safari, explorer, chrome 은 모두 다른 application 이지만 모두 같은 HTTP (protocol) 을 사용하므로 브라우저와 무관하게 application 사용이 가능

## HTTP 연결의 두가지 방식
### 1. non-persistent HTTP
- 지속적이지 않은 HTTP
- TCP 커넥션을 HTTP 사용후 close
- 매 http 마다 TCP 커넥션을 새로 맺음(비효율)
- 응답 시간이 persistent 방식보다 더 오래 걸림
- RTT : round trip time(= 패킷 왕복 시간), 패킷을 목적지에 보내고 그 응답이 돌아오기까지의 시간

### 2. persistent HTTP
- 지속되는 HTTP
- 클라이언트/서버 간 하나의 TCP 커넥션으로 여러개의 HTTP 송수신을 수행(고효율)
- 현재 사용하는 HTTP 1.1 버전은 persistent 가 default. (지속커넥션 사용)
- 파이프라인 사용


## Web caches(proxy server)
- origin server에 HTTP 요청을 하는 대신 proxy 서버에 HTTP 요청
- 서버와 클라이언트 사이에 중계기로서 대리로 통신을 수행하는 것을 가리켜 '프록시', 그 중계 기능을 하는 것을 프록시 서버라고 함
- 프록시 서버 중 일부는 프록시 서버에 요청된 내용들을 캐시를 이용하여 저장함
- 이렇게 캐시를 해 두고 난 후에, 캐시 안에 있는 정보를 요구하는 요청에 대해서는 원격 서버에 접속하여 데이터를 가져올 필요가 없게 됨
- 전송 시간과 비용을 절약 + 불필요하게 외부와의 연결을 하지 않아도 되기 때문에 네트워크 병목 현상을 방지하는 효과

### Conditional GET
- Cache에 저장된 데이터가 최신이 아닐 수 있음.(일관성 문제)
- 브라우저로 전달되는 객체들이 최신임을 확인하며 캐싱할 수 있도록 Conditional GET 사용
- HTTP 요청에 If-Modified-Since 헤더 라인 포함.
- 서버에 있는 객체의 마지막 수정된 날짜와 비교.
- 수정된 객체라면 객체를 보내줌 (200 OK + data)
- 최신 상태이면 object를 보내지 않음 (304 Not modified)

## DNS
- Domain Name System
- hostname 를 ip 주소로 해석.
- IP, Port 번호를 일일이 다 기억하기 힘드니, Domain Name으로 접속할 수 있도록 한 시스템
- 전화번호부 역할
- 한 곳에 몰아놓으면 문제가 생기기 때문에 계층화(hierarchial database)

### centralize DNS 사용하지 않는 이유
- 트래픽 집중
- 먼 거리에 위치한 국가의 데이터베이스 접근 불리
- 유지보수
- 에러를 대비한 클러스터링 없음

### TLD, Authoritative Servers
- 보유하고 있는 host name에 대한 관리

### DNS records
- type A(Address), type NS(Name Server) => 두 가지 타입을 쌍으로 저장



>
DNS는 Host Name을 IP 주소로 해석하는 Protocol이며 HTTP 통신을 하기 위한 준비 과정임
DNS HTTP 모두 Application 계층의 Protocol임
DNS는 UDP 기반 / HTTP는 TCP 기반






## Type Of Socket
- __소켓은 TCP(SOCK_STREAM)와 UDP(SOCK_DGRAM) 두가지 타입이 있음__
![](https://images.velog.io/images/protect-me/post/f26dc73a-beb7-487a-9eab-51ff2664c2fc/image.png)

### TCP(SOCK_STREAM)
![](https://images.velog.io/images/protect-me/post/df3c2fb8-c6a5-4ca8-88e5-982ac6fae240/image.png)
[이미지 출처: TCP socket function](https://younghu.wordpress.com/2013/02/21/tcp-socket-function/)
- Server: bind()를 통해 특정 포트번호와 연결
- Server: accept()까지 진행 후 client의 요청이 올 때까지 대기
- Client: 포트를 특정할 필요가 없기 때문에 bind()가 없음



<br>
<br>


📚 참고
---
[[Network] 2. Application layer : HTTP, Cookie, Web Cache, Conditional GET, SMTP](https://developyo.tistory.com/244?category=746382)
[[네트워크] 한양대 컴퓨터 네트워크 이석복 교수님 2015년 - 2. 컴퓨터 네트워크 기본2
](https://velog.io/@injoon2019/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%95%9C%EC%96%91%EB%8C%80-%EC%BB%B4%ED%93%A8%ED%84%B0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%9D%B4%EC%84%9D%EB%B3%B5-%EA%B5%90%EC%88%98%EB%8B%98-2015%EB%85%84-2.-%EC%BB%B4%ED%93%A8%ED%84%B0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B8%B0%EB%B3%B82)


---


<br>
<br>
<br>
<br>

# 컴퓨터 네트워크 03 전송 계층 | KOCW 한양대 이석복

<br>
<br>

![](https://images.velog.io/images/protect-me/post/ff7dc9e1-af61-416a-bc28-a29fd2633d6a/image.png)
[이미지 출처](https://www.rfwireless-world.com/Terminology/Segment-vs-Packet-vs-Frame.html)

## 3.1 Transport-layer
- TCP / UDP 두 가지 방식이 있음

## 3.2 Multiplexing and Demultiplexing
- 프로세스에서 메세지를 보낼 때 알맞은 목적지 프로세스에 보내는 방식
- 발신자: 수많은 인터페이스를 가지고 있지만 나가는 곳은 하나이기 때문에 Multiplexing
- 수신자: 들어오는 곳 하나에서 수많은 인터페이스에 뿌려주는 것이 Demultiplexing


- TCP/UDP 모두 Multiplexing/Demultiplexing을 하지만 방식에서 차이가 있음
- __UDP: Connentionless transport__
port 번호만 보고 주고 받음. 커넥션이 없음.
- __TCP: Connection-oriented transport__
수신자 소켓과 발신자 소켓이 1:1 관계임(고유함)


> 각 소켓은 고유의 포트번호를 가지는 것이 아님.
- TCP에서 source IP / source Port / dest IP / dest Port가 모두 일치하는 소켓을 찾아감
- 즉, 위 4가지 중 한가지만 달라도 다른 소켓으로 Demultiplexing을 함.
- 하나의 프로세스는 여러개의 소켓을 가질 수 있음

## 3.3 Connentionless transport: UDP
- UDP Segment
- header / data
- header: source port / dest port / length / checksum(에러 판단)

## 3.4 Principles of RDT
- RDT: Reliable Data Transfer
- RDT는 TCP 에서는 보장하지만, UDP에서는 보장하지 않음

### rdt 1.0
> __error도 loss도 없는 상황__

### rdt 2.0
> __error는 있는 상황__
__error detection + feedback + Sequence number__

- error detection: checksum

- feedback : ACK(acknowledge) / NAK(negative acknowledge)
client는 segment를 보내고 feedback으로 ACK을 받으면 다음 segment를 전송, NAK을 받으면 재전송

- fatal flaw(치명적 결함) : feedback 자체가 에러일 경우에는 어떻게 할까?
=> 원래는 ACK인데, NAK을 받았을 경우 재전송.
=> server는 중복된 데이터를 다시 받게 됨. 이전에 받은 데이터를 지우고 이걸 써야할지. 아니면 원래 같은 데이터가 중복되는 상황인지 판단할 수 없음
=> 중복된 메세지인지 새로운 메세지인지 판단하기 위해 등장한 것이 Sequence number. 넘버링을 하면 중복 체크가 가능
- Sequence number의 크기를 ++시키면 header의 크기는 무한대로 늘어나기 때문에 `0`과 `1`로 구분

#### rdt 2.2
- feedback은 무조건 ACK을 하는데, Sequence number로 ACK NAK을 판단함 


### rdt 3.0
> __error도 loss도 있는 상황__
__error detection + feedback + Sequence number + Timer__

- client는 segment를 보내면서 timer를 작동 시키고 timeout이 발생하면 loss로 인식해서 재전송

### Pipeline protocols
- 위의 rdt는 신뢰성은 보장이 되나 효율이 매우 좋지 못함
(데이터를 하나씩 주고 받으며 확인하는 절차이기 때문)
- 따라서 여러 데이터를 한꺼번에 주고 받을 수 있는 Pipeline이 등장.

#### go-Back-N
![](https://images.velog.io/images/protect-me/post/777258d0-1e43-4095-97bd-d5ec87aa9976/image.png)
- window 크기 만큼의 데이터를 한 번에 주고 받음
- ACK(n): n번까지 잘 받았다는 feedback
- receiver의 역할이 없음

ex) window size = 4,
`1~4`까지 보내고, window는 전진하다가 window가 `4~7`을 전달.
중간에 `4`를 전송하다 유실이 있었을 경우,
데이터 4, 5, 6, 7을 전달 받았을 때 모두 drop하고 feedback은 모두 ACK(3).
따라서 `4~7`을 다시 보내야하는 비효율 발생.
n만큼 다시 돌아온다고 해서 `go-Back-N`이라 명명함

#### Selective repeat
![](https://images.velog.io/images/protect-me/post/d785013d-cdc8-48a0-afe1-17043798b0cf/image.png)
- `go-Back-N`의 비효율을 개선
- receiver가 buffer 역할을 해주기 때문에 중복되는 데이터를 보내지 않음
receiver는 들어오는 데이터가 순서가 맞지 않더라도 drop시키지 않고 가지고 있음
- 현재 window에 해당하는 데이터를 모두 받을 때까지 기다렸다가 한번에 이동.
- Selective repeat: dilemma
header의 크기를 줄여야하는데 `0`과 `1`로만은 표현이 되지 않음. window크기와 같아도 문제가 발생. 따라서, seq는 window size의 2배 이상이어야함
![](https://images.velog.io/images/protect-me/post/6b0c493a-a5e6-47b1-aeb9-b12b501af76e/image.png)


## 3.5 Connection-oriented transport: TCP
> TCP 특징
- __point-to-point__
: 1:1 매칭
- __reliable, in-order byte stream__
: 신뢰할 수 있으며, 순차적인 바이트 스트림
- __pipelined__
: window size를 가변적으로 설정함(congestion과 flow control을 고려)
- __send & receive buffers__
: 전달, 수신 버퍼가 존재함
- __full duplex data__
: 양방향 데이터 통신
- __connections-oriented__
: 데이터 통신이 일어나기 전에 3 way hand shake를 통해 connection을 맺음
- __flow controlle__
: receiver 혹은 네트워크가 받아들일 수 있는 만큼만 전달(둘 중 최소값을 따름)

### segment structure
![](https://images.velog.io/images/protect-me/post/14332977-67c6-412f-aaa9-c7bd51685a7c/image.png)
- 포트번호 하나에 16bit씩 쓰기 때문에 2^16-1개의 포트번호 사용 가능
- ACK(n): n-1번까지 잘 받았다는 feedback. 즉, 이제 n이 올 차례라는 의미
- receive window는 지금 receiver buffer에 얼마나 빈 공간이 있는가를 알려줌
- setting the timeout
: 데이터를 보내면서 timer를 설정하는데, 타이머의 시간을 어떻게 설정할지
: RTT(round trip Time = 패킷 왕복 시간)의 편차가 시시각각 편차가 크기 때문에 종합적으로 판단

### reliable data transfer
- TCP는 pipeline 방식이다.
- timer expired => 해당하는 segment를 재전송
- segment보내고 feedback으로 ack를 받음
- feedback을 통해 loss를 파악하고 재전송, 따라서 신뢰할 수 있음

### flow control
- sender가 receiver의 용량을 고려해서 segment를 전달(receivr-driven)
- 빈 공간이 얼마나 있는지 정보를 segment에 담아서 전달
- 처음 sender가 보넀을때 receiver가 버퍼에 자리가 없다고 응답을 보내면 sender는 계속해서 아무것도 보내지 않는 상황이 발생할 수 있기 때문에, 아주 작은 데이터를 계속해서 보내고 feedback을 받으면서 receiver buffer의 동향을 살핀다.

### connection management: TCP 3-way handshake
![](https://images.velog.io/images/protect-me/post/558d948d-8d13-4612-8d07-7e952b855202/image.png)
- SYN 비트에 1을 담아 보내면 연결을 맺자는 의미.
- 3번째에는 client에서 segment도 함께 보냄.
- closing TCP Connection

![](https://images.velog.io/images/protect-me/post/8a379bdb-d70d-48d2-824e-a60bc306328b/image.png)
> timed wait이 있는 이유
ack를 보내고 client에서는 close를 했는데, loss로 인해 server에서 ack를 받지 못할 경우 server에서는 계속해서 ack를 기다리게 됨. client는 이미 close를 했기 때문에 ack를 보낼 수 없는 상황. 따라서 약간의 여유를 두고 close를 함.

## 3.6 Principles of congestion control
- TCP에서 segment loss가 일어날 경우, timer expire => 데이터 재전송이 일어남.
- 즉, 네트워크 상태가 좋지 않아서 막혀 있는데, 거기에 계속해서 재전송을 하면서 상태는 더욱 악화 됨.
- 네트워크 상황이 어떤지 어떻게 알아낼까.
### Network-assisted congestion control
- 라우터에서 현재 네트워크 상황을 계속해서 피드백 해준다(?)
- 라우터에서는 데이터를 주고 받는 것만으로도 힘에 부치기 때문에 현실적으로 불가능함

### End-end congestion control
- TCP를 통해 segment를 보냈는데 반응이 느리면 네트워크 상황이 좋지 않다고 유추함.
- TCP는 현재 이 방식을 채택함

## 3.7 TCP congestion control
![](https://images.velog.io/images/protect-me/post/95f0184b-8e19-494f-962d-10053b064e60/image.png)
x: MSS(Maximum Segment Size)
y: congestion window size

### 1. Slow start
- 병목현상이 있을 지도 모르니, 0부터 시작해서 빠르게(지수적) 증가

### 2. Additive increase
- threshold를 만나면(수용량에 가까워지고 있으니), 보수적이고 천천히 증가

### 3. Multiplicative decrease
- 문제가 생기면 한 번에 확 낮춤. 공유 자원이기 때문에 각자 조금씩 줄인다고 해결되지 않기 때문
- CASE 1. `timeout`을 통해 `Loss`를 감지하면 slow start로 돌아감
- CASE 2. `3 duplicated ACK`를 통해 `Error`를 감지하면 반으로 떨어뜨림
(다 잘 가고 있는데 하나만 문제인 상황)

> 여기서 말하는 갯수는 MSS(Maximum Segment Size)
window size(buffer)를 1MSS부터 시작해서 늘렸다 줄였다 한다는 의미
네트워크 상황에 따라 전송속도가 달라지고,
사용자 각각이 네트워크 상황에 영향을 미치기 때문에 서로 영향을 미치는 관계에 있음

## TCP Fairness
- TCP는 개개인들에게 형평성을 어떻게 보장할까?
![](https://images.velog.io/images/protect-me/post/faf27986-60bd-4c4c-9f54-5226f89b5141/image.png)
- 먼저 쓰고 있던 사람이 처음에는 더 높은 속도를 가질 수는 있음
- 후발주자가 들어오면서 loss가 발생하면 Multiplicative decrease를 통해 __모두가__ 속도를 반으로 줄임(MSS를 반으로 줄임)
- 늘리고 줄이고를 반복하다보면 결국 공평해짐
> TCP 각각에게 공평하지만 사용자 단위로 TCP Connection을 많이 여는 사용자가 더 많이 가져가는 맹점이 있음

---
---

## TCP(Transmission Control Protocol)
: 인터넷상에서 데이터를 메세지의 형태로 보내기 위해 IP와 함께 사용하는 프로토콜
![](https://images.velog.io/images/protect-me/post/0c422fac-8cb6-4d31-ab9b-9b463eaef559/image.png)
### UDP(User Datagram Protocol)
: 데이터를 데이터그램 단위로 처리하는 프로토콜
![](https://images.velog.io/images/protect-me/post/f000f5a8-5af4-4392-9aeb-c17b1851363e/image.png)

[이미지 출처](https://mangkyu.tistory.com/15)

<br>
<br>

📚 참고
---
[[네트워크] 한양대 컴퓨터 네트워크 이석복 교수님 2015년 - 7. 전송계층3](https://velog.io/@injoon2019/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%95%9C%EC%96%91%EB%8C%80-%EC%BB%B4%ED%93%A8%ED%84%B0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%9D%B4%EC%84%9D%EB%B3%B5-%EA%B5%90%EC%88%98%EB%8B%98-2015%EB%85%84-7.-%EC%A0%84%EC%86%A1%EA%B3%84%EC%B8%B53)

---


<br>
<br>
<br>
<br>


# 컴퓨터 네트워크 04 네트워크 계층 | KOCW 한양대 이석복

<br>
<br>

![](https://images.velog.io/images/protect-me/post/ff7dc9e1-af61-416a-bc28-a29fd2633d6a/image.png)
[이미지 출처](https://www.rfwireless-world.com/Terminology/Segment-vs-Packet-vs-Frame.html)

> client - router - router - ... - router - server
client, server: Application / Transport / Network / Physical
router: Network / Physical

## 4.2 virtual circuit and dagagram networks
### Two key network-layer functions
#### forwarding
- 포워딩은 라우터의 입력 포트에서 출력 포트로 패킷을 이동시킴(포워딩 테이블을 보고)
#### routing
- 라우팅은 경로를 결정(라우팅 알고리즘을 통해 포워딩 테이블을 관리)

### Forwarding table
- 모든 주소를 적어놓을 수는 없기 때문에 범위로 표현함

### longest prefix matching
- 범위로 적어놓다보니 여러 엔트리에 속하는 경우도 발생
=> 가장 길게 일치하는 prefix로 출력 포트를 배정

## 4.3 what's inside a router
- 입력포트, 출력 포트 모두 queue가 있어서 일을 순차적으로 처리함

## 4.4 IP: Internet Protocol
### datagram format
![](https://images.velog.io/images/protect-me/post/0f0b33e1-3fe7-42c4-86c5-ad097341e387/image.png)

- packet의 최소 단위는 40byte: packet header(20byte) + segment header(20byte)
- time to live
: 각 router를 거칠 때마다 `-1`.
: 네트워크 오류로 인해 router 내부를 무한히 돌 수 있기 때문에 수명을 정해놓음
- upper layer
: 상위 레이어의 정보를 기입(transport의 타입이 무엇인지 TCP or UDP + 이외 정보)

### IPv4 addressing
- IP Address: host가 아니라, 머신의 interface를 지칭함.
ex) router의 경우 interface가 여러개 있기 때문에 IP Address도 다양한 것.
- hierarchical Addressing
: 한 곳에서 모든 IP를 관리하면 forwarding table이 엄청나게 커지고 느려질 것
: 서버에 문제가 발생 시, 모든 네트워크가 마비됨

#### 계층화(hierarchical)
- 확장성이 좋고, 새로운 호스트가 들어와도 말단의 forward table에 간단하게 추가

#### Subnet Mask
![](https://images.velog.io/images/protect-me/post/1cafd9d4-307d-4926-86a0-35aac6534e0d/image.png)
(network id = prefix = IP address = subnet)
ex) 12.34.158.0/24 => 32자리 중에 앞 24자리가 IP 주소이고 그 값은 12.34.158 입니다.
ex) 255.255.255.0 => 32자리 중에 앞 24자리가 IP 주소입니다.

#### Classful Addressing 
- 클래스를 정해서 `/8`, `16`, `/24` 이런식으로 배정을 했는데 비효율적이라 개선함

#### Class Inter-Domain Routing(CIDR)
- 필요한 만큼 합리적으로 나눌 수 있게 됨.
ex) 12.4.0.0/15 ...

> forwarding table은 prefix 단위로 엔트리가 나뉘어있음

#### Subnets
- network id = prefix = IP address = subnet
- subnet: 라우터를 거치지 않고 직접적으로 접근할 수 있는 집합
- 라우터는 여러개의 subnet에 속함

#### NAT
![](https://images.velog.io/images/protect-me/post/ea66cf9a-7863-4daf-a5a4-bfe363b71c91/image.png)
- Network Address Translation
- IPv4: 32bits = 2^32개, 약 40억 => 전 세계적으로 고유한 숫자가 이만큼 뿐
- 이를 보완하기 위해 IPv6를 고안해서 출시했지만 옮겨가지 못하고 있음
- 모든 router를 교체해야하는데 이게 쉽지 않음


- 그렇다면 왜 문제가 발생하지 않고 있는가? => NAT
- 나갈 때 WAN/LAN 주소를  NAT translation table에 기록하고, 들어올 때 table을 보고 다시 매칭함.
- IP 뿐만 아니라, Port번호도 바꿈. 이유는 내부에서는 IP주소가 고유하지, Port번호는 고유하지 않을 수 있기 때문
- 결국 들어올 때는 모두 같은 IP로 들어오기 때문에 내부에서는 port번호로 식별을 한다고 볼 수 있음

> __LAN/WAN__
LAN: Local Area Network
WAN: Wide Area Network

> __부작용__
- Server의 역할을 하기 힘들어짐
Client 역할일 때는 나갈 때 NAT table에 기록되기 때문에 문제가 없지만,
Server 역할일 때는 먼저 나가는 것이 아니라 요청을 기다리고 있는 입장이기 때문에 NAT table에 기록된 나의 고유한 주소가 없음.
- 계층화의 핵심이 무너짐.
Layer로 나뉘어 있는데, 다른 Layer의 정보를 열람해보고 심지어 수정을 가함.
ex) 네트워크 계층에서 packet header의 IP주소를 수정함
ex) 네트워크 계층에서 packet 내부의 segment 내부의 header의 port 번호를 열람함
=> port 번호는 전달 계층에서 애플리케이션 계층으로 올라갈 때 socket을 구분하는 용도인데, IP를 구분하는 용도로 변질됨.

### DHCP
- Dynamic Host Configuration Protocol
- DHCP Server Default port: 67
- DHCP Client Default port: 68

![](https://images.velog.io/images/protect-me/post/7e6a2244-3781-461b-8b4d-d1f16b2d59a2/image.png)
- discover: 새로운 Client는 Server(67 port)로 IP 주소를 요청 함
- offer: 여러 서버들이 client의 discover에 응답함
- request: 여러 서버들 중에 한 서버와 연결을 함. 나머지 offer를 제공한 서버들은 release를 함
- ACK: 연결이 되었다는 feedback을 전달

> DHCP애서 IP를 제공할 때 
- IP address / Subnet mask
- Gateway router IP address
- DNS Server IP address

### IP fragmentation, reassembly
- IP packet이 생성되어서 라우터를 통해서 최종 목적지까지 도달하는데,
- 라우터 사이의 link의 MTU(Maximum Transmission Unit)는 링크마다 다름
- fragmentation(단편화/조각): packet size가 MTU size보다 클 경우, 쪼개서 보냄 
- reassembly(재조립): 쪼개진 packet을 이어붙임
- fragflag(fragmentation flag)쪼개졌을 경우 모두 fragflag가 1이 아니라, 뒤에 남은 쪼개진 조각이 있을 경우에만 `1`
즉, 쪼개지지 않았거나 쪼개진 조각 중 마지막 packet일 경우 `0`
- offset: 쪼개진 packet이 전체 packet에서 시작하는 포인트 나누기8(`/8`) 한 값(header 값 줄이기 위한 노력)

### ICMP
- Internet Control Message Protocol
- 네트워크상에서 발생한 이벤트를 source에 알려주기 위한 프로토콜(네트워크 진단에 쓰일 수 있음)

### IPv6
- address: 128bits
#### Tunneling
- 버전을 다르게 쓰는 라우터에 packet을 보낼 때, 알아볼 수 있는 header에 감싸서 보냄


## 4.5 routing algorithms
> 앞서 포워딩은 포워딩 테이블을 보고 라우터의 입력 포트에서 출력 포트로 패킷을 이동시키는 작업이라고 했는데, 그렇다면 포워딩 테이블을 어떻게 형성되는 것인가 => routing algorithms

> Graph abstraction(그래프 추상화)
- node: router
- edge: link
- value: link cost(거리 혹은 트래픽 양)
=> 최소 비용을 구하는 문제와 동일


### link state
- 모든 라우터의 정보를 알고 있을 경우
- Dijkstra's algorithm(다익스트라 | 최단경로)
![](https://images.velog.io/images/protect-me/post/72977a14-c293-4d3d-bcfc-e37fb5b2ea2a/image.png)
- 이러한 정보들을 위에서 배운 ICMP로 뿌려줄 수 있음(broadcast)

### distance vetor
- 이웃들과의 자료교환만으로 계산
- poisoned reverse: link cost가 변했을 때, 최소경로가 온 길을 되돌아가는 경로를 포함한 값일 경우 역류할 수 있으므로, 온 길은 무한대로 업데이트하여 역류를 방지함

### hierarchical routing
- 규모의 문제는 계층화로 해결
- Autonomous Systems: 쪼개진 각각의 네트워크는 자치권을 가지고 내부 알고리즘을 결정
- AS(Autonomous Systems) = ISP(internet Service Provider)
- 관계 : Peer - Peer || Provider - customer

## 4.6 routing in the Internet
- RIP
- OSPF
- BGP
> AS내에서는 최단 경로지만, AS간에는 수입 극대화되는 경로를 찾게됨.


## 4.7 broadcast and multicast routing
(현재 사용되지 않고 있기 때문에 생략)


<br>
<br>

---

<br>
<br>
<br>
<br>

# 컴퓨터 네트워크 05 링크 계층 | KOCW 한양대 이석복



>
- Host와 Gateway 간에 전용선이 있는 것이 아니라,
공용선 혹은 broad cast medium이라는 것을 통해서 연결되어있음
즉, 하나의 Gateway에 수많은 Host가 연결되어있음
- medium에서는 한 공간 안에 있으면 어디에 말하든 다 들리는 것처럼 
하나의 packet은 모두가 전달 받으며,
packet이 하나 전달될 때, 다른 packet이 함께 전달되면 쓰레기가 된다.
따라서, collision(충돌)을 제어해야함! 

## 5.2 error detection, correction

## 5.3 Multiple Access protocols
- 결국 충돌이 나지 않게 하는 것이 목적

### 이상적인 multiple access protocol
- 한 사람만 쓰려고 할 때, bandwidth를 모두 사용함
- 전부 다 동시에 사용하려고 하면 1/n씩 공평하게 사용함
- 분산적으로 컴퓨팅이 되어야함
- 동작이 단순해야함

### MAC protocols 분류
- Medium Access Control(MAC)

#### channel partitioning
- TDMA: time division multiple access, 시간 분할 배정
- FDMA: frequency division multiple access, 주파수 분할 배정

#### random access
- 현실에서 많이 쓰임
- 랜덤하게 필요한 연결이 있으면 연결함.
=> 충돌이 일어날 수밖에 없고, 어떻게 해결할 것인지 명시해둬야함
=> 그 해결 방식 중에 하나가 __CSMA(carrier sense multiple access)__


- CSMA
: listen before transmit: 전송 전 다른 frame이 전송중인지 확인 후 전송
=> 먼저 전송을 시작했지만, 다른 Host에 도달하기 전까지는 listen을 해도 알 수가 없음
=> 기다리던 두 Host가 동시에 시작하면 충돌이 일어남.
=> 충돌을 완전히 막을 수 없기 때문에 그 충돌로 인한 피해를 최소화 하기 위해 나온 것이 CSMA/CD


- CSMA/CD(collision detection)
=> 충돌이 감지되면 모든 host가 frame 전송을 멈춤
=> 대기 random time을 두배씩 늘려가면서 재전송
=> Host가 많을수록 대기 시간이 늘어날 수밖에 없음.


#### taking turns
##### polling(여론 조사)
- master node를 통해 관리함.
- master node에서 오류가 났을 경우 전체가 피해를 보는 문제 => 현실에서 쓰이지 않음

##### token passing
- token을 돌리면서 돌아가면서 token을 가진 Host만 전송함.
- token을 분실하는 경우 전체가 피해를 보는 문제 => 현실에서 쓰이지 않음

## 5.4 LANs
### addressing, ARP
(생략?)
### Ethernet
- = 유선 상황
- CSMA/CD 사용 (carrier sense multiple access / collision detection)
- 충돌이 일어나지 않으면 전송이 성공했다고 봐도 무방
- 그러나 충돌이 일어나면 재전송을 해야하는데, feedback이 따로 없음
- 따라서 collision detection이 100% 되야하는 상황.
![](https://images.velog.io/images/protect-me/post/b7bd7d6d-85c0-4801-8fab-0bfe3dddd864/image.png)
- A에서 보내고 있고, G에서는 A에서 시작된 것이 오고 있는 줄 모르고 시작했다가 충돌이 나고 G는 전송을 멈춤
- 그러나 이미 출발한 frame의 조각이 있을 것이고, 퍼져나가고 있는데, A에 도착하기 직전에 A에서 나오던 frame이 모두 전송됨. 
- G에서는 detection이 되었지만, A에서는 detection이 되지 않았기 때문에 방금 전에 보낸 frame은 재전송이 일어나지 않음
- 해결 방법: frame size의 최소값을 설정(LAN의 길이)


>
MAC : Medium Access Control(MAC)
앞 24bit: 제조사 번호
뒤 24bit: 제조사의 고유번호
>
사람을 추상화해봤을 때,
- 이름: Host name
- 주소: IP address
- 주민번호: MAC address
머신의 MAC address는 언제 어디서도 바뀌지 않음

### ARP
- address resolution protocol
- GWR(Gateway Router)의 IP는 아는데, 아직 모르는 MAC address를 알아오기 위한 프로토콜
- ARP query를 broadcasting하고 GWR은 이에 응답함

### Addressing: routing to another LAN
- forwarding table lookup(출력 포트 확인) => ARP table lookup(MAC address 확인)
- frame의 header(MAC src, MAC dest)를 계속해서 새로운 주소로 떼었다 붙였다 하면서 이동
- packet에서 변하는 것은 TTL(Time To live, 데이터 유효 기간) 뿐

![](https://images.velog.io/images/protect-me/post/4a2d1f3c-f00f-45c4-832d-f8feff6cd386/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-08-25%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.03.13.png)
![](https://images.velog.io/images/protect-me/post/2f9f2f34-dab1-462b-84eb-c4cdde5bb270/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-08-25%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.03.32.png)
![](https://images.velog.io/images/protect-me/post/746ccecb-e921-4a13-8590-88b242865184/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-08-25%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.03.41.png)
![](https://images.velog.io/images/protect-me/post/808a2921-d88c-4078-9d1e-fa35d559761b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-08-25%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.03.55.png)
![](https://images.velog.io/images/protect-me/post/8a782b63-4b37-474b-a50f-5b1231631559/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-08-25%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.04.07.png)

### switches
![](https://images.velog.io/images/protect-me/post/b5b083d1-b678-4129-9db5-f40259af1143/image.png)
#### switch:self-learning
![](https://images.velog.io/images/protect-me/post/5ca8a9a4-b3c6-4408-88c4-043ae6ab7b92/image.png)
- A에서 A'로 보내고 싶다고 switch에 보내면, switch에서는 A가 1번에 있구나를 알게 됨.
- switch table에 A-1를 기록
- A'를 swtich table에서 찾아보는데 없으므로, 1번 빼고 flood.
- A'에서 A로 보내고 싶다고 switch에 보내면, switch에서는 A'가 4번에 있구나를 알게 됨.
- switch table에 A'-4를 기록
- A를 swtich table에서 찾아보니 있으므로, 1번으로 전달

#### Interconnecting switches
![](https://images.velog.io/images/protect-me/post/3e482651-c424-417d-ae99-373324aab47f/image.png)

#### Switches vs Routers
![](https://images.velog.io/images/protect-me/post/0944b2bd-7dfb-4332-ac2f-007ce2825472/image.png)

> __router__
네트워크 계층,
라우팅 알고리즘을 통해 포워딩 테이블을 관리함
IP Address

> __switch__
링크 계층, 
self-learning, flood를 통해 스위치 테이블을 관리함
특이하게도 본인은 MAC address는 없음. 즉, host에게는 안보임. 도우미 역할만 수행할 뿐.



### VLANS

## 5.5 link virualization: MPLS
(생략)

## 5.6 data center networking

## 5.7 a day in the life of a web request
![](https://images.velog.io/images/protect-me/post/37937a3e-3fdc-420d-93ff-3c7bf4f4c8ee/image.png)



# 컴퓨터 네트워크 06 무선 네트워크 | KOCW 한양대 이석복

# Wireless
## 6.2 Wireless links, characteristics
![](https://images.velog.io/images/protect-me/post/33d3ec73-f665-4c5a-9b62-ef1b3fb69ffd/image.png)
> __무선에는 CDMA/CD을 적용하기 어려움__
유선에서처럼 신호의 세기가 유지되지 않고 거리에 반비례하며 약해짐.
내가 보내는 신호의 세기가 강하고 다른 신호의 세기가 약한 상황에서는 Detection도 잘 되지 않음.

## 6.3 IEEE 802.11 Wireless LANs("Wi-Fi")
- AP가 모여서 BSS가 된다
base station = access point(AP)
BSS(Basic Service Set)
host들은 가까이 있는 AP에 요청을 하게 됨

### CSMA/CA
: Carrier Sense Multiple Access/Collision Avoidance

#### feedback 도입
유선(이더넷)의 경우, Collision Detection이 100%된다고 볼 수 있지만
무선의 경우, 충돌 감지가 어렵기 때문에 링크 계층에 (이전에 전송 계층에서 본) ACK를 도입함
내 바로 앞에 있는 AP와 나 사이의 feedback(ACK)
=> feedback이 오기 전까지 충돌이 났는지 안났는지 모르기 때문에 실제로 충돌이 일어나도 계속해서 frame을 보낼 것이고 그만큼 시간은 낭비됨. 다른 host와 경쟁적으로 ACK를 받을 때까지 계속해서 재전송이 일어남
=> 이것을 개선하고자 RTS-CTS를 도입

#### RTS-CTS exchange
![](https://images.velog.io/images/protect-me/post/8f34d668-f624-49d1-b396-9f49def6d3c0/image.png)
- host는 frame을 보내기 전에 작은 RTS를 전송함. 충돌이 일어나면 재전송.
- AP는 RTS를 받고 CTS를 broadcast
- RTS(A) => CTS(A) \*CTS에는 A가 얼마만큼 사용할거니까 다 조용히 하라는 메시지가 담겨있음
- A의 전송이 끝나면 ACK를 feedback
- 즉, 채널 예약제라고 보면 된다.

### 802.11 frame:addressing
![](https://images.velog.io/images/protect-me/post/5ca15a57-21e2-40c6-984e-0f2c3852a274/image.png)
- address 1: 받는 AP의 MAC addr
- address 2: 보내는 HOST의 MAC addr
- address 3: AP에서 전달될 Router의 MAC addr
- address 4: 잘 쓰이지 않음
![](https://images.velog.io/images/protect-me/post/4d542907-3989-419b-9a7e-61c5ca19b785/image.png)
- address2, address3의 순서를 바꿔서 dest address, source address에 넣어 라우터에 전달
- __즉, Host는 Wifi(802.11) frame을 전달하고
이를 받은 AP는 Ethernet frame으로 전환 후 전달__

> AP는 switch와 다르게 MAC address가 존재함 => 둘 다 링크 계층

> Q. HOST에서 번거롭게 AP에 router MAC addr 달아서 보내주는 이유는?
AP는 링크 계층까지 밖에 없기 때문에 frame을 까보고
네트워크 계층의 IP packet을 확인할 능력이 없음
(why? 링크 계층까지만 있으면 네트워크 계층에 있는 forwarding table이 없으니까 어디에 보내야하는지 판단할 수 없음)
따라서 HOST에서 router MAC addr까지 붙여서 보내줘야함

> [무선 기기] ---(A)- [AP] -(B)--- [Router]
- 위 상황에서 AP의 A방면에는 MAC addr가 있지만 B방면에는 없음
(마치 유선에서 switch가 그러했던 것처럼)
따라서 Router 입장에서 AP는 보이지 않고, 무선기기가 모두 유선 연결된 것으로 인식됨
- Q. switch에는 MAC addr가 없었는데 AP에 MAC addr가 있는 이유는?
유선상황에서는 선을 따라 보내면 switch에 도달했지만
무선상황에서는 전달을 하면 AP에 보내지는 보장이 되지 없음. 
따라서 Host에서 보낼 때는 AP의 MAC addr가 필요함


> 보통 가정에서 사용하는 무선 공유기는 보통 AP+Router로 합쳐져 구현된 기기
=> 애플리케이션 계층까지 있기 때문에 NAT, DHCP를 기본적으로 제공함
NAT: network address translation,
DHCP: Dynamic Host Configuration Protocol

ex) H1과 google의 통신(google에서 response를 보낼 때)
![](https://images.velog.io/images/protect-me/post/d9dbd148-8d1c-4f2f-990c-dc158ac5ebd9/image.png)


### 802.11: mobility within same subnet
![](https://images.velog.io/images/protect-me/post/46aefd16-0704-4a8f-937c-ff33a5583be6/image.png)
- 같은 switch 내에서 이동을 했을 경우 어떻게 될까?
- 예를 들어 H1과 google이 TCP Connection을 맺었다고 하면
Client(H1) IP/Port `<->` Server(Google) IP/Port
위 네가지 정보를 통해 유일한 Connection이 맺어져있음.
정보는 바뀌지 않을테니, switch table만 업데이트 해주면 된다.
어떻게? H1에서 나갈 때 switch table은 자동으로 업데이트가 이루어짐.

### 802.11: advanced capabilities
![](https://images.velog.io/images/protect-me/post/bc8d77de-7c3a-477a-a164-7a2c57b6526c/image.png)
- Mbps가 높을수록 에러가 발생할 확률이 높으므로,
AP와 가까워지면 높게 유지, 멀어지면 낮게 변경하면서 속도를 조절함(에러에 대처하기 위함)


## 6.4 Cellular Internet Access
### architecture
### standards(e.g. GSM)


# Mobility(생략)
## 6.5 addressing and routing to mobile users
## 6.6 Mobiel IP
## 6.7 Handling mobility in cellular networks
## 6.8 Mobility and higher-layer protocols

<br>
<br>
---


