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

### 솔루션 
Having a layered business architecture allows us to define a solution architecture which is also a layered architecture. But this is not a necessity and someone can come up with a fully distributed solution architecture even with the above-mentioned business architecture if needed. But for the sake of simplicity, let’s take a layered approach with well defined functional components for each layer. 

![API-led-connectivity-2](images/API-led-Business-Transformation-2.png)

Figure 2: API-led integration, solution architecture

As depicted in the above figure, we can map the functionalities of each layer to certain functional capabilities within enterprise architecture. 

- Experience APIs layer can be implemented with an API management platform. This may require a different set of functionalities depending on your enterprise and selecting an API management vendor needs to be done after evaluating the requirements. The fundamental capabilities like security, monitoring, rate-limiting, throttling, caching and better performance are supported by majority of vendors. 
- One fundamental difference in this API-led connectivity or API-led integration is that you don’t need an API management component at each and every layer though it discusses APIs at each layer. Process APIs layer can be easily implemented with an integration technology platform that is capable of doing protocol translations, message transformations, service orchestration and support for major messaging formats and wire-level protocols. These integrated services can be exposed as managed or un-managed APIs to the upper experience layer. 
- System APIs layer can sometimes be directly passed through if the core data is coming from those systems through a defined API. If not, there should be a core business logic layer that converts the business-specific, raw data to meaningful data through an intermediate layer. Users can either utilize an existing integration framework or a standard web-services, microservices technology stack to implement this layer. 
- One major advantage of this proposed API-led integration approach is that every functional capability is available in the means of APIs. Having a centralized developer portal that has details of all the APIs (experience, system, and process) would increase the overall operational efficiency in magnitudes since users do not need to make individual manual requests get certain things implemented on a lower layer. There are API management vendors who can provide this sort of a developer portal as part of their core offering or through a plugin or add-on. 

## Final thoughts
Though people going after hyped words like microservices, containers, serverless, the fundamental architectures for building digital businesses still remains the same. API-led connectivity or API-led integration is such a fundamental concept that can live nicely in both existing monolithic enterprise as well as modern cloud-native, microservices-based enterprise. Any large digital transformation project can be kicked-off with this fundamental architecture pattern and can grow to much bigger projects. Having the fundamental architecture right at the start is crucial in any successful project whether it is large or small. 
