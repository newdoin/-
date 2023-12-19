1. PDU의 캡슐화와 비캡슐화
2. 프로토콜의 커넥션 타입과 커넥션리스 타입
3. 대표적으로 사용되는 프로토콜
	- 물리 계층 & 데이터 링크 계층: 이더넷
	- 네트워크 계층: IP
	- 트랜스포트 계층: TCP, UDP
	- 애플리케이션 계층: HTTP, HTTPS, QUIC, DNS
> 단말 내 컴포넌트가 각 계층에서 하나씩 프로토콜을 선택하여 자동으로 처리들이 이루어짐.
4. 각 계층에서 동작하는 기기
	- 물리 계층
		- NIC
		- repeater
		- repeater hub
		- media converter
		- access point
	- 데이터링크 계층(MAC)
		- bridge
		- L2 switch: 단말에서 받아들인 MAC 주소를 테이블로 관리하고 전송 처리함
	- 네트워크 계층(IP)
		- router
		- L3 switch: MAC 주소 테이블과 라우팅 테이블을 조합한 정보를 패킷 전송 처리 전용 하드웨어에 기록하고, 그 정보를 기반으로 스위칭 혹은 라우팅 함
	- 트랜스포트 계층(Port)
		- firewall
			- network firewall method: stateful vs stateless
		- L4 switch: 헤더 정보를 분석하여 데이터 패킷을 처리하고 전송 방향 결정하거나, 패킷의 송수신을 모니터링하고 필요에 따라 트래픽을 제어함
	- 애플리케이션 계층(Message)
		- next-generation firewall
		- WAF: 웹 애플리케이션 방화벽, 일반적인 공격으로부터 웹 애플리케이션을 보호하는 보안 솔루션
		- L7 switch: 패킷의 포트 정보뿐만 아니라 페이로드까지 분석해 로드 밸런싱을 함. L4 switch보다 더 세밀한 수준의 고급 로드 밸렁싱과 트래픽 관리를 가능케 함
> 그럼 L7 스위치가 짱이네?
> 상황에 따라 L7 스위치는 불필요하게 많은 기능을 하기 때문에 자원 낭비가 될 수 있다. 예를 들어 단순히 포트 정보만을 이용해 부하 분산을 하려고 할 때, L7가 최선일까? L4만 써도 충분한데 말이다.
> 정리하면, HTTP 요청 등 L7 계층의 해석이 필요한 경우에는 L7 스위치를! TCP/UDP 로드밸런싱이 필요하다면 L4스위치를!!
5. 네트워크 기기의 형태
	- 물리 어플라이언스
	- 가상 어플라이언스
6. 네트워크 형태
	- LAN
	- WAN
		- 인터넷
		- VPN을 사용한 내부망: 폐역 VPN 망에 접속해 그 폐역 VPN 망을 통해 각 거점과 정보 교환하는 방식
	- DMZ(DeMilitarized Zone): 인터넷에 공개하는 서버를 설치한 네트워크
7. 새로운 네트워크 형태
	- SDN, Software Defined Network
	- CDN, Content Delivery Network
	- IoT, Internet of Things
	- IaaS, Infrastructure as a Service