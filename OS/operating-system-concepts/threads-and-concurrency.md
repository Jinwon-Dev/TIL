> **현대 운영체제는 한 프로세스가 다중 스레드를 포함하는 특성을 제공한다.**

→ 다중 CPU를 제공하는 최신 다중 코어 시스템에서, **스레드 사용을 통한 병렬 처리의 기회를 식별하는 것**이 중요하다.

---

## 1. 개요

→ ***스레드는 CPU 이용의 기본 단위이다.***

- 스레드 ID, 프로그램 카운터, 레지스터 집합, 스택으로 구성된다.
    - 스레드는 **같은 프로세스에 속한 다른 스레드와 운영체제 자원들을 공유**한다.

</br>

<img width="489" alt="image" src="https://user-images.githubusercontent.com/106216912/210487126-fba2b150-aafc-41ff-bb87-a7c403c2f905.png">

- 프로세스가 다수의 제어 스레드를 갖는다면, **프로세스는 동시에 하나 이상의 작업을 수행**할 수 있다.
    - **단일 스레드 프로세스**
    - **다중 스레드 프로세스**

</br>

### 동기

→ ***현대의 컴퓨터와 모바일 기기에서 작동하는 소프트웨어 응용들은 다중 스레드를 이용한다.***

- 하나의 응용은 몇 개의 실행 흐름을 가진 독립적인 프로세스로 구현된다.
    - ex) 웹 브라우저는 하나의 스레드가 이미지를 표시하고, 다른 스레드는 데이터 검색을 할 수 있다.

</br>

> **응용은 다중 코어 시스템에서 처리 능력을 향상시키도록 설계될 수 있다.**

→ **다중 계산 코어를 사용해서 다수의 CPU-집중 작업을 병렬로 처리**할 수 있다.

</br>

- **하나의 응용 프로그램이 여러 개의 비슷한 작업을 수행할 필요가 있는 상황**이 있다.
    - ex) 웹 서버는 수천 개의 클라이언트들이 병행하게 접근한다.
        - 이 때, **웹 서버가 단일 스레드 프로세스로 작동한다면, 클라이언트들은 매우 긴 시간을 기다려야 한다.**

</br>

- **해결책** : 서버가 요청을 받아들이는 하나의 프로세스로 동작하게 하는 것이다.
    - 즉, 서비스 요청이 들어오면, 프로세스는 그 요청을 수행할 별도의 프로세스를 생성하는 것이다.

</br>

> **하지만 새 프로세스가 해야 할 일이 기존 프로세스와 동일하다면 왜 이런 오버헤드를 감수해야 할까?**

→ **그럴 바엔, 프로세스 안에 여러 스레드를 만들어 나가는 것이 효율적이다!**

<img width="486" alt="image" src="https://user-images.githubusercontent.com/106216912/210487279-52bf1eb1-c1cc-49f7-ba7b-eab0fc0eca2c.png">

</br>

- 대부분의 운영체제 커널도 일반적으로 다중 스레드이다.
    - 많은 응용 프로그램 또한, 기본 정렬, 트리 및 그래프 알고리즘을 포함하여 다중 스레드를 활용할 수 있다.

</br>

### 장점

→ ***다중 스레드 프로그래밍의 이점은 4가지 큰 부류로 나눌 수 있다.***

1. **응답성(responsiveness)**
    - 응용 프로그램의 일부분이 봉쇄되거나 긴 작업을 수행하더라도 프로그램이 계속되는 것을 허용한다.
        - **사용자에 대한 응답성을 증가**시킨다.
        - 사용자 인터페이스를 설계하는 데 있어 특히 유용하다.

</br>

2. **자원 공유(resouce sharing)**
    - 프로세스는 공유 메모리와 메시지 전달 기법을 통해야만 자원을 공유할 수 있다.
    - 하지만, **스레드는 자동으로 그들이 속한 프로세스의 자원들과 메모리를 공유**한다.

</br>

3. **경제성(economy)**
    - 프로세스 생성을 위해 메모리와 자원을 할당하는 것은 비용이 많이 든다.
    - 하지만, 스레드는 자신이 속한 프로세스의 자원들을 공유한다.
        - **스레드를 생성하고, 문맥 교환하는 것이 경제적**이다.

</br>

4. **규모 적응성(scalability)**
    - 다중 처리기 구조에서는 **각각의 스레드가 다른 처리기에서 병렬로 수행**될 수 있다.

---

## 2. 다중 코어 프로그래밍

→ ***컴퓨터 설계에서 단일 CPU 시스템은 다중 CPU 시스템으로 발전하였다.***

<img width="514" alt="image" src="https://user-images.githubusercontent.com/106216912/210490562-d9d4c94f-3b27-499e-90d4-b668132d8290.png">

- 현재의 추세는 단일 컴퓨팅 칩에 여러 컴퓨팅 코어를 배치하는 것이다.
    - **다중 코어 시스템** : 각 코어가 운영체제에 별도로 존재하는 시스템
    - 다중 스레드 프로그래밍은 **여러 컴퓨팅 코어를 효율적으로 사용하고 병행성을 향상시키는 기법을 제공**한다.

</br>

> **병행성과 병렬성의 차이점은?**

- **병행** : 모든 작업이 진행되게 하여 둘 이상의 작업을 지원한다.
- **병렬** : 둘 이상의 작업을 동시에 수행할 수 있다.

</br>

### 프로그래밍 도전과제

→ ***다중 코어가 발전함에 따라, 시스템 설계자뿐 아니라 응용 프로그래머도 다중 코어의 활용도를 높여야 한다.***

<img width="323" alt="image" src="https://user-images.githubusercontent.com/106216912/210490673-325a784e-c853-419b-a0cb-1ae3924e060b.png">

- **운영체제 설계자** : 병렬 수행이 될 수 있도록 여러 코어를 활용하는 스케줄링 알고리즘을 개발해야 한다.
- **응용 프로그래머** : 기존 프로그램을 다중 스레드를 사용하도록 수정하고, 새로운 다중 스레드 프로그램을 설계해야 한다.

</br>

> **다중 코어 시스템을 위해 프로그래밍하기 위한 5가지 극복해야 할 도전 과제**
> 
1. **태스크 인식(identifying tasks)**
    - 응용을 분석하여 독립된 병행 가능 태스크로 나눌 수 있는 영역을 찾는 작업이 필요하다.
        - 태스크는 서로 독립적이고, 개별 코어에서 병렬 실행될 수 있어야 한다.

</br>

2. **균형(balance)**
    - 병렬로 실행될 수 있는 태스크를 찾는 것도 중요하지만, 찾아진 부분들이 전체 작업에 균등한 기여도를 가지도록 태스크로 나누는 것도 중요하다.

</br>

3. **데이터 분리(data spliting)**
    - 응용이 독립된 태스크로 나누어지는 것처럼, 태스크가 접근하고 조작하는 데이터 또한 개별 코어에서 사용할 수 있도록 나누어져야 한다.

</br>

4. **데이터 종속성(data dependency)**
    - 태스크가 접근하는 데이터는 둘 이상의 태스크 사이에 종속성이 없는지 검토되어야 한다.

</br>

5. **시험 및 디버깅(testing and debugging)**
    - 프로그램이 다중 코어에서 병렬로 실행될 때, 다양한 실행 경로가 존재할 수 있다.
        - 병행 프로그램을 시험 및 디버깅 하는 것은, 단일 스레드 응용을 시험 및 디버깅하는 것보다 어렵다.

</br>

### 병렬 실행의 유형

→ ***일반적으로 데이터 병렬 실행, 태스크 병렬 실행의 두 가지 유형이 존재한다.***

<img width="389" alt="image" src="https://user-images.githubusercontent.com/106216912/210490831-a75615ca-b947-42c3-8a30-27df62b1aad3.png">

- **데이터 병렬 실행**
    - 동일한 데이터의 부분집합을 다수의 계산 코어에 분배한 뒤, 각 코어에서 동일한 연산을 실행한다.

</br>

- **태스크 병렬 실행**
    - 데이터가 아닌, 태스크(스레드)를 다수의 코어에 분배한다.
    - 각 스레드는 고유의 연산을 실행한다.
    - 스레드들은 동일한 데이터에 의해 연산을 할 수도 있고, 서로 다른 데이터에 의해 연산을 실행할 수도 있다.

→ **데이터와 태스크 병럴 처리는 상호 배타적이지 않으며, 두 가지 전략을 혼합하여 사용할 수 있다!**

---

## 3. 다중 스레드 모델

→ ***스레드를 위한 지원은 사용자 스레드(user threads)를 위해서는 사용자 수준에서, 또는 커널 스레드(kernel threads)를 위해서는 커널 수준에서 제공된다.***

- **사용자 스레드** : 커널 위에서 지원되며, 커널의 지원 없이 관리된다.
- **커널 스레드** : 운영체제에 의해 직접 지원되고 관리된다.

</br>

> **사용자 스레드와 커널 스레드는 어떤 연관 관계가 존재해야 한다.**

<img width="341" alt="image" src="https://user-images.githubusercontent.com/106216912/210952724-02fbeef5-eb76-486b-b327-9b15e6555135.png">


→ 연관 관계를 확립하는 **다대일, 일대일, 다대다 모델**을 알아보자!

</br>

### 다대일 모델(Many-to-One Model)

→ ***다대일 모델은 많은 사용자 수준 스레드를 하나의 커널 스레드로 사상한다.***

<img width="390" alt="image" src="https://user-images.githubusercontent.com/106216912/210952880-13ec3e98-92ae-44a9-8b34-da948658b051.png">

- **스레드 관리가 사용자 공간의 스레드 라이브러리에 의해 행해지므로, 효율적이다!**
    - 하지만, **한 스레드가 봉쇄형 시스템 콜을 할 경우, 전체 프로세스가 봉쇄**된다.

</br>

- 또한, **한 번에 하나의 스레드만이 커널에 접근할 수 있다.**
    - 따라서, **다중 스레드가 다중 코어 시스템에서 병렬로 실행될 수 없다.**

</br>

- 그린 스레드(green thread)가 다대일 모델을 사용하였다.
    - 그린 스레드 : Solaris 시스템을 위한 스레드 라이브러리

</br>

→ **최근에는 다중 처리 코어를 대부분 사용하며, 이 모델을 사용 중인 시스템은 거의 존재하지 않는다.**

</br>

### 일대일 모델(One-to-One Model)

→ ***일대일 모델은 각 사용자 스레드를 각각 하나의 커널 스레드로 사상한다.***

<img width="389" alt="image" src="https://user-images.githubusercontent.com/106216912/210953043-35ea709c-0327-4e06-9ea7-a75f461b55f5.png">

- **하나의 스레드가 봉쇄적 시스템 콜을 호출하더라도, 다른 스레드가 실행될 수 있다.**
    - 다대일 모델보다 **더 많은 병렬성을 제공**한다.
    - 다중 처리기에서 다중 스레드가 병렬로 수행되는 것을 허용한다.

</br>

- **일대일 모델의 단점**
    - 사용자 스레드를 만들려면 해당 커널 스레드를 만들어야 한다.
    - **많은 수의 커널 스레드가 시스템 성능에 부담**을 줄 수 있다.

</br>

→ **Linux는 Windows 운영체제 제품군과 함께 일대일 모델을 구현한다.**

</br>

### 다대다 모델(Many-to-Many Model)

→ ***다대다 모델은 여러 개의 사용자 수준 스레드를 그보다 작은 수, 혹은 같은 수의 커널 스레드로 멀티플렉스 한다.***

<img width="386" alt="image" src="https://user-images.githubusercontent.com/106216912/210953224-6a107546-8202-4bdd-9556-bd8e882079b3.png">

- 커널 스레드의 수는 응용 프로그램이나 특정 기계에 따라 결정된다.

</br>

> **이러한 설계가 병행 실행에 미치는 영향은?**

- 다대일 모델은 사용자 수준 스레드는 많이 생성할 수 있지만, **커널은 한 번에 하나의 커널 스레드만 스케줄 할 수 있다.**
- 일대일 모델은 더 많은 병행 실행이 가능하지만, **너무 많은 스레드를 생성하지 않도록 주의해야 한다.**
    
    → **다대다 모델은 이런 단점들을 어느 정도 해결했다!**

</br>

- 다대다 모델에서 개발자는 **필요한 만큼 사용자 수준 스레드를 생성**할 수 있다.
    - 또한, **상응하는 커널 스레드가 다중 처리기에서 병렬로 수행**될 수 있다.
    - 스레드가 봉쇄형 시스템 콜을 했을 때, 커널이 다른 스레드의 수행을 스케줄 할 수 있다.

</br>

> **두 수준 모델(two-level model)**

→ ***다대다 모델의 변형은 한 사용자 스레드가 하나의 커널 스레드에만 연관되는 것도 허용한다.***

<img width="390" alt="image" src="https://user-images.githubusercontent.com/106216912/210953371-d73133e4-df26-445e-854e-f1e77908b56f.png">

- 현재 논의된 모델 중 **가장 좋아보이지만, 구현하기 어렵다.**
    - 대부분의 운영체제는 일대일 모델을 사용한다.
    - 현대 병행 라이브러리는 개발자가 태스크를 식별하면, 다대다 모델을 사용하여 스레드에 매핑될 수 있게 한다.

---

## 4. 스레드 라이브러리

→ ***스레드 라이브러리는 프로그래머에게 스레드를 생성하고, 관리하기 위한 API를 제공한다.***

</br>

> **스레드 라이브러리를 구현하는 두 가지 방법**

1. **커널의 지원 없이, 완전히 사용자 공간에서만 라이브러리를 제공하는 것**
    - 라이브러리를 위한 모든 코드와 자료구조는 사용자 공간에 존재한다.
    - 라이브러리의 함수를 호출하면, 시스템 콜이 아닌 사용자 공간의 지역 함수를 호출하게 된다.

</br>

2. **운영체제에 의해 지원되는 커널 수준 라이브러리를 구현하는 것**
    - 라이브러리를 위한 코드와 자료구조는 커널 공간에 존재한다.
    - 라이브러리의 API를 호출하면, 커널 시스템 콜을 호출하는 것이다.

</br>

> **세 종류의 라이브러리 → POSIX Pthreads, Windows, Java**

- **Pthreads** : POSIX 표준안의 스레드 확장판으로, 사용자 또는 커널 수준 라이브러리로서 제공된다.
- **Windows 스레드 라이브러리** : Windows 시스템에서 사용 가능한 커널 수준 라이브러리이다.
- **Java 스레드 API** : Java에서 직접 스레드 생성과 관리가 가능하게 한다.

</br>

> **다수의 스레드를 생성하는 두 가지 일반적인 전략?**

- **비동기 스레딩**
    - **부모가 자식 스레드를 생성한 후, 부모는 자신의 실행을 재개**한다.
    - 부모와 자식 스레드가 서로 독립적으로 병행하게 실행된다.
    - 스레드 사이의 데이터 공유는 거의 없다.

</br>

- **동기 스레딩**
    - **부모 스레드가 자식 스레드를 생성하고, 자식 스레드 모두가 종료할 때까지 기다렸다가 자신의 실행을 재개**한다.
    - 부모는 자식들의 작업이 끝날 때까지 실행을 계속할 수 없다.
    - 스레드 사이의 상당한 양의 데이터 공유를 수반한다.

</br>

### Pthreads

→ ***Pthreads는 POSIX가 스레드 생성과 동기화를 위해 제정한 표준 API이다.***

- 스레드의 동작에 대한 **명세**일 뿐, 자체를 구현한 것은 아니다.
    - Linux와 macOS등 많은 시스템이 Pthreads 명세를 구현하고 있다.

</br>

> **음이 아닌 정수의 합을 구하는 다중 스레드 프로그램을 제작하기 위한 Pthreads API**

<img width="486" alt="image" src="https://user-images.githubusercontent.com/106216912/211146247-5abb407a-ec01-4c99-8ed9-bc8ebf876498.png">

</br>

- `pthread_join()` 함수를 사용하여 여러 개의 스레드를 기다리는 방법 : `for` 반복문으로 둘러싼다.

<img width="435" alt="image" src="https://user-images.githubusercontent.com/106216912/211146282-d4beb380-fab0-4c2b-935f-02173dd002b0.png">

</br>

### Windows 스레드

→ ***Windows 스레드 라이브러리는 많은 점에서 Pthreads 기법과 유사하다.***

</br>

> **Windows 스레드 API**

<img width="438" alt="image" src="https://user-images.githubusercontent.com/106216912/211146328-04b088ae-e56d-4e6c-bc79-ece6b8106ed8.png">

- `WaitForSingleObject()` : 합산 스레드가 종료할 때까지, 생성 스레드가 봉쇄되도록 한다.

</br>

- 여러 스레드의 종료를 기다려야 한다면, `WaitForMultipleObjects()` 함수가 사용된다.
    - 4개의 매개변수를 전달받는다.
    1. 기다려야 하는 객체의 개수
    2. 객체 배열을 가리키는 포인터
    3. 모든 객체가 신호를 보내왔는지를 나타내는 플래그
    4. 대기해야 하는 타임아웃 시간

</br>

### Java 스레드

→ ***스레드는 Java 프로그램의 실행의 근본적인 모델이고, Java와 API는 스레드의 생성과 관리를 지원하는 풍부한 특성을 제공한다.***

- 모든 Java 프로그램은 적어도 하나의 단일 제어 스레드를 포함한다.
    - `main()` 으로만 이루어진 단순한 프로그램조차, JVM 내의 하나의 단일 스레드로 수행된다.

</br>

- Java 스레드는 JVM을 제공하는 어떠한 시스템에서도 사용할 수 있다.
    - Windows, Linux, macOS 등

</br>

> **Java 프로그램에서 스레드를 명시적으로 생성하는 두 가지 기법**

1. `Thread` 클래스에서 파생된 새 클래스를 만들고, `run()` 메소드를 재정의 하는 것
2. `Runnable` 인터페이스를 구현하는 클래스를 정의하는 것

```java
class Task implements Runnable {
	public void run() {
		System.out.println("I am a thread.");
	}
}
```

</br>

- Java에서 스레드를 생성하려면, `Thread` 객체를 생성하고 `Runnable` 을 구현하는 클래스의 인스턴스를 전달한다.
    - 그 후, `Thread` 객체의 `start()` 메소드를 호출해야 한다.

```java
Thread worker = new Thread(new Task());
worker.start();
```

</br>

> **`Thread` 객체에 대해 `start()` 메소드를 호출하면 두 가지 작업이 수행된다.**
> 
1. 메모리가 할당되고, JVM 내에 새로운 스레드가 초기화된다.
2. `run()` 메소드를 호출하면 스레드가 JVM에 의해 수행될 자격을 갖게 한다.
    - 이 때, **`run()` 을 직접 호출하는 것이 아닌, `start()` 메소드를 호출한다!**

</br>

- Java의 `join()` 메소드는 부모 스레드가 각 스레드가 완료되기를 기다렸다가 계속 진행하게 해준다.

```java
try {
	worker.join();
} catch (InterruptedException ie) { }
```

</br>

> **Java Executor 프레임워크**

→ ***Java는 스레드 생성 및 통신에 대한 제어 기능을 크게 향상시키는 몇 가지 새로운 병행 처리 기능을 도입하였다.***

- `Thread` 객체를 명시적으로 생성하는 대신, `Executor` 인터페이스를 중심으로 스레드 생성을 구성한다.

```java
public interface Executor {
	void execute(Runnable command);
}
```

</br>

- 이 인터페이스를 구현하는 클래스는, `Runnable` 객체가 인자로 전달되는 `execute()` 메소드를 정의해야 한다.
    - 별도의 `Thread` 객체를 만들고 `start()` 메소드를 호출하는 대신, `Executor` 를 사용한다.

```java
Executor service = new Executor;
service.execute(new Task());
```

</br>

- `Executor` 프레임워크는 **생산자-소비자 모델**을 기반으로 한다.
    - **장점**
        - 스레드 생성을 실행에서 분리할 수 있고, 병행하게 실행되는 작업 간의 통신 기법을 제공한다.
        - 스레드 종료를 기다리는 대신, 부모는 결과가 가용해지는 것만 기다리면 된다.
        - 다른 기능과 결합하여 대량의 스레드를 관리하기 위한 강력한 도구를 만들 수 있다.

<img width="481" alt="image" src="https://user-images.githubusercontent.com/106216912/211146486-c49d519d-9d29-49cd-bc06-7905749624ff.png">

---

## 5. 암묵적 스레딩

→ ***수백 또는 수천 개의 스레드를 가진 응용을 설계하는 것은 쉬운 일이 아니다.***

- 따라서, **암묵적 스레딩**이라는 전략이 널리 사용되고 있다.
    - **암묵적 스레딩** : **스레딩의 생성과 관리 책임을 응용 개발자로부터 컴파일러와 실행시간 라이브러리에게 넘겨주는 것**

</br>

> **이번 절에서는 암묵적 스레딩을 이용하여 다중 코어 처리기를 활용할 수 있는 응용 프로그램을 설계하는 네 가지 접근법을 알아본다.**

- 이러한 전략은, 일반적으로 응용 프로그램 개발자가 병렬로 실행할 수 있는 스레드가 아닌 작업을 식별해야 한다.
    - 작업은 함수로 작성되며, 런타임 라이브러리는 다대다 모델을 사용한다.
    - 장점 : **개발자는 병렬 작업만 식별하면 되고, 라이브러리는 스레드 생성 및 관리에 대한 특정 세부 사항을 결정한다.**

</br>

### 스레드 풀

→ ***다중 스레드로 구성된 웹 서버는, 요청을 받을 때마다 그 요청을 위해 새로운 스레드를 만들어 준다.***

</br>

> **새로운 프로세스를 만들어 주는 것보다는 낫지만, 여러 문제를 가지고 있다.**

1. 서비스할 때마다 스레드를 생성하는 데 소요되는 시간
2. 시스템에서 동시에 실행할 수 있는 최대 스레드 수가 몇 개까지 가능할 것인지 한계를 정해야 한다.
    - 스레드를 무한정 만들면, CPU 시간, 메모리 공간 같은 시스템 자원이 언젠가는 고갈된다.

</br>

→ **이러한 문제를 해결해 줄 수 있는 방법의 하나가 스레드 풀(pool)이다!**

</br>

> **스레드 풀의 기본 아이디어는 프로세스를 시작할 때 아예 일정한 수의 스레드들을 미리 풀로 만들어두는 것이다.**

- 이 스레드들은 평소에는 하는 일 없이 작업을 기다리게 된다.
- 서버는 **스레드를 생성하지 않고, 요청을 받으면 스레드 풀에 제출하고, 추가 요청 대기를 재개**한다.
    - 풀에 사용 가능한 스레드가 있으면 깨어나고, 요청이 즉시 서비스된다.
    - 풀에 사용 가능한 스레드가 없다면, 사용 가능한 스레드가 생길 때까지 작업이 대기된다.
- 스레드가 서비스를 완료하면 풀로 돌아가서 다른 작업을 기다린다.

</br>

> **스레드 풀의 장점**

1. 새 스레드를 만들어 주는 것보다, **기존 스레드로 서비스해 주는 것이 더 빠르다.**
2. 스레드 풀은 **임의 시각에 존재할 스레드 개수에 제한**을 둔다.
    - 제한은 많은 수의 스레드를 병렬 처리할 수 없는 시스템에 도움이 된다.
3. **태스크를 생성하는 방법을 태스크로부터 분리**하면, 태스크의 실행을 다르게 할 수 있다.

</br>

- 스레드 풀에 있는 스레드의 개수는 CPU 수, 물리 메모리 용량, 동시 요청 클라이언트 최대 개수 등을 고려하여 정해질 수 있다.
    - 시스템 부하가 적을 때는 더 작은 풀을 유지하도록 함으로써, 메모리 등의 소모를 더 줄일 수 있다.

</br>

> **Windows API는 스레드 풀과 관련된 여러 함수를 제공한다.**
> 

```c
DWORD WINAPI PoolFunction(PVOID Param) {
	...
}
```

- `PoolFunction()` 을 가리키는 포인터가 스레드 풀 API 중 하나의 함수에 전달되고, 풀 중의 한 스레드가 이 함수를 실행한다.

</br>

- 스레드 풀 API 중 한 함수가 `QueueUserWorkItem()` 함수이고, 세 가지 매개 변수를 전달받는다.
    - `LPTHREAD_START_ROUTINE Function` : 별도의 스레드가 실행할 함수에 대한 포인터
    - `PVOID Param` : `Function` 에 전달될 매개변수
    - `ULONG Flags` : 스레드 풀이 스레드를 생성하고 관리하는 방법을 가리키는 플래그

</br>

> **Java 스레드 풀**

→ ***`java.util.concurrent` 패키지에는 여러 종류의 스레드 풀 구조에 대한 API가 있다.***

1. 단일 스레드 `Executor` , `newSingleThreadExecutor()` 는 크기가 1인 풀을 생성한다.
2. 고정 스레드 `Executor` , `newFixedThreadPool(int size)` 는 지정된 수의 스레드가 있는 스레드 풀을 생성한다.
3. 캐시 스레드 `Executor` , `newCachedThreadPool()` 는 많은 경우 스레드를 재사용하는 무제한 스레드 풀을 생성한다.

</br>

- `Executors` 클래스의 기본 메소드 중 하나를 사용하여 스레드 풀이 생성된다.
    - `static ExecutorService newSingleThreadExecutor()`
    - `static ExecutorService newFixedThreadPool(int size)`
    - `static ExecutorService newCachedThreadPool()`

</br>

### Fork Join

→ ***Fork Join 모델을 사용하면, 메인 부모 스레드가 하나 이상의 자식 스레드를 생성(fork)한 다음, 자식의 종료를 기다린 후 join하고, 그 시점부터 자식의 결과를 확인하고 결합할 수 있다.***

- 암시적 스레딩에서, fork 단계에서는 스레드가 직접 구축되지 않고 병렬 작업이 식별된다.
- 라이브러리는 생성되는 스레드 수를 관리하며, 스레드에 작업 배정을 책임진다.

<img width="529" alt="image" src="https://user-images.githubusercontent.com/106216912/211155637-51e7e759-3c2b-4bbf-9f1d-2a0de0bd6105.png">

</br>

> **Java에서의 Fork Join**

→ ***Java는 재귀 분할-정복 알고리즘과 함께 사용되도록 설계된 API에 fork join 라이브러리를 도입하였다.***

<img width="384" alt="image" src="https://user-images.githubusercontent.com/106216912/211155681-2eb78f63-6060-439b-9e9c-04ae09fe3407.png">

- 이 라이브러리를 사용하여 분할-정복 알고리즘을 구현할 때, 분할 단계 동안 별도의 작업이 fork되고 원래 문제의 작은 부분집합이 할당된다.
    - 작업에 할당된 문제의 크기는 직접 해결할 수 있을 정도로 작아서, 추가 작업을 만들지 않아도 된다.

</br>

- **Java fork-join 모델의 일반적인 재귀 알고리즘**

<img width="390" alt="image" src="https://user-images.githubusercontent.com/106216912/211155717-4ce83659-1486-4fb1-9773-c089970cd2df.png">

</br>

- Java는 새로운 기본 풀인 `ForkJoinPool` 을 도입하여, 추상 기본 클래스 `ForkJoinTask` 를 상속하는 작업을 배정받을 수 있다.
    - 다음 코드는 `ForkJoinPool` 객체를 만들고, `invoke()` 메소드를 통해 초기 작업을 제출한다.

<img width="344" alt="image" src="https://user-images.githubusercontent.com/106216912/211155733-a04fe284-684b-49c9-b5e1-fb6dc062634e.png">

</br>

- **fork-join을 사용하여 배열의 내용을 합산하는 분할-정복 알고리즘**

<img width="437" alt="image" src="https://user-images.githubusercontent.com/106216912/211155752-806f13de-8963-493d-ae0f-745c3670b55f.png">

- 추상 기본 클래스 `ForkJoinTask` 를 중심으로 구성되며, `RecursiveTask` 및 `RecursiveAction` 클래스는 이 클래스를 확장한다.
    - `RecursiveTask` : 결과를 반환한다.
    - `RecursiveAction` : 결과를 반환하지 않는다.

<img width="381" alt="image" src="https://user-images.githubusercontent.com/106216912/211155774-b35d49ac-f317-49c1-a3ae-acb41bf16241.png">

</br>

→ **고려해야 할 중요한 쟁점** : 문제가 직접 해결할 만큼 “충분히 작은” 크기여서 더 이상 추가 작업을 만들 필요가 없는 때가 언제인지 결정하는 것

</br>

- Java의 fork-join 모델에서 흥미로운 점?
    - 라이브러리가 작업자 스레드 풀을 생성하고 사용 가능한 작업자 간 부하의 균형을 조정하는 작업 관리

</br>

### OpenMP

→ ***OpenMP는 C, C++, FORTRAN으로 작성된 API와 컴파일러 디렉티브의 집합이다.***

- OpenMP는 공유 메모리 환경에서 병렬 프로그래밍을 할 수 있도록 도움을 준다.
    - **병렬 영역** : 병렬로 실행될 수 있는 블록

</br>

- 응용 개발자는 자신들의 코드 중, 병렬 영역에 컴파일러 디렉티브를 삽입한다.
    - 이 디렉티브는 OpenMP 실행시간 라이브러리에 해당 영역을 병렬로 실행하도록 지시한다.

</br>

> **`printf()` 문을 포함하고 있는 병렬 영역 위에, 컴파일러 디렉티브가 사용된다.**

<img width="297" alt="image" src="https://user-images.githubusercontent.com/106216912/211155847-dc4ff357-5586-4dbe-b379-2fcdb5fc44e0.png">

- OpenMP가 컴파일러 디렉티브를 만나게 되면 시스템의 코어 개수만큼 스레드를 생성한다.
    - 모든 스레드는 동시에 병렬 영역을 실행하고, 각 스레드가 병렬 영역을 빠져나가면 스레드는 종료된다.

</br>

> **OpenMP는 병렬 처리 반복문 등을 포함하여 코드 영역을 실행하기 위한 추가적인 디렉티브를 제공한다.**
> 
- 병렬화를 위한 디렉티브를 제공할 뿐만 아니라, 개발자가 병렬화 수준을 선택할 수 있게 한다.

</br>

### Grand Central Dispatch

→ ***Grand Central Dispatch(GCD)는 macOS 및 iOS 운영체제를 위해 Apple에서 개발한 기술이다.***

- 개발자가 병렬로 실행될 코드 섹션을 식별할 수 있도록 하는 **런타임 라이브러리, API 및 언어 확장의 조합**이다.
    - 스레딩에 대한 대부분의 세부 사항을 관리한다.

</br>

> **GCD는 실행시간 수행을 위해 태스크를 디스패치 큐에 넣어서 스케줄 한다.**

→ **직렬(serial)과 병행(concurrent)의 두 가지 유형의 디스패치 큐를 유지한다.**

- **직렬 큐**
    - 직렬 큐에 넣어진 태스크는 FIFO 순서대로 제거된다.
    - 개발자는 특정 프로세스에 로컬인 추가 직렬 큐를 만들 수 있다.
    - 여러 작업을 순차적으로 실행하는 데 유용하다.

</br>
    
- **병행 큐**
    - 태스크가 FIFO 순서로 제거되지만, 한 번에 여러 태스크가 제거되어 병렬로 실행될 수 있다.
    - 다수의 시스템 전체의 병행 큐가 존재하며, 네 가지 주요 서비스 품질 클래스로 나뉜다.
        - QOS_CLASS_USER_INTERACTIVE : 사용자 대화형 클래스
        - QOS_CLASS_USER_INITIATED : 사용자 시작 클래스
        - QOS_CLASS_UTILITY : 유틸리티 클래스
        - QOS_CLASS_BACKGROUND : 백그라운드 클래스

</br>

→ 내부적으로 GCD의 스레드 풀은 POSIX 스레드로 구성된다.

</br>

### Intel 스레드 빌딩 블록

→ ***Intel TBB는 C++에서 병렬 응용 프로그램 설계를 지원하는 템플릿 라이브러리이다.***

- 라이브러리이므로, 특별한 컴파일러나 언어 지원이 필요하지 않다.
    - 개발자는 병렬로 실행할 수 있는 태스크를 지정하고, TBB 태스크 스케줄러는 태스크를 하부 스레드에 매핑한다.
    - 태스크 스케줄러는 부하 균형 기능을 제공하고, 캐시를 인지한다.
        - 캐시를 인지한다. = 캐시 메모리에 데이터가 저장되어, 보다 빠르게 실행되는 태스크에 우선순위를 부여한다.

</br>

> **TBB는 병렬 루프 구조, 원자적 연산 및 상호 배제 잠금을 위한 템플릿을 포함하여 다양한 기능을 제공한다.**

- TBB 라이브러리는 루프 반복을 개별적인 “청크”로 나누고, 해당 청크에 대해 연산을 수행하는 많은 태스크를 만든다.
    - 또한, 여러 스레드를 생성하고 사용 가능한 스레드에 태스크를 배정한다.
    - 장점 : **개발자는 병렬로 실행할 수 있는 작업을 식별만 하고, 라이브러리가 작업을 병렬로 실행되는 개별적인 태스크로 나누는 데 필요한 상세사항만 관리**한다.

---

## 6. 스레드와 관련된 문제들

→ ***다중 스레드 프로그램을 설계할 때 고려해야 할 몇 가지 문제들을 알아본다.***

</br>

### `Fork()` 및 `Exec()` 시스템 콜

→ ***다중 스레드 프로그램에서는 `fork()` 와 `exec()` 의 의미가 달라질 수 있다.***

- 한 프로그램의 스레드가 `fork()` 를 호출하면, 새로운 프로세스는 모든 스레드를 복제해야 할까 아니면 한 개의 스레드만 가지는 프로세스여야 할까?
    - 몇몇 UNIX 기종은 이 두 가지 버전 `fork()` 를 다 제공한다.

</br>

- 어떤 스레드가 `exec()` 시스템 콜을 부르면, `exec()` 의 매개변수로 지정된 프로그램이 모든 스레드를 포함한 전체 프로세스를 대체시킨다.
    - **`fork()` 를 부르자마자 다시 `exec()` 를 부른다면, 모든 스레드를 다 복제해서 만들어주는 것은 불필요하다.**
        - `exec()` 에서 지정한 프로그램이 모든 것을 다시 대체하기 때문이다.
    - **반대로, 새 프로세스가 `fork()` 후 `exec()` 를 하지 않는다면, 새 프로세스는 모든 스레드를 복제해야 한다.**

</br>

### 신호 처리

→ ***신호는 UNIX에서 프로세스에 어떤 이벤트가 일어났음을 알려주기 위해 사용된다.***

- **신호는 알려줄 이벤트의 근원지나 이유에 따라 동기식, 또는 비동기 식으로 전달**될 수 있다.
    - 신호는 특정 이벤트가 일어나야 생성된다.
    - 생성된 신호가 프로세스에 전달된다.
    - 신호가 전달되면 반드시 처리되어야 한다.

</br>

- 동기식 신호는 **신호를 발생시킨 연산을 수행한 동일한 프로세스에 전달**된다.
    - 비동기식 신호는 통상 **다른 프로세스에 전달**된다.

</br>

> **모든 신호는 둘 중 하나의 처리기에 의해 처리된다.**

1. **디폴트 신호 처리기** : 모든 신호마다 커널이 실행시킨다.
2. **사용자 정의 신호 처리기** : 신호를 처리하기 위하여 호출되며, 디폴트 처리기를 대체할 수 있다.

</br>

> **단일 스레드 프로그램에서의 신호 처리는 간단하다.**

- **신호는 항상 프로세스에 전달**된다.

</br>

> **다중 스레드 프로그램에서의 신호 처리는 복잡하다.**

- **어느 스레드에 신호를 전달해야 하는가?**
    1. 신호가 적용될 스레드에게 전달한다.
    2. 모든 스레드에 전달한다.
    3. 몇몇 스레드들에만 선택적으로 전달한다.
    4. 특정 스레드가 모든 신호를 전달받도록 지정한다.

</br>

- 신호를 전달하는 방법은 **신호의 유형**에 따라 다르다.
    - **동기식 신호** : 그 신호를 야기한 스레드에게 전달되어야 하고, 다른 스레드에 전달되면 안 된다.
    - **비동기식 신호** : 명확하지 않거나, 프로세스 내 모든 스레드에 전달되어야 한다.

</br>

- 신호를 전달하는 표준 UNIX 함수

```bash
kill(pid_t pid, int signal)
```

</br>

- POSIX Pthreads는 지정된 스레드에만 전달이 되도록 허용하는 다음과 같은 함수를 제공한다.

```bash
pthread_kill(pthread_t tid, int signal)
```

</br>

- Windows는 신호를 명시적으로 지원하지 않고, **비동기식 프로시저 호출(APC)** 이라는 것을 사용해서, 이를 대리 실행할 수 있다.
    - 사용자 스레드들이 특정 이벤트의 발생을 전달받았을 때 호출될 함수를 지정할 수 있게 한다.

</br>

### 스레드 취소

→ ***스레드 취소는 스레드가 끝나기 전에 강제 종료시키는 작업을 말한다.***

- **목적 스레드**는 취소되어야 할 스레드이고, 취소는 두 가지 방식으로 발생할 수 있다.
    - **비동기식 취소** : 한 스레드가 즉시 목적 스레드를 강제 종료시킨다.
    - **지연 취소** : 목적 스레드가 주기적으로 자신이 강제 종료되어야 할지를 점검한다.

</br>

> **취소 스레드에 할당된 자원 문제가 발생한다.**

- 또한, **스레드가 다른 스레드와 공유하는 자료구조를 갱신하는 도중에 취소 요청이 와도 문제**가 된다.
    - 비동기식 취소인 경우 심각하다.
    - **필요한 시스템 자원을 다 사용 가능한 상태로 만들지 못할 수도 있다.**

</br>

- 지연 취소의 경우에는, 한 스레드가 목적 스레드를 취소해야 한다고 표시하지만, 실제 취소는 목적 스레드가 최소 여부를 결정하기 위한 플래그를 검사한 이후에 일어난다.
    - 스레드는 자신이 취소되어도 안전하다고 판단되는 시점에서 취소 여부를 검사할 수 있다.

</br>

- Pthreads에서는 `pthread_cancel()` 함수를 사용하여 스레드를 취소할 수 있다.

<img width="292" alt="image" src="https://user-images.githubusercontent.com/106216912/211159004-1ec2a33c-8cc0-424f-b62c-1f0e79697cca.png">

</br>

- Pthreads는 세 가지 취소 모드를 지원한다.

<img width="391" alt="image" src="https://user-images.githubusercontent.com/106216912/211159016-90bb1f5f-dbdd-4fd6-b7e4-6c5df5c7ebd0.png">

</br>

> **기본 취소 유형은 지연 취소로, 스레드가 취소 점에 도달한 경우에만 취소가 발생한다.**

- `pthread_testcancel()` 함수를 호출하여 **취소 점**을 설정할 수 있다.
- 또한, Pthreads는 스레드가 취소될 때 **정리 핸들러**라고 하는 함수가 호출되게 할 수 있다.
    - 스레드가 종료되기 전에 스레드가 획득한 모든 자원을 해제할 수 있다.

</br>

- 스레드가 취소 요청에 대해 지연 취소를 사용하여 응답하는 방법

<img width="392" alt="image" src="https://user-images.githubusercontent.com/106216912/211159040-a603b2f1-5b25-4831-819c-0aee0c435083.png">

→ Pthreads 에서는 비동기 취소를 권장하지 않는다.

</br>

> **Java의 스레드 취소**
> 
- Pthread의 지연 취소와 유사한 정책을 사용한다.
- `interrupt()` 메소드를 호출하여 대상 스레드의 인터럽트 상태를 `true` 로 설정한다.

<img width="386" alt="image" src="https://user-images.githubusercontent.com/106216912/211159064-819181b4-ebd8-4b43-9b93-1eda36e03c34.png">

</br>

- 스레드는 자신의 인터럽트 상태를 `isInterrupted()` 메소드를 호출하여 확인할 수 있다.

<img width="388" alt="image" src="https://user-images.githubusercontent.com/106216912/211159079-aaf78ecd-c82c-4400-9db6-3fdb1ff04af8.png">

</br>

### 스레드-로컬 저장장치

→ ***한 프로세스에 속한 스레드들은 그 프로세스의 데이터를 모두 공유한다.***

- 하지만 상황에 따라서는, **각 스레드가 자기만 액세스할 수 있는 데이터를 가져야 할 필요도 있다.**
    
    → **스레드-로컬 저장장치(TLS)**

</br>

- ex) 트랜잭션 처리 시스템에서 각 트랜잭션을 독립된 스레드가 처리해 준다고 가정한다.
    - 이 때, 스레드마다 고유한 식별자를 연관시키기 위해서는 스레드 국지 저장소가 있어야 한다.

</br>

- **지역 변수** : 하나의 함수가 호출되는 동안에만 보인다.
- **TLS** : 전체 함수 호출에 걸쳐 보인다.

</br>

- TLS는 정적 데이터와 유사하지만, 차이점은 **TLS 데이터는 스레드마다 고유하다.**
    - 대부분의 스레드 라이브러리 및 컴파일러는 TLS를 지원한다.

</br>

### 스케줄러 액티베이션

→ ***다대다 및 두 수준 모델에서 반드시 해결해야 할 문제로, 스레드 라이브러리와 커널의 통신 문제가 있다.***

- 응용 프로그램이 최고의 성능을 보이도록 보장하기 위해서 커널 스레드의 수를 동적으로 조절하는 것을 가능하게 한다.

</br>

- **다대다 또는 두 수준 모델을 구현하는 많은 시스템은 사용자와 커널 스레드 사이에 중간 자료구조를 둔다.**
    - 중간 자료 구조 : **LWP(경량 프로세스)**

<img width="255" alt="image" src="https://user-images.githubusercontent.com/106216912/211159127-fe668a6c-c511-467f-8a81-ec481923b913.png">

</br>

- 각 LWP는 하나의 커널 스레드에 부속되어 있으며, 물리 처리기에서 스케줄 하는 대상은 바로 이 커널 스레드이다.
    - 커널 스레드가 봉새되면, LWP도 같이 봉쇄된다.

</br>

> **스케줄러 액티베이션**

→ ***사용자 스레드 라이브러리와 커널 스레드 간의 통신 방법***

- 커널은 응용에 가상 처리기(LWP)의 집합을 제공하고, 응용은 사용자 스레드를 가용한 가상 처리기로 스케줄 한다.
    - **Upcall** : **커널이 응용에게 특정 이벤트에 대해 알려주는 통신 프로시저**
    - 커널이 스레드가 봉쇄되었다는 것과 스레드의 식별자를 알려주는 upcall을 하면, upcall 처리기는 다른 실행 가능한 스레드를 스케줄 한다.

---

## 7. 운영체제 사례

→ ***Windows와 Linux 시스템에서 스레드를 어떻게 구현하는지 알아본다.***

</br>

### Windows 스레드

→ ***Windows 응용들은 프로세스 형태로 실행되며, 각 프로세스는 한 개 이상의 스레드를 가질 수 있다.***

- **일대일 대응**을 사용하며, 사용자 수준 스레드 하나마다 커널 스레드 하나가 대응된다.

- **스레드의 일반적인 구성 요소**
    - 각 스레드를 유일하게 지목하는 스레드 ID
    - 처리기의 상태를 나타내는 레지스터 집합
    - 프로그램 카운터
    - 사용자 모드에서 실행될 때 필요한 사용자 스택, 커널 모드에서 실행될 때 필요한 커널 스택
    - 실행 시간 라이브러리와 동적 링크 라이브러리(DLL) 등이 사용하는 개별 데이터 저장 영역

</br>

<img width="344" alt="image" src="https://user-images.githubusercontent.com/106216912/211159859-b8da03fc-e52a-4601-aac0-6334d93a2dbc.png">

- **스레드의 주요 자료구조**
    - **ETHREAD** : 실행 스레드 블록
    - **KTHREAD** : 커널 스레드 블록
    - **TEB** : 스레드 환경 블록

</br>

### Linux 스레드

→ ***프로세스를 복제하는 기능을 가진 `fork()` 시스템 콜을 제공한다.***

- **`clone()` 시스템 콜을 이용하여 스레드를 생성할 수 있는 기능**도 제공한다.
    - Linux는 프로세스와 스레드를 구별하지 않는다.

</br>

> **`clone()` 이 호출될 때, 부모와 자식 태스크가 자료구조를 얼마나 공유할지 결정하는 플래그의 집합이 전달된다.**

<img width="342" alt="image" src="https://user-images.githubusercontent.com/106216912/211159902-5dfb936c-545c-4367-b764-6abad948d8db.png">

</br>

> **Linux 커널이 태스크를 표현하는 방식 때문에, 다양한 공유 수준이 가능하다.**

- 시스템의 태스크마다 고유한 커널 자료구조가 존재한다.

</br>

> **`clone()` 시스템 콜의 융통성은 컨테이너 개념으로 확장될 수 있다.**

- 운영체제가 제공하는 가상화 기법으로, **하나의 Linux 커널 아래 서로 격리되어 실행되는 여러 개의 Linux 시스템을 생성하는 것**을 가능하게 한다.