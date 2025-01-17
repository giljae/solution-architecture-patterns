# API-led Connectivity pattern (API 주도 연결 패턴)
## 소개

기업은 소비자와 관련이 있는 시장과 함께 장기적으로 성장해야 합니다. 성공적인 장기 비즈니스를 구축하려면 주변의 변화에 대해 대응할 수 있는 계획과 전략이 필요합니다. 디지털 트랜스포메이션은 기본적으로 모든 기업이 채택해야 하는 현재 트렌드입니다. 하지만 디지털 트랜스포메이션을 전문으로 하는 컨설턴트를 고용하고 엄청난 많은 금액을 지불해야 한다는 의미는 아닙니다. 다만 비즈니스 확장에 대한 기본 요구 사항부터 천천히 디지털 트랜스포메이션을 할 수 있도록 준비해야 합니다.

디지털 트랜스포메이션의 기본 요구 사항은 기존 시스템, 애플리케이션 및 데이터를 통합하는 것입니다. 본 글에서는 "API기반의 연결 또는 통합"개념을 기반으로 WSO2 제품을 사용하는 것을 예로써 설명합니다.

## 아키텍처

"지구상의 모든 비즈니스가 소프트웨어에서 동작되고 있습니다."라는 말은 잘못된 얘기가 아닙니다. 이것은 약 80% 사례를 의미합니다. 애플리케이션을 사용하여 비즈니스 운영을 실행하는 것은 기업을 특별하는 만드는 것이 아닙니다. 소매, 은행, 교육, 커머스와 같은 산업은 이미 내부 및 외부 운영을 위해 소프트웨어를 채택하고 있습니다. 그러나 현재까지도 디지털의 가치를 활용하여 비즈니스를 강화하지 못하는 특정 산업이 존재합니다.

API(Application Programming Inteface)는 내부 및 외부 사용자가 비즈니스에서 데이터를 가져오는데 사용할 수 있는 인터페이스를 정의합니다. 웹 사이트를 통해 제품을 구매하거나, 원자재 공급을 위한 구매 주문서를 보내거나 손익 계산서를 본사에 업데이트 하는 것처럼 간단한 일을 할 수 있습니다. API를 사용하면 고객, 파트너, 직원등 전체 비즈니스의 이해관계자간의 상호 작용을 구축할 수 있습니다. 

### 비즈니스 아키텍처

API 기반 접근 방식을 사용하는 비즈니스 아키텍처를 살펴보고 이해하도록 하겠습니다.

![API-led-connectivity-1](images/API-led-Business-Transformation-1.png)

그림1: API기반 연결 방식 비즈니스 아키텍처

일반적인 기업에서는 특정 유형의 사용자가 시스템, 애플리케이션 및 데이터와 상호 작용을 합니다. 생태계 내에서의 역할에 따라 다양한 서비스 및 데이터에 대한 접근이 필요합니다. 다양한 사용자의 요구 사항을 충족 시키기 위해 엔터프라이즈 시스템을 3가지 계층으로 분류할 수 있습니다.

* Experience APIs - 사용자는 가치가 높은 데이터에 간편하게 접근하기를 기대합니다. 스마트폰으로 자전거를 구매하려는 사용자는 스마트폰을 통해 자전거의 모든 세부 사항을 알고 싶어합니다. 이 레이어에서 제공되는 데이터는 사용자 경험을 개선합니다.
* Process APIs - 프로세스 API를 제공하려면 여러 시스템과 데이터 소스의 상호 작용을 위한 데이터 구조 설계가 필요합니다. 이 레이어는 여러 시스템 및 데이터 소스에 대한 오케스트레이션 역할을 하기에 비즈니스의 가치를 창출하고 운영에 민첩성을 제공 합니다.
* System APIs - 전체 시스템을 대신하여 무거운 작업을 수행할 수 있는 구성 요소가 필요합니다. 이 역할을 시스템 API 레이어에서 담당합니다. 중요한 비즈니스 데이터를 빠르고 안전하게 제공할 수 있도록 데이터 소스 및 Cache와 상호 작용합니다.

위의 아키텍처를 기반으로 비즈니스 아키텍처를 위한 솔루션 아키텍처를 구축해보겠습니다.

### 솔루션 아키텍처

비즈니스 아키텍처를 통해 솔루션 아키텍처를 정의할 수 있습니다. 이렇게 작업하는 것은 필수 사항은 아니며 필요한 경우에 활용할 수 있습니다.

![API-led-connectivity-2](images/API-led-Business-Transformation-2.png)

그림2 : API 기반 통합, 솔루션 아키텍처

위의 그림에 표시된 것처럼 각 레이어의 기능을 엔터프라이즈 아키텍처내의 특정 기능과 매핑할 수 있습니다.

* Experience API 레이어는 API 관리 플랫폼으로 구축할 수 있습니다. 이를 위해서 요구 사항을 정의한 후 API 솔루션을 선택해야 합니다. 보안, 모니터링, 속도 제어, Control, Caching등과 같은 기본 기능은 대부분 솔루션에서 지원합니다.
* API 기반 통합 방식의 장점은 API를 통해 모든 기능을 사용할 수 있다는 것입니다. 모든 API(Experience, Process, System)에 대한 세부 정보가 포함된 개발자 포털을 제공하면 수동 요청이 필요 없어지기에 전반적으로 운영 효율성이 향상됩니다. 솔루션 선택시 이 부분도 고려해야 합니다.

## 결론

일반적으로 현재 시장에서는 마이크로 서비스, 컨테이너, 서버리스와 같은 용어를 추구하지만 디지털 비즈니스 플랫폼 구축을 위한 아키텍처는 항상 필요합니다. API 기반 연결 및 통합은 기존의 Monolithic과 클라우드 네이티브, 마이크로 서비스 기반에서 모두 사용할 수 있는 기본 개념입니다. 모든 디지털 트랜스포메이션 프로젝트에서 규모에 상관없이 기본 아키텍터 패턴으로 사용할 수 있습니다.
