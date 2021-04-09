## API Security Pattern

### 소개

API는 외부 및 내부에 중요한 비즈니스 정보를 공유하는 인터페이스입니다. 이런 정보에 대한 접근을 보호하는 것은 엔터프라이즈 소프트웨어 설계에서 매우 중요합니다.

![API Security Pattern](images/API-Security-Pattern.png)

소비자 및 비즈니스는 디지털 환경에 익숙해지고 있습니다. 도메인에 관계 없이 오늘날 모든 기업은 디지털 전환을 시도하는 것이 필수적입니다. API는 디지털 환경에서 경쟁할 수 있는 기능을 제공합니다.

스리랑카의 일부 시골 마을에서 만든 제품을 ebay 또는 alibaba와 같은 온라인 전자 상거래를 통해 뉴욕에 거주하는 개인에게 판매 할 수 있습니다. 소매점이나 도매점에 가지 않고도 휴대폰이나 태블릿을 사용하여 물건을 주문할 수 있습니다. 과거에는 이런 전자 상거래 사이트 없이도 사업을 잘해왔지만, 이제는 세상이 변했습니다.

이제 기업은 다양한 채널을 통해 내부 및 외부 소비자에게 비즈니스 서비스를 제공해야 합니다. 소비자는 여러 매체를 사용하여 비즈니스 정보에 접근합니다. 잘 정의되고, 문서화되고 탐색 가능한 API 세트를 보유하면 서로 다른 사용자가 다른 매체에서도 비즈니스 정보를 사용할 수 있습니다.

다양한 매체
* 모바일 애플리케이션
* 웹 애플리케이션
* 웹 사이트

### API 보호

사용자가 비즈니스 정보에 접근하도록 허용하면 비즈니스 생태계 측면에서 다른 업체와 경쟁하는데 도움이 됩니다. 그러나 보안 및 제어없이 중요한 비즈니스 정보를 노출 할 수는 없습니다. API를 제어하지 않으면 비즈니스를 위험가 처해질 수 있습니다.

API 보안은 10년동안 진화해왔습니다. API 보안에는 크게 두 가지 주요 요소가 존재하빈다.

* 인증(Authentication) - 사용자 식별 및 검증
* 승인(Authorization) - 비즈니스 정보에 대한 접근 권한

인증은 모든 시스템에 대한 접근을 제어하기 위한 기본 요구 사항입니다. 이 방법은 IT역사적으로 가장 오랫동안 존재했습니다. 과거에는 사용자 아이디와 패스워드를 보관하고 이를 사용하여 접근하려는 시스템을 인증했었습니다.
그러나 매일 엑세스하는 다양한 비즈니스 시스템 및 웹 애플리케이션이 성장함에 따라 모든 사용자 아이디와 패스워드를 유지하는 것이 매우 어려운 작업이 되었습니다. 대부분의 사람들은 은행 계좌, 소셜 로그인, 컴퓨터 로그인 및 비즈니스 애플리케이션에 동일한 자격 증명을 사용합니다. 따라서 악의적 목적을 지닌 해커가 해당 정보에 엑세스하는 경우, 하나의 시스템에서 이 정보를 제공하는 것은 매우 위험 할 수 있습니다.

이런 상황들로 인해 사용자가 신뢰할 수 있는 하나의 시스템에 단일 사용자 아이디 및 패스워드를 저장하면서 다른 애플리케이션에서 사용할 수 있도록 자격 증명을 손상시키지 않고 기존 ID를 재사용 할 수 있는 매커니즘을 원하게 되었습니다. 비즈니스 또는 엔터프라이즈 시나리오에서 자격 증명이 LDAP 또는 AD에 안전하게 저장되는 방식을 가질 수 있습니다.

### API 보안 매커니즘

#### OAuth2
OAuth2는 엑세스를 위임하는 매커니즘을 통해 API 보안의 실질적인 표준이 되었습니다.OAuth2를 사용하면 자격 증명을 제공하지 않고도 애플리케이션이 사용자를 대신하여 특정 리소스에 접근할 수 있는 권한을 부여할 수 있습니다. 이 모델을 사용하면 보안 ID 공급자에 대해서 인증을 하게 됩니다. 애플리케이션(웹,모바일)은 사용자를 대신하여 엑세스 토큰을 받고 해당 토큰을 이용하여 허용된 정보에 접근할 수 있습니다.

#### OIDC
Sometimes these applications wanted to identify the user information (without password) and the OAuth2 framework didn't have a standard mechanism to do this. Because of this limitation, engineers came up with the Open ID Connect (OIDC) framework through that applications can request for basic user information once the user had given permissions to access a certain resource (with user consent).

#### Basic Authentication
On top of all these modern security frameworks, there are some enterprises who still uses username and password based authentication (basic authentication) for API security. 

#### Token exchange with existing security mechanisms
Sometimes as an enterprise solutions architect, you need to introduce new concepts like API management without modifying the existing applications and the user experience. If the end user applications are out of your control, you might not have the luxury of completely introducing a new security mechanism like OAuth2 with these applications. In such cases, you need to build your api management layer so that it can interoperate with the existing security mechanisms like SAML2, Kerberos, NTLM and build a token exchange mechanism around the applications. Users might not see the difference in security implementation since you can either have a token proxy at the enterprise level or develop some code at the client side applications to perform the token exchange. 

### API Gateway and the Identity Provider
API Gateway (sometimes called as API Manager) is the runtime component which recieves all the requests from different users through applications. It is the duty of gateway to validate the user requests before calling the actual endpoints which provides the business information. API Gateway uses a special component to validate the user identities and the access control levels named as Identity Provider. It can be a fully fledged Identity and Access Management product or a component built as part of the same API Management product (e.g. Key Manager). This Identity Provider component takes care of all the security related tasks like

- User management
- Key and token management (OAuth2 and OIDC)
- Entitlement management (XACML)
- Authentication
- Authorization

Sometimes, the same IdP is used for managing authentication and authorization for existing back end applications as well. If a user wants to access an API through an application, user will be redirected to the authentication endpoint of this IdP (or to another IdP if there is federation) and the user credentials are provided here. These user credentials are securely stored within this IdP. If the enterprise already has an IdP, it makes sense to use that to provide these token validation and token generation functionalities. To do that, the particular IdP should have the retrospective API implemented on that server. 

### Connecting to backend endpoints
Sometimes the authentication and authorization at the API Gateway is not sufficient and the back end services also expects some information about the user to validate the data access at that level. In such cases, most of the time, API gateway should pass the basic authentication information coming from the client side or a JWT generated out of the access token.

