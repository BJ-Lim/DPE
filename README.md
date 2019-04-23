# 개요
정보처리기사 요약 정리를 위한 저장소입니다.

# 과목
## 데이터베이스
- 트랜잭션(Transaction)의 특징
  - 원자성(automicity) : 트랜잭션의 연산은 DB에 모두 반영되거나 전혀 반영되지 않아야 한다
  - 일관성(consistency) : 트랜잭션이 그 실행을 성공적으로 완료하면 언제나 일관성 있는 DB 상태로 변환한다
  - 독립성(isolation) : 둘 이상의 트랜잭션이 동시에 실행되는 경우 어느 하나의 트랜잭션이 실행 중 다른 트랜잭션의 연산에 끼어들 수 없다
  - 영속성(Durability) : 성공적으로 완료된 트랜잭션의 결과는 영구적으로 반영되어야 한다
- 관계 대수 : 절차적 언어
  - 셀렉트(select, σ : 시그마) : 릴레이션에서 조건을 만족하는 튜플을 구한다
  - 프로젝트(project, π : 파이) : 릴레이션에서 주어진 속성들의 값으로만 구성된 튜플을 구한다
  - 조인(Join, ⋈) : 공통 속성을 이용해 두 릴레이션의 튜플들을 연결하여 생성된 튜플을 구한다
  - 디비전(Division, ÷) : 나누어지는 릴레이션에서 나누는 릴레이션의 모든 튜플과 관련이 있는 튜플을 구한다
- 관계 해석 : 비절차적 언어
- 정규형
  - 제 1 정규형(1NF) : 모든 속성의 도메인(속성값)이 원자값으로만 구성
  - 제 2 정규형(2NF) : 1NF + 모든 속성의 종속이 기본키를 통해서만 만족
  - 제 3 정규형(3NF) : 2NF + 모든 속성의 함수종속이 기본키를 통해서만 만족되며 기본키에 이행적 함수종속이 없음
  - 보이스-코드 정규형(BCNF) : 3NF + 모든 속성의 함수종속이 호보키를 통해서만 만족
  - 제 4 정규형(4NF) : BCNF + 함수종속이 아닌 다치종속(MultiValued Dependency)이 제거됨
  - 제 5 정규형(5NF) : 4NF + 모든 조인의 함수종속이 후보키를 통해서만 만족
- 무결성 제약 조건
  - 엔티티(개체) 무결성: 릴레이션에서 기본키를 구성하는 속성은 널값이나 중복 값을 가질 수 없음
  - 참조 무결성 : 외래키 값은 널이거나 참조 릴레이션의 기본키 값과 동일해야함. 즉, 릴레이션은 참조할 수 없는 외래키 값을 가질 수 없음
  - 널 무결성 : 릴레이션의 특정 속성값이 널이 될 수 없도록 하는 규정
  - 고유 무결성 : 릴레이션의 특정 속성에 대해서 각 튜플이 갖는 값들이 서로 달라야 한다는 규정
  - 도메인 무결성 : 특정 속성의 값이 그 속성이 정의된 도메인에 속한 값이어야 한다는 규정
  - 키 무결성 : 하나의 릴레이션에는 적어도 하나의 키가 존재해야 한다는 규정
  - 관계 무결성 : 릴레이션에 어느 한 튜플의 삽입 가능 여부 또는 한 릴레이션과 다른 릴레이션의 튜플들 사이의 관계에 대한 적절성 여부를 지정한 규정
- 2단계 로킹 규약
  - 확장 단계 : lock만 실행 가능
  - 축소 단계 : unlock만 실행 가능
- E-R 다이어그램
  - [link](https://blog.naver.com/coocly/221401820298)
- 스키마의 종류
  - 외부 스키마(External Schema, sub schema) : 응용프로그램 개발자 관점(view 등)
  - 개념 스키마(Conceptional Schema) : 그 DB의 실제 스키마 구조
  - 내부 스키마(Internal Schema) : 실제 물리적으로 저장되는 스키마
- DB의 설계 단계

  단계 | 내용 | 할일 | 결과물
  ---- | ---- | ---- | ----
  1 | 요구사항 분석 | DB의 용도 파악 | 요구 사항 명세서
  2 | 개념적 설계   | DBMS 독립적인 개념적 구조 설계 | 개념적 스키마(E-R 다이어그램)
  3 | 논리적 설계   | - | -
  4 | 물리적 설계   | - | -
  5 | 구현         | -  | -
- 정렬
  - [link](https://github.com/BJ-Lim/Algorithm_Practice/blob/master/concept/sorts.md)
- 트리
  - 차수(Degree) : 노드 중 가장 자손이 많은 노드의 자손 수
  - 순회
    - 전위(preorder) : Root - Left - Right
    - 중위(inorder) : Left - Root - Right
    - 후위(postorder) : Left - Right - Root
- 해싱
  - Slot : 1개의 레코드를 저장할 수 있는 공간으로 n개의 슬롯이 모여 하나의 버킷을 형성
  - Bucket : 하나의 주소를 갖는 파일의 한 구역을 의미, 버킷의 크기는 같은 주소에 포함될 수 있는 레코드의 수를 의미
  - Synonym : 같은 Home Address를 갖는 레코드들의 집합

## 전자계산기구조
- 디지털 IC의 전달지연 시간 순서(짧은 순서부터) : ETCM
  1. ECL
  2. TTL
  3. CMOS
  4. MOS
- 코어 기억장치
  - 한 장의 코어 플레인(core plane)은 1,0을 기억할 수 있으므로 1비트를 기억함
- 명령어의 구성
  - 연산자(Operation Code)부 : 인스트럭션의 형식, 연산자, 자료의 종류 등을 
  - 주소(Operand)부 : 기억장소의 주소, 레지스터 번호, 사용할 데이터 등을 표시 
- PACK 형식
  - 만드는법 : 총 2바이트 중 상위 12비트는 수, 하위 4비트는 부호를 나타냄
  - 부호 : 1100(C)(+), 1101(D)(-)
  - ex) -456 = 45 6D
- 인터럽트 처리 절차
  1. 프로그램 상태 보존
  2. 다른 인터럽트가 발생되지 않도록 조치( IEN(IF, Interrupt Flag) ← 0 을 저장)
  3. 인터럽트 처리
  4. 메인 프로그램으로 복귀
- 주소 명령어 방식
  - 0-주소 명령어 방식 : 스택 이용, 후위연산으로 계산
  - 1-주소 명령어 방식 : 누산기 이용
- 전가산기
  - 구성 : 반가산기 2개 + or 게이트 1개
  - 암기법 : 전가산기 = 반가산기 +(or) 반가산기
- 플롭스(FLOPS) : Floating Point Operations Per Second, 초당 부동소수점 연산수
  - 계산식 : 프로그램 내의 부동소수점 연산개수 / (수행시간 x 단위)
- 단위
  - Kilo : 10^3
  - Mega : 10^6
  - Giga : 10^9
  - Tera : 10^12
- 가상 기억 장치(Virtual Memory System)
  - 실질적인 기억 공간보다 훨씬 큰 논리적 공간을 주소화 가능
  - 운영체제의 설계가 복잡해짐
  - 실행속도가 느려짐
- 오버레이(overlay) : 하나의 프로그램을 몇 개의 영역으로 분할하여 보조 기억 장치에 수용하고, 처리의 흐름에 필요한 영역을 주 기억장치에 차례로 불러내어 실행하며 루트 영역은 늘 주기억장치에 존재하는 방식
- 메이저 상태
  - [link](https://blog.naver.com/davidoff73/30033148868) : 그림으로 보기
- RAM

  종류 | 속도 | refresh | 집적도 | 회로구조 | 용량 | 가격 | 용도 | 전력소모
  ---- | ---- | ----   | ----   | ----    | ---- | ---- | ---- | ----
  SRAM | 빠름 | 불필요 | 낮음 | 복잡 | 소 | 비쌈 | 캐쉬 | 높음
  DRAM | 느림 | 필요 | 높음 | 단순 | 대 | 쌈 | 대용량메모리 | 낮음
- 레지스터의 크기
  - 주기억장치의 word 수 = PC(프로그램 카운터) = MAR(메모리 주소 레지스터)
  - word의 크기 = MBR(메모리 버퍼 레지스터)

## 운영체제
- 디스크 스케줄링
  - [link](https://m.blog.naver.com/jevida/140193949948) : 그림으로 보기
  - FCFS(First - Come - First - Served) : 선입선출, 단순하며 이동거리 김
  - SSTF(Shortest Seek Time First) : 탐색 시간이 가장 적을 수 있는 가까운 cylinder로 이동
  - SCAN : 시작 -> 0 -> 끝 -> 0 순으로 지나가며 모두 탐색
  - C-SCAN : 시작 -> 끝 --> 0 -> 끝 --> 0 순으로 지나가며 모두 탐색.(-->은 탐색하지 않고 바로 이동)
  - Look : 0과 끝이 아닌, 큐 내에서의 최솟값과 최댓값 범위에서 이동하며 작동은 SCAN과 동일

## 소프트웨어공학
- 데이터 흐름도(DFD: Data Flow Diagram)의 구성요소
  - 프로세스(Process)
  - 데이터 흐름(Data Flow)
  - 데이터 저장소(Data Store)
  - 외부 엔티티(External Entity)
- 테스트 기법
  - 블랙박스 검사 : 어떤 소프트웨어를 내부 구조나 작동 원리를 모르는 상태에서 소프트웨어의 동작을 검사하는 방법
  - 화이트박스 검사 : 블랙박스와 반대되며, 보통 내부 소스코드를 테스트하는 
- Component : 소프트웨어 재사용과 관련하여 객체들의 모임, 대규모 재사용 단위로 정의되는 것
  - 컴포넌트 기반 개발
    - 후보 컴포넌트가 요구되는 기능을 수행하는지를 조사하기 위해 컴포넌트 검증을 수행한다
    - 컴포넌트 라이브러리가 컴포넌트 확장 언어를 제공하면 그레이-박스 랩핑을 적용할 수 있다.
    - 어플리케이션 구현을 위해 검증, 개작, 개발된 컴포넌트 들을 조립하는 컴포넌트 합성을 수행한다.
- 소프트웨어 품질 보증을 위한 정형 기술 검토의 지침 사항
  - 각 체크 리스트를 작성하고, 자원과 시간 일정을 할당
  - 검토의 과정과 결과를 재검토
  - 논쟁과 반박을 제한
- User Interface 설계 시 오류 메시지나 경고에 관한 지침
  - 메시지는 이해하기 쉬워야 함
  - 오류로부터 회복을 위한 구체적인 설명이 제공되어야 함
  - 소리나 색 등을 이용하여 듣거나 보기 쉽게 의미 전달을 해야함
- stub 모듈
  - 하향식 통합 테스트 수행을 위해 일시적으로 필요한 조건만을 가지고 임시로 제공되는 시험용
- CASE(Computer-aided software engineering)
  - 소프트웨어, 하드웨어, 데이터베이스, 테스트 등을 통합하여 소프트웨어를 개발하는 환경을 조겅한다는 의미
- NS(Nassi-Schneiderman) Chart
  - 논리의 기술에 중점을 두고 도형을 이용한 표현 방법
  - 이해하기 쉽고 코드로 변환이 용이
  - 연속, 선택, 반복 등의 제어 논리 구조를 표현
- 캡슐화
  - 결합도가 낮아짐
  - 재사용 용이
  - 인터페이스 단순화 가능
  - 변경 발생시 파급효과 적음
- 자료사전의 '{}' 은 반복을 의미
- COCOMO(Constructive Cost Model) : 시스템의 비용을 산정하기 위해 시스템을 구성하고 있는 모듈과 서브 시스템의 비용 합계를 계산하는 방식
  - 특징 : 비용 예측, 의존성, 유연성, 이용성
  - 모델 유형 : 기본형, 중간형, 발전형
  - 모델 프로젝트 유형
    - organic(유기적) Mode : 50,000 코드 라인(50KDSI) 이하
      - KDSI(Kilo Delivered Source Instruction) : 전체 라인수를 1000라인 단위로 묶은 것으로, KLOC(Kilo LOC)와 같다
    - Semidetached Mode(반 결합 모드 프로젝트) : 300,000 코드 라인 정도
    - Embedded Mode(내장모드 프로젝트) : 300,000 코드 라인 이상의 대형 프로젝트
- Rumbaugh의 모델링
  - 상태도 : 동적 모델링
  - 자료흐름도 : 기능 모델링
## 데이터통신
- HDLC(High-level Data Link Control)
  - 프레임 구조 : Flag - Address - Control - Data - Frame Check Sequence - Flag
- CDMA(Code Division Multiple Access)
  - 특징
    - 시스템의 포화 상태로 인한 통화 단절 및 혼선이 적다
    - 실내 또는 실외에서 넓은 서비스 권역을 제공한다
    - 배경 잡음을 방지하고 감쇄시킴으로써 우수한 통화 품질을 제공한다
    - 산악 지형 또는 혼잡한 도심 지역에서도 품질이 떨어지지 않는다.
- 계층 구조

주요 프로토콜 | TCP/IP 프로토콜 계층 모델 | OSI 계층 모델
---- | ---- | ----
TELNET, FTP, SNMP, DHCP | Application | Application, Presentation, Session
SCTP, TCP, UDP | Transport | Transport
IGMP, ICMP, IP, ARP | Network(IP) | Network
\- | Data Link | Data Link
\- | Physical | Physical

- 나이키스트 표본화 정리
  - 표본화 주기(T) = 1 / 2* 최고주파수(W)
    - <=> 표본화 주파수 = 최고주파수 * 2
- PAD(Packet Assembler/Disassembler)
- 터널링 : IPv6 데이터그램을 IPv4 패킷에 캡슐화하여 IPv4 라우팅 토폴로지 영역을 통해 전송하는 방법
- FEC(Forward Error Correction) : 전진 에러 수정
  - [link](http://blog.naver.com/PostView.nhn?blogId=wlsqor2&logNo=40019966587&redirect=Dlog&widgetTypeCall=true)
  - 에러 정정 기능 포함
  - 연속적 데이터 전송 가능
  - 역채널 사용 안함
- VoIP(Voice over Internet Protocol) : 음성 인터넷 프로토콜
  - 프로토콜 : SIP(Session Initiation Protocol, 세션 개시 프로토콜), H.323, Megaco
- SIGTRAN : 유선 전화망(PSTN : Public Switched Telephone Network, 공중교환전화망)과 인터넷 망(IP Network)를 상호 연동시키는데 사용되는 시그널링 프로토콜
- RARP(Reverse Address Resolution Protocol, 역순 주소 결정 프로토콜) : 물리 네트워크 주소로 논리 IP 주소를 얻기위해 사용되는 프로토콜
- 해밍코드 : 이진 선형 블록 오류 정정 부호의 일종
  - 특징 : 2비트 오류 감지 및 1비트 오류 수정 가능
  - 수식 : ![Style_Images](https://github.com/BJ-Lim/DPE/blob/master/captures/%EC%88%98%EC%8B%9D.png)
    - k = 해밍 비트수, n = 정보 비트수
- 프로토콜의 기본 구성 요소
  - 구문(Syntax)
  - 의미(Semantics)
  - 순서(Timing)
- FLSM(Fixed-Length Subnet Masking) : 같은 주 네트워크가 같은 크기로 나뉘어진 경우에만 라우팅 업데이트를 해주는 방식
- QPSK(Quadrature Phase Shift Keying) : 위상변화를 90도씩 변화를 주는 4진 PSK 방식(효율 2배)
  - [link](http://www.ktword.co.kr/abbr_view.php?m_temp1=1150)
- X.25 프로토콜
  - 구성 계층 : 물리(1계층), 링크(2계층), 패킷 계층(3계층)
- 아날로그 변조 방식
  - AM(Amplitude Modulation, 진폭 변조)
  - FM(Frequency Modulation, 주파수 변조)
  - PM(Phase Modulation, 위상 변조)
- OSI 7 Layer

  계층 순서 | 계층 이름 | 역할
  ---- | ---- | ----
  1 | 물리 | 하드웨어 전송
  2 | 데이터 링크 | 오류제어, 흐름제어
  3 | 네트워크 | 라우팅, 흐름제어, 세그멘테이션, 오류 제어, 인터네트워킹
  4 | 전송 | 단말기간의 오류 수정 및 흐름제어를 수행하여 신뢰성 있고 명확한 데이터를 전달하는 계층
  5 | 세션 | 양 끝단의 응용 프로세스가 통신을 관리하기 위한 방법 제공
  6 | 표현 | 코드간의 번역을 담당(ex. 인코딩)
  7 | 응용 | 응용 프로세스와 직접 
  
  
