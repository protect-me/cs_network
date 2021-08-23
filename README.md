> ### [KOCW | 컴퓨터네트워크 | 한양대학교 | 이석복](http://www.kocw.net/home/cview.do?mty=p&kemId=1169634)
__위 강의를 수강하며 정리한 내용임을 밝힙니다.__
네트워크 계층을 Top-Down 방식으로 위에서부터 한 겹씩 까보면서 디테일하게 알아보는 강의

<br>
<br>

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
### 1. connection-oriented service: TCP (Transmission Control Protocol)__
- reliable, in-order byte-stream data transfer : 신뢰할 수 있는, 순차적인 데이터 전송
- flow control : 수신자 혹은 네트워크의 능력 고려하여 받을 수 있는 만큼 전송
- congestion control : 네트워크 막힘 현상시 속도를 낮춰서 전송
사용: HTTP, FTP, Telnet, SMTP(email)

### 2. connectionless: service UDP (User Datagram Protocol)__
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



📚 참고
---
[KOCW | 컴퓨터네트워크 | 한양대학교 | 이석복](http://www.kocw.net/home/cview.do?mty=p&kemId=1169634)
[[Network] 1. 네트워크 기본 : Network 구성요소, TCP vs UDP, 서킷 스위칭 vs 패킷 스위칭, 패킷 딜레이](https://developyo.tistory.com/243)
[[TCP/UDP] TCP와 UDP의 특징과 차이](https://mangkyu.tistory.com/15?category=762469)
[[네트워크] 한양대 컴퓨터 네트워크 이석복 교수님 2015년 - 1. 컴퓨터 네트워크 기본](https://velog.io/@injoon2019/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%95%9C%EC%96%91%EB%8C%80-%EC%BB%B4%ED%93%A8%ED%84%B0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%9D%B4%EC%84%9D%EB%B3%B5-%EA%B5%90%EC%88%98%EB%8B%98-2015%EB%85%84-1.-%EC%BB%B4%ED%93%A8%ED%84%B0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B8%B0%EB%B3%B8)


---

Photo by <a href="https://unsplash.com/@dulgier?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Nastya Dulhiier</a> on <a href="https://unsplash.com/s/photos/network?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>

