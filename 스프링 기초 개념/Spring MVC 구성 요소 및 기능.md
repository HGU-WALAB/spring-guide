# 🌱 스프링 MVC 구성 요소 및 기능

### 이 섹션은 Spring MVC의 주요 구성 요소와 기능, 그리고 Spring MVC가 어떻게 동작하는지에 대해 설명합니다.

---

## 🚀 DispatcherServlet

- **설명** : '보내다'의 의미를 지닌 'dispatch'에서 유래된 DispatcherServlet은 HTTP 요청을 최초로 받아 적절한 컨트롤러에 전달하는 역할을 하는 프론트 컨트롤러입니다. 클라이언트로부터의 요청이 서블릿 컨테이너(예: Tomcat)로 들어오면, DispatcherServlet이 이를 가장 먼저 인수하고, 공통적인 작업을 처리한 뒤, 해당 요청을 관리할 컨트롤러를 탐색하여 컨트롤러에게 작업을 위임합니다. 이로써, 컨트롤러를 구현해 놓기만 하면, DispatcherServlet이 자동으로 적합한 컨트롤러에 요청을 전달하는 구조를 갖추게 됩니다.

## 🚀 Handler Mapper

- **설명** : DispatcherServlet에 의해 수신된 요청을 어느 컨트롤러가 처리할지 결정하는 역할을 하는 클래스입니다. 요청이 어떤 규칙에 따라 컨트롤러에 매핑되는지를 정의합니다.

## 🚀 Controller

- **설명** : 모델과 뷰 사이에서 사용자의 요청을 처리하는 중간자 역할을 합니다. 사용자로부터 요청을 받으면, 해당 요청에 맞는 모델 데이터를 생성하여 뷰로 전송합니다.

## 🚀 ViewResolver

- **설명** : 컨트롤러가 처리를 마친 후, 어떤 뷰를 사용하여 응답을 생성할지 결정합니다. 컨트롤러가 반환하는 뷰 이름을 실제 뷰 템플릿 파일과 매핑합니다. 모델은 키와 값으로 구성된 HashMap으로, JSP와 같은 뷰에 컨트롤러에서 생성된 데이터를 전달하는 역할을 합니다.

## 🚀 View

- **설명** : 최종적으로 사용자에게 보여지는 화면을 담당합니다. 모델을 사용하여 웹 브라우저에 표시될 리소스를 생성합니다.

<img src="img/spring_mvc_flow.png">

## 🔄 Spring MVC 동작 흐름

1. **요청 수신** : 클라이언트가 특정 URL로 HTTP 요청을 보내면, DispatcherServlet이 이를 받습니다.
2. **컨트롤러 탐색** : DispatcherServlet은 Handler Mapper와 상의하여 요청을 처리할 적절한 컨트롤러를 찾습니다.
3. **컨트롤러 선택** :
   Handler Mapper는 요청 URL과 매핑된 컨트롤러를 결정하고, 이 정보를 DispatcherServlet에 반환합니다.
4. **요청 위임** :
   DispatcherServlet은 결정된 컨트롤러에 요청을 전달하여 처리하도록 합니다.
5. **모델 생성 및 뷰 반환** :
   컨트롤러는 요청을 처리하고, 결과 데이터를 모델에 담아 뷰 이름과 함께 DispatcherServlet에 반환합니다.
6. **뷰 결정** :
   DispatcherServlet은 ViewResolver에게 반환된 뷰 이름을 실제 뷰로 변환해달라고 요청합니다.
7. **뷰 렌더링** :
   ViewResolver는 뷰 이름을 실제 뷰와 매핑하고, 이 정보를 DispatcherServlet에 다시 전달합니다.
8. **응답 생성** :
   DispatcherServlet은 뷰와 모델을 뷰 컴포넌트로 전달하고, 뷰 컴포넌트는 이를 사용하여 최종 HTML 응답을 생성합니다.
9. **응답 반환** :
   생성된 HTML 응답은 DispatcherServlet을 통해 클라이언트에게 전송됩니다.

---

참고자료 : https://www.javaguides.net/2020/07/how-spring-mvc-works-internally.html
