# 솔루션 아키텍처 패턴
이 저장소에는 엔터프라이즈 소프트웨어 시스템을 구축하는데 재사용 할 수 있는 솔루션 아키텍처 패턴이 포함되어 있습니다. 

여기서 소개된 패턴 중 일부는 시장에서 잘 사용되고 있고 일부는 점진적으로 진화하고 있는 패턴입니다.

본 글은 https://github.com/chanakaudaya/solution-architecture-patterns의 글을 한국어로 번역하고 있으며, 언제 완료될지는 아직 알 수 없습니다.

번역자:
* 주길재 ([@giljae](https://github.com/giljae))
* 윤지상 ([@jisangyun](https://github.com/jisangyun))


## 벤더 중립적 아키텍처 패턴

- API Security pattern (API 보안 패턴)
[API Security Pattern](vendor-neutral/API-Security-Pattern.md)

- API-led Connectivity pattern (API 주도 연결 패턴)
[API-led Connectivity pattern](vendor-neutral/API-led-Connectivity-Pattern.md)

- Anti Corruption Layer pattern (손상 방지 레이어 패턴)
[Anti Corruption Layer Pattern](vendor-neutral/Anti-Corruption-Layer-Pattern.md)

- Ballerina sidecar pattern (발레리나 사이드카 패턴)
[Ballerina sidecar pattern](vendor-neutral/Ballerina-sidecar-pattern-microservices.md)

- Centralized Identity and Access Management Pattern (중앙 집중식 ID 및 접근 관리 패턴)
[Centralized Identity and Access Management Pattern](vendor-neutral/Centralized-Identity-Access-Management-Pattern.md)

- Change Data Capture Pattern (변경 데이터 캡쳐 패턴) [Change Data Capture Pattern](vendor-neutral/Introduction-to-Change-Data-Capture.md)

- Cloud Migration with Strangler Pattern (스트랭글러 패턴을 사용한 클라우드 마이그레이션)
[Cloud Migration with Strangler Pattern](vendor-neutral/Cloud-Migration-Strangler-Pattern.md)

- Decentralized Enterprise Architecture pattern (분산형 엔터프라이즈 아키텍처 패턴)
[Decentralized Enterprise Architecture Pattern](vendor-neutral/Decentralized-Enterpise-Architecture-Pattern.md)

- Enterprise CICD pattern (엔터프라이즈 CI/CD 패턴)
[Enterprise CICD Pattern](vendor-neutral/Enterprise-CICD-Pattern.md)

- Enterprise Software Stack (엔터프라이즈 소프트웨어 스택)
[Enterprise Software Stack](vendor-neutral/Enterprise-Software-Stack.md)

- Event Driven Architecture Kafka Pattern (이벤트 기반 아키텍처 카프카 패턴)
[Event Driven Architecture Kafka Pattern](vendor-neutral/Event-Driven-Architecture-Kafka-Pattern.md)

- GraphQL enterprise architecture patterns (GraphQL 엔터프라이즈 아키텍처 패턴)
[GraphQL Pattern](vendor-neutral/GraphQL-Pattern.md)

- Hybrid API Management pattern (하이브리드 API 관리 패턴)
[Hybrid API Management Pattern](vendor-neutral/Hybrid-API-Management-Pattern.md)

- Hybrid Integration pattern (하이브리드 통합 패턴)
[Hybrid Integration Pattern](vendor-neutral/Hybrid-Integration-Pattern.md)

- Istio Service Mesh pattern (Istio 서비스 메시 패턴)
[Istio Service Mesh Pattern](vendor-neutral/Istio-Service-Mesh-Pattern.md)

- Kubernetes Deployment pattern (쿠버네티스 배포 패턴)
[Kubernetes Deployment Pattern](vendor-neutral/Kubernetes-Deployment-Pattern.md)

- Layered architecture pattern (계층화된 아키텍처 패턴)
[Layered Architecture Pattern](vendor-neutral/Layered-Architecture-Pattern.md)

- Micro architecture pattern (마이크로 아키텍처 패턴)
[Micro Architecture Pattern](vendor-neutral/Micro-Architecture-Pattern.md)

- Microservices with NATS messaging (NATS 메시징을 이용하는 마이크로 서비스)
[Microservices with NATS messaging](vendor-neutral/Microservices-with-NATS-messaging.md)

- Microservices Security Pattern - Policy based (마이크로서비스 보안 패턴 - 정책 기반)
[Microservices Security Pattern - Policy based](vendor-neutral/Microservices-Security-Pattern-Policy-Based.md)

- Multi Cloud Enterprise Deployment pattern (멀티 클라우드 엔터프라이즈 배포 패턴)
[Multi Cloud Enterprise Deployment Pattern](vendor-neutral/Multi-Cloud-Enterprise-Deployment-Pattern.md)

- OpenAPI Based Digital Transformation pattern (오픈 API기반 디지털 트랜스포메이션 패턴)
[OpenAPI Based Digital Transformation Pattern](vendor-neutral/OpenAPI-Based-Digital-Transformation-Pattern.md)

- SOA Governance to API Management Pattern (SOA 거버넌스와 API 관리 패턴)
[SOA Governance to API Management Pattern](vendor-neutral/SOA-governance-to-API-management-pattern.md)

- Microservices Governance and API Management Pattern (마이크로서비스 거버넌스 및 API 관리 패턴)
[Microservices Governance and API Management Pattern](vendor-neutral/Microservices-Governance-And-API-Management.md)


## 산업별 아키텍처 패턴
여기서 설명하는 패턴은 비즈니스 도메인 또는 인더스트리에 따라 다르기에 레퍼런스 아키텍처로 참고해주세요.

- Telecommunication Reference Architecture
[Telecommunication Reference Architecture](industry-specific/Telecommunication-reference-architecture-pattern.md)

- Transportation Reference Architecture
[Transportation Reference Architecture](industry-specific/Effective-ground-transportation-architecture-pattern.md)

- Digital Health Platform Open Source Architecture
[Digital Health Platform Open Source Architecture](industry-specific/Digital-Health-Platform-Open-Source-Architecture.md)

- Hospitality Platform Reference Architecture
[Hospitality Platform Reference Architecture](industry-specific/Hospitality-Platform-Reference-Architecture-WSO2.md)

- Retail Platform Reference Architecture
[Retail Platform Reference Architecture](industry-specific/future-retail-a-business-and-technical-architecture.md)

- Higher Education Information Technology Architecture [Higher Education Information Technology Architecture](industry-specific/Higher-Education-Information-Technology-Architecture.md)

- Energy industry Information Technology Reference Architecture [Energy industry Information Technology Reference Architecture](industry-specific/Energy-Information-Technology-Reference-Architecture.md)

- Automotive industry Information Technology Reference Architecture [Automotive industry Information Technology Reference Architecture](industry-specific/Automotive-Industry-Information-Technology-Reference-Architecture.md)


## 공급 업체별 아키텍처 패턴
여기서 설명하는 패턴은 벤더에 따라 다르며, 언급된 일부 용어는 다른 벤더에서는 일반적이지 않을 수 있습니다.

- Amazon Web Services (AWS) [Amazon Web Services (AWS)](vendor-specific/aws)

- Microsoft Azure [Microsoft Azure](vendor-specific/azure)

- Google Cloud Platform (GCP)[Google Cloud Platform (GCP)](vendor-specific/gcp)

- Mulesoft [Mulesoft](vendor-specific/mulesoft)

- Pivotal [Pivotal](vendor-specific/pivotal)

- RedHat [RedHat](vendor-specific/redhat)

- WSO2 [WSO2](vendor-specific/wso2)

## 기술 선택 가이드
- API 관리 플랫폼 선택 가이드 [API Management platform selection guide](technology-selection-guides/API-Management-Platform-selection-guide.md)
- Integration 플랫폼 선택 가이드 [Integration platform selection guide](technology-selection-guides/Integration-Platform-selection-guide.md)

## 연관 아키텍처 리소스
- Technology reference architecture [Technology reference architecture](https://github.com/wso2/reference-architecture)
- Design patterns for humans [Design patterns for humans](https://github.com/kamranahmedse/design-patterns-for-humans)
- Awesome scalability [Awesome scalability](https://github.com/binhnguyennus/awesome-scalability)
- Awesome design patterns [Awesome design patterns](https://github.com/DovAmir/awesome-design-patterns)
- Awesome distributed systems [Awesome distributed systems](https://github.com/theanalyst/awesome-distributed-systems)

# 라이센스 

Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

본 작업물은 아래의 라이센스를 따릅니다.
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
