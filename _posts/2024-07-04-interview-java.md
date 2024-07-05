---
title: 기술 면접 대비 - Java편
author: BCY
date: 2024-07-05 20:18:37 +0900
categories: [interview, java]
tags: [interview]
---
## 개요
이 글은 기술 면접을 대비하여 예상 질문 리스트를 정리하고자 작성했습니다.
내용은 계속 추가 될 예정입니다.

<details>
  <summary>1. OOP란 무엇인가?</summary>
  Object-Oriented Programming의 약자로 객체 지향 프로그래밍을 뜻함
</details>

<details>
  <summary>2. OOP의 특징은 무엇인가?</summary>
  OOP의 특징은 크게 4가지로 나뉜다.
  <ul>
    <li>캡슐화(Encapsulation)
      <ul>
        <li>하나의 객체가 특정한 목적을 위해 필요한 변수나 메소드를 하나로 묶는 것을 의미</li>
        <li>캡슐화를 하면 불필요한 정보를 감출 수 있기 때문에, 정보은닉을 할 수 있다는 특징이 있음</li>
      </ul>
    </li>
    <li>추상화(Abstraction)
      <ul>
        <li>목적과 관련이 없는 부분을 제거하여 필요한 부분만을 표현하기 위한 개념</li>
        <li>객체들의 공통된 특징을 파악해 정의해 놓은 설계 기법</li>
      </ul>
    </li>
    <li>상속(Inheritance)
      <ul>
        <li>기존 상위클래스에 근거하여 새롭게 클래스와 행위를 정의할 수 있게 도와주는 개념</li>
        <li>기존 클래스에 기능을 가져와 재사용할 수 있으면서도 동시에 새롭게 만든 클래스에 새로운 기능을 추가할 수 있게 만들어줌(코드의 중복을 없애기 위함)</li>
      </ul>
    </li>
    <li>다형성(Polymorphism)
      <ul>
        <li>형태가 같은데 다른 기능을 하는 것을 의미, 이를 통해 코드의 재사용, 코드 길이 감소가 되어 유지보수가 용이하도록 도와줌</li>
        <li>
          <ul>
            <li>Overriding: 상위 클래스의 메소드를 하위 클래스에서 재정의하여 사용하는 것</li>
            <li>Overloading: 메소드의 이름은 같지만 파라미터의 타입, 개수에 따라 다른 메소드가 되도록 함</li>
          </ul>
        </li>
      </ul>
    </li>
  </ul>
</details>

<details>
  <summary>3. SOLID란 무엇인가?</summary>
  객체 지향 프로그래밍의 5가지 주요 원칙, 이 원칙을 따를 시 높은 수준의 유지/보수가 쉬운 코드를 작성하고 시스템을 올바르게 설계할 수 있음
  <ul>
    <li>단일 책임 원칙(Single Responsibility Principle, SRP): 클래스 자체는 하나의 작업만 수행하는데 집중해야 한다는 원칙, 어떤 클래스를 변경할 때는 단 하나의 이유만 있어야 단일 책임 원칙을 지키는 것</li>
    <li>개방 폐쇄 원칙(Open-Close Principle, OCP): 상속에 관한 것으로 클래스는 수정에 대해 닫혀 있어야 하고 확장에 대해 열려있어야 함, 기존 구성요소는 수정이 일어나지 말아야하며 쉽게 확장이 가능하여 재사용할 수 있어야함</li>
    <li>리스코프 치환 원칙(Liskov Substitution Principle, LSP): OCP를 적용한 원칙으로 상위 클래스 객체를 하위 클래스 객체로 변경해도 올바르게 동작해야함, 하위 클래스는 상위 클래스의 동작이나 의미를 변경할 수 없음</li>
    <li>인터페이스 분리 원칙(Interface Segregation Principle, ISP): 클라이언트가 자신이 이용하지 않는 메소드에 의존하지 않아야 한다는 원칙, 인터페이스를 작은 단위로 분리시켜 클라이언트가 꼭 필요한 메소드들만 이용할 수 있게 해야함</li>
    <li>의존관계 역전 원칙(Dependency Inversion Principle, DIP): 클래스가 추상화의 구체적인 구현에 의존하는 것이 아니라 추상화 자체에 의존해야한다는 원칙으로 의존성 주입(Dependency Injection)이 이 원칙을 따르는 방법 중 하나</li>
  </ul>
</details>

<details>
  <summary>4. Java의 특징은 무엇인가?</summary>
  <ul>
    <li>운영체제에 독립적(JVM에서 동작하기 때문에, 특정 운영체제에 종속 되지 않음)</li>
    <li>객체 지향 언어
      <ul>
        <li>클래스와 객체를 사용하여 프로그램을 간결하게 구현 가능</li>
        <li>프로그래밍 하기 위해 여러 언어적 지원을 하고 있음</li>
        <li>캡슐화, 상속, 추상화, 다형성이 특징</li>
      </ul>
    </li>
    <li>자동 메모리 관리(Garbage Collection)</li>
    <li>네트워크와 분산환경 지원</li>
    <li>멀티쓰레드(동시사용가능) 지원</li>
    <li>동적 로딩(그때 그때 사용 가능) 지원</li>
    <li>오픈소스임(OpenJDK가 오픈소스)</li>
  </ul>
</details>

<details>
  <summary>5. Call by Value, Call by Reference의 차이점을 설명하고 Java는 이 중 무엇인지 설명하시오.</summary>
  <ul>
    <li>Call by Value: 값에 의한 호출</li>
    <li>Call by Reference: 참조에 의한 호출</li>
  </ul>
  Java는 Call by Value 방식을 사용함, primitive type을 파라미터로 넘기는 경우 해당 함수에서 같은 이름의 다른 변수를 새로 만들기 때문에 기존 값이 변경되지 않음.
  다만, Heap Memory에 생성되는 참조 타입 변수는 주소값을 전달하기 때문에 기존의 값이 변경되어 Call by Reference를 사용한다는 오해를 사기도 함
</details>

<details>
  <summary>6. JVM은 어떻게 구성되어 있는가?</summary>
  <ul>
    <li>JVM: 자바 가상머신으로 자바 바이트코드를 실행 할 수 있는 주체로 JVM 덕분에 CPU나 운영체제(플랫폼)과 독릭접으로 동작 가능</li>
    <li>Garbage Collection: Heap 메모리 영역에 생성 된 객체들 중 Reachability를 잃은 객체를 탐색 후 제거하는 역할</li>
    <li>Class Loader: JVM내로 클래스 파일을 로드하고 링크를 통해 배치하는 모듈, Runtime 시에 동적으로 클래스를 로드</li>
    <li>Execution Engine: 메모리에 적재된 클래스들을 기계어로 변경해 명령어 단위로 실행하는 역할
      <ul>
        <li>Interpreter
          <ul>
            <li>자바 바이트 코드를 명령어 단위로 읽어서 실행</li>
            <li>한 줄 씩 수행하기 때문에 느림</li>
          </ul>
        </li>
        <li>JIT(Just-In-Time)
          <ul>
            <li>인터프리터 방식으로 실행되다가 적절한 시점에 바이트 코드 전체를 컴파일하여 네이티브 코드로 변경하고, 그 이후부터는 더 이상 인터프리팅 하지 않고 네이티브 코드로 직접 실행함</li>
          </ul>
        </li>
      </ul>
    </li>
    <li>Runtime Data Areas
      <ul>
        <li>Method Area
          <ul>
            <li>클래스 멤버 변수, 메소드 정보, Type(Class or interface)정보, Constant Pool, static, final 변수 등이 생성</li>
          </ul>
        </li>
        <li>Heap Area
          <ul>
            <li>동적으로 생성된 오브젝트와 배열이 저장되는 곳</li>
            <li>Garbage Collection의 대상이 되는 영역</li>
          </ul>
        </li>
        <li>Stack Area
          <ul>
            <li>지역 변수, 파라미터 등이 생성되는 영역</li>
            <li>동적으로 객체를 생성하면 실제 객체는 Heap에 할당되고 해당 레퍼런스만 Stack에 저장됨</li>
            <li>Heap에 있는 오브젝트가 Stack에서 참조 할 수 없는 경우 GC의 대상이 됨</li>
          </ul>
        </li>
        <li>PC Register
          <ul>
            <li>Thread가 시작될 때마다 생성됨</li>
            <li>현재 Thread가 실행되는 부분의 주소와 명령을 저장</li>
          </ul>
        </li>
        <li>Native Method Stack
          <ul>
            <li>기계어로 작성된 프로그램을 실행시키는 영역</li>
            <li>Java외의 언어로 작성된 네이티브 코드를 위한 메모리 영역</li>
          </ul>
        </li>
      </ul>
    </li>
  </ul>
</details>

<details>
  <summary>7. JVM은 어떻게 동작하는가?</summary>
  <ul>
    <li>프로그램이 실행되면 OS로부터 프로그램이 필요로 하는 메모리를 할당 받음</li>
    <li>javac를 통해 .java 파일이 .class파일(바이트 코드)로 변환됨</li>
    <li>Class Loader에서 바이트 코드를 JVM에 로드 시킴</li>
    <li>로딩된 바이트 코드를 execution engine을 통해 기계어로 해석</li>
    <li>해석된 바이트 코드는 runtime data areas에 배치되어 실질적인 수행이 이루어짐</li>
  </ul>
</details>

<details>
  <summary>8. GC는 어떻게 동작하는가?</summary>
  <ul>
    <li>Major GC
      <ul>
        <li>Old 영역을 조사하여 참조하지 않는 객체들을 삭제, 시간이 오래걸리고 실행중에 프로세스가 정지됨(stop-the-world)</li>
      </ul>
    </li>
    <li>Minor GC
      <ul>
        <li>JVM 의 Young 영역에서 일어나는 GC </li>
        <li>Young 에 위치한 각각의 영역이 가득 차게 되어 더 이상 새로운 객체를 생성할 수 없을 때 발생</li>
        <li>GC를 담당하는 스레드 외의 스레드에서 stop-the-world가 발생하긴 하지만 매우 짧기 때문에 stop-the-world가 발생하지 않는다고 함</li>
      </ul>
    </li>
  </ul>
</details>

<details>
  <summary>9. 직렬화(Serialization)는 무엇인가?</summary>
  <ul>
    <li>자바에서 입출력을 할 때에는 스트림이라는 통로를 통해 데이터가 이동함. 하지만 객체는 바이트형이 아니라서 스트림을 통해 파일에 저장하거나 네트워크로 전송할 수 없음</li>
    <li>따라서 객체를 스트림을 통해 입출력하려면 바이트 배열로 변환하는 것이 필요한데, 이를 '직렬화' 라고 함</li>
    <li>시스템이 종료되더라도 없어지지 않는 장점을 가지며 영속화(Persistence)된 데이터이기 때문에 네트워크로 전송이 가능함</li>
  </ul>
</details>

<details>
  <summary>10. Java의 접근 제어자에 대해 설명하시오</summary>
  <ul>
    <li>public: 어떤 클래스에서라도 접근이 가능</li>
    <li>protected: 동일 패키지의 클래스 또는 해당 클래스를 상속받은 다른 패키지의 클래스에서만 접근이 가능</li>
    <li>default:  해당 패키지 내에서만 접근이 가능, 접근 제어자를 별도로 설정하지 않을 때는 default가 사용됨</li>
    <li>private: 해당 클래스에서만 접근이 가능</li>
  </ul>
</details>

<details>
  <summary>11. 박싱/언박싱은 무엇인가?</summary>
  <ul>
    <li>박싱: primitive data type(기본 자료형) ➝ Wrapper Class</li>
    <li>언박싱: Wrapper Class ➝  primitive data type</li>
  </ul>
</details>

<details>
  <summary>12. HashMap VS HashTable VS ConcurrentHashMap</summary>
  <ul>
    <li>HashMap: 주요 메소드에 synchronized 키워드 선언 X, key/value에 null 입력 가능</li>
    <li>HashTable: 주요 메소드에 synchronized가 선언 O, key/value에 null 입력 불가</li>
    <li>ConcurrentHashMap: HashMap을 thread-safe하도록 만든 클래스, key/value에 null 입력 불가</li>
  </ul>
</details>

<details>
  <summary>13. interface VS abstract</summary>
  <ul>
    <li>interface(인터페이스)
      <ul>
        <li>다중 상속</li>
        <li>추상 메소드, 상수만 선언 가능</li>
        <li>생성자, 일반 변수를 가질 수 없음</li>
        <li>팀별 협업시 추상메소드를 통해 결과를 예측하고 작업 가능함(구현 객체의 동일성 보장)</li>
      </ul>
    </li>
  </ul>
  <ul>
    <li>abstract(추상 클래스)
      <ul>
        <li>다중 상속 불가</li>
        <li>추상 메소드 1개 이상, 일반 변수, 일반 메소드 선언 가능</li>
        <li>생성자, 일반 변수를 가질 수 있음</li>
        <li>메소드의 부분 구현이 가능(부분 구현된 메소드를 상속받아 확장시키기 위함)</li>
      </ul>
    </li>
  </ul>
</details>

<details>
  <summary>14. String VS StringBuilder VS StringBuffer</summary>
  <ul>
    <li>String
      <ul>
        <li>immutable(불변)</li>
        <li>객체를 한 번 할당할 시 메모리 공간에 변동이 없음(할당 시 Heap String Pool영역에 생성되어 그 값을 계속 사용함)</li>
        <li>동기화 신경X</li>
      </ul>
    </li>
  </ul>
  <ul>
    <li>StringBuilder
      <ul>
        <li>mutable(가변)</li>
        <li>동기화 지원X</li>
      </ul>
    </li>
  </ul>
  <ul>
    <li>StringBuffer
      <ul>
        <li>mutable(가변)</li>
        <li>각 메소드 별로 Synchronized Keyword가 존재함</li>
        <li>멀티 스레드 환경에서도 동기화 지원(thread-safe)</li>
      </ul>
    </li>
  </ul>
</details>

<details>
  <summary>15. Iterator VS Iterable</summary>
  <ul>
    <li>Iterator
      <ul>
        <li>Java 1.2에 발표된 인터페이스</li>
        <li>hasNext, next 등을 통해 현재 위치를 알 수 있고 다음 element가 있는지를 판단하는 기능등에 대한 명세를 제공</li>
        <li>대게 Collection 인터페이스를 사용하는 클래스의 경우 별도의 Iterator를 구현하여 사용</li>
      </ul>
    </li>
  </ul>
  <ul>
    <li>Iterable
      <ul>
        <li>Java 1.5부터 나온 인터페이스</li>
        <li>Iterator보다 더 늦게 나온 인터페이스로 Iterator를 제공하는 메서드를 보유하고 있는 인터페이스</li>
        <li>실질적으로 for-each를 사용할 수 있는 클래스라는것을 명세해주는 기능을 제공</li>
      </ul>
    </li>
  </ul>
</details>

<details>
  <summary>16. Vector VS ArrayList</summary>
  둘 다 동적인 배열을 다루는 Collection Framework
  <ul>
    <li>Vector
      <ul>
        <li>동기화가 된 상태(thread-safe)</li>
        <li>상대적으로 속도가 느림(동기화가 되었기 때문)</li>
      </ul>
    </li>
    <li>ArrayList
      <ul>
        <li>동기화가 안된 상태</li>
        <li>상대적으로 속도가 빠름(동기화가 되지 않았기 때문)</li>
        <li>멀티 스레드 환경이 아닐 경우 사용 권장</li>
      </ul>
    </li>
  </ul>
</details>

<details>
	<summary>17. ArrayList VS LinkedList</summary>
	<ul>
		<li>ArrayList
			<ul>
				<li>내부적으로 데이터를 배열로 관리하고 데이터 추가/삭제 시 임시 배열을 사용하여 데이터를 복사함</li>
				<li>데이터 별 인덱스가 있어서 검색에는 유리</li>
				<li>임시 배열을 사용하기 때문에 데이터 추가/삭제에는 불리</li>
			</ul>
		</li>
		<li>LinkedList
			<ul>
				<li>내부적으로 노드 단위의 데이터를 관리함, 자신의 앞/뒤 노드만 인지하는 상태</li>
				<li>인덱스가 따로 없기 때문에 검색 시 전 노드를 순회 해야해서 검색에 불리</li>
				<li>데이터 추가/삭제 시 불필요한 데이터 복사가 없어서 유리</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>18. volatile은 무엇인가?</summary>
	<ul>
		<li>멀티 스레딩 환경에서 동기화를 해주는 키워드</li>
		<li>Java에서는 멀티 코어 프로세서에서 코어마다 별도의 캐시를 가지고 있어서 발생되는 일을 방지할 때 사용</li>
		<li>변수 앞에 volatile을 붙이면 코어가 변수의 값을 읽어올 때, 캐시가 아닌 메모리에서 읽어오기 때문에 캐시와 메모리간의 값의 불일치가 해결됨</li>
	</ul>
</details>

<details>
	<summary>19. try-with-resource는 무엇인가?</summary>
	<ul>
		<li>try 구문이 끝날 때 자동으로 자원을 해제시켜주는 기능</li>
		<li>이 때, try에 전달할 수 있는 자원은 AutoCloseable 인터페이스의 구현체로 한정됨(AutoCloseable은 JDK1.7부터 추가된 인터페이스)</li>
	</ul>
</details>

<details>
	<summary>20. Synchronized(동기화)는 무엇이고 동기화 방식에는 무엇이 있는가?</summary>
	여러 개의 스레드가 하나의 자원에 접근할 때 주어진 순간에는 단 하나의 스레드만 접근이 가능하도록 하는 것
	<ul>
		<li>동기화 방법
			<ul>
				<li>synchronized 메소드를 만들어 사용</li>
				<li>synchronized 블록을 사용</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>21. Java의 메모리는 어떻게 구성되어 있는가?</summary>
	<ul>
		<li>메소드 영역: static 변수, 전역변수, 코드에서 사용되는 class 정보가 할당됨</li>
		<li>Stack: 지역변수, 메소드 등이 할당되는 LIFO 방식의 메모리</li>
		<li>Heap: new 연산자를 통해 동적 할당된 객체들이 저장됨, GC에 의해 메모리가 관리됨</li>
	</ul>
</details>

<details>
	<summary>22. Collection Framework는 무엇인가?</summary>
	<ul>
		<li>다수의 데이터를 쉽고 효과적으로 처리할 수 있는 표준화된 방법을 제공하는 클래스의 집합</li>
		<li>List, Set은 Collection Interface를 상속받음</li>
		<li>구조상의 차이로 Map은 별도로 정의됨</li>
		<li>List
			<ul>
				<li>순서가 있는 데이터의 집합으로 데이터의 중복을 허용</li>
				<li>구현 클래스: Vector, ArrayList, LinkedList, Stack, Queue</li>
			</ul>
		</li>
		<li>Set
			<ul>
				<li>순서가 없는 데이터의 집합으로 데이터의 중복을 허용하지 않음</li>
				<li>구현 클래스: HashSet, TreeSet</li>
			</ul>
		</li>
		<li>Map
			<ul>
				<li>키와 한 쌍을 이루는 데이터의 집합으로 순서가 없음, 키는 중복 허용X / 값은 중복 허용O</li>
				<li>구현 클래스: HashMap, TreeMap, HashTable, Properties</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>23. Generic은 무엇인가?</summary>
	<ul>
		<li>객체의 타입을 컴파일 시에 체크하여 객체 타입의 안정성을 높이고 형변환의 번거로움을 덜어줌</li>
		<li>안정성을 높이고 코드를 간결하게 짤 수 있도록 도움</li>
	</ul>
</details>

<details>
	<summary>24. CheckedException과 UncheckedException에 대해 설명하시오.</summary>
	<ul>
		<li>CheckedException
			<ul>
				<li>반드시 예외를 처리해야함(try-catch, throws)</li>
				<li>확인 시점: 컴파일 단계</li>
				<li>예외 발생시 롤백하지 않음</li>
				<li>예외 종류: RuntimeException을 제외한 모든 예외</li>
			</ul>
		</li>
		<li>UncheckedException
			<ul>
				<li>예외 처리를 강제하지 않음</li>
				<li>확인 시점: 실행(Runtime)단계</li>
				<li>예외 발생시 롤백함</li>
				<li>예외 종류: RuntimeException 하위 예외(RuntimeException을 상속함)</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>25. Java8에서 추가된 기능에 대해서 설명하시오.</summary>
	<ul>
		<li>추가된 기능: Lambda식, Stream API, Optional, 날짜 시간 API, StringJoiner</li>
		<li>Lambda는 함수형 프로그래밍을 지원하기 위한 기능</li>
		<li>Stream API는 고차함수를 지원함</li>
		<li>Optional은 Null-safety를 제공하며, Stream과 사용법이 유사함 </li>
		<li>날짜 시간 API는 Joda-time등의 라이브러리에서 영향을 받음</li>
		<li>StringJoiner는 문자열을 간단하게 구분자로 합칠 수 있는 기능을 제공</li>
	</ul>
</details>

<details>
	<summary>26. final / finally / finalize() 차이점을 설명하시오.</summary>
	<ul>
		<li>final
			<ul>
				<li>final class: 다른 클래스에서 상속할 수 없음</li>
				<li>final method: 다른 메소드에서 오버라이딩할 수 없음</li>
				<li>final variable: 변하지 않는 상수 값이 되어 새로 할당할 수 없는 변수가 됨</li>
			</ul>
		</li>
		<li>finally
			<ul>
				<li>try-catch or try-catch-resource 구문 사용 시, 정상적으로 작업을 한 경우와 에러가 발생했을 경우를 포함하여 마무리가 필요한 작업이 있을 경우 해당 코드를 작성해주는 코드 블록</li>
			</ul>
		</li>
		<li>finalize()
			<ul>
				<li>GC에 의해 호출되는 함수로 절대 호출해서는 안되는 함수</li>
				<li>GC가 발생하는 시점이 불분명하기 때문에 해당 함수가 실행된다는 보장이 없음</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>27. new String()과 “”의 차이점을 설명하시오</summary>
	<ul>
		<li>“”로 선언된 String은 String Pool에 추가되고 해당 값을 참조 값으로 가지게 됨</li>
		<li>new String()의 경우는 Heap 영역에 새로운 객체를 등록하게 됨</li>
	</ul>
</details>

<details>
	<summary>28. 강한 결합과 느슨한 결합이 무엇인지 설명하시오.</summary>
	<ul>
		<li>강한 결합(Tight Coupling)
			<ul>
				<li>클래스와 객체가 서로 의존적이라 객체가 변경될 시 클래스가 전체적으로 수정되어야 할 위험이 있음</li>
				<li>객체 간 강한 결합을 이루게 되면 멤버 변수에 대한 오브젝트 변경시 코드의 변경이 많이 일어나 유지보수에 좋지 않음</li>
			</ul>
		</li>
		<li>느슨한 결합(Loose Coupling)
			<ul>
				<li>클래스의 자료구조, 메서드를 추상화 할 수 있는 인터페이스 클래스를 사용해 의존성을 최소화</li>
				<li>인터페이스를 통해 약한 결합을 이루게 하여 유지보수를 향상</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>29. 자바의 동시성 이슈(공유자원 접근)에 대해 설명하시오.</summary>
	<ul>
		<li>가시성 문제
			<ul>
				<li>여러 개의 스레드가 사용됨에 따라 CPU Cache Memory와 RAM의 데이터가 서로 일치하지 않아 발생하는 문제</li>
				<li>가시성이 보장되어야하는 변수들을 CPU Cache Memory에서 불러오는 것이 아닌 RAM에서 바로 읽도록 보장해야함
					<ul>
						<li>변수에 volatile 키워드를 붙여 가시성을 보장할 수 있음</li>
					</ul>
				</li>
			</ul>
		</li>
		<li>원자성(동시 접근) 문제
			<ul>
				<li>한 줄의 프로그램 문장이 컴파일러에 의해 기계어로 변경되면서, 이를 기계가 순차적으로 처리하기 위한 여러 개의 Machine Instruction이 만들어져 실행되기 때문에 일어나는 현상</li>
				<li>원자성 문제를 synchronized, atomic을 통해 해결하면 가시성의 문제도 해결됨</li>
				<li>synchronized(blocking)
					<ul>
						<li>멀티 스레드 환경에서 동시성 제어를 위해 공유 객체를 동기화하는 키워드</li>
						<li>synchronized 블록안에서 관리되는 자원들은 원자성을 보장할 수 있음</li>
					</ul>
				</li>
				<li>atomic
					<ul>
						<li>멀티 스레드 환경에서 원자성을 보장하기 위해 나온 개념</li>
						<li>blocking이 아닌 CAS(Compared And Swap)라는알고리즘으로 작동하여 원자성을 보장함
							<ul>
								<li>CAS: volatile처럼 CPU Cache Memory와 RAM을 비교하여 일치한다면 CPU Cache Memory와 RAM에 적용하고, 일치하지 않는다면 재시도하여 어떤 스레드에서 공유자원에 읽기/쓰기 작업을 하더라도 원자성을 보장함</li>
								<li>Java의 Concurrent 패키지 타입들이 CAS를 사용</li>
							</ul>
						</li>
					</ul>
				</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>30. mutable VS immutable</summary>
	<ul>
		<li>mutable: 변할 수 있는; 잘 변하는</li>
		<li>immutable: 변경할 수 없는, 불변의
			<ul>
				<li>ex. String, Boolean, Integer, Float, Long</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>31. 자바에서 null을 안전하게 다루는 방법에 대해 설명하시오.</summary>
	<ul>
		<li>공개 메서드가 아닌 곳에는 assert를 사용하여 null을 방어할 수 있음</li>
		<li>메서드의 인자를 받을 때 Objects.requireNonNull()을 사용하여 방어할 수 있음</li>
		<li>Optional을 사용해 리턴 타입에서 null을 반환하지 않도록 방어할 수 있음</li>
	</ul>
</details>

<details>
	<summary>32. Statement와 PreparedStatement의 차이점은 무엇인가?</summary>
	<ul>
		<li>Statement
			<ul>
				<li>단일로 사용될 때 빠른 속도를 지님</li>
				<li>쿼리에 인자를 부여할 수 없음</li>
				<li>매번 컴파일을 수행해야함</li>
			</ul>
		</li>
		<li>PreparedStatement
			<ul>
				<li>여러 번 수행될 때 빠른 속도를 지님</li>
				<li>쿼리에 인자를 부여할 수 있음</li>
				<li>처음에 한 번만 컴파일함 </li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>33. Stream API에 대해 설명하시오.</summary>
	<ul>
		<li>데이터를 추상화하고, 처리하는데 자주 사용되는 함수들을 정의</li>
		<li>여기서 데이터를 추상화하였다는 것은 데이터의 종류에 상관 없이 같은 방식으로 데이터를 처리할 수 있다는 것을 의미하며, 그에 따라 재사용성을 높일 수 있음</li>
		<li>특징
			<ul>
				<li>원본의 데이터를 변경하지 않음</li>
				<li>일회용</li>
				<li>내부 반복으로 작업을 처리</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>34. JUnit에 대해 설명하시오.</summary>
	<ul>
		<li>JUnit: 자바에서 동작하는 수많은 테스트 라이브러리
			<ul>
				<li>통합 테스트, 시스템 테스트, UI 테스트 등 모든 수준의 테스트를 만들 수 있음</li>
			</ul>
		</li>
		<li>JUnit 관련 어노테이션
			<ul>
				<li>@BeforeClass(@BeforeAll) : 전체 테스트 시작 전에 딱 한번 호출되는 메서드</li>
				<li>@Before(@BeforeEach) : 테스트를 진행하기 전에 동작할 메서드에 사용</li>
				<li>@Test : 테스트를 진행할 메서드에 사용</li>
				<li>@After(@AfterEach) : 테스트를 진행한 후에 동작할 메서드에 사용</li>
				<li>@AfterClass(@AfterAll) : 전체 테스트 종료 후에 딱 한번 호출되는 메서드</li>
				<li>괄호 내부의 어노테이션은 JUnit 5 문법</li>
			</ul>
		</li>
		<li>실행 순서: @BeforeClass ➝ (@Before + @Test + @After) ➝ @AfterClass
			<ul>
				<li>@Test 메서드는 독립적으로 @Before, @After를 실행</li>
				<li>@Before, @After, @Test가 여러개일 경우, 실행 순서는 순서에 의존되지 않음</li>
			</ul>
		</li>
	</ul>
</details>

<details>
	<summary>35. JUnit 4 와 JUnit 5의 차이를 설명하시오.</summary>
	<ul>
		<li>구성이 다름
			<ul>
				<li>JUnit4: 하나의 라이브러리만 추가하면 됨</li>
				<li>JUnit5: 3개의 모듈(JUnit Platform + JUnit Jupiter + JUnit Vintage)로 나눠짐</li>
			</ul>
		</li>
		<li>Java 버전 지원
			<ul>
				<li>JUnit4: java4 이상</li>
				<li>JUnit5: java8 이상</li>
			</ul>
		</li>
		<li>Spring Boot 기본 제공 버전
			<ul>
				<li>JUnit4는 Spring Boot 2.1 버전까지 기본 제공</li>
				<li>JUnit5는 Spring Boot 2.2 이후버전 부터 기본 제공</li>
			</ul>
		</li>
		<li>어노테이션의 차이
			<ul>
				<li>어노테이션 명칭이 달라짐</li>
			</ul>
		</li>
	</ul>
</details>
