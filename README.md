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
## 데이터통신
