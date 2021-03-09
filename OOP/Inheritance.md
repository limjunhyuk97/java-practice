# Inheritance (상속)

  - 프로그램의 코드 재사용성을 높여준다. (유지보수, 프로그램의 확장성을 높여준다.)

  |상위 클래스|하위 클래스|
  |:---:|:---:|
  |상속된 클래스|상속한 클래스|
  |기초(base) 클래스|유도(derived) 클래스|
  |슈퍼(super) 클래스|서브(sub) 클래스|
  |부모(parent) 클래스|자식(child) 클래스|

## Class Inheritance (클래스 상속) 

  - 상속 시에, **여러 개의 부모 클래스를 상속할 수는 없다**
  - 상속 시에, **access modifier에 의해서 접근이 제한된다.**
  
## 생성자 호출 관계
  
  - 유도 클래스에 의해 **인스턴스가 생성될 때, 부모 클래스의 생성자가 호출(부모 인스턴스 생성)되고 -> 자식 클래스의 생성자가 호출**된다.
    - **super( 매개인자, 매개인자, ,,,)**
      - 부모 클래스의 생성자를 불러온다.
      - super에 전달되는 매개인자의 종류와 갯수, 타입과 일치하는 부모 클래스의 생성자를 불러온다.
    
```java
// A package의 parent class
package A;

public class parent{

  public parent() {}
  // 기본생성자
  
}

// A package의 child class
package A;

public class child extends parent{

  public child() { super(); }
  // 기본 생성자
  
}

// 자식 인스턴스 생성 시에, 부모 인스턴스도 같이 생기기에, 생성자의 호출이 맞물려 있는 것이므로..!
// 자식 기본 생성자 -> 부모 기본생성자 있어야 함
// 자식 생성자 -> super() 사용안하면, 부모 기본생성자 있어야 함
// 자식 생성자 -> super() 사용하면, 부모 기본생성자 없어도 됨

```

## 메소드 재정의

  - **부모 클래스에 존재하는 메소드를, 시그니처는 똑같이 유지한 채 내용 바꿈 가능.** (메소드 재정의, 내용의 재정의)
  - 조건 (3)
    - 부모 메소드와 동일한 시그니처여야 함. (리턴값, 함수명, 매개인자의 갯수, 자료형, 순서가 같아야 함)
    - 접근 제한 조건을 더 강하게 걸 수 없다. / 접근 제한 조건을 완화할 수는 있다. (cannot reduce the visibility.. 컴파일 오류 발생)
      - public -> protected, private X
      - private -> public O
    - 새로운 예외(exception)를 throw할 수는 없다.

```java

package A;

public class A{
  
  public void foo1(){
    
  }
  
  public final void foo2() {
  
  }
  
}

```











