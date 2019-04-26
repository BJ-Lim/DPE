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
  - 릴레이션을 처리하기 위한 연산의 집합으로 피연산자가 릴레이션이고 결과도 릴레이션
  - 원하는 정보와 그 정보를 어떻게 유도하는가를 기술하는 절차적 특징
  - 일반 집합 연산과 순수 관계 연산이 존재
  - 연산의 종류
    - 셀렉트(select, σ : 시그마) : 릴레이션에서 조건을 만족하는 튜플을 구한다
    - 프로젝트(project, π : 파이) : 릴레이션에서 주어진 속성들의 값으로만 구성된 튜플을 구한다
    - 조인(Join, ⋈) : 공통 속성을 이용해 두 릴레이션의 튜플들을 연결하여 생성된 튜플을 구한다
    - 디비전(Division, ÷) : 나누어지는 릴레이션에서 나누는 릴레이션의 모든 튜플과 관련이 있는 튜플을 구한다
- 관계 해석 : 비절차적 언어
  - 수학의 프레디킷 해석(Predicate Calculuis)에 기반
  - 관계 데이터 모델의 제안자인 코드(codd)가 관계 데이터 베이스에 적용할 수 있도록 설계하여 제안
  - 튜플 관계해석과 도메인 관계해석이 존재
- 색인 순차 파일
  - 인덱스 저장 공간 및 오버플로우 처리 공간이 필요하므로 공간 효율이 안좋다
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
- 로킹
  - 주요 데이터의 액세스를 상호 배타적으로 하는 것
  - 데이터베이스, 파일, 레코드, 필드 등은 로킹 단위가 될 수 있다
  - 로킹 단위가 크면 로크 수가 작아 관리하기 쉽지만, 병행성 수준이 낮아짐
  - 로킹 단위가 작아지면 로크 수가 많아 관리가 복잡하여 오버헤드가 증가하지만, 병행성 수준이 높아짐
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
- OLAP(on-line analytical processing, 온라인 분석처리)
  - 데이터웨어하우스(많은 양의 데이터 저장소(Repository)의 역할)에 입력된 정보를 처리하는 방법
  - 데이터웨어하우스의 자료들을 이용하여 업무에서 요구 하는 유형 대로 데이터를 분석하고 보고서를 생성하는 도구의 역할
  - OLAP 종류 : ROLAP, MOLAP, HOLAP
  - OLAP 연산 : roll-up, drill-down, pivoting, slicing & dicing
- 이상(anomaly) 현상
  - 데이터의 중복으로 인해 릴레이션을 처리할때 발생하는 곤란한 현상
  - 데이터 베이스 사용자의 의도와는 다르게 다른 데이터가 삽입 삭제 갱신되는 현상
- cardinality : 튜플의 수를 의미
- 뷰(view)
  - 뷰는 제거시 drop문을 이용
  - 뷰 정의시 create문 이용
  - 뷰는 수정이 불가하며 필요한경우 drop후 create를 다시 해야함
- 로그(log)를 필요로 하는 회복 기법
  - 연기 갱신 기법(Deferred Update)
  - 즉각 갱신 기법(Immediate Update)
  - 그림자 페이지 대체 기법(Shadow Paging)
  - 검사점 기법(Check Point)
- 정렬
  - [link](https://github.com/BJ-Lim/Algorithm_Practice/blob/master/concept/sorts.md)
- 트리
  - 차수(Degree) : 노드 중 가장 자손이 많은 노드의 자손 수
  - 깊이에 따른 최대 노드 수 : 2^n - 1
  - 순회
    - 전위(preorder) : Root - Left - Right
    - 중위(inorder) : Left - Root - Right
    - 후위(postorder) : Left - Right - Root
- 해싱
  - Slot : 1개의 레코드를 저장할 수 있는 공간으로 n개의 슬롯이 모여 하나의 버킷을 형성
  - Bucket : 하나의 주소를 갖는 파일의 한 구역을 의미, 버킷의 크기는 같은 주소에 포함될 수 있는 레코드의 수를 의미
  - Synonym : 같은 Home Address를 갖는 레코드들의 집합
  - 제산법 : 나머지 연산자(%)를 이용해 주소로 사용
  - 폴딩법 : 마지막을 제외하고 동일한 크기로 key를 나눠 xor 연산하여 주소로 사용
  - 기수변환법 : key 값을 다른 진법으로 변환해 초과길이는 잘라 사용
  - 숫자분석법 : 각 숫자의 분포를 이용해서 균등한 분포의 숫자를 선택해서 사용

## 전자계산기구조
- 디지털 IC의 전달지연 시간 순서(짧은 순서부터) : ETCM
  1. ECL
  2. TTL
  3. CMOS
  4. MOS
- 코어 기억장치
  - 한 장의 코어 플레인(core plane)은 1,0을 기억할 수 있으므로 1비트를 기억함
- 마이크로명령어 형식
  - 조건 필드 : 분기를 위한 플래그 정보
  - 연산 필드 : 동시에 수행되는 연산 정보
  - 주소 필드 : 분기가 발생할 경우 실행할 목적지 마이크로 명령어 주소
  - 분기 필드 : 분기의 종류와 다음에 실행할 마이크로 명령어의 주소를 결정하는 방법
  
- 명령어의 구성
  - 연산자(Operation Code)부 : 인스트럭션의 형식, 연산자, 자료의 종류 등을 
  - 주소(Operand)부 : 기억장소의 주소, 레지스터 번호, 사용할 데이터 등을 표시 
  - 데이터 구조 : 워드의 크기
- PACK 형식
  - 만드는법 : 총 2바이트 중 상위 12비트는 수, 하위 4비트는 부호를 나타냄
  - 부호 : 1100(C)(+), 1101(D)(-)
  - ex) -456 = 45 6D
  - ex) +376 = 37 6C
- UNPACK 형식
  - 1바이트를 존(zone) 부분과 디지트(digit) 부분으로 구성
  - 존 부분은 항상 F(1111)이 들어가고 디지트 부분에는 10진수 값이 들어감
  - 가장 오른쪽 바이트의 존 부분에 부호를 표시
    - 양수 : 1100(C)
    - 음수 : 1101(D)
    - 무부호 : 1111(F)
  - ex) +375 = 1111 0011 1111 0111 1100 0101 = F3 F7 C5
- 인터럽트 처리 절차
  1. 프로그램 상태 보존
  2. 다른 인터럽트가 발생되지 않도록 조치( IEN(IF, Interrupt Flag) ← 0 을 저장)
  3. 인터럽트 처리
  4. 메인 프로그램으로 복귀
- 인터럽트 우선순위 판별법
  - 소프트웨어적 : 폴링
  - 하드웨어적 : 데이지 체인 
- 주소 명령어 방식
  - 0-주소 명령어 방식 : 스택 이용, 후위연산으로 계산
  - 1-주소 명령어 방식 : 누산기 이용
- 반가산기
  - 구성 : and, or, not 게이트
- 전가산기
  - 구성 : 반가산기 2개 + or 게이트 1개
  - 암기법 : 전가산기 = 반가산기 +(or) 반가산기
- Carry Lookahead Adder : 리플캐리 지연을 제거한 가산기
- 디코더
  - 구성 : 주로 and
- 레지스터
  - 구성 : 플립플롭(Flip-Flop), 래치(Latch)
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
- 레지스터
  - 크기
    - 주기억장치의 word 수 = PC(프로그램 카운터) = MAR(메모리 주소 레지스터)
    - word의 크기 = MBR(메모리 버퍼 레지스터)
  - 종류
    - 세그먼트 레지스터
      - 총 6개(CS, SS, DS, ES, FS, GS)로 구성
      - 세그먼트 디스크립터와 가상메모리가 조합되어 선형주소가 됨
      - 페이징 기법에 의해 선형 주소가 최종적으로 물리주소로 변환
      - 운영체제에서 관리하며 응용프로그램이 직접 접근 
- 캐시 메모리
  - 사상 기법
    - 주기억 장치의 임의의 블록을 지정된 캐시 블록에 기억시키는 방법
    - 직접 사상(Direct Mapping) : 기억시킬 캐시 블록 결정 함수는 주기억 장치의 블록 번호를 캐시 전체의 블록 수로 나눈 나머지로 결정
    - 전체 연합 사상(Fully Associative Mapping) : 주기억 장치 임의의 블록 하나를 캐시 전체 블록 중 아무 곳이나 하나를 정해서 기억시키는 방법
    - 세트 연합 사상(Set Associative Mapping) : 직접사상+연합사상
  - 기록 정책
    - write-Through : 캐시에 쓰기 동작이 이루어질 때마다 캐시 메모리와 주기억장치의 내용을 동시에 갱신하는 방식, 쓰기 동작에 걸리는 시간이 김
    - write-Back : 캐시에 쓰기 동작이 이루어지는 동안은 캐시의 내용만이 갱신되고, 캐시의 내용이 캐시로부터 제거될 대 주기억장치에 복사
    - write-Once : 캐시에 쓰기 동작이 이루어질 때 한 번만 기록하고 이후의 기록은 모두 무시
- 파괴적 읽기 : 해당 장치에서 데이터를 읽으면 해당 내용이 손상되는 것
- 클록 사이클 계산
  - 파이프라인 구조의 속도 : (클록 사이클 결정)시간 지연 중 가장 큰 값 + 중간 레지스터 지연
  - 비 파이프라인 구조의 속도 : 모든 세그먼트 지연시간의 합 + 중간 레지스터의 지연 시간
  - 배수 = 비파이프라인 구조의 속도 / 파이프라인 구조의 속도
- 세그먼트의 최대 크기 = 2^(페이지 번호 비트 + 워드 필드 비트)
- 메모리 인터리빙 : 대역폭을 늘려주는 효과
- 메모리 버스트 : 어드레스에 액세스 할 때 미리 길이를 4개 또는 8개 정도로 지정해 놓고 연속된 데이터 읽기
- 인스트럭션 사용 빈도
  - 메모리에 접근 빈도가 많아질수록 속도가 느려지며 사용빈도는 낮아짐
- 디멀티플렉서(demultiplexer)
  - 한 개의 선으로부터 입수된 정보를 받아들임
  - N개의 선택 입력
  - 2^N개의 가능한 출력중 하나를 선택
  - 조합회로
- 그레이 코드(gray code)
  - 가중치가 없는 코드이기 때문에 연산에 부적합
  - 아날로그-디지털 변환기나 입출력 장치 코드로 주로 쓰임
  - XOR 연산이 사용됨
  - 이진 코드 -> 그레이 코드
    - MSB 비트는 그대로 씀
    - 이진코드의 앞 비트와 뒷 비트를 비교하여 같으면 0, 다르면 1을 씀
    - ex) 1101 -> 1011
  - 그레이 코드 -> 이진 코드
    - MSB 비트는 그대로 씀
    - 그레이 코드가 0이면 이진코드의 앞 비트와 동일하게, 1이면 반전함
    - ex) 1101 -> 1001
  - [참조](https://m.blog.naver.com/PostView.nhn?blogId=k97b1114&logNo=140156127190&proxyReferer=https%3A%2F%2Fwww.google.com%2F)
- Thrashing :  가상 기억장치 시스템에서, 프로그램이 접근한 페이지나 세그먼트를 디스크에서 주기억장치로 올려놓기 위한 페이지폴트가 너무 자주 일어나 프로그램의 처리속도가 급격히 떨어지는 상태
- 마이크로오퍼레이션(micro-operation)
  - 레지스터에 저장된 데이터에 의해 이루어지는 동작
  - 한 개의 클록펄스동안 실행되는 기본동작
  - 한개의 인스트럭션은 여러개의 마이크로오퍼레이션이 동작되어 실행
  - 마이크로 오퍼레이션을 순차적으로 일어나게 하는데 필요한 신호를 제어신호라 함
  - 명령을 수행하기 위해 CPU내의 레지스터와 플래그의 상태 변환을 일으키는 작업
- Micro Cycle Time 부여 방식
  - 동기고정식(Synchronous Fixed)
    - 모든 마이크로오퍼레이션의 동작 시간이 같은 것으로 가정하여 CPU Clock 주기와 Micro Cycle Time을 동일하게 정의한다
    - 모든 마이크로 오퍼레이션 중 동작시간이 가장 긴 마이크로 오퍼레이션의 동작시간을 Micro Cycle Time으로 정한다
    - 모든 마이크로 오퍼레이션의 동작 시간이 비슷할 때 유리하다
    - 제어기의 구현이 단순하나 CPU의 시간 낭비가 심하다
  - 동기 가변식(Synchronous Variable)
    - 수행시간이 비슷한 Micro Operation 끼리 그룹을 지어 그룹별로 Micro Cycle Time 을 정의하는 방식     
    - 수행시간이 현저한 차이를 나타날 때 사용동기 고정식에 비해 CPU 시간 낭비를 줄일 수 있으나 제어기의 구현이 복잡
    - 각 그룹 간 서로 다른 사이클 타임 동기를 맞추기 위해 그룹 간 사이클 타임을 정수배가 되게 설정
  - 비동기식(Asynchronous)
    - 모든 마이크로 오퍼레이션에 대해 서로 다른 Micro Operation Cycle Time 부여
    - CPU 시간 낭비는 거의 없으나 제어기가 매우 복잡해지므로 실제로는 거의 사용 안함
- DMA(Direct Memory Access)
  - 대용량의 자료 전송을 위해 장치 드라이버가 CPU의 레지스터를 거치지 않고 직접 장치와 메모리 간 블록 단위로데이터를 전송하는 기법
- 사이클스틸링(Cycle Straling)
  - DMA 컨트롤러와 CPU가 동시에 Bus를 사용 요청을 할 경우 속도가 빠른 CPU가 속도가 다소 느린 DMA 에게 우선순위를 주어 빠른 입출력이 가능하게 하는 방법
  - 한번의 DMA 동작 중 1 word 정도 작은 데이터 전송시 적용
- 명령 파이프라인
  - 명령어를 읽어 순차적으로 실행하는 프로세서에게 적용되는 기술로, 한번에 하나의 명령어만 실행하는 것이 아니라 하나의 명령어가 실행되는 도중에 다른 명령어 실행을 시작하는 식으로 동시에 여러개의 명령을 실행하는 기법
- 데이지 체인(daisy-chain)
  - 병렬 우선순위 방법
  - H/W 우선순위 판별 방법
  - 인터럽트를 발생하는 모든 장치들을 인터럽트의 우선순위에 따라 직렬로 연결함으로써 이루어지는 우선순위 인터럽트 처리방법
  - 장치번호 버스를 이용
  - 벡터에 의한 인터럽트 처리방법
  - 응답속도 빠르다
- n의 보수
  - 계산식 : (해당 진수의 최대값) - (보수를 구하고자 하는 값)
- n-1의 보수
  - 계산식 : (해당 진수의 최댓값) - (보수를 구하고자 하는 값) + 1
- 모듈러스-n 카운터
  - 가질 수 있는 상태 수 : n 개
  - 플립플롭의 수 >= log(밑수)2(n)
- SDRAM(Synchronous Dynamic Random Access Memory)
  - 여러 개의 내부 뱅크들(Banks)에서 동시 액세스가 진행
  - 액세스가 진행되는 동안 CPU가 동기
  - 버스 클럭에 동기화되어 정보가 전송
  - 여러 개의 데이터들을 연속으로 전송하는 버스트 모드를 지원
- 코드의 특징
  - 허프만 코드 : 그래픽 기호 표현이 용이
  - 해밍 코드 : 에러 검출이 쉬움
  - 그레이 코드 : 연속된 순간에 하나의 비트만 변화
  - 3초과 코드 : 자기 보수 가능한 비가중치 코드
  - 2421 코드 : 자기 보수 가능한 가중치 코드
- Masking Operation : 특정 문자 또는 특정 비트를 삭제시키는 명령으로 AND
  
## 운영체제
- 운영체제의 기능에 따른 분류
  - 제어프로그램 : 데이터관리 프로그램, 감시 프로그램, 작업 제어 프로그램
  - 처리 프로그램
    - 언어 번역(Language Translate) 프로그램: 원시 프로그램을 기계어 형태의 목적 프로그램으로 번역하는 프로그램(어셈블러, 컴파일러, 인터프리터)
    - 서비스(Service) 프로그램: 컴퓨터를 효율적으로 사용할 수 있는 사용 빈도가 높은 프로그램
    - 문제(Problem) 프로그램: 특정 업무 및 해결을 위해 사용자가 작성한 프로그램  
- 디스크 스케줄링
  - [link](https://m.blog.naver.com/jevida/140193949948) : 그림으로 보기
  - FCFS(First - Come - First - Served) : 선입선출, 단순하며 이동거리 김
  - SSTF(Shortest Seek Time First) : 탐색 시간이 가장 적을 수 있는 가까운 cylinder로 이동
  - SCAN : 시작 -> 0 -> 끝 -> 0 순으로 지나가며 모두 탐색
  - C-SCAN : 시작 -> 끝 --> 0 -> 끝 --> 0 순으로 지나가며 모두 탐색.(-->은 탐색하지 않고 바로 이동)
  - Look : 0과 끝이 아닌, 큐 내에서의 최솟값과 최댓값 범위에서 이동하며 작동은 SCAN과 동일
  - Sector Queuing : 회전시간의 최적화를 위해 구현된 디스크 스케줄링 기법
- 비선점 스케줄링(Non-Preemptive Scheduling)
  - 이미 할당된 CPU를 다른 프로세스가 강제로 빼앗아 사용할 수 없는 스케줄링 기법
  - 프로세스가 CPU를 할당받으면 해당 프로세스가 완료될 때까지 CPU를 사용함
  - 모든 프로세스에 대한 요구를 공정하게 처리할 수 있음
  - 일괄 처리 방식에 적합하며, 중요한 작업(짧은 작업)이 중요하지 않은 작언(긴 작업)을 기다리는 경우가 발생할 수 있다.
  - 응답 시간 예측의 용이함
  - 종류
    - HRN(Highest Responce Ratio Next)
      - 짧은 작업에 유리한 SJF의 단점을 개선 한 기법, 각 작업의 우선순위로 서비스 해주는 스케줄링
      - 우선순위 = (대기시간 + 서비스 실행시간) / 실행시간
    - FIFO, FCFS, SJF
- 선점 스케줄링(Preemptive Scheduling)
  - 하나의 프로세스가 CPU를 할당받아 실행 하고 있을 때 우선순위가 높은 다른 프로세스가 CPU를 강제로 빼앗아 사용할 수 있는 스케줄링 기법
  - 우선순위가 높은 프로세스를 빠르게 처리할 수 있음
  - 주로 빠른 응답시간을 요구하는 대화식 시분할 시스템에 사용됨
  - 선점으로 인한 많은 오버헤드를 초래함-선점을 위해 시간 배당을 위한 인터럽트용 타이머 클럭이 필요함 
  - 종류 : SRT, 선점 우선순위, RR, 다단계 큐, 다단계 피드백 큐
- 페이지 교체 기법
  - FIFO(First In First Out) : 먼저 온걸 먼저 내보내는 방식
  - LFU(Least Frequently Used) : 최근에 가장 사용되지 않은 페이지 교체(참조 횟수 기준)
  - LRU(Lease Recently Used) : 최근에 가장 사용되지 않은 페이지 교체(참조 시간 기준)
  - NUR(Not Used Recently) 기법 : 참조, 갱신 비트를 이용하여 LRU의 오버헤드를 줄인 방식
    - 참조 갱신 비트가 00 01 10 11 순으로 11이 가장 나중에 교체된다
  - OPT(OPTimal) : 가장 오랫동안 사용되지 않을 페이지를 교체하는 구현이 불가능한 최적의 알고리즘
- 에이징(Aging)
  - 특정프로세스의 우선순위가 낮아 무한정 기다리게 되는 경우, 양보하거나 기다린 시간에 비례하여 일정 시간이 지나면 우선순위를 한단계씩 높여 무기한 문제를 해결하는 기법
  - SJF나 우선순위 기법에서 발생할 수 있는 무한 연기 상태, 기아 상태를 예방 할 수 있다
- 데커(Dekker) 알고리즘
  - 교착상태가 발생하지 않음을 보장
  - 공유 데이터에 대한 처리에 있어서 상호배제를 보장
  - 소프트웨어적으로 해결한 방법
- crossbar switch matrix
  - 각 기억장치마다 다른 경로를 사용할 수 있다
  - 시분할 및 공유버스 방식에서 버스의 숫자를 기억장치의 숫자만큼 증가시킨 구조
  - 두 개의 서로 다른 저장장치를 동시에 참조 가능
  - 장치의 연결이 복잡
- 교착상태(deadlock)
  - 한정된 자원을 여러 곳에서 사용하려고 할 때 모두 작업수행을 할 수 없이 대기 상태에 놓이는 상태
  - 발생 조건
    - 상호 배제(Mutual Exclusion)
    - 점유 및 대기(Hold and Wait)
    - 비선점(Nonpreemption)
    - 환영대기(Circular Wait)
  - 해결 방법
    - Avoidance(회피) : 교착 상태가 발생할 가능성을 배제하지 않고, 교착 상태가 발생하면 적절히 피해나가는 방법
     - ex) 은행원 알고리즘
    - Detection(발견): 시스템에 교착생태가 발생했는지 점검하여 교착 상태에 있는 프로세스와 자원을 발견하는 것으로, 자원 할당 그래프 등을 사용
    - Prevention(예방): 교착 상태가 발생되지 않도록 사전에 시스템을 제어하는 방법으로, 교착 상태 발생의 4가지 조건 중에서 어느 하나를 제거하여 수행되며 일반적으로 자원의 낭비가 가장심함
    - Recovery(회복): 교착 상태를 일으킨 프로세스를 종료하거나 교착 상태의 프로세스에 할당된 자원을 선점하여 프로세스나 자원을 회복하는것
- 프로세스의 정의
  - PCB를 가진 프로그램 
  - 비동기적 행위를 일으키는 주체 
  - 프로세서가 할당되는 실체 
  - 활동 중인 프로시저(Procedure)
- 모니터
  - 동기화 문제를 해결하는 도구 중 하나
  - 외부의 프로시저를 직접 액세스 불가
  - 모니터의 경계에서 상호배제 시행
  - 정보 은폐의 개념 사용
  - 자원 요구 프로세스는 그 자원 관련 모니터 진입부를 반드시 호출
  - 한 순간에 하나의 프로세스만이 모니터에 진입 가능

## 소프트웨어공학
- 데이터 흐름도(DFD: Data Flow Diagram)의 구성요소
  - 프로세스(Process) : 원
  - 데이터 흐름(Data Flow) : 화살표
  - 데이터 저장소(Data Store) : 직선(평행선, 이중선)
  - 외부 엔티티(External Entity) : DFD 범위 밖에 사각형
  - 단말 : 사각형
- 테스트 기법
  - 블랙박스 검사 : 어떤 소프트웨어를 내부 구조나 작동 원리를 모르는 상태에서 소프트웨어의 동작을 검사하는 방법
    - 동치 분할 검사, 경계값 분석, 원인-효과 그래프 검사, 오류 예측 검사, 비교 검사
  - 화이트박스 검사 : 블랙박스와 반대되며, 보통 내부 소스코드를 테스트하는 방법
    - 기초 경로 검사, 조건 검사, 루프 검사, 데이터 흐름 검사 등
- Component : 소프트웨어 재사용과 관련하여 객체들의 모임, 대규모 재사용 단위로 정의되는 것
  - 컴포넌트 기반 개발
    - 후보 컴포넌트가 요구되는 기능을 수행하는지를 조사하기 위해 컴포넌트 검증을 수행한다
    - 컴포넌트 라이브러리가 컴포넌트 확장 언어를 제공하면 그레이-박스 랩핑을 적용할 수 있다.
    - 어플리케이션 구현을 위해 검증, 개작, 개발된 컴포넌트 들을 조립하는 컴포넌트 합성을 수행한다.
- 소프트웨어 품질 보증을 위한 정형 기술 검토의 지침 사항
  - 각 체크 리스트를 작성하고, 자원과 시간 일정을 할당
  - 검토의 과정과 결과를 재검토
  - 논쟁과 반박을 제한
- 소프트웨어 품질 목표
  - 정확성(Correctness) : 사용자의 요구 기능을 충족시키는 정도
  - 무결성(Integrity)
  - 유연성(Flexibility)
  - 이식성(Portability)
- User Interface 설계 시 오류 메시지나 경고에 관한 지침
  - 메시지는 이해하기 쉬워야 함
  - 오류로부터 회복을 위한 구체적인 설명이 제공되어야 함
  - 소리나 색 등을 이용하여 듣거나 보기 쉽게 의미 전달을 해야함
- stub 모듈
  - 하향식 통합 테스트 수행을 위해 일시적으로 필요한 조건만을 가지고 임시로 제공되는 시험용
- CASE(Computer-aided software engineering)
  - 소프트웨어, 하드웨어, 데이터베이스, 테스트 등을 통합하여 소프트웨어를 개발하는 환경을 조겅한다는 의미
  - 주요 기능 : 소프트웨어 생명주기 전 단계의 연결, 다양한 소프트웨어 개발 모형 지원, 그래픽 지원 등
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
- 소프트웨어 비용 추정모형(Estimation Models)
  - COCOMO(Constructive Cost Model)
    - 시스템의 비용을 산정하기 위해 시스템을 구성하고 있는 모듈과 서브 시스템의 비용 합계를 계산하는 방식
    - 특징 : 비용 예측, 의존성, 유연성, 이용성
    - 모델 유형 : 기본형, 중간형, 발전형
    - 모델 프로젝트 유형
      - organic(유기적) Mode : 50,000 코드 라인(50KDSI) 이하
        - KDSI(Kilo Delivered Source Instruction) : 전체 라인수를 1000라인 단위로 묶은 것으로, KLOC(Kilo LOC)와 같다
      - Semidetached Mode(반 결합 모드 프로젝트) : 300,000 코드 라인 정도
      - Embedded Mode(내장모드 프로젝트) : 300,000 코드 라인 이상의 대형 프로젝트
  - Putnam 모형
    - 소프트웨어 생명 주기의 전 과정 동안 사용될 노력의 분포를 가정하는 모형
  - 기능점수(FP) 모형
    - Albrecht가 제안한 것
    - 소프트웨어의 기능을 증대시키는 요인별로 가중치를 부여
    - 요인별 가중치를 합산하여 총 기능을 점수를 산출
    - 총 기능 점수와 영향도를 이용하여 기능 점수(FP)를 구한 후, 이를 이용해서 비용을 산정하는 기법
- 결합도(coupling) : 어떤 모듈이 다른 모듈에 의존하는 정도, 약할수록 이상적
  - 순서(약->강) : 자료 - 스탬프 - 제어 - 외부 - 공통 - 내용
  - 암기법 : (자)(스)니까 합격(제)(외) (공)부는 (내)처럼
  - 자료 결합도(data coupling) : 모듈들이 파라미터 등을 통해 데이터를 공유하는 경우
  - 스탬프 결합도(stamp coupling) : 데이터 구조를 공유하고 서로 다른 일부만을 사용하는 경우
  - 제어 결합도(control coupling) : 하나의 모듈이 다른 모듈로 무엇을 해야하는지에 대한 정보를 넘겨줌으로써 다른 모듈의 흐름을 제어
  - 외부 결합도(external coupling) : 두 개의 모듈이 외부에서 도입된 데이터 포맷, 통신 프로토콜, 또는 디바이스 인터페이스를 공유할 때 발생
  - 공통 결합도(common coupling) : 두 개의 모듈이 같은 글로벌 데이터를 공유하는 상태
  - 내용 결합도(content coupling,  Pathological coupling) : 하나의 모듈이 다른 모듈의 내부 동작을 수정하거나 내부 동작에 의존하는 상태
  - [참조](https://ko.wikipedia.org/wiki/%EA%B2%B0%ED%95%A9%EB%8F%84)
- 모듈의 응집도(cohension) : 모듈 내부의 기능적인 집중 정도, 강할수록 이상적
  - 순서(강->약) : 기능적 - 순차적 - 교환적 - 절차적 - 시간적 - 논리적 - 우연적
  - 암기법 : (기순교절시논우) (기)엽고 (순)진한 (교)회오빠는 (절)은 (시)러 (노[논])(우)
  - 기능적 응집도(Functional Cohension) : 모듈 내부의 모든 기능이 단일한 목적을 위해 수행되는 경우
  - 순차적 응집도(Sequential Cohension) : 모듈 내에서 한 활동으로 부터 나온 출력값을 다른 활동이 사용할 경우
  - 교환적 응집도(Communication Cohension) : 동일한 입력과 출력을 사용하여 다른 기능을 수행하는 활동들이 모여있을 경우
  - 절차적 응집도(Procedural Cohension) : 모듈이 다수의 관련 기능을 가질 때 모듈 안의 구성요소들이 그 기능을 순차적으로 수행할 경우
  - 시간적 응집도(Temporal Cohension) : 연관된 기능이라기 보단 특정 시간에 처리되어야 하는 활동들을 한 모듈에서 처리할 경우
  - 논리적 응집도(Logical Cohension) : 유사한 성격을 갖거나 특정 형태로 분류되는 처리 요소들이 한 모듈에서 처리되는 경우
  - 우연적 응집도(Coincidental Cohension) : 모듈 내부의 각 구성요소들이 연관이 없을 경우
- 자동화 추정 도구 : 비용 산정의 자동화를 위해 개발된 도구로는 SLIM과 ESTIMACS가 존재
  - SLIM : Rayleigh - Norden 곡선과 Putnam 예측 모델을 기초로 하여 개발된 자동화 추정 도구
  - ESTIMACS : 다양한 프로젝트와 개인별 요소를 수용하도록 FP 모형을 기초로 하여 개발된 자동화 추정 도구
- 객체 지향 분석 방법론
  - Booch 방법 : 미시적(Micro), 거시적(Macro) 개발 프로세스를 모두 사용하는 분석 방법으로, 클래스와 객체들을 분석 및 식별하고 클래스의 속성과 연산을 정의
  - Jacobson 방법 : Use Case를 강조하여 사용하는 분석 방법
  - code와 yourdon 방법 : E-R 다이어그램을 사용하여 객체의 행위를 모델링하며, 객체 식별, 구조식별, 주제 정의, 속성과 인스턴스 연결 정의, 연산과 메시지 연결 정의 등의 과정으로 구성
  - Wirfs-Brock 방법 : 분석과 설계 간의 구분이 없고, 고객 명세서를 평가해서 설계 작업까지 연속적으로 수행하는 기법
  - 럼바우(Rumbaugh) 분석 기법
    - 암기법 : 객동기
    - 객체 모델링(Object) : 객체도 작성, 정보모델링이라고도 함, 시스템에 요구되는 객체를 찾아내어 속성과 연산 식별 및 객체들 간의 관계를 규정
    - 동적 모델링(Dynamic) : 상태도 작성, 시간에 흐름을 따른 객체들 사이의 제어 흐름, 상호작용, 동작 순서 등의 동적인 행위 표현
    - 기능 모델링(Functional) : 자료흐름도를 이용하여 처리과정을 표현
- 나선형 모델
  - 개발 순서 : 계획 및 정의(Planning) -> 위험분석(Risk Analysis) -> 공학적개발(Engineering) -> 고객평가(Customer Evaluation)
  - [참고](https://m.blog.naver.com/PostView.nhn?blogId=seilius&logNo=130185846022&proxyReferer=https%3A%2F%2Fwww.google.com%2F)
- CPM(Critical Path Method)의 임계 경로 : 가장 오래 걸리는 경로
- 유지보수의 종류
  - 완전화(perfective)보수 : 소프트웨어의 본래 기능에 새로운 기능을 추가하거나 성능을 개선하기 위해 소프트웨어를 확장시키는 활동
  - 적응(adaptive) 보수 : 소프트웨어의 수명 기간 중에 운영체제나 컴파일러와 같은 프로그래밍 환경 변화와 주변장치 또는 다른 시스템 요소가 향상되거나 변경될때 기존의 소프트웨어에 반영하기 위해 수행하는 활동
  - 예방(preventive)보수 : 장래의 유지보수성 또는 신뢰성을 개선하거나 소프트웨어의 오류 발생에 대비하여 미리 예방 수단을 강구해 두는 활동
  - 수정(Corrective)보수 : 시스템을 운영하면서 검사 단계에서 발견하지 못한 잠재적인 오류를 찾아 수정하는 활동
- 브룩스의 법칙
  - 소프트웨어 개발 일정이 지연된다고 해서 말기에 새로운 인원을 투입하면 작업 적응 기간과 부작용으로 인해 일정은 더욱 지연된다는 법칙
  
## 데이터통신
- HDLC(High-level Data Link Control)
  - 프레임 구조 : Flag - Address - Control - Data - Frame Check Sequence - Flag
  - 모드
    - NRM(Normal Response Mode, 정규 응답 모드) : 반이중 / 점대점, 다중점 링크 / 불균형
    - ARM(Asynchronous Response Mode, 비동기 응답 모드) : 전이중 / 점대정 / 불균형
    - ABM(Asynchronous Balanced Mode, 비동기 균형 모드) : 전이중 / 점대점 / 균형
  - 프레임 종류
    - I-Frame(Information, 정보프레임) : 제어부가 0으로 시작하는 프레임, 사용자가 데이터를 전달하거나 피기백킹 기법을 통해 데이터에 대한 확인 응답을 보낼 때사용
    - S-Frame (Supervisory, 감독프레임) : 제어부가 10으로 시작하는 프레임,오류 제어와 흐름 제어를 위해 사용
    - U-Frame (Unnumbered, 비번호프레임) : 제어부가 11로 시작하는 프레임,링크와 동작 모두 설정과 관리, 오류 회복을 수행함
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
- ARP(Address Resolution Protocol, 주소 결정 프로토콜)
- RARP(Reverse Address Resolution Protocol, 역순 주소 결정 프로토콜) : 물리 네트워크 주소로 논리 IP 주소를 얻기위해 사용되는 프로토콜
- 해밍코드 : 이진 선형 블록 오류 정정 부호의 일종
  - 특징 : 2비트 오류 감지 및 1비트 오류 수정 가능
  - 수식 : ![Style_Images](https://github.com/BJ-Lim/DPE/blob/master/captures/%EC%88%98%EC%8B%9D.png)
    - k = 해밍 비트수, n = 정보 비트수
  - 해밍 거리
    - 검출 가능한 오류 갯수 : 해밍거리 - 1
    - 정정 가능한 최대 오류 개수(n) : 해밍거리 >= 2n + 1
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

  계층 순서 | 계층 이름 | 전송 단위 | 역할
  ---- | ---- | ---- | ----
  1 | 물리 | 비트 | 하드웨어 전송
  2 | 데이터 링크 | 프레임 | 오류제어, 흐름제어
  3 | 네트워크 | 패킷 | 라우팅, 흐름제어, 세그멘테이션, 오류 제어, 인터네트워킹
  4 | 전송 | (TCP)Segment/(UDP)Datagram | 단말기간의 오류 수정 및 흐름제어를 수행하여 신뢰성 있고 명확한 데이터를 전달하는 계층
  5 | 세션 | 메시지 | 양 끝단의 응용 프로세스가 통신을 관리하기 위한 방법 제공
  6 | 표현 | 메시지 | 코드간의 번역을 담당(ex. 인코딩)
  7 | 응용 | 메시지 | 응용 프로세스와 직접 통신
  
- Eye Pattern에 대한 해석
  - 눈을 떴을 때의 좌우 폭은 수신파를 상호 부호간 간섭(ISI, Inter Symbol Interference) 없이 샘플링 할 수 있는 주기가 됨
  - 바람직한 샘플링 주기는 눈을 가장 넓게 뜬 경우로 출력펄스의 폭 변동이나 펄스 위치의 변동이 클수록 주기간의 차는 커짐
  - 타이밍 에러에 의한 시스템의 감도는 샘플링 시간의 변동에 따라 눈이 감기는 비율로 결정
  - 눈을 뜬 상하의 높이는 특정한 샘플링 시간에 대한 잡음의 여유도임
  - ISI 간섭이 심할 경우 눈 패턴의 윗부분과 아랫부분이 겹치게 되어 눈이 완전히 감기게 됨
  - 입력신호가 완전히 랜덤하고 시스템이 선형적이라면 모든 눈의 모양은 동일하나 실제로는 전송 채널이 비선형적이므로 눈 패턴은 비대칭임
- 양자화 step(양자화 레벨) = 2^(표본당 전송 비트수)
- 나이키스트 정리
  - 채널 용량 = 주파수 대역폭 x log2(1+s/n)
- ARQ(Automatic Repeat Request, 자동 재전송 요청) : 오류가 발생한 프레임을 재전송하는 오류제어방식
  - Stop and Wait : 한 번에 하나씩 ACK를 받고, 후속 데이터 전송
  - Go-back-N(슬라이딩 윈도우) : 한번에 여러 개를 보낸후 하나의 ACK를 받고, 후속 데이터 전송
  - Selective-Repeat : 오류가 발생된(NAK) 프레임 이후 또는 오류 발생된 프레임 만을 재전송
- NRZ(None Return to Zero) 전송 부호
  
  종류 | 1 | 0
  ---- | ---- | ----
  NRZ-L(None Return to Zero - Level) | High | Low
  NRZ-I(None Return to Zero - Inverted) | 이전 레벨 반전 | 이전 레벨 유지
  NRZ-M(None Return to Zero - Mark) | 이전 레벨 반전 | 이전 레벨 유지
  NRZ-S(None Return to Zero - Space) | 이전 레벨 유지 | 이전 레벨 반전

- IPv6
  - Broadcast 주소 없음
- 이더넷의 기본 규격
  - ex) 10Base-5
  - 10 : 전송속도 = 10Mbps
  - Base : baseband
  - 전송매체 : 굵은 동축케이블
  - 5 : 한 세그먼트 최대 전송거리는 500m
- PCM(Pulse Code Modulation) 순서(변조 과정) : 표본화 - 양자화 - 부호화
  - 표본화(Sampling) : 일정 시간 간격으로 아날로그 신호의 순간적인 값을 취하는 것
  - 양자화(Quantization) : 진폭에 따라 이산적인 각각의 대푯값으로 변환 하는 것
  - 부호화(Coding) : 0과 1의 이진수로 표현하는 것
- 축적교환방식
  - 송신측에서 전송한 데이터를 송신 측 교환기에 저장시켰다가 이를 다시 적절한 통신 경로를 선택하여 수신 측 터미널에 전송하는 방식
  - 종류
    - 메시지 교환방식
    - 패킷 교환 방식
      - 가상회선방식
      - 데이터그램방식
- 회선교환방식
  - 통신을 원하는 두 지점을 교환기를 이용하여 물리적으로 접속시키는 방식
- OSPF(Open Shortest Path First, 최단 경로 우선 프로토콜)
  - 인터넷 프로토콜(IP) 네트워크를 위한 링크 스테이트 라우팅 프로토콜
  - 멀티캐스팅 지원
  - 네트워크 변화에 신속하게 대처 가능
  - 최단 경로 탐색에 Dijkstra 알고리즘 사용
- Hand off : 이동통신 가입자가 셀 경계를 지나면서 신호의 세기가 작아지거나 간섭이 발생하여 통신 품질이 떨어져 현재 사용 중인 채널을 끊고 다른 채널로 이동하는 것
- ATM cell의 크기
  - 1 옥텟 = 8비트
  - 헤더 = 5 옥텟, payload(유로부하) = 48 옥텟
- SONET(Synchronous Optical Network)
  - 광전송망 노드와 망간의 접속을 표준화한 것
  - 다양한 전송기기를 상호 접속하기 위한 광 신호와 인터페이스 표준 제공
  - STS-12의 기본 전송속도는 622.08MBbps
- 동기식 문자 지향 프로토콜의 제어문자
  - SOH(Start Of Heading) : 헤딩의 시작
  - STX(Start of Text) : 헤딩의 종료 및 본문의 시작
  - SYN(SYNchronous Idle) : 문자 동기
  - DLE(Data Link Escape) : 제어 문자 앞에 삽입
