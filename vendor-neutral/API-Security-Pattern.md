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

### Protecting your APIs

Allowing users to access your business information helps you to expand your business and compete with the other vendors. But due to the competition and the nature of the internet, you cannot expose your valuable business information without any security and control. If you don't control your APIs, there are hackers who will jeopardize your business even before you think about it by various means. 

API Security is an evolving concept which has been there for less than a decade. When it comes to securing your APIs, there are 2 main factors. 

- Authentication - Identifying and validating the user identity (who you are)
- Authorization - Recognizing the level of access a user has to the business information (what you can do)

User authentication is the basic requirement of providing access to any system. That method has been there for a longest of time since the beginning of computers. In the past you could have keep your user names and password in some vault and use them to authenticate into the systems you want to access. With the growth of different business systems and the other web applications you access day to day, sometimes keeping all these usernames and passwords has become a difficult task. Most people uses same credentials for their bank accounts, social logins, computer logins as well as business applications. So providing this information to one system can be dangerous if some hackers access this information (Facebook recently found out that they have stored user credentials in plain-text in their databases). 

Due to various reasons, people wanted a mechanism to reuse their existing identities without compromising their credentials so that you can use different applications while having a single username password pair stored in one system which you trust. In a business or enterprise scenario, you can have your enterprise account where your credentials are stored securely in enterprise user store (LDAP, AD). 

### API Security mechanisms

#### OAuth2
OAuth2 has become the defacto standard in securing APIs through access delegation mechanism. With OAuth2, you can give permissions for an applications to access a certain set of resources on behalf of you to provide a valuable service to you without giving your credentials. With this model, you authenticate against your secured identity provider. The application (web, mobile) will get an access token on behalf of you and access the information which you are allowed through the token. 

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

