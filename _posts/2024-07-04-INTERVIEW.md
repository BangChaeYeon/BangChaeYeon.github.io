---
title: 기술 면접 대비_1_Java
author: BCY
date: 2024-07-04 20:22:36 +0900
categories: [interview, java]
tags: [interview]
---
## 개요
이 글은 기술 면접을 대비하여 예상 질문 리스트를 정리하고자 작성했습니다.
내용은 계속 추가 될 예정입니다.

<details>
  <summary>OOP란 무엇인가?</summary>
  Object-Oriented Programming의 약자로 객체 지향 프로그래밍을 뜻함
</details>

<details>
  <summary>OOP의 특징은 무엇인가?</summary>
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
  <summary>SOLID란 무엇인가?</summary>
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
  <summary>Java의 특징은 무엇인가?</summary>
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
  <summary>Call by Value, Call by Reference의 차이점을 설명하고 Java는 이 중 무엇인지 설명하시오.</summary>
  <ul>
    <li>Call by Value: 값에 의한 호출</li>
    <li>Call by Reference: 참조에 의한 호출</li>
  </ul>
  Java는 Call by Value 방식을 사용함, primitive type을 파라미터로 넘기는 경우 해당 함수에서 같은 이름의 다른 변수를 새로 만들기 때문에 기존 값이 변경되지 않음.
  다만, Heap Memory에 생성되는 참조 타입 변수는 주소값을 전달하기 때문에 기존의 값이 변경되어 Call by Reference를 사용한다는 오해를 사기도 함
</details>

<details>
  <summary>JVM은 어떻게 구성되어 있는가?</summary>
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
  <summary>JVM은 어떻게 동작하는가?</summary>
  <ul>
    <li>프로그램이 실행되면 OS로부터 프로그램이 필요로 하는 메모리를 할당 받음</li>
    <li>javac를 통해 .java 파일이 .class파일(바이트 코드)로 변환됨</li>
    <li>Class Loader에서 바이트 코드를 JVM에 로드 시킴</li>
    <li>로딩된 바이트 코드를 execution engine을 통해 기계어로 해석</li>
    <li>해석된 바이트 코드는 runtime data areas에 배치되어 실질적인 수행이 이루어짐</li>
  </ul>
</details>

<details>
  <summary>GC는 어떻게 동작하는가?</summary>
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
  <summary>직렬화(Serialization)는 무엇인가?</summary>
  <ul>
    <li>자바에서 입출력을 할 때에는 스트림이라는 통로를 통해 데이터가 이동함. 하지만 객체는 바이트형이 아니라서 스트림을 통해 파일에 저장하거나 네트워크로 전송할 수 없음</li>
    <li>따라서 객체를 스트림을 통해 입출력하려면 바이트 배열로 변환하는 것이 필요한데, 이를 '직렬화' 라고 함</li>
    <li>시스템이 종료되더라도 없어지지 않는 장점을 가지며 영속화(Persistence)된 데이터이기 때문에 네트워크로 전송이 가능함</li>
  </ul>
</details>

<details>
  <summary>Java의 접근 제어자에 대해 설명하시오</summary>
  <ul>
    <li>public: 어떤 클래스에서라도 접근이 가능</li>
    <li>protected: 동일 패키지의 클래스 또는 해당 클래스를 상속받은 다른 패키지의 클래스에서만 접근이 가능</li>
    <li>default:  해당 패키지 내에서만 접근이 가능, 접근 제어자를 별도로 설정하지 않을 때는 default가 사용됨</li>
    <li>private: 해당 클래스에서만 접근이 가능</li>
  </ul>
</details>

<details>
  <summary>박싱/언박싱은 무엇인가?</summary>
  <ul>
    <li>박싱: primitive data type(기본 자료형) ➝ Wrapper Class</li>
    <li>언박싱: Wrapper Class ➝  primitive data type</li>
  </ul>
</details>

<details>
  <summary>HashMap VS HashTable VS ConcurrentHashMap</summary>
  <ul>
    <li>HashMap: 주요 메소드에 synchronized 키워드 선언 X, key/value에 null 입력 가능</li>
    <li>HashTable: 주요 메소드에 synchronized가 선언 O, key/value에 null 입력 불가</li>
    <li>ConcurrentHashMap: HashMap을 thread-safe하도록 만든 클래스, key/value에 null 입력 불가</li>
  </ul>
</details>

<details>
  <summary>interface VS abstract</summary>
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
  <summary>String VS StringBuilder VS StringBuffer</summary>
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
  <summary>Iterator VS Iterable</summary>
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
  <summary>Vector VS ArrayList</summary>
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
