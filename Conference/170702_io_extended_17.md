# IO Extended 17
GDG Korea 에서 운영하는 컨퍼런스

## The Age of Open Development
- 7,000+ Attendees
- 80+ I/O Extended events 

## 구글의 머신러닝 비전: TPU부터 모바일까지
- 기반 및 소프트웨어
    + 소프트웨어, Tensorflow 를 중심으로 모바일로부터 거대 연산 클러스터까지 다양한 스케일의 머신러닝 보급 준비
- 서비스 / 제품 ( Show Case )
    + Image-based breakthrough
        * Google Lens
            - 센서 기반의 위치 정보 서비스
            - 이미지 + 지역정보 + 추천 검색
            - 실시간으로 현재 위치의 정보 파악
            - 이미지 기반의 POV 정보 추적
            - 추천기능
            - Visual Positioning Service (VPS)
        * Google Photo
    + Google Home
        * 다중 사용자 구분 ( 신경망 기반의 빔포밍, 유저 인식 기술 )
        * 중요한 점
            - Google Home은 구글이 보여준 하나의 예다
            - Google Assistant 를 사용하여 누구나 만들 수 있다는것을 강조
    + Android Things
        * 임베디드 및 저스펙 환경을 위한 안드로이드 배포판
        * 개발킷, BSP 등 제공
        * H/W 프로토타이핑 업체 제휴
        * https://www.autopi.io/
    + Google Assistant API
        * Hoeword 라이브러리
            - 특정 키워드 (Hotword)
            - 타이머
            - 알람
        * 하드웨어
            - 최소 라즈베리파이 이상
            - 마이크 1개 이상
            - 스피커
            - 인터넷 연결
        * gRPC API
            - 굉장한 다양한 언어와 플랫폼을 제공
                + TCP/IP 가 되면 지원
            - 최소화된 계산
            - 최소화된 전력 소모
            - 오픈 소스 샘플 코드 제공
        * DIY 키트 : https://aiyprojects.withgoogle.com/voice
        * 공개 예정
            - 기반의개선된 음성 기반컨트롤

## PWA x ProtoPie
- PWA 란?
    + Reliable - 신뢰있는
        * 오프라인 환경에서 볼 수 있다
    + Fast - 민첩함
        * 유저의 입력에 빠르게 반응 (HTML5을 적극적으로 도입)
    + Engaging - 매력적인
        * 실제 앱과 같이 보이고, 몰입감 있는 유저 경험을 제공한다
- ProtoPie 란?
    + 웹 툴보다는 클라이언트 툴
    + 디자이너를 위한 ( 핵심 기능 )
        * 디자이너들이 인터랙션을 쉽고 빠르게 표현하는 방법을 제공
    + 개발자를 위한
        * 개발자들이 디자이너가 의도한것들을 쉽게 이해할 수 있도록 제공
    + 모들 위한
- ProtoPie 가 주목한 PWA 적용 부분
    + 새로운 URL Share
        * 프로토타입을 만들면 URL을 생성해서 브라우저에서 확인할 수 있는 기능
        * 문제 이슈
            - 모바일 브라우저 상단바를 제거할 수 있는 방법이 없다
                + Chrome Extenstion인 Lighthouse 를 받아서 PWA 사이트 평가
                + Service Worker 를 등록
                    * [Debgguer] - [Application] - [Service Worker] 에서 확인가능
                    * SSL 필수
                + App 구성 필수 파일들을 Cache
                + manifest.json
                    * 다양한 설정들 가능 (상단바 백그라운드 컬러, 아이콘, index 파일등)
- 정리
    + Standalone Mobile Webapp 에는 최적화됨
        * 데이터만 변하는 것이 많은 Webapp 에 적용하기 좋다
        * 데이터 캐시에다가 API Call 한 데이터를 저장해두면 추후 오프라인 환경에서도 마지막 데이터를 불러올 수 있다
    + Lighthouse
    + Service worker & Manifeset.json
- AMP 맛보기
    + 빠른 Web
        * 빠른 Web 을 만들기 위한 노력 
    + 간편하고 편한 적용
        * 다변하는 컨텐츠에 대응 할 수 있음
        * AMP v2.0 에서는 JavaScript 도 사용할 수 있음
    + ProtoPie 는 AMP의 어디에 주목 하나?
        * Documents, News 페이지 등
        * 고정된 데이터를 보여주는곳에서는 굉장히 좋다
    + AMP 가 적용되어있으면 구글 검색 점수가 조금 더 높아진다
## Application 용량 줄이기 - 플레이윙즈 실적용을 중심으로
- ... 

## IT의 변화와 NoOPS, 빅데이타, 머신러닝
- ...

## 파이어베이스 무엇이 달라지나?
- ...

