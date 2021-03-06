# 경력 활동사항

# 주로 개발한 제품
  - DAST(Dynamic Application Security Testing): 동적 분석. 웹 서버 애플리케이션을 대상으로 취약점을 검출하는 솔루션.
    - Truescan: 블랙박스 테스팅의 한계를 벗어나 서버 애플리케이션에 직접 접근하여 취약점을 검출하는 서비스
  - RASP(Runtime Application Self-Protection): 런타임 애플리케이션 자가 보호. 현재 동작 중인 애플리케이션에 공격성 행위가 감지되면 차단하는  솔루션.
  - 이벤트 클립보드: DAST 보조 도구로써, 주로 DAST 분석 시 세션처리를 위해 로그인하는 부분을 기록하고 필요할 때 재현하는 크롬 확장 프로그램.

## 1. 웹 애플리케이션 동적 분석 취약점의 소스코드 내 검출 위치 확인 (연구)

* 진행 기간
  - 2020.10 ~ 2021.10
* 주요 내용
  - 새로운 기능을 위한 연구(혼자 연구 진행)
  - 동적 분석 서비스를 사용하는 개발자의 입장에서 어느 소스코드를 중점으로 봐야하는지 알 수 있도록 어떻게 정보 제공에 대한 연구
  - 서버 플랫폼이 아닌 언어를 대상으로 연구 진행
  - 모든 서버 언어를 대상으로 할 수 있도록 구조 설계. 주 언어는 Java, Node.js, python
  - 프로그래밍 언어학 측면에서 분석
  - 화이트 박스 테스트에서 그레이 박스 테스트로 변경하는 연구이기에 정적 및 동적 분석 그리고 dynamic instrumentation 기술 검토
  - 제품 DAST와 Truescan 프로토콜 확장 설계
  - Truescan과 에이전트 간의 프로토콜 확장 설계
  - 정적 분석은 스패로우 제품 SAST을 만드는 팀에 도움을 요청. 정적 분석의 경우 주어진 소스코드를 가지고 제안된 구조를 설계
  - 시간과 메모리를 최소화하되, 메모리를 늘려서라도 시간을 줄일 수 있는 방향도 고려토록 연구 진행(우선순위가 시간이 메모리보다 높음)
  - 버전 업데이트와 성능 테스트를 위해 제시된 모든 언어에 대한 데모 환경 구축
* 기여한 점
  - 프로그래밍 언어 분석 및 일반화
  - 구조 기획 및 설계
  - 연구 제안서 작성
  - Java8 dynamic instrumentation 운용
  - Python dynamic instrumentation 설계/구현
  - Node.js dynamic instrumentation 설계/구현
  - 데모 환경 구축
    - 언어 Java
    - 언어 Python(pygoat)
    - 언어 Node.js(nodegoat)
  - 언어 Java, Python, Node.js에 대한 성능 테스트 진행
* 기술 스택
  - Python3
  - Node.js v16.13.0
  - Java8
  - maven, Rest API  
* 결과 및 성과
  - 제품 DAST에 관련된 엔진, 백엔드, 기획팀과 협의하에 2022년도 상반기 제품 DAST 로드맵에 해당 연구 기능 구현하기로 결정
  - 성능 테스트에서 시간 및 메모리상 충분히 적은 리소스로 기능을 수행할 수 있음을 확인
  - 여러 언어를 대상으로 각 함수 및 메모리 관리를 연구할 수 있는 기회
  - 제품 DAST 내부 Truescan 사이의 Rest API 세부 프로토콜까지 설계해볼 수 있는 기회
  - 여러 언어에 대해 dynamic instrumentation을 연구 및 구현함으로써 제품 RASP에 확장 가능성 제시
  
## 2. 이벤트 클립보드

* 진행 기간
  - 2019.01 ~ 2021.11
* 주요 내용
  - 사용자가 직접 발생시킨 이벤트를 감지하고 이를 기록하여 해당 동작을 재현
  - 웹 취약점을 재현 동작을 파일 형식으로 저장하여 DAST 서버와 연동
  - 유연한 UI로 기록된 이벤트를 편집
  - 크롬 확장 프로그램으로 개발
  - 크롬 웹 스토어에 접근할 수 없는 고객사에 설치 용이하게 패키지 생성
  - 유지 보수 서비스
* 기여한 점
  - 신규 버전 개발
  - 기업 사용자 장애 접수 및 대응 (패치 개발)
  - 프론트 사이드 개발 담당자
  - 레거시 코드 걷어낸 뒤 ES6에 맞게 리팩토링
  - 프레임 단위의 이벤트를 감지하여 기록 및 재현
  - 추가적으로 감지해야 하는 이벤트 연구 및 개발(ex: frame, iframe에서 발생하는 이벤트를 기록 및 재현할 수 있게 구현으로 DAST 엔진 추가 목표 수립)
* 기술 스택
  - Javascript (ECMAScript6)
  - Less
  - Chrome extension
  - Maven
* 결과 및 성과
  - 프레임 단위 이벤트 기록 및 재현이 가능하게 되어 좀 더 다양한 사이트를 분석 가능
  - 크롬 확장 프로그램의 API으로 구현하고 자바스크립트의 메시지 구조를 사용한 기회
  - 웹 브라우저(크롬)와 서버 플랫폼이 업데이트 됨에 따라 같이 발전하는 구조


## 3. 패치 모듈 개발

* 진행 기간
  - 2020.02 ~ 2021.10
* 주요 내용
  - 컨설팅과 엔지니어팀을 위한 사내 프로그램
  - 버전 업데이트, 핫픽스 할 때 용량 문제 해결하기 위함
  - 버전을 올리도록 패치하는 것뿐 아니라 낮출 수 있도록 함
  - 추후 패치 모듈을 커스터마이징할 수 있도록 오픈소스에 의존하지 않고 직접 구현
  - Teamcity와 연동하여 빌드할 때마다 새로운 패치 데이터 생성
  - Teamcity에서 이전 버전과 패치 버전을 선택하여 패치 데이터 생성
  - 버전이 오래된 제품을 업데이트 해야하는 경우 업데이트 대상 버전까지의 패치 데이터들을 모아서 일괄적으로 업데이트
  - GB 단위 제품에 대한 메모리 성능 테스트
  - Windows/Linux 지원
* 기여한 점
  - 패치 데이터 설계 및 구현
  - 패치 CLI 에이전트 개발
* 기술 스택
  - Java
  - maven
* 결과 및 성과
  - 기획과 추가적으로 들어온 개선사항을 모두 구현, QA까지 통과하여 성공적으로 마무리
  - GB 단위 제품에 대한 메모리 성능 테스트 및 개발자 테스트 완료
  - diff 라이브러리 활용
  - 컨설팅과 엔지니어 팀 내에 패치 모듈 공유 및 사용 매뉴얼 배포

## 4. 제품 DAST 전용 HTTP 라이브러리 및 모듈 기획, 설계 및 개발

* 진행 기간
  - 2019.10 ~ 2021.10
* 주요 내용
  - 제품 DAST에 HTTP 모듈 대체재 설계 및 개발
  - 기존 모듈에 있는 문제점 해결
	- 오픈 소스 모듈이기에 취약점 오탐 또는 미탐이 나는 취약점에 대해 디버깅할 수 없음
	- HTTP에 관한 기능을 추가하기 어려움
	- 오픈 소스 자체에 버그가 있어도 쉽게 패치하기 어려움
  - HTTP 2.0 버전 확장 가능성 고려하여 설계
  - 가능한 시간 복잡도가 적은 자료구조와 알고리즘을 사용하여 구현
* 기여한 점
  - 모듈 기획 및 개발
  - DAST 엔진 개발자와 협의하여 인터페이스 설계
* 기술 스택
  - Java
  - maven
* 결과 및 성과
  - DAST 전수 테스트 및 QA까지 통과하여 성공적으로 마무리
  - 개발 이후 버그 0건 유지
  - 취약점 오탐 또는 미탐이 사라졌고 커스터마이징할 수 있는 환경 구축

## 5. RASP Node.js 코어 개발

* 진행 기간
  - 2020.07 ~ 2021.10
* 주요 내용
  - 기존 RASP 솔루션 언어 확장
  - RASP가 설치된 서버에 직접 붙어 취약점 검출 로직 작성
  - 정의된 프로토콜에 따른 Rest API 송수신 구현
  - RASP 백엔드와 직접 통신하지 않고 RASP 에이전트와 통신하는 방식
  - Node.js의 언어적 특성을 이해 및 Node.js에 적합한 동적 계측(Dynamic instrumentation) 연구 및 구현
  - 서버 과부하를 막기위한 취약점 정보를 담은 HTTP 요청 제어
  - 서버 기동중에 RASP를 적용하고, 적용된 것을 취소하여 원복하는 기능 구현
* 기여한 점
  - RASP 에이전트와 통신하는 RASP Node.js 코어 개발
  - 언어 Node.js의 Dynamic instrumentation 연구 및 구현
  - HTTP 요청 및 응답 제어
* 기술 스택
  - Node.js v16.13.0
  - ECMAScript6 기반
* 결과 및 성과
  - 서버 과부화 테스트 및 QA까지 통과하여 성공적으로 마무리
  - 제품 설계자, 백엔드 개발자, RASP 에이전트 개발자와 협업 진행
  - MSA 기반의 모듈로 다중 통신과 프로토콜의 개념 이해

## 개인 연구

* 트라이(Trie)와 Java 패키지 연구
  - intellij IDE에서 프로젝트 내부에서 어떻게 패키지 및 클래스를 검색하는지 의문이 생겨 연구 시작
  - 총 세가지 구조를 제안하여 실험했고 결과를 확인
    - 연결 리스트 구조
	- Hash map 구조
	- 트라이(Trie) 구조
  * 보다 더 자세한 내용은 https://coloredrabbit.tistory.com/167 참고 바랍니다.
  
* DOM 유사도 분석
  - DAST 동적 분석 시간이 너무 오래걸려서 개인적으로 어떻게 시간을 줄이고자 개인적으로 연구
  - 두 가지 구조를 실험했고 결과를 확인
    - Randomized Longest Common Branch Sequences
    - Network flow
  * 보다 더 자세한 내용은 https://coloredrabbit.tistory.com/169 참고 바랍니다.

