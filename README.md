# 개요
정보처리기사 요약 정리를 위한 저장소입니다.

# 과목
## 데이터베이스
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


## 전자계산기구조
- 메이저 상태
  - [link](https://blog.naver.com/davidoff73/30033148868) : 그림으로 보기
- RAM

  종류 | 속도 | refresh | 집적도 | 회로구조 | 용량 | 가격 | 용도 | 전력소모
  ---- | ---- | ----   | ----   | ----    | ---- | ---- | ---- | ----
  SRAM | 빠름 | 불필요 | 낮음 | 복잡 | 소 | 비쌈 | 캐쉬 | 높음
  DRAM | 느림 | 필요 | 높음 | 단순 | 대 | 쌈 | 대용량메모리 | 낮음

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
