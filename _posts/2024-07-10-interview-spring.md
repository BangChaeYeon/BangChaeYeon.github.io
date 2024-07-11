---
title: 기술 면접 대비 - Spring framework편
author: BCY
date: 2024-07-11 20:58:28 +0900
categories: [interview, spring]
tags: [interview]
---
## 개요
이 글은 기술 면접을 대비하여 예상 질문 리스트를 정리하고자 작성했습니다.
해당 내용은 Spring framework편으로 계속 추가 될 예정입니다.

<details>
	<summary>1. Spring framework란 무엇인가?</summary>
	<ul>
		<li>Java EE 개발을 편리하게 해주는 경량급 오픈소스 애플리케이션 프레임워크</li>
		<li>동적인 웹 사이트 개발하기 위한 여러 가지 서비스를 제공</li>
		<li>대한민국 공공기관의 웹 서비스 개발 시 사용을 권장하고 있는 전자정부 표준프레임워크의 기반 기술</li>
	</ul>
</details>

<details>
	<summary>2. Spring framework의 특징은 무엇인가?</summary>
	<ul>
		<li>DI(Dependency Injection) - 의존성 주입: 설정 파일이나 어노테이션을 통해 객체간의 의존 관계를 설정하여 개발자가 직접 의존하는 객체를 생성할 필요없음</li>
		<li>Spring AOP(Aspect Oriented Programming) - 관점 지향 프로그래밍: 트랜잭션, 로깅, 보안 등 여러 모듈, 여러 계층에서 공통으로 필요로 하는 기능의 경우 해당 기능을 분리해 관리</li>
		<li>POJO(Plain Old Java Object)
			<ul>
				<li>다른 클래스나 인터페이스를 상속/implements 받아 메서드가 추가된 클래스가 아닌 getter, setter 같이 기본적인 기능만 가진 자바 객체</li>
			</ul>
		</li>
		<li>IOC(Inversion of Control) - 제어 반전
			<ul>
				<li>컨트롤의 제어권이 개발자가 아니라 프레임워크에 있다는 뜻</li>
				<li>객체의 생성부터 Life Cycle을 관리하고 제어해주는 것</li>
				<li>제어권이 스프링 프레임워크로 넘어오게 되면서 DI(의존성 주입), AOP(관점 지향 프로그래밍) 등을 가능하게함</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>3. Spring AOP가 무엇인지 OOP와 AOP를 비교하여 설명하시오.</summary>
	<ul>
		<li>AOP(Aspect Oriented Programming): 관점 지향 프로그래밍</li>
		<li>애플리케이션의 핵심적인 기능과 부가적인 기능을 분리해 Aspect라는 모듈로 만들어 설계하고 개발하는 방법</li>
		<li>OOP(Object Oriented Programming): 객체 지향 프로그래밍</li>
		<li>OOP와 AOP는 서로 상반되는 개념은 아니며 오히려 OOP를 더욱 OOP답게 사용할 수 있도록 하는 것이 AOP</li>
		<li>AOP 등장 사유
			<ul>
				<li>공통적 기능을 모든 모듈에 적용하기 위한 방법으로 상속을 이용하는데 Java에서는 다중 상속이 불가능</li>
				<li>기능 구현 부분에서 핵심 코드와 공통 기능 코드가 섞여있어서 보기에도 불편하고, 효율성이 떨어짐</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>4. Dispatcher Servlet이란?</summary>
	<ul>
		<li>톰캣과 같은 서블릿 컨테이너를 통해 들어오는 모든 요청을 제일 앞에서 받는 프론트 컨트롤러</li>
		<li>Dispatcher Servlet은 공통된 작업을 처리한 후에, 적절한 세부 컨트롤러로 작업을 위임해줌. 그리고 각각의 세부 컨트롤러는 처리할 부분을 처리하고 반환할 view를 Dispatcher Servlet에 넘김</li>
	</ul>
</details>

<details>
	<summary>5. WAS와 WS의 차이점은 무엇인가?</summary>
	<ul>
		<li>WAS(Web Application Server) : 비즈니스 로직을 넣을 수 있음 (Tomcat, PHP, ASP, Net 등)</li>
		<li>WS(Web Server) : 비즈니스 로직을 넣을 수 없음 (Nginx, Apache 등)</li>
	</ul>
</details>

<details>
	<summary>6. Spring의 동작 방식을 설명하시오.</summary>
	<ul>
		<li>DispatcherServlet이 브라우저로부터 요청을 받음</li>
		<li>DispatcherServlet은 요청된 URL을 HandlerMapping 객체에 넘기고, 호출해야 할 Controller 메소드(핸들러) 정보를 얻음</li>
		<li>DispatcherServlet이 HandlerAdapter 객체를 가져옴 </li>
		<li>HandlerAdapter 객체의 메소드를 실행  </li>
		<li>Controller 객체는 비즈니스 로직을 처리하고, 그 결과를 바탕으로 뷰(ex. JSP)에 전달할 객체를 Model 객체에 저장, DispatcherServlet에게 view name을 리턴</li>
		<li>DispatcherServlet은 view name을 Viewresolver에게 전달하여 View 객체를 얻음</li>
		<li>DispatcherServlet은 View 객체에 화면 표시를 의뢰</li>
		<li>View 객체는 해당하는 뷰(ex. JSP, Thymeleaf)를 호출하며, View는 Model 객체에서 화면 표시에 필요한 객체를 가져와 화면 표시를 처리함</li>
	</ul>
</details>

<details>
	<summary>7. Model1, Model2 패턴의 차이를 설명하시오.</summary>
	<ul>
		<li>Model1: View와 로직을 모두 JSP페이지 하나에서 처리하는 구조</li>
		<li>Model2 : JSP, Servlet, 그리고 로직을 위한 Class가 나뉘어 브라우저 요청을 함</li>
	</ul>
</details>

<details>
	<summary>8. Servlet VS JSP</summary>
	<ul>
		<li>Servlet
			<ul>
				<li>자바 언어로 웹 개발을 위해 만들어진 것</li>
				<li>Container가 이해할 수 있게 구성된 순수 자바 코드로만 이루어진 것</li>
			</ul>
		</li>
		<li>JSP
			<ul>
				<li>html기반에 JAVA코드를 블록화하여 삽입한 것</li>
				<li>Servlet을 좀 더 쉽게 접근할 수 있도록 만들어 진 것</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>9. JSTL은 무엇이고 ,왜 사용하는가?</summary>
	<ul>
		<li>JSP 표준 태그 라이브러리의 약어로써, 자신만의 태그를 추가할 수 있는 기능을 제공함</li>
		<li>주로 JSTL의 core에서 c를 사용하여 <c:if> <c:forEach> 등으로 사용함</li>
	</ul>
</details>

<details>
	<summary>10. JSON VS XML</summary>
	<ul>
		<li>JSON
			<ul>
				<li>JSON은 경량의 DATA-교환 형식, 데이터를 저장하고 전달하는 메타언어</li>
				<li>Javascript에서 객체를 만들 때 사용하는 표현식을 의미</li>
				<li>장점: JSON은 문자열을 전송받은 후에 해당 문자열을 바로 파싱하므로, XML보다 빠른 속도를 가지고 있음</li>
				<li>단점: JSON은 개발자가 문자열 데이터의 무결성을 검증이 필요</li>
			</ul>
		</li>
		<li>XML
			<ul>
				<li>XML은 HTML과 매우 비슷한 문자 기반의 마크업 언어(text-based markup language)</li>
				<li>장점 : 스키마를 사용하여 데이터의 무결성을 검증할 수 있음</li>
				<li>단점 : XML은 배열을 사용할 수 없고 (JSON은 배열 사용 가능), 데이터를 읽고 쓰는 것이 JSON 대비 느림</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>11. 동기 VS 비동기식</summary>
	<ul>
		<li>동기식: 요청과 결과가 동시에 이루어지는 것. 설계가 간단하지만 결과가 주어질 때까지 아무것도 못하고 대기해야 하므로 비동기식 보다 비효율적임</li>
		<li>비동기식: 요청과 결과가 동시에 이루어지지 않는 것. 하나의 요청을 처리하는 동안 다른 요청도 처리가능. 동기보다 복잡하고 결과가 주어지는데 시간이 걸리더라도 그동안 다른 작업을 할 수 있으므로 자원을 효율적으로 사용할 수 있음</li>
	</ul>
</details>

<details>
	<summary>12. Spring VS Spring Boot</summary>
	<ul>
		<li>SpringBoot는 Spring Framework에서 사용하는 프로젝트를 간편하게 셋업할 수 있는 서브 프로젝트</li>
		<li>독립 컨테이너에서 동작할 수 있기 때문에 embedded tomcat이 자동으로 실행됨</li>
		<li>starter을 통한 dependency 자동화: starter가 대부분의 dependency를 관리하여 version 관리를 도움</li>
		<li>XML설정을 하지 않아도 됨</li>
		<li>jar file을 이용해 자바 옵션만으로 손쉽게 배포가 가능</li>
		<li>Spring Actuator를 이용한 애플리케이션의 모니터링과 관리를 제공함</li>
	</ul>
</details>

<details>
	<summary>13. Spring Boot의 특징을 설명하시오</summary>
	<ul>
		<li>애플리케이션을 신속하게 세팅할 수 있음</li>
		<li>추가 WAS 설치 없이 embedded tomcat으로 실행함</li>
		<li>번거로운 개발 세팅을 대신 해줌</li>
	</ul>
</details>

<details>
	<summary>14. Spring MVC를 설명하시오.</summary>
	<ul>
		<li>웹 애플리케이션 개발을 위한 MVC 패턴 기반의 웹 프레임워크</li>
		<li>Spring MVC는 애플리케이션의 구성요소를 Model, View, Controller로 분리함</li>
		<li>Spring MVC 컴포넌트
			<ul>
				<li>Dispatcher Servlet: 어플리케이션으로 들어오는 모든 Request를 받는 관문. Request를 실제로 처리할 Controller에게 전달하고 그 결과값을 받아서 View에게 전달하여 적절한 응답등 생성할 수 있도록 흐름을 제어</li>
				<li>Handler Mapping: Request URL 각각을 어떤 Controller가 실제로 처리할 것인지 찾아주는 역할</li>
				<li>Controller: Request를 직접 처리한 후 그 결과를 다시 DispatcherServlet 에게 돌려줌</li>
				<li>ViewResolver: View 관련 정보를 갖고 실제 View를 찾아주는 역할</li>
				<li>View: Controller가 처리한 결과값을 보여줄 View를 생성</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>15. Spring Bean이란 무엇인가?</summary>
	<ul>
		<li>Spring IoC Container가 관리하는 자바 객체</li>
		<li>Spring Bean Container에 존재하는 객체</li>
		<li>Spring IoC Container에 의해 인스턴스화, 관리, 생성됨</li>
		<li>Bean Container는 의존성 주입을 통해 Bean 객체를 사용할 수 있도록 해줌</li>
	</ul>
</details>

<details>
	<summary>16. Spring Bean의 생성 방식을 설명하시오.</summary>
	<ul>
		<li>Component Scanning
			<ul>
				<li>@ComponentScan, @Component Annotation을 사용해서 Bean을 등록하는 방법
					<ul>
						<li>@ComponentScan: @Component가 부여된 Class를 찾아 자동으로 Bean으로 등록해주는 역할</li>
						<li>@Component: 실제로 찾아서 Bean으로 등록할 Class를 의미</li>
					</ul>
				</li>
			</ul>
		</li>
	</ul>
		<li>Configuration
			<ul>
				<li>@Configuration 사용, @Bean 정의
					<ul>
						<li>Java class에서 @Configuration을 사용해서 직접 @Bean을 등록해주는 방법</li>
						<li>@Bean Annotation을 사용해 직접 Bean을 정의하면 자동으로 Bean으로 등록됨</li>
					</ul>
				</li>
				<li>XML 파일에 설정: XML 파일에 직접 Bean을 등록하여 Application의 Bean을 설정하는 방법</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>17. Spring Bean의 Scope에 대해서 설명하시오.</summary>
	<ul>
		<li>Spring은 기본적으로 모든 Bean을 Singleton(어떤 Class가 최초 한번만 메모리를 할당하고(Static) 그 메모리에 객체를 만들어 사용하는 디자인 패턴)으로 생성하여 관리함</li>
		<li>Singleton Bean은 Spring Container에서 한 번 생성 후, Container가 사라질 때 Bean도 제거</li>
		<li>생성된 하나의 Instance는 Single Beans Cache에 저장되고, 해당 Bean에 대한 요청과 참조가 있으면 캐시된 객체를 반환</li>
		<li>하나만 생성되기 때문에 동일한 것을 참조</li>
		<li>기본적으로 모든 Bean은 Scope가 명시적으로 지정되지 않으면 Singleton</li>
		<li>구체적으로는 Application 구동 시 JVM 안에서 스프링이 Bean마다 하나의 객체를 생성하는 것을 의미함</li>
		<li>그래서 Spring을 통해서 Bean을 주입 받으면 언제나 주입받은 Bean은 동일한 객체라는 가정하에서 개발함</li>
	</ul>
</details>

<details>
	<summary>18. DI 종류는 어떤것이 있고, 이들의 차이는 무엇인가?</summary>
	<ul>
		<li>Setter Injection
			<ul>
				<li>Setter 메소드를 통한 의존성 주입</li>
				<li>의존성을 입력받는 Setter 메서드를 만들고 이를 통해 의존성 주입</li>
			</ul>
		</li>
		<li>Constructor Injection
			<ul>
				<li>생성자를 통한 의존성 주입</li>
				<li>필요한 의존성을 포함하는 클래스의 생성자를 만들고 이를 통해 의존성을 주입</li>
			</ul>
		</li>
		<li> Method Injection
			<ul>
				<li>일반 메소드를 이용한 의존성 주입</li>
				<li>의존성을 입력 받는 일반 메서드를 만들고 이를 통해 의존성을 주입</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>19. Autowiring은 무엇이고, Autowiring 과정은 어떻게 되는지 설명하시오.</summary>
	<ul>
		<li>@Autowired: 의존관계 주입(DI)을 할 때 사용하는 어노테이션(Annotation)이며, 의존 객체의 타입에 해당하는 빈(Bean)을 찾아 주입하는 역할</li>
		<li>과정
			<ul>
				<li>컨테이너에서 타입(인터페이스 또는 오브젝트)을 이용해 의존 대상 객체를 검색</li>
				<li>할당할 수 있는 빈 객체를 찾아 주입</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>20. Servlet Filter VS Spring Interceptor</summary>
	<ul>
		<li>Servlet Filter
			<ul>
				<li>관리 컨테이너: 웹 컨테이너</li>
				<li>Request/Response 조작 가능 여부: O</li>
				<li>스프링과 무관하게 전역적으로 처리해야 하는 작업들을 수행</li>
				<li>용도
					<ul>
						<li>공통된 보안 및 인증/인가 관련 작업</li>
						<li>모든 요청에 대한 로깅 또는 감사</li>
						<li>이미지/데이터 압축 및 문자열 인코딩</li>
						<li>Spring과 분리되어야 하는 기능</li>
					</ul>
				</li>
			</ul>
		</li>
		<li>Spring Interceptor
			<ul>
				<li>관리 컨테이너: 스프링 컨테이너</li>
				<li>Request/Response 조작 가능 여부: X</li>
				<li>클라이언트의 요청과 관련되어 전역적으로 처리해야 하는 작업들을 처리</li>
				<li>용도
					<ul>
						<li>세부적인 보안 및 인증/인가 공통 작업</li>
						<li>API 호출에 대한 로깅 또는 감사</li>
						<li>Controller로 넘겨주는 정보(데이터)의 가공</li>
					</ul>
				</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>21. Spring에서 CORS 에러를 해결하기 위한 방법을 설명하시오.</summary>
	<ul>
		<li>CorsFilter 생성
			<ul>
				<li>Access-Control 을 확인할 수 있도록 커스텀 Filter 를 생성</li>
				<li>@Component 이라는 어노테이션을 추가하고, Filter 인터페이스를 구현하여 Override</li>
				<li>Filter 는 꼭 javax.servlet 의 Filter를 사용해야함</li>
			</ul>
		</li>
		<li>CrossOrigin 어노테이션 사용
			<ul>
				<li>컨트롤러에서 특정 메서드 혹은 컨트롤러 상단부에 @CrossOrigin 만 추가
					<ul>
						<li>컨트롤러 클래스 단에서 설정</li>
						<li>메서드 단에서 설정</li>
					</ul>
				</li>
				<li>단점: 컨트롤러가 많을 수록 설정해야하는 어노테이션이 많아진다는 것</li>
			</ul>
		</li>
		<li>WebMvcConfigurer 에서 설정
			<ul>
				<li>main 함수에서 Bean 으로 Configurer 를 추가</li>
				<li>@Configuration 을 허용한 클래스에서 등록을 할 수도 있음</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>22. 스프링 트랜잭션 추상화에서 Rollback 대상은 무엇인가?</summary>
	스프링 트랜잭션 추상화에서 Rollback 대상은 UncheckedException
</details>
