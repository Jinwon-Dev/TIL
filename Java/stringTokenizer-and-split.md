# StringTokenizer�� split()

</br>

## Java������ ���ڿ��� Ư�� �����ڷ� ����Ǿ� ���� ���, �����ڸ� �������� ���ڿ��� �и��ϱ� ���� ����� �����Ѵ�.
1. `java.util` ��Ű���� StringTokenizer
2. `String` �� split() �޼ҵ�

</br>

### StringTokenizer
- ���ڿ��� �����ڸ� �̿��Ͽ� �и��� �� ����� �� �ִ�.
- **����/���ڿ�**�� ���ڿ��� �����Ѵ�.
- ���� ���ڿ��� �������� �ʴ´�.

</br>

### StringTokenizer ����
```Java
StringTokenizer st = new StringTokenizer("���ڿ�");	// �����̽�, ��, �ٹٲ�, ĳ���� ���� �� �⺻ ������ �������� ���ڿ� �и�
```

```Java
StringTokenizer st = new StringTokenizer("���ڿ�", "������");	// ������ �������� ���ڿ� �и�
```

```Java
StringTokenizer st = new StringTokenizer("���ڿ�", "������", boolean);	
// ������ �������� ���ڿ� �и��� �� �����ڵ� Token���� ������(true), ����(false = default)
```

</br>

### StringTokenizer�� ��ǥ �޼ҵ�
|Ÿ��|�޼ҵ�|����|
|:---:|:---:|:---:|
|`int`|`countTokens()`|������ �ʰ� �����ִ� ��ū�� ���� ��ȯ|
|`boolean`|`hasMoreTokens()`|�����ִ� ��ū�� �ִ����� ����|
|`String`|`nextToken()`|���� ��ū�� ��ȯ|

</br>

> StringTokenizer ��ü���� �� �̻� ������ ��ū�� ���ٸ� `nextToken()` �޼ҵ�� `java.util.NoSuchElementException` ���ܸ� �߻���Ų��. �׷��� `nextToken()` �޼ҵ带 ����ϱ� ���� `hasMoreTokens()` �޼ҵ�� ������ ��ū�� �ִ��� ������ �� `nextToken()` �޼ҵ带 ȣ���ϴ� ���� �ٶ����ϴ�.

</br>

### StringTokenizer ������ ��� ����
```Java
StringTokenizer st = new StringTokenizer("����� ����� �̱� �� ����");

while (st.hasMoreTokens()) {
    System.out.println(st.nextToken());
}
```
- ���� ���� �ڵ�ó�� �����ڸ� �Է����� ������ �⺻ �����ڸ� �̿��� �и��Ѵ�.
- `hasMoreTokens()` �� ���� �����ִ� ��ū�� ���� ������ �ݺ��Ѵ�.
- `nextToken()` �� ���� ��ū�� �ϳ��� ����Ѵ�.

</br>

### split()
- ���ڿ��� ������ �迭�� �����Ѵ�.
- **����ǥ����**���� ���ڿ��� �����Ѵ�.
- ���� ���ڿ��� �����Ѵ�.

</br>

### split() ����
```Java
public String[] split(String regex) // ����ǥ����(regex)���� ���ڿ� ������ �ް�, �� ���ϰ� ��ġ�ϴ� ���ڿ��� �������� �ڸ�
```

```Java
public String[] split(String regex, int limit) // limit�� ���ڿ��� ���� �ִ� ����
```

</br>

### split() ������ ��� ����
```Java
String str = "�����,�����,�̱�,��,����";

String[] arr = str.split(","); 

for(int i = 0; i < arr.length; i++) { 
    System.out.println(arr[i]); 
}
```
- `,`�� �������� ���ڿ��� �������� �迭�� ����.

</br>

### �� ����
1. ������ + ������ + ������
- `String str = "java,network,database";`
    - StringTokenizer�� ���
        - java
        - network
        - database
    - split()�� ���
        - java
        - network
        - database

    -> ����� �����ϴ�.

</br>

2. ������ ���̿� �����Ͱ� ���� ���(������ + ������ + ������ + ������)
- `String str = "java,network,,database";`
    - StringTokenizer�� ���
        - java
        - network
        - database
    - split()�� ���
        - java
        - network
        - 
        - database
    
    -> split()�� ������ �����ϱ� ������ ����� �ٸ���.

</br>

3. ���ڿ��� �����ڷ� ������ ���(������ + ������)
- `String str = "java,network,database,";`
    - StringTokenizer�� ���
        - java
        - network
        - database
    - split()�� ���
        - java
        - network
        - database
    
    -> �� ��� ��� ������ �����ڴ� �����Ѵ�.

</br>

> split() �޼ҵ�� ���ڷ� ���� ǥ������ ����ϱ� ������ �ӵ����� ���鿡���� StringTokenizer�� �� ������ ����. ������ �������� ��Ұ� ���� ���ڿ��̳�, �����ڰ� ���� ��Ȯ�� �и��� �ʿ��� ���� split() �޼ҵ带 ����ϴ� ���� �����ϴ�.

</br>

### ���� �ڷ�
- [���� ǥ����](https://codechacha.com/ko/java-regex/)
- [StringTokenizer](https://docs.oracle.com/javase/7/docs/api/java/util/StringTokenizer.html)
- [split()](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#split(java.lang.String))