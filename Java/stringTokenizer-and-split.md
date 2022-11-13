# StringTokenizer와 split()

</br>

## Java에서는 문자열이 특정 구분자로 연결되어 있을 경우, 구분자를 기준으로 문자열을 분리하기 위한 기능을 제공한다.
1. `java.util` 패키지의 StringTokenizer
2. `String` 의 split() 메소드

</br>

### StringTokenizer
- 문자열을 구분자를 이용하여 분리할 때 사용할 수 있다.
- **문자/문자열**로 문자열을 구분한다.
- 공백 문자열은 포함하지 않는다.

</br>

### StringTokenizer 사용법
```Java
StringTokenizer st = new StringTokenizer("문자열");	// 스페이스, 탭, 줄바꿈, 캐리지 리턴 등 기본 구분자 기준으로 문자열 분리
```

```Java
StringTokenizer st = new StringTokenizer("문자열", "구분자");	// 구분자 기준으로 문자열 분리
```

```Java
StringTokenizer st = new StringTokenizer("문자열", "구분자", boolean);	
// 구분자 기준으로 문자열 분리할 때 구분자도 Token으로 넣을지(true), 말지(false = default)
```

</br>

### StringTokenizer의 대표 메소드
|타입|메소드|설명|
|:---:|:---:|:---:|
|`int`|`countTokens()`|꺼내지 않고 남아있는 토큰의 수를 반환|
|`boolean`|`hasMoreTokens()`|남아있는 토큰이 있는지의 여부|
|`String`|`nextToken()`|다음 토큰을 반환|

</br>

> StringTokenizer 객체에서 더 이상 가져올 토큰이 없다면 `nextToken()` 메소드는 `java.util.NoSuchElementException` 예외를 발생시킨다. 그래서 `nextToken()` 메소드를 사용하기 전에 `hasMoreTokens()` 메소드로 꺼내올 토큰이 있는지 조사한 후 `nextToken()` 메소드를 호출하는 것이 바람직하다.

</br>

### StringTokenizer 간단한 사용 예시
```Java
StringTokenizer st = new StringTokenizer("기억은 기록을 이길 수 없다");

while (st.hasMoreTokens()) {
    System.out.println(st.nextToken());
}
```
- 위의 예시 코드처럼 구분자를 입력하지 않으면 기본 구분자를 이용해 분리한다.
- `hasMoreTokens()` 를 통해 남아있는 토큰이 없을 때까지 반복한다.
- `nextToken()` 을 통해 토큰을 하나씩 출력한다.

</br>

### split()
- 문자열을 나누어 배열에 저장한다.
- **정규표현식**으로 문자열을 구분한다.
- 공백 문자열도 포함한다.

</br>

### split() 사용법
```Java
public String[] split(String regex) // 정규표현식(regex)으로 문자열 패턴을 받고, 그 패턴과 일치하는 문자열을 기준으로 자름
```

```Java
public String[] split(String regex, int limit) // limit은 문자열을 나눌 최대 개수
```

</br>

### split() 간단한 사용 예시
```Java
String str = "기억은,기록을,이길,수,없다";

String[] arr = str.split(","); 

for(int i = 0; i < arr.length; i++) { 
    System.out.println(arr[i]); 
}
```
- `,`을 기준으로 문자열이 나누어져 배열에 담긴다.

</br>

### 비교 예시
1. 데이터 + 구분자 + 데이터
- `String str = "java,network,database";`
    - StringTokenizer의 경우
        - java
        - network
        - database
    - split()의 경우
        - java
        - network
        - database

    -> 결과가 동일하다.

</br>

2. 구분자 사이에 데이터가 없는 경우(데이터 + 구분자 + 구분자 + 데이터)
- `String str = "java,network,,database";`
    - StringTokenizer의 경우
        - java
        - network
        - database
    - split()의 경우
        - java
        - network
        - 
        - database
    
    -> split()만 공백을 포함하기 때문에 결과가 다르다.

</br>

3. 문자열이 구분자로 끝나는 경우(데이터 + 구분자)
- `String str = "java,network,database,";`
    - StringTokenizer의 경우
        - java
        - network
        - database
    - split()의 경우
        - java
        - network
        - database
    
    -> 두 경우 모두 마지막 구분자는 무시한다.

</br>

> split() 메소드는 인자로 정규 표현식을 사용하기 때문에 속도적인 측면에서는 StringTokenizer가 더 성능이 좋다. 하지만 가변적인 요소가 많은 문자열이나, 구분자가 많고 정확한 분리가 필요할 때는 split() 메소드를 사용하는 것이 유용하다.

</br>

### 참고 자료
- [정규 표현식](https://codechacha.com/ko/java-regex/)
- [StringTokenizer](https://docs.oracle.com/javase/7/docs/api/java/util/StringTokenizer.html)
- [split()](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#split(java.lang.String))