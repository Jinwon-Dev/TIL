# TIL
기억보다는 기록이 중요하다고 생각합니다.

좋은 개발자가 되기 위해 그 날의 학습한 내용을 기록합니다.

Today I Learned인데 날짜를 표기하지 않는 이유는 날짜를 신경쓰지 않고 꾸준하기 위함입니다.

</br>

## 작성 규칙
1. 디렉토리와 파일명은 영문으로 작성합니다.
2. 추가적인 검색의 비용이 들지 않도록 간략하지만 정확히 기록합니다.
3. 당일에 학습한 내용은 당일에 기록합니다.

</br>

## 분류

## Java
- [StringTokenizer와 split()](https://github.com/Jinwon-Dev/TIL/blob/main/Java/stringTokenizer-and-split.md)
- [SOLID 원칙](https://github.com/Jinwon-Dev/TIL/blob/main/Java/SOLID-%EC%9B%90%EC%B9%99.pdf)
- ### Modern Java in Action
    - [Chapter 1. 자바 8, 9, 10, 11 : 무슨 일이 일어나고 있는가?](https://jinwonyoon.notion.site/Chapter-1-8-9-10-11-e1d2dab906a74df8b6b30a7f2c42c7c4)
    - [Chapter 2. 동작 파라미터화 코드 전달하기](https://jinwonyoon.notion.site/Chapter-2-1236396b95714d9baa9bf7ef4875c79b)
    - [Chapter 3. 람다 표현식](https://jinwonyoon.notion.site/Chapter-3-da8a2c37559c4e379ca17d28d0dd50d3)
    - [Chapter 4. 스트림 소개](https://jinwonyoon.notion.site/Chapter-4-3d9c1995409c44f69deae9ad904533b5)
    - [Chapter 5. 스트림 활용](https://jinwonyoon.notion.site/Chapter-5-e6ebe733f36a4bd89b7407faee364dfb)
    - [Chapter 7. 병렬 데이터 처리와 성능](https://jinwonyoon.notion.site/Chapter-7-9b816ed51a5649298c34b6c76064a0fb)
    - [Chapter 8. 컬렉션 API 개선](https://jinwonyoon.notion.site/Chapter-8-API-1a6d7e1abfde4721a4f8e4e050a42c2a)
    - [Chapter 9. 리팩터링, 테스팅, 디버깅](https://jinwonyoon.notion.site/Chapter-9-14a871bb994f49e8b51f759390ba21d4)
    - [Chapter 10. 람다를 이용한 도메인 전용 언어](https://jinwonyoon.notion.site/Chapter-10-4247227dd0bb4afdb1881c6a8252fedf?pvs=4)
    - [Chapter 11. null 대신 Optional 클래스](https://jinwonyoon.notion.site/Chapter-11-null-Optional-b21343b9149f43c3a86006c31bc067e6?pvs=4)
    - [Chapter 13. 디폴트 메서드](https://jinwonyoon.notion.site/Chapter-13-fc2cc7c8d3f34d979f77312cf0e4092a?pvs=4)
    - [Chapter 15. CompletableFuture와 리액티브 프로그래밍 컨셉의 기초](https://jinwonyoon.notion.site/Chapter-15-CompletableFuture-aed8c43be0684deeabd0daa0f5f13c49?pvs=4)
- ### Effective Java
    - [Item 1. 생성자 대신 정적 팩터리 메서드를 고려하라](https://jinwonyoon.notion.site/Item-1-1cfb82db13964083a71c6ca2bd688386?pvs=4)
    - [Item 2. 생성자에 매개변수가 많다면 빌더를 고려하라](https://jinwonyoon.notion.site/Item-2-1318884e435b40b8aec0c6b63b247c8a?pvs=4)
    - [Item 3. private 생성자나 열거 타입으로 싱글턴임을 보증하라](https://jinwonyoon.notion.site/Item-3-private-428a18b4586d4ccdb21647a4cf53711a?pvs=4)
    - [Item 4. 인스턴스화를 막으려거든 private 생성자를 사용하라](https://jinwonyoon.notion.site/Item-4-private-32aabc70e91441a9bbaabf520b9db681?pvs=4)
    - [Item 5. 자원을 직접 명시하지 말고 의존 객체 주입을 사용하라](https://jinwonyoon.notion.site/Item-5-64454d15d42d423da2e485bd6ee11217?pvs=4)
    - [Item 6. 불필요한 객체 생성을 피하라](https://jinwonyoon.notion.site/Item-6-8acfb769a78643aab9db64941b882346?pvs=4)
    - [Item 7. 다 쓴 객체 참조를 해제하라](https://jinwonyoon.notion.site/Item-7-ee9265442d8541ccbd1712e55295174a?pvs=4)
    - [Item 8. finalizer와 cleaner 사용을 피하라](https://jinwonyoon.notion.site/Item-8-finalizer-cleaner-8876f8e2c918496a8ad70eee596ab35d?pvs=4)
    - [Item 9. try-finally보다는 try-with-resources를 사용하라](https://jinwonyoon.notion.site/Item-9-try-finally-try-with-resources-f8a29451ea404c13ae5a41df6da0c1d4?pvs=4)
    - [Item 10. equals는 일반 규약을 지켜 재정의하라](https://jinwonyoon.notion.site/Item-10-equals-caeed647270c4bc2afe1c5b16727e5e4?pvs=4)
    - [Item 11. equals를 재정의하려거든 hashCode도 재정의하라](https://jinwonyoon.notion.site/Item-11-equals-hashCode-0e18db0e2de349f892935ca215cb47f7?pvs=4)
    - [Item 12. toString을 항상 재정의하라](https://jinwonyoon.notion.site/Item-12-toString-474e8d0ae48e4180a27d881346fc91d6?pvs=4)
    - [Item 13. clone 재정의는 주의해서 진행하라](https://jinwonyoon.notion.site/Item-13-clone-f10f90af4f194f448ef7ce596ce7370c?pvs=4)
    - [Item 14. Comparable을 구현할지 고려하라](https://jinwonyoon.notion.site/Item-14-Comparable-68a41de451a14801a8aca2872d075f7e?pvs=4)
    - [Item 15. 클래스와 멤버의 접근 권한을 최소화하라](https://jinwonyoon.notion.site/Item-15-8402bec6fd354d2aab6b1340bdc594bc?pvs=4)
    - [Item 16. public 클래스에서는 public 필드가 아닌 접근자 메서드를 사용하라](https://jinwonyoon.notion.site/Item-16-public-public-f386fb49efb34c88bfae685824cbb91d?pvs=4)
    - [Item 17. 변경 가능성을 최소화하라](https://jinwonyoon.notion.site/Item-17-55976ff5a464445dbeca66aa59e10f9f?pvs=4)
    - [Item 18. 상속보다는 컴포지션을 사용하라](https://jinwonyoon.notion.site/Item-18-663cd3958d5a48fd974fa0e72f958763?pvs=4)

</br>

## JPA
- ### 자바 ORM 표준 JPA 프로그래밍
    - [Chapter 1. JPA 소개](https://jinwonyoon.notion.site/1-JPA-42a6db19a07345478fa9982a38df4706)
    - [Chapter 2. JPA 시작](https://jinwonyoon.notion.site/2-JPA-af0411d173484ffbbc213a676e0ca4a2)
    - [Chapter 3. 영속성 관리](https://jinwonyoon.notion.site/3-791ed72965af41eea897b0e6f2e71a8b)
    - [Chapter 4. 엔티티 매핑](https://jinwonyoon.notion.site/4-acfb38c37cce46448993da621b80ea03)
    - [Chapter 5. 연관관계 매핑 기초](https://jinwonyoon.notion.site/5-1a9a3a25386549b2a9ff3c49bcd44a76)
    - [Chapter 6. 다양한 연관관계 매핑](https://jinwonyoon.notion.site/6-d6abb513eb2f4027bd029a14a57641c4)
    - [Chapter 8. 프록시와 연관관계 관리](https://jinwonyoon.notion.site/8-b4e53cbfbe14453fadb3b0904afb1fc7)
    - [Chapter 10. 객체지향 쿼리 언어 - QueryDSL](https://jinwonyoon.notion.site/10-2a93575abaa54a81b2887bdb886c8734?pvs=4)
    - [JPQL을 Query DSL로 리팩토링하기](https://velog.io/@jinony/Spring-Boot-JPQL%EC%9D%84-Query-DSL%EB%A1%9C-%EB%A6%AC%ED%8C%A9%ED%86%A0%EB%A7%81%ED%95%B4%EB%B3%B4%EC%9E%90)

</br>

## Software Architecture
- ### 만들면서 배우는 클린 아키텍처
    - [Chapter 1. 계층형 아키텍처의 문제점은 무엇일까?](https://jinwonyoon.notion.site/Chapter-1-28ee32dc22e845c180a5b2c082df3683?pvs=4)
    - [Chapter 2. 의존성 역전하기](https://jinwonyoon.notion.site/Chapter-2-f7eea28d98dd4a2b949458e097b57432?pvs=4)
    - [Chapter 3. 코드 구성하기](https://jinwonyoon.notion.site/Chapter-3-46d2dcae709b4db8a3bb83d4e7ec693d?pvs=4)
    - [Chapter 4. 유스케이스 구현하기](https://jinwonyoon.notion.site/Chapter-4-e724a4075eac43fab30775e8cc68f41c?pvs=4)
    - [Chapter 5. 웹 어댑터 구현하기](https://jinwonyoon.notion.site/Chapter-5-b32f94f0d1bb44439408872e23a0039e?pvs=4)
    - [Chapter 6. 영속성 어댑터 구현하기](https://jinwonyoon.notion.site/Chapter-6-c87d1053b0444253bbb9a2f6e3e0d360?pvs=4)

</br>

## System Design
- ### 가상 면접 사례로 배우는 대규모 시스템 설계 기초
    - [Chapter 1. 사용자 수에 따른 규모 확장성](https://jinwonyoon.notion.site/Chapter-1-b53e55e5ab644b5bb6822beb5cb87e4a?pvs=4)
    - [Chapter 2. 개략적인 규모 측정](https://jinwonyoon.notion.site/Chapter-2-49ad12b41ab94bd1b3f88f427b33340d?pvs=4)
    - [Chapter 3. 시스템 설계 면접 공략법](https://jinwonyoon.notion.site/Chapter-3-cb6ba58f30044b38998509d92b580738?pvs=4)
    - [Chapter 4. 처리율 제한 장치의 설계](https://jinwonyoon.notion.site/Chapter-4-80a2a5c037f8492596096c3adcd5b101?pvs=4)
    - [Chapter 5. 안정 해시 설계](https://jinwonyoon.notion.site/Chapter-5-459e2d08fc8b4487b0bfe9766b9f843c?pvs=4)
    - [Chapter 6. 키-값 저장소 설계](https://jinwonyoon.notion.site/Chapter-6-2842621c4d4c447e8a091743606e131a?pvs=4)
    - [Chapter 7. 분산 시스템을 위한 유일 ID 생성기 설계](https://jinwonyoon.notion.site/Chapter-7-ID-d3f62f95d80147b2b2018231d48e1d18?pvs=4)
    - [Chapter 8. URL 단축기 설계](https://jinwonyoon.notion.site/Chapter-8-URL-0919a0fe17fa41df943317fa6a36fab9?pvs=4)
    - [Chapter 9. 웹 크롤러 설계](https://jinwonyoon.notion.site/Chapter-9-9700909555ce4e1d87bd0008d8f13e17?pvs=4)
    - [Chapter 10. 알림 시스템 설계](https://jinwonyoon.notion.site/Chapter-10-3b993b2a97ad493cb4eb239a32167487?pvs=4)
    - [Chapter 11. 뉴스 피드 시스템 설계](https://jinwonyoon.notion.site/Chapter-11-4b561af84daa474183b44de80146ca51?pvs=4)

</br>

## Network
- [HTTP Status Code](https://github.com/Jinwon-Dev/TIL/blob/main/Network/http-status-code.md)
- [MQTT](https://github.com/Jinwon-Dev/TIL/blob/main/Network/mqtt.md)
- [세션, 쿠키, JWT](https://github.com/Jinwon-Dev/TIL/blob/main/Network/session-cookie-jwt.md)
- [Load Balancing](https://jinwonyoon.notion.site/c222393f452344ad8b243956097b4de2?pvs=4)
- [OSI 7 Layer](https://jinwonyoon.notion.site/OSI-7-176d50cfad9442b0bf384c7f4ce3bd66?pvs=4)
- [HTTP & HTTPS](https://jinwonyoon.notion.site/HTTP-HTTPS-3b7b9d13dab048329302a2bd1dee5868?pvs=4)
- ### 모든 개발자를 위한 HTTP 웹 기본 지식
    - [인터넷 네트워크](https://jinwonyoon.notion.site/5cb947e3264b4b13a1603cfbf30765e0)
    - [URI와 웹 브라우저 요청 흐름](https://jinwonyoon.notion.site/URI-47564cc67fd540b7807320dfb62b9984)

</br>

## OS
- [페이징 & 세그멘테이션](https://jinwonyoon.notion.site/cff074373fbf4e8c9fedd594f49e30c5?pvs=4)
- [교착 상태](https://jinwonyoon.notion.site/4ddc1898fcb341c9876a6b1fb28e43d8?pvs=4)
- [CPU 스케줄링](https://jinwonyoon.notion.site/CPU-808301a329a14e4386d9a945c17c418b?pvs=4)
- [문맥 교환](https://jinwonyoon.notion.site/b9d4bf21d89b4be6bf5d274a26d876b4?pvs=4)
- ### Operating System Concepts
    - [Chapter 1. 서론](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/introduction.md)
    - [Chapter 2. 운영체제 구조](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/operating-system-structures.md)
    - [Chapter 3. 프로세스](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/process.md)
    - [Chapter 4. 스레드와 병행성](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/threads-and-concurrency.md)
    - [Chapter 5. CPU 스케줄링](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/cpu-scheduling.md)
    - [Chapter 6. 동기화 도구들](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/synchronization-tools.md)
    - [Chapter 7. 동기화 예제](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/synchronization-examples.md)
    - [Chapter 8. 교착 상태](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/deadlocks.md)
    - [Chapter 9. 메인 메모리](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/main-memory.md)
    - [Chapter 10. 가상 메모리](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/virtual-memory.md)
    - [Chapter 11. 대용량 저장장치 구조](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/mass-storage-structure.md)
    - [Chapter 12. 입출력 시스템](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/io-system.md)
    - [Chapter 13. 파일 시스템 인터페이스](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/file-system-interface.md)
    - [Chapter 14. 파일 시스템 구현](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/implementing-file-systems.md)
    - [Chapter 16 & 17. 보호 & 보안 -> SSO, SAML, OAuth, OIDC](https://github.com/Jinwon-Dev/TIL/blob/main/OS/operating-system-concepts/sso-saml-oauth-oidc.md)

</br>

## Database
- [인덱스](https://jinwonyoon.notion.site/a4a3d775576d45848ecff01c668bbe77?pvs=4)
- [정규화](https://jinwonyoon.notion.site/2d5fa5fde2214f799d16b7fdbb808264?pvs=4)
- [트랜잭션](https://jinwonyoon.notion.site/3232205424b04c0aa4221367de7d905d?pvs=4)
- [조인](https://jinwonyoon.notion.site/Join-182316a6dfa64cc28c9c73040a326053?pvs=4)

</br>

## Clean Code
- [Chapter 1. 깨끗한 코드](https://jinwonyoon.notion.site/1-9722dd08d61647dd885fc5463bed02d0)
- [Chapter 2. 의미 있는 이름](https://jinwonyoon.notion.site/2-12f7c1c46ff44e99b2eb339e86dba1a7)

</br>

## AWS
- ### 원티드 프리온보딩 백엔드 챌린지 5월
    - [홈페이지 링크](https://www.wanted.co.kr/events/pre_challenge_be_7)
    - [Week 1-1 : AWS 인프라 - Cloud Computing, AWS VPC, AWS API Gateway, AWS ELB, AWS S3, AWS CloudFront, AWS Secret Manager](https://jinwonyoon.notion.site/AWS-72822ad14ac549f7baa324102fc07064)
    - [Week 1-2 : AWS의 가상 서버 관련 서비스 - AWS EC2, AWS Elastic Beanstalk, AWS Fargate, AWS ECR, AWS ECS, AWS Lambda(Serverless)](https://jinwonyoon.notion.site/AWS-909a599e602c472786b12ac73dc5542d)
    - [Week 2-1 : AWS의 메세지 큐 서비스 - AWS SQS, AWS Kinesis](https://jinwonyoon.notion.site/AWS-23baa468b6434b7e82d55a13244164cb)

</br>

## ETC
- ### 주니어 백엔드 개발자가 반드시 알아야 할 실무 지식
    - [느려진 서비스, 어디부터 봐야 할까](https://jinwonyoon.notion.site/1f56a89b208780a4af43cc88f23c5ea2?pvs=4)
    - [성능을 좌우하는 DB 설계와 쿼리](https://jinwonyoon.notion.site/DB-1f56a89b20878006abe0fc446dcbf7fa?pvs=4)
    - [외부 연동이 문제일 때 살펴봐야 할 것들](https://jinwonyoon.notion.site/1f56a89b2087805eaafae70f727ac812?pvs=4)