<div align="center">

<img src="./image/profile.png" width="140" alt="정정교 프로필 사진" />

# 정정교 Junggyo Jung

**Backend Developer**

[![Email](https://img.shields.io/badge/willy__1020@naver.com-03C75A?style=flat-square&logo=naver&logoColor=white)](mailto:willy_1020@naver.com)
[![Blog](https://img.shields.io/badge/Tistory-willie의_작은_공간-000000?style=flat-square&logo=tistory&logoColor=white)](https://willie1020.tistory.com/)
[![Portfolio](https://img.shields.io/badge/Portfolio-PDF-FF9900?style=flat-square&logo=adobeacrobatreader&logoColor=white)](./docs/Portfolio_JunggyoJung.pdf)

</div>

<br>

## Experience

| 기간 | 소속 | 내용 |
|:---:|---|---|
| <code>2026.09&nbsp;~&nbsp;현재</code> | **하나금융티아이** | 금융 IT 서비스 개발 및 운영 |
| <code>2026.06</code> | **삼성인력개발원** | 삼성 계열사 사장단 및 임원단 대상 AX 교육 보조강사 <br> Claude Code 멀티 에이전트, Google AI 도구 실습 지원 |
| <code>2019.12</code> | **GDS 컨설팅 그룹** | 빅데이터 플랫폼 표준화 사업 참여 (단기 인턴) |

<br>

## Projects

### WITHY
AI 클린봇을 탑재한 실시간 영상 같이보기 서비스

[![Award](https://img.shields.io/badge/SSAFY_공통_프로젝트-최우수팀_선정,_우수상_%28150팀_중%29-E3A008?style=flat-square)](#awards)
[![GitHub](https://img.shields.io/badge/GitHub-WITHY-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Watch-with-WITHY/WITHY-SERVER)

| 기간 | 소속 | 팀 구성 | 역할 |
|:---:|:---:|:---:|:---:|
| <code>2026.01&nbsp;~&nbsp;2026.02</code> | SSAFY 14기 공통 프로젝트 | 6명 (BE 2) | 팀 리더(PM), 기획, 백엔드 |

| 과제 | 문제와 해결 | 결과 |
|---|---|---|
| **AI 통신 지연** | JSON 파싱 오버헤드로 비속어 검사 지연 <br> → REST를 gRPC(Protobuf)로 전환 | **처리량 25% 향상** <br> **평균 지연 32% 단축** (517 → 356ms) <br> **최대 지연 63% 단축** (1.4 → 0.5s) |
| **AI 장애 전파** | 무거운 스포일러 검사가 메인 서버에 영향 <br> → Kafka 비동기 분리, Lua Script 원자 처리 | **AI 서버 장애 시 채팅 유실 0건** |
| **AI 호출 비용** | 추천 요청마다 영화 줄거리 전체 전송 <br> → 파티 생성 시점에 Context Caching | **입력 토큰 비용 90% 절감** |
| **영상 동기화** | 클라이언트 간 시간 차이로 재생 시점 불일치 <br> → 서버 시간 기준 재생 위치 보정 공식 | **동기화 오차 12ms 이내** <br> 50명 동시 시청 기준 |
| **프로젝트 리딩** | 5주 안에 기능 완성과 품질 확보 필요 <br> → 기술 방향, 일정, 이슈 진행 총괄 | **이슈 339건 해결** <br> 1,000명 대상 최종 발표 |

**Tech** `Java 17` `Spring Boot 3` `Spring Security` `JPA` `QueryDSL` `gRPC` `WebSocket(STOMP)` `Kafka` `MySQL 8` `Redis` `Docker` `Jenkins` `Nginx`

<br>

### Tickle
AI 기반 매크로 방지 공정 티켓팅 플랫폼

[![Award](https://img.shields.io/badge/SSAFY_자율_프로젝트-우수상_%28116팀_중%29-E3A008?style=flat-square)](#awards)
[![GitHub](https://img.shields.io/badge/GitHub-Tickle-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Tickle-ticket/Tickle)

| 기간 | 소속 | 팀 구성 | 역할 |
|:---:|:---:|:---:|:---:|
| <code>2026.04&nbsp;~&nbsp;2026.05</code> | SSAFY 14기 자율 프로젝트 | 6명 (BE 2) | 인프라 전담, 백엔드 |

| 과제 | 문제와 해결 | 결과 |
|---|---|---|
| **대기열 응답 지연** | SSE 장기 연결로 스레드 고갈 <br> 대기자 1명당 Redis 7회 개별 호출 <br> → Virtual Thread, Redis Pipeline 도입 | **P95 응답시간 49% 단축** <br> (889ms → 454ms) <br> **Redis 호출 85% 감소** |
| **좌석 선점 병목** | 회차 단위 분산락으로 다른 좌석까지 대기 <br> → 좌석 단위 InnoDB row lock 전환 | **100건 동시 요청 시** <br> **성공 1건, 에러 0건** |
| **Redis 단일 장애점** | 노드 장애 시 대기열, 선점, 인증 동시 중단 <br> → Redis Sentinel 구성 <br> (Master 1, Replica 2, Sentinel 3) | **5초 내 자동 페일오버** |
| **매크로 탐지 연동** | 정상 사용자와 매크로 구분 기준 부재 <br> → 행동 데이터 30종 수집, AI 추론, <br> 블랙리스트 등록 파이프라인 설계 | **6가지 매크로 유형 탐지** <br> 탐지 즉시 블랙리스트 차단 |

**Tech** `Java 21` `Spring Boot 3.4` `Spring Security` `JPA` `Kafka` `SSE` `MySQL 8` `Redis 7` `Docker` `Jenkins` `AWS` `Nginx` `Prometheus` `Grafana`

<br>

### Terning
대학생 맞춤 인턴 공고 탐색 및 지원 일정 관리 앱

[![Award](https://img.shields.io/badge/SOPT_34기_APPJAM-최우수상-E3A008?style=flat-square)](#awards)
[![GitHub](https://img.shields.io/badge/GitHub-Terning-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/teamterning/Terning-Server)
[![Behance](https://img.shields.io/badge/Behance-Terning-1769FF?style=flat-square&logo=behance&logoColor=white)](https://www.behance.net/gallery/209714965/terning-College-Internship-App)

| 기간 | 소속 | 팀 구성 | 역할 |
|:---:|:---:|:---:|:---:|
| <code>2024.06&nbsp;~&nbsp;2025.10</code> | SOPT 34기 APPJAM | 14명 (서버 3) | 백엔드 리더, 인프라 전담 |

| 과제 | 문제와 해결 | 결과 |
|---|---|---|
| **조회 성능** | 스크랩 여부 확인으로 N+1 쿼리 발생 <br> → QueryDSL Tuple 기반 Left Join 단일 쿼리 | **평균 응답시간 61% 단축** <br> **처리량 2.5배 향상** |
| **알림 장애 전파** | 알림 로직과 운영 서버의 강한 결합 <br> → 알림 서버 분리, AWS Lambda 스케줄링 | **알림 장애와 공고 조회 분리** <br> 푸시 알림 3종 운영 |
| **스테이징 비용** | 스테이징용 RDS 신설 시 비용 증가 <br> → 단일 PostgreSQL 내 스키마 분리 | **DB 비용 70% 절감** <br> **전체 운영비 40% 절감** |
| **배포 안정성** | 신규 버전 배포 시 서비스 중단 위험 <br> → Nginx Blue/Green 무중단 배포 | **배포 다운타임 0** <br> **누적 사용자 1,700명 이상** |

**Tech** `Java 21` `Spring Boot 3` `Spring Security` `JPA` `QueryDSL` `PostgreSQL` `FCM` `AWS EC2` `AWS Lambda` `Docker` `GitHub Actions` `Nginx`

<br>

### CapSure
필요한 보장만 골라 월 단위로 구독하는 보험 플랫폼

[![GitLab](https://img.shields.io/badge/GitLab-SSAFY_내부_비공개-FC6D26?style=flat-square&logo=gitlab&logoColor=white)](#capsure)

| 기간 | 소속 | 팀 구성 | 역할 |
|:---:|:---:|:---:|:---:|
| <code>2026.02&nbsp;~&nbsp;2026.04</code> | SSAFY 14기 특화 프로젝트 | 5명 (BE 3) | 팀장(PM), 기획, 백엔드 |

| 과제 | 문제와 해결 | 결과 |
|---|---|---|
| **구독 변경 관리** | 월 구독의 변경 시점과 상태 관리 필요 <br> → 변경 예약, 확정, 취소 상태 흐름 설계 | **익월 적용 변경 예약** <br> **매월 자동 갱신** |
| **감사 로그 정합성** | 업무 처리와 감사 로그 간 불일치 위험 <br> → Transactional Outbox 패턴 적용 <br> (메시지 브로커 없이 스케줄러 폴링) | **이관 시 중복 확인으로 멱등성 보장** <br> 실패 건 원인과 함께 DLQ 저장 |
| **요청 추적** | 여러 로그에 흩어진 요청 흐름 파악 필요 <br> → MDC 기반 요청 ID 로그 추적 | **요청 ID로 전 구간 로그 조회** <br> 로그 내 민감정보 자동 마스킹 |

**Tech** `Java` `Spring Boot` `Spring Security` `MyBatis` `PostgreSQL` `GPT API` `Gemini API` `AWS EC2` `GitLab CI` `Loki` `Grafana`

<br>

### Other Projects

| 프로젝트 | 소개 | 담당 업무 및 성과 |
|---|---|---|
| **[SOPT Playground](https://github.com/sopt-makers/sopt-playground-backend)** <br> <code>2025.02&nbsp;~&nbsp;2025.08</code> | SOPT 3,000명 규모 커뮤니티 | JWK 기반 JWT 공통 인증 모듈 구축 <br> 커뮤니티, 타임캡슐, 언급 기능 개발 |
| **[AlgoHub](https://github.com/GAMZA-BAT/algohub-server)** <br> <code>2025.07&nbsp;~&nbsp;2026.06</code> | 알고리즘 스터디 관리 플랫폼 | 추천 API 3종 설계 <br> (최다 활동, 가입률 상승, 난이도 유사) <br> 스냅샷 테이블로 실시간 집계 제거 |
| **[Confeti](https://github.com/team-confeti/confeti-api-server)** <br> <code>2024.03&nbsp;~&nbsp;2024.08</code> | 공연 및 페스티벌 정보 플랫폼 | 테이블 5개 이상 반정규화 <br> 핵심 API 응답시간 80% 단축 <br> 공연 데이터 수집 배치 서버 분리 |
| **[Coumo](https://github.com/UMC-5th-Coumo/server)** <br> <code>2023.12&nbsp;~&nbsp;2024.02</code> | QR 코드 쿠폰 적립 플랫폼 | 회원가입, 로그인 API 개발 <br> 사장님용 영수증 구독, 디자인 기능 |

<br>

## Tech Stack

| 분류 | 기술 |
|---|---|
| **Backend** | ![Java](https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white) ![JPA](https://img.shields.io/badge/JPA_/_QueryDSL-59666C?style=flat-square&logo=hibernate&logoColor=white) ![MyBatis](https://img.shields.io/badge/MyBatis-BE0000?style=flat-square) |
| **Database** | ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) |
| **Messaging** | ![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white) ![gRPC](https://img.shields.io/badge/gRPC-244C5A?style=flat-square&logo=google&logoColor=white) ![WebSocket](https://img.shields.io/badge/WebSocket_/_SSE-010101?style=flat-square&logo=socketdotio&logoColor=white) |
| **Infra / DevOps** | ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white) ![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) |
| **Monitoring / Test** | ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white) ![JUnit5](https://img.shields.io/badge/JUnit5-25A162?style=flat-square&logo=junit5&logoColor=white) ![k6](https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white) ![JMeter](https://img.shields.io/badge/JMeter-D22128?style=flat-square&logo=apachejmeter&logoColor=white) |
| **Collaboration** | ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![Jira](https://img.shields.io/badge/Jira-0052CC?style=flat-square&logo=jira&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-000000?style=flat-square&logo=notion&logoColor=white) ![Figma](https://img.shields.io/badge/Figma-F24E1E?style=flat-square&logo=figma&logoColor=white) |

<br>

## Education

| 기간 | 기관 | 내용 |
|:---:|---|---|
| <code>2025.07&nbsp;~&nbsp;2026.06</code> | **SSAFY 14기 서울캠퍼스** | 우수 등급(상위 30%) 수료, 총 1,628시간 <br> 전공반 반장, 알고리즘 스터디장, CS 스터디 그룹장 |
| <code>2023.03&nbsp;~&nbsp;2025.08</code> | **한양대학교** | 컴퓨터소프트웨어학부 졸업 (편입) |
| <code>2018.03&nbsp;~&nbsp;2023.01</code> | **고려대학교** | 경제통계학부 |

<br>

## Awards

| 연도 | 수상 | 주관 |
|:---:|---|---|
| <code>2026</code> | [SSAFY 자율 프로젝트 우수상 (Tickle, 116팀 중)](./image/%E1%84%8C%E1%85%A1%E1%84%8B%E1%85%B2%E1%86%AF%E1%84%91%E1%85%B3%E1%84%85%E1%85%A9%E1%84%8C%E1%85%A6%E1%86%A8%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%AE%E1%84%89%E1%85%AE%E1%84%89%E1%85%A1%E1%86%BC.jpg) | 삼성전자 |
| <code>2026</code> | [SSAFY 공통 프로젝트 최우수팀 선정 및 우수상 (WITHY, 150팀 중)](./image/%E1%84%80%E1%85%A9%E1%86%BC%E1%84%90%E1%85%A9%E1%86%BC%E1%84%91%E1%85%B3%E1%84%85%E1%85%A9%E1%84%8C%E1%85%A6%E1%86%A8%E1%84%90%E1%85%B3%20%E1%84%8B%E1%85%AE%E1%84%89%E1%85%AE%E1%84%89%E1%85%A1%E1%86%BC.jpg) | 삼성전자 |
| <code>2024</code> | [NOW SOPT 34th APPJAM Demoday 최우수상 (Terning)](./image/SOPT_APPJAM_%E1%84%8E%E1%85%AC%E1%84%8B%E1%85%AE%E1%84%89%E1%85%AE%E1%84%89%E1%85%A1%E1%86%BC.JPG) | SOPT |
| <code>2024</code> | [FORIF 23 Winter Hackathon 1위](./image/forif.pdf) | 한양대학교 FORIF |
| <code>2022</code> | [학장상 (평점 4.5 만점)](./image/%E1%84%92%E1%85%A1%E1%86%A8%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%89%E1%85%A1%E1%86%BC.jpg) | 고려대학교 |
| <code>2021</code> | [707 대테러 합동훈련 종합평가 1위, 특수임무단장상](./image/707%E1%84%90%E1%85%B3%E1%86%A8%E1%84%89%E1%85%AE%E1%84%8B%E1%85%B5%E1%86%B7%E1%84%86%E1%85%AE%E1%84%83%E1%85%A1%E1%86%AB%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%89%E1%85%A1%E1%86%BC.pdf) | 707 특수임무단 |

<br>

## Certificates

| 자격증 | 발행처 | 취득 |
|---|---|:---:|
| [TOEIC Speaking IH (150)](./image/%E1%84%8B%E1%85%A5%E1%84%92%E1%85%A1%E1%86%A8%E1%84%89%E1%85%A5%E1%86%BC%E1%84%8C%E1%85%A5%E1%86%A8%20%E1%84%89%E1%85%A1%E1%84%8C%E1%85%A5%E1%86%AB%E1%84%83%E1%85%B3%E1%86%BC%E1%84%85%E1%85%A9%E1%86%A8%20%E1%84%92%E1%85%AA%E1%86%A8%E1%84%8B%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A5.pdf) | ETS | <code>2026.02</code> |
| [정보처리기사](./image/%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%87%E1%85%A9%E1%84%8E%E1%85%A5%E1%84%85%E1%85%B5%E1%84%80%E1%85%B5%E1%84%89%E1%85%A1_%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%80%E1%85%AD.pdf) | 한국산업인력공단 | <code>2025.09</code> |
| [투자자산운용사](./image/%ED%88%AC%EC%9E%90%EC%9E%90%EC%82%B0%EC%9A%B4%EC%9A%A9%EC%82%AC.pdf) | 한국금융투자협회 | <code>2026.01</code> |
| [SQLD (SQL 개발자)](./image/SQLD%E1%84%8C%E1%85%A1%E1%84%80%E1%85%A7%E1%86%A8%E1%84%8C%E1%85%B3%E1%86%BC.pdf) | 한국데이터산업진흥원 | <code>2025.04</code> |
| [ADsP (데이터분석 준전문가)](./image/ADSP.pdf) | 한국데이터산업진흥원 | <code>2026.06</code> |
| [컴퓨터활용능력 1급](./image/%E1%84%8F%E1%85%A5%E1%86%B7%E1%84%92%E1%85%AA%E1%86%AF1%E1%84%80%E1%85%B3%E1%86%B8.jpg) | 대한상공회의소 | <code>2021.12</code> |
| [빅데이터분석실무 2급](./image/%E1%84%87%E1%85%B5%E1%86%A8%E1%84%83%E1%85%A6%E1%84%8B%E1%85%B5%E1%84%90%E1%85%A5%20%E1%84%87%E1%85%AE%E1%86%AB%E1%84%89%E1%85%A5%E1%86%A8%E1%84%89%E1%85%B5%E1%86%AF%E1%84%86%E1%85%AE%202%E1%84%80%E1%85%B3%E1%86%B8%20-%20%E1%84%92%E1%85%A1%E1%86%AB%E1%84%80%E1%85%AE%E1%86%A8%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%87%E1%85%A9%E1%84%8B%E1%85%B5%E1%86%AB%E1%84%8C%E1%85%A2%E1%84%80%E1%85%A2%E1%84%87%E1%85%A1%E1%86%AF%E1%84%8B%E1%85%AF%E1%86%AB.pdf) | 한국정보인재개발원 | <code>2019.06</code> |
| [ICDL Python](./image/icdl_python.jpg) | ICDL | <code>2019.07</code> |

<br>

## Activities

| 기간 | 활동 | 주요 내용 |
|:---:|---|---|
| <code>2025.07&nbsp;~&nbsp;2026.06</code> | **SSAFY 14기 서울캠퍼스** <br> [수료증](./image/SSAFY_certificate.pdf) | **공통, 특화, 자율 프로젝트 3회 중 2회 수상** <br> 이달의 동료 2회 선정 <br> 입학생 대표 삼성 뉴스룸 인터뷰 |
| <code>2025.02&nbsp;~&nbsp;2025.08</code> | **SOPT Makers 36기** <br> [GitHub](https://github.com/sopt-makers/sopt-playground-backend) | **3,000명 규모 커뮤니티** 백엔드 개발 및 운영 <br> 디자이너 40명 설문 후 협업 세미나, 30명 참석 |
| <code>2024.03&nbsp;~&nbsp;2024.07</code> | **SOPT 34기 서버 파트** <br> [수료증](./image/SOPT%E1%84%89%E1%85%AE%E1%84%85%E1%85%AD%E1%84%8C%E1%85%B3%E1%86%BC.JPG), [APPJAM](./image/APPJAM%E1%84%92%E1%85%AA%E1%86%AF%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%B5%E1%86%AB%E1%84%8C%E1%85%B3%E1%86%BC%E1%84%89%E1%85%A5.JPG), [SOPKATHON](./image/SOPKATHON%E1%84%92%E1%85%AA%E1%86%AF%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%B5%E1%86%AB%E1%84%8C%E1%85%B3%E1%86%BC%E1%84%89%E1%85%A5.JPG) | 서버 파트 리드, **APPJAM 최우수상** (Terning) <br> 출시 후 실사용자 1,700명 이상 운영 |
| <code>2023.09&nbsp;~&nbsp;2024.02</code> | **UMC 5기 서버 파트** <br> [명예의 전당](./image/UMC%E1%84%86%E1%85%A7%E1%86%BC%E1%84%8B%E1%85%A8%E1%84%8B%E1%85%B4%E1%84%8C%E1%85%A5%E1%86%AB%E1%84%83%E1%85%A1%E1%86%BC.png), [활동인증서](./image/UMC%E1%84%92%E1%85%AA%E1%86%AF%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%B5%E1%86%AB%E1%84%8C%E1%85%B3%E1%86%BC%E1%84%89%E1%85%A5.png) | 주간 서버 과제로 **명예의 전당 최다 등재** <br> 3개월 팀 프로젝트 Coumo 서버 개발 |
| <code>2023.09&nbsp;~&nbsp;2023.12</code> | **한양대학교 FORIF** <br> [수료증](./image/forif.pdf) | **Winter Hackathon 8팀 중 1위** <br> Node.js 풀스택 과정 수료 |
| <code>2023.03&nbsp;~&nbsp;2024.02</code> | **한양대학교 ALOHA** | 알고리즘 동아리 정기 강의 및 문제 풀이 <br> 중급반 자료구조 심화 학습 |

<details>
<summary><b>2018 ~ 2019 학부 활동 더보기</b></summary>
<br>

| 기간 | 활동 |
|:---:|---|
| <code>2018.10&nbsp;~&nbsp;2019.10</code> | 고려대학교 장애학습지원센터 학습도우미 (534시간) |
| <code>2019.03&nbsp;~&nbsp;2019.12</code> | 공공정책대학 학생회 집행부장, 빅데이터와 국가통계 전공 학생회 사무국장 |
| <code>2019.03&nbsp;~&nbsp;2019.12</code> | 전공 스터디 SCR 회장, 밴드 소모임 청울림 회장 |
| <code>2019.03&nbsp;~&nbsp;2019.07</code> | 파이썬 스터디 BigPy 팀장 |
| <code>2019.09&nbsp;~&nbsp;2020.01</code> | 비교과 서포터즈 잡아라서포터즈 4기 |
| <code>2019.03&nbsp;~&nbsp;2019.06</code> | 중앙 마케팅 동아리 MMC |
| <code>2018.09&nbsp;~&nbsp;2018.12</code> | 교내 학습지원 비상서포터즈 6기 |

</details>

<br>

## GitHub Stats

<table>
  <tr>
    <td align="center"><img src="github-metrics-left.svg" alt="GitHub metrics" /></td>
    <td align="center"><img src="github-metrics-right.svg" alt="GitHub metrics" /></td>
  </tr>
</table>
