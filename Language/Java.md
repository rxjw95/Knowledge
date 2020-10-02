# Java

- [JAVA feature](#JAVA-feature)
- [절차 지향과 객체 지향](#절차-지향과-객체-지향)
- [객체 지향 프로그래밍 특징](#객체-지향-프로그래밍-특징)
- [5 Principle of Object-Oriented Programming](#5-Principle-of-Object-Oriented-Programming)
- [JVM 역할](#JVM-역할)
- [JAVA 메모리 구조](#JAVA-메모리-구조)
- [클래스와 객체](#클래스와-객체)
- [JAVA 접근 제어자](#JAVA-접근-제어자)
- [static](#static)
- [final](#final)
- [Generic, Collection](#Generic,-Collection)
- [Primitive type, Reference type](#Primitive-type,-Reference-type)
- [Wrapper Class](#Wrapper-Class)
- [JAVA Exception](#JAVA-Exception)
- [String, StringBuilder, StringBuffer](#String,-StringBuilder,-StringBuffer)
- [Interface, Abstract class](#Interface,-Abstract-class)
- [Java Thread](#Java-Thread)
- [Java Thread의 Synchroized](#Java-Thread의-Synchroized)
- [Serializable과 Parcelable](#Serializable과-Parcelable)
- [JDK, JRE](#JDK,-JRE)
- [Reflection](#Reflection)
- [자바에서 클래스 다중 상속 불가능한 이유](#자바에서-클래스-다중-상속-불가능한-이유)



---



## ☝JAVA feature

1. Object-Oriented Programming
2. JVM에 의한 OS 독립적
3. Garbage Collection(JVM)을 통한 메모리 관리
4. 기본 자료형을 제외한 모든 요소들이 객체로 표현
5. Multi-thread를 지원

---



## ☝절차 지향과 객체 지향

- 절차 지향

  데이터를 중심으로 순차적 흐름에 따라 개발하는 방법

- 객체 지향

  데이터와 데이터의 상태 혹은 동작을 하나의 객체로 묶어 다른 객체들과 상호작용하며 개발하는 방법

---



## ☝객체 지향 프로그래밍 특징

- 추상화

  객체들의 공통 특징을 추출하여 묶는 것

- 캡슐화

  데이터와 그 데이터를 사용하는 메소드를 묶어서 은닉하고 보호하는 것

- 상속

  부모 클래스의 형질을 자식 클래스에게 그대로 물려주는 것

- 다형성

  하나의 메세지로 여러 기능을 동작시키는 것(오버로딩, 오버라이딩)

---



## ☝5 Principle of Object Oriented Programming

- Single Responsibility Principle

  객체는 단 하나의 책임만을 가진다. (단일 책임의 원칙)

- Open-closed Principle

  객체의 변경이나 추가사항이 발생하더라도, 기존 구성요소는 수정이 일어나지 말아야 하며, 기존 구성요소를 쉽게 확장해서 재사용할 수 있어야 한다. (개방-폐쇄의 원칙)

- Liskov Substitution Principle

  슈퍼 클래스가 서브 클래스로 치환되어도 동일한 동작을 보장해야 한다는 원칙

- Interface Segregation Principle

  일반적인 한개의 인터페이스보다 구체적인 여러가지의 인터페이스를 구현해야 한다. (인터페이스 분리 원칙)

- Dependency Inversion Principle

  어떤 Class를 참조해야하는 상황이 생긴다면 그 Class를 직접 참조하는 것이 아니라 그 대상의 추상 클래스를 만들어서 사용한다. (의존성 역전의 원칙)

---



## ☝JVM 역할

1. Java 애플리케이션을 Class Loader를 통해 읽어들여 Java API와 함께 실행.
2. JVM은 Java와 OS사이에서 중개자 역할을 수행, Java가 OS에 독립적으로 실행 및 재사용을 가능하게 해준다.
3. 메모리 관리, Garbage Collection을 수행한다.
4. JVM은 스택기반의 가상머신이다. ARM 아키텍쳐 같은 하드웨어는 레지스터 기반으로 동작하는데 비해 JVM은 스택기반으로 동작한다.

---



## ☝JAVA 메모리 구조

![JVM_memory](https://user-images.githubusercontent.com/62179353/93015595-aa3ae300-f5f5-11ea-8378-05ca1beb1f4e.png)

- Method Area (= Class Area)

  static 변수, 코드에서 사용되는 class 정보 등이 저장되는 영역

- Stack Area

  메소드 내에서 정의하는 지역 변수(매개 변수, 블럭 내 변수 등)가 저장되는 영역

- Heap Area

  new 연산자를 통한 동적 할당된 객체들이 저장되며, Garbage 컬렉션에 의해 메모리가 관리된다.

---



## ☝클래스와 객체

클래스는 ‘변수와 변수를 처리할 메소드를 정의한 설계도’

객체는 ‘설계도로 구현한 모든 대상'

---

## ☝JAVA 접근 제어자

1. **private** : 같은 클래스 내에서만 접근 가능
2. **default** : 같은 패키지 내에서만 접근 가능
3. **protected** : 같은 패키지 내에서, 그리고 다른 패키지의 자손 클래스에서 접근 가능
4. **public** : 접근 제한이 전혀 없다.

> 접근 제어자가 사용될 수 있는 곳 : 클래스, 멤버변수, 메서드, 생성자

---



## ☝static

실행시에 메모리에 올라가서 공유되고 종료시에 할당이 해제되는 것

static은 클래스 변수라고도 불리며 객체를 생성하지 않아도 접근이 가능합

### 구현 예시

```java
public class MyCalculator {
    public static appName = "MyCalculator";
         
    public static int add(int x, int y) {
        return x + y;
    }
 
    public int min(int x, int y) {
        return x - y;
    }
}
 
MyCalculator.add(1, 2);   //(o) static 메소드 이므로 객체 생성 없이 사용 가능
MyCalculator.min(1, 2);   //(x) static 메소드가 아니므로 객체 생성 후에 사용 가능
 
 
MyCalculator cal = new MyCalculator();
cal.add(1, 2);   // (o) 가능은 하지만 권장하지 않는 방법
cal.min(1, 2);   // (o)
```



---



## ☝final

변경 불가능이라는 제약을 거는 것

클래스의 상속 불가, 메소드의 오버라이드 불가, 변수의 상수 선언

---



## ☝Generic, Collection

- Generic

  매개변수에 **특정 객체 타입을 지정**하여 지정한 형식의 데이터만을 처리한다.

  이를 통해 잘못된 데이터 타입을 방지하고 **런타임 에러가 아닌 컴파일 에러**

- Collection

  자바에서 자료구조를 따로 구현하지 않고 사용할 수 있는 프레임워크

---



## ☝Collection 자료구조

1. **List** (저장 순서 유지)
   - ArrayList : 일반 배열 + 가변적 공간, 동기화 처리 없음
   
   - LinkedList : 양방향 포인터 구조, 인덱싱 없음, 삽입/삭제 효과적
   
   - Vector : ArrayList와 동일한 구조, 동기화 제공
   
2. **Set** (저장 순서 유지되지 않음, 데이터 중복 미허용, Indexing 없음
   - HashSet : 순서가 필요없는 데이터를 hashtable에 저장. 가장 성능이 좋음
   
   - HashTree : 저장된 데이터의 값에 따라 정렬. 정렬 시간으로 인해 성능이 비교적 떨어짐
   
3. **Map** (<key,value> 쌍을 저장, key 중복 x, value 중복 o)
   - HashMap : 일반적인 Map,  value에 null 저장 가능, 동기화 미지원
   - HashTable : HashMap과 동일하지만 동기화를 지원
   - TreeMap : 기능은 같지만 key를 기준으로 정렬을 해줌

---



## ☝Primitive type, Reference type

- **Primitive type**

  메모리 공간에 직접 값을 저장한 변수 (Java에선 8개의 기본 데이터 타입)

- **Reference type**

  값을 참조하는 주소값을 저장한 변수

---



## ☝Wrapper Class

근본적인 이유는 기본 데이터 타입을 객체로 변환시켜 전달하기 위해 사용

> 기본 데이터 타입은 객체가 아니어서 Object로 받는 다형성을 지원되지 않는다. Generic과 같이 객체 형태의 타입을 전달해야 할 때나 데이터 타입 변경 등을 사용하는 경우가 있다. 이 때 Wrapper class를 사용한다.

---



## ☝JAVA Exception

- **Error와 Exception의 차이**

  - Error : H/W 오동작 or 고장으로 인해 응용프로그램에 이상이 생기거나 JVM 실행에 문제가 생겼을 경우 발생하는 것을 의미 - 이 경우 개발자는 대처할 방법이 극히 제한적
  - Exception :  사용자의 잘못된 조작 or 개발자의 잘못된 코딩으로 인해 발생하는 프로그램 오류를 의미 - 이 경우 `예외 처리(Exception Handling )`을 통해 프로그램을 정상적으로 작동시킬 수 있다.

- **try-catch-finally**

  - Exception의 종류

    - | 예외                          | 원인                                                         |
      | ----------------------------- | ------------------------------------------------------------ |
      | ArithmeticException           | 정수를 0으로 나눌경우 발생                                   |
      | ArrayIndexOutOfBoundsExcetion | 배열의 범위를 벗어난 index를 접근할 시 발생                  |
      | ClassCastExcetion             | 변환할 수 없는 타입으로 객체를 반환 시 발생                  |
      | NullPointException            | 존재하지 않는 레퍼런스를 참조할때 발생                       |
      | IllegalArgumentException      | 잘못된 인자를 전달 할 때 발생                                |
      | IOException                   | 입출력 동작 실패 또는 인터럽트 시 발생                       |
      | OutOfMemoryException          | 메모리가 부족한 경우 발생                                    |
      | NumberFormatException         | 문자열이 나타내는 숫자와 일치하지 않는 타입의 숫자로 변환시 발생 |

  - ```java
    try{
        //에러가 발생할 수 있는 코드
        throw new Exception(); //강제 에러 출력 
    }catch (Exception e){
        //에러시 수행
         e.printStackTrace(); //오류 출력(방법은 여러가지)
         throw e; //최상위 클래스가 아니라면 무조건 던져줘야 Main에서 예외를 인지시킬 수 있음
    }finally{
        //무조건 수행, 생략 가능
    } 
    ```

- **throw와 throws의 차이**

  - throw : `억지로 에러를 발생시키고자 할 때 사용되기도 하고 현재 메소드의 에러를 처리한 후에 상위 메소드에 에러 정보를 줌으로써 상위 메서드에서도 에러가 발생한 것을 감지할 수 있다.`
    즉, throw는 개발자가 exception을 강제로 발생시켜 메서드 내에서 예외처리를 수행하는 것이다.

  - throws : `현재 메서드에서 자신을 호출한 상위 메서드로 Exception을 발생 시킨다.`
    즉, throws 키워드는 사용하는 메서드를 호출한 상위 메서드에서 이러한 에러 처리에 대한 책임을 맡게 되는 것이다.

    > 예외를 전가시키는 것( 예외를 자신이 처리하지 않고, 자신을 호출하는 메소드에게 책임을 전가하는 것)

  - 예시

    - ```java
      public class Main{
          public static void main(String[] args){
              try{
                  onPower(false); //1번.
              }
              catch (CheckOnException e){ //5번 전달받은 예외 처리
                  System.out.print("전원을 키기를 실패했습니다.");
              }
          }
      
          //4번. throws 키워드를 통해 3번에서 전달한 exception 정보를 main으로 전달
          public static void onPower(boolean push) throws CheckOnException{
              try{
                  if(push)    System.out.print("전원 On");
                  else throw new CheckOnException(); //2번. 예외 발생 catch 이동
              }
              catch(CheckOnException e){
                  System.out.print("전원 On 실패, CheckOnException이 onPower()에서 발생");
                  throw e; //3번. main에 error를 전달
              }
          }
      }
      ```

    

---



## ☝String, StringBuilder, StringBuffer

String 객체는 immutable. 즉, 한번 생성이 되면 변경이 불가능하다.

예를 들면 String 2개를 연결하는 작업을 할 때에 새로운 String을 객체를 이용하여 문자열을 참조하게 됩니다.

StringBuilder와 StringBuffer의 차이점은 멀티쓰레드 상태에서 동기화의 지원 여부가 다르다.

StringBuffer은 멀티쓰레드 환경에서 동기화를 보장하지만 StringBuilder은 동기화를 보장하지 않는다.

- JDK 1.5버전 이하에서는 String을 사용할때 StringBuilder와 성능 차이가 있었지만 1.5버전 이후부터는 String을 컴파일 할때 자동적으로 StringBuilder로 컴파일 하여 실행되므로 성능 차이가 사라졌다고 한다.

---



## ☝Interface, Abstract class

- **Interface**

  상수 필드와 메소드 프로토타입만 가지는 틀로, 공통된 기능을 사용하기 위한 규격(implements로 구현)

- **Abstract** class

  하나 이상의 추상 메소드를 포함하고 있는 클래스로, 기능의 이용/확장을 위한 클래스 (extends로 구현)

---



## ☝Java Thread

일반 스레드와 거의 차이가 없으며, JVM이 운영체제의 역할

자바에는 프로세스가 존재하지 않고 스레드만 존재

스레드 스케줄링은 전적으로 JVM에 의해 이루어짐

- Thread class 상속
- Runnable Interface 상속

---



## ☝Java Thread의 Synchroized

멀티 스레드간의 처리 순서와 접근 제어를 위한 키워드

변수, 메소드에 Synchronized 키워드를 사용한다.

즉, 로킹 단위에 따라 병행성이 틀려서 융통성있게 로킹을 고려해야한다.

---



## ☝Serializable과 Parcelable

Serializable은 자바 표준 인터페이스로 객체를 다른 액티비티, 시스템으로 전송하기 위해서 바이트 단위로 변환하여 전송하는 도구

Parcelable도 Serializable과 같은 동작을 하지만 자바 표준 인터페이스가 아닌 안드로이드 SDK 인터페이스

**차이점**

 Serializable은 내부에서 Reflection 을 사용하여 직렬화를 하게 되는데, 이를 통해서 많은 추가 객체들이 생성이 된다. 처리 후 많은 객체들이 가비지 객체가 되고 가비지 콜렉션이 이를 수거하는 동작이 필요해서 성능 저하를 야기할 수 있다.

반면 Parcelable은 Reflection 을 사용하지 않기 때문에 성능 저하를 피해갈 수 있지만, 이러한 처리 코드를 개발자가 직접 오버라이드하여 명시해야하기 때문에 보일러 플레이트 코드가 발생하게 된다.

---



## ☝JDK, JRE

- **JDK(Java Development Kit)**
  - JDK는 개발을 위해 필요한 도구(javac, java등)들을 포함한다.
  - JDK를 설치하면 JRE도 같이 설치가 된다.
  - 즉 **JDK = JRE + @** 라고 생각하면 된다.
- **JRE(Java Runtime Environment)**
  - JRE는 JVM이 자바 프로그램을 동작시킬 때 필요한 라이브러리 파일들과 기타 파일들을 가지고 있다.
  - JRE는 JVM의 실행환경을 구현했다고 할 수 있다.
  - 자바 프로그램을 **실행**시키기 위해선 JRE를 반드시 설치해야한다.
  - 하지만 **자바 프로그래밍 도구**는 포함되어있지 않기 때문에 **자바 프로그래밍**을 하기 위해선 JDK가 필요하다.

---



## ☝Reflection

리플렉션은 생성된 객체로부터 클래스의 정보를 분석해 내는 프로그램 기법을 말한다.

이를 통해 실행중인 객체 내부를 검사하고 내부의 속성을 수정할 수 있도록 한다.

직렬화에도 사용되며 스프링의 의존성 주입에도 사용된다.

구체적인 클래스 타입을 알지 못해도, 그 클래스의 메소드, 타입, 변수들에 접근할 수 있도록 해주는 자바 API

리플렉션은 애플리케이션 개발에서보다는 프레임워크, 라이브러리에서 많이 사용된다.

프레임워크, 라이브러리는 사용하는 사람이 어떤 클래스를 만들지 모른다. 이럴 때 동적으로 해결해주기 위해서 리플렉션을 사용한다.

대표적인 사용 예로는 스프링의 DI(dpendency injection), Proxy, ModelMapper 등

```java
@Controller
@RequestMapping("/articles")
public class ArticleController {    

    @Autowired    
    private ArticleService articleService;       
       ....

    @PostMapping
    public String write(UserSession userSession, ArticleDto.Request articleDto){
       ...
    }

    @GetMapping("/{id}")
    public String show(@PathVariable int id, Model model) {
       ...
    }
}
```

스프링을 사용할 때 `@Controller` 를 넣어주면 인스턴스를 생성 하지 않아도 스프링이 알아서 생성해서 빈으로 관리해준다.

- 스프링은 `ArticleController` 클래스의 존재를 어떻게 알고 만들어주는 것일까?
- `ArticleService` 라는 필드는 어떻게 주입해주는 걸까?
- 모든 메소드의 파라미터 개수, 타입이 다른데 어떻게 알고 해당하는 값을 바인딩 해줄까?

`ArticleController`을 작성한 개발자는 클래스의 정보를 알겠지만, 스프링은 모른다.

이 문제를 해결하기 위해서 리플렉션을 사용한다. (스프링이 ArticleController의 정보를 알아내기 위해서)

대략 흐름을 보자면

- `@Controller` 를 갖고있는 클래스를 스캔
- 해당하는 클래스의 인스턴스 생성 및 필드 DI

---



## ☝자바에서 클래스 다중 상속 불가능한 이유

다중 상속에는 여러가지 문제가 내재되어 있다.

예를 들어 변수명 충돌이나 중복된 클래스 상속으로 인해 오버라이딩이 모호한 다이아몬드 문제가 대표적이다.