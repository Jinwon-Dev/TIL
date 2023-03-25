> **��Ű, ����, JWT? </br>
�� �� ���ø����̼ǿ��� ����� ������ ���� �������� �۾��� �����ϴ� �� ���Ǵ� �� ���� ��Ŀ�����̴�.**

</br>

## Session / Cookie ���

</br>

### ����

> ***��Ű***
> 
- Ŭ���̾�Ʈ(������)�� ����Ǵ� Ű-�� ���� ���� ������ �����̴�.
- ������ ������� �� ���������� �����Ͽ� Ŭ���̾�Ʈ ���� �����ϰ� �ʿ��� ������ ������ �����ϴ� ������� ���ȴ�.

</br>

> ***����***
> 
- ��Ű�� ���������� Ŭ���̾�Ʈ�� ���� �� ��ȣ�ۿ��� ���� ���Ǹ�, ��Ű�� �޸� ���� ������ �����ȴ�.
- Ŭ���̾�Ʈ�� ������ �����ϸ� ������ ���� ID�� �����ϰ�, Ŭ���̾�Ʈ���� �����Ѵ�.
- ���� Ŭ���̾�Ʈ�� ���� ID�� ��Ű�� �����صΰ�, ������ ��ȣ�ۿ��� ������ ���� ID�� �����Ѵ�.

</br>

</br>

### ���� ����

<img width="635" alt="image" src="https://user-images.githubusercontent.com/106216912/226191853-81bfbe64-285b-4b56-8f71-93209f7a512f.png">

1. ����ڰ� �α����� �Ѵ�.
2. ���������� ���� ������ �о� ����ڸ� Ȯ���Ѵ�.
3. ������ ������� ������ ID ���� �ο��Ͽ�, ���� ����ҿ� �����Ѵ�.
4. �ش��ϴ� ���� ID�� �����ϰ�, ������ �������� ����ڿ��� �����ش�.
5. ����ڴ� �������� �ش� ���� ID�� �޾� ��Ű�� ������ �ϰ� �ȴ�.
6. �� ��, ������ �ʿ��� ��û���� ��Ű�� ����� �Ǿ� ������.
7. ���������� ��Ű�� ����ڷκ��� �޾� ���� ����ҿ��� ������ �Ѵ�.
8. �� ��, ���� ����ҷκ��� �����Ǵ� ������ �����´�.
9. ������ �Ϸ�ǰ�, ������ ����ڿ��� �´� �����͸� �����Ѵ�.

</br>

> **������ ����ϴ� ����?**
> 
- ��������δ�, ***������ å���� ������ �����ϱ� ����*** ������ ����Ѵ�.
    - ����ڴ� ��Ű�� �̿��ϰ�, ���������� ��Ű�� �޾� ������ ������ �����ϴ� ������� ������ �Ѵ�.

</br>

</br>

### �����

> **����**
> 
1. ��Ű�� �Ű��� ������ ��ġ�µ�, ��Ű�� �ܼ��� ���� ����ҿ� ��� ���� ������ ��� ���� �����̴�.
    - ����, ��Ű�� ��� HTTP ��û�� �߰��� ����Ǵ���, ��Ű ��ü(���� ID)�� ���ǹ��� ���� ���� ���� �ʱ� ������ �����ϴ�.

</br>

2. ����ڸ��� ������ ID ���� �߱޹ް� �ȴ�.
    - ���������� ��Ű ���� �޾��� �� ������ ȸ�������� Ȯ���� �ʿ� ����, ***�ٷ� � ȸ�������� Ȯ���� �� �־ ����***�ϴ�.

</br>

> **����**
> 
1. ���� ��Ű�� ��� HTTP ��û�� ��Ŀ�� ����ä��, �� �ȿ� ����ִ� ��Ű�� ����� ��ĥ �� �ִ�.
    - ����, **��Ŀ�� �� ��ģ ��Ű�� �̿��� HTTP ��û�� ������ ���� ����ҿ��� ������� ������ ������ �� �ִ�**(���� ������ŷ ����).

</br>

�� **�ذ�å** 

1. ***HTTPS***�� ����ؼ� ��û ��ü�� Ż���ص� ���� ������ �б� ����� �Ѵ�.
2. ���ǿ� ***��ȿ�ð�***�� �־��־, �ð��� ������ ����ǰ� �Ѵ�.

---

## JWT

</br>

### ����

> ***JWT***
> 
- JSON Web Token�� ���ڷ�, �� ǥ������ ������ ��ū ����� ���� ����̴�.
- ����� ������ ��� �ִ� JSON ��ü�� �������� �����Ͽ� Ŭ���̾�Ʈ���� �����ϰ�, ���� ����� ������ �ʿ��� API�� ȣ���� ������ JWT�� �Բ� �����Ͽ� ������ �����Ѵ�.

</br>

</br>

### JWT�� ����

- ***Header*** : Header, Payload, Verify Signature�� ��ȣȭ�� ���, Ÿ�� ���� ����.
- ***Payload*** : �������� ���� �����Ͱ� ����.
    - �Ϲ������� ������ ���� ID ��, ��ȿ �Ⱓ�� ����.
- ***Verify Signature*** : Base64 ������� ���ڵ��� Header, Payload, Secret Key�� ���� �� �����ȴ�.

</br>

> **��ȣȭ, ��ȣȭ ����**
> 
- ***Header, Payload�� ���ڵ��� ��, ���� ��ȣȭ���� �ʴ´�.***
    - ����, JWT ��ū���� ����� ���̷ε�� ������ ���ڵ��Ͽ� Ȯ���� �� �ִ�.

- ***Verify Signature�� Secret Key�� ���� ���ϸ� ��ȣȭ�� �� ����.***
    - ex) � ����ڰ� ��ū�� �����ؼ� A ������� �����͸� ��ġ�����Ѵ�.
    - �׷��� Payload�� �ִ� A�� ID�� �ڽ��� ID�� �ٲ㼭 �ٽ� ���ڵ��� ��, ��ū�� ������ ������.
    - �׷���, ������ ó���� ��ȣȭ�� Verify Signature�� �˻��ϰ� �ȴ�.
    - ���⼭ Payload�� ���۵� ������� ������ �� ������, Verify Signature�� A�� Payload�� ������� ��ȣȭ �Ǿ��� ������, ��ȿ���� �ʴ� ��ū���� ���ֵȴ�.
    - **����, Secret Key�� ���� ���ϴ� �̻� ��ū�� ������ �� ����!**

</br>

</br>

### ���� ����

<img width="628" alt="image" src="https://user-images.githubusercontent.com/106216912/226191993-81abc878-e4dc-47c6-96b4-1dc9eeeb2fcd.png">

1. ����ڰ� �α����� �Ѵ�.
2. ���������� ���� ������ �о ����ڸ� Ȯ���Ѵ�.
    - ������� ������ ID���� �ο��� ��, ��Ÿ ������ �Բ� Payload�� �ִ´�.
3. JWT ��ū�� ��ȿ �Ⱓ�� �����ϰ�, ��ȣȭ�� Secret Key�� �̿��� Access Token�� �߱��Ѵ�.
4. ������ Access Token�� �������� �����ְ�, ����ڴ� �޾Ƽ� �����Ѵ�.
5. �� ��, ������ �ʿ��� ��û���� ��ū�� ����� �Ǿ� ������.
6. ���������� �ش� ��ū�� Verify Signature�� Secret Key�� ��ȣȭ�� ��, ���� ����, ��ȿ �Ⱓ�� Ȯ���Ѵ�.
7. ������ �Ϸ�ȴٸ�, Payload�� ���ڵ��Ͽ� ������� ID�� �´� �����͸� �����´�.

</br>

</br>

### �����

> **����**
> 
1. �����ϴ�.
    - ����/��Ű ����� ������ ����� ������ �ʿ�������, ***JWT�� �߱��� �� ������ �ϸ� �Ǳ� ������ �߰� ����Ұ� �ʿ� ����.***

</br>

2. ***Ȯ�强***�� �پ��.
    - ��ū ������� �ϴ� �ٸ� ���� �ý��ۿ� ������ �����ϴ�.
    - ex) Facebook �α���, Google �α���

> **����**
> 
1. �̹� �߱޵� JWT�� ���ؼ��� ����ų �� ����.
    - ����/��Ű�� ��� ��Ű�� ���������� �̿�ȴٸ�, �ش��ϴ� ������ ���������� �ȴ�.
    - ������ **JWT�� �� �� �߱� �Ǹ� ��ȿ�Ⱓ�� �Ϸ�� �� ���� ����� �����ϴ�.**

</br>

�� **�ذ�å**

- ������ Access Token�� ��ȿ�Ⱓ�� ª�� �ϰ�, ***Refresh Token***�̶�� ���ο� ��ū�� �߱��Ѵ�.
    - �׷��� �Ǹ� Access Token�� Ż����ص� ���ظ� ���� �� �ִ�.

</br>

2. **Payload ������ ������**�̴�.
    - Payload�� ���� ��ȣȭ���� �ʱ� ������, ���ڵ��ϸ� ������ ������ Ȯ���� �� �ִ�.
    - ����, ������ �߿��� �������� Payload�� ���� �� ����.

</br>

3. JWT�� ���̴� ����/��Ű ��Ŀ� ���� ���.
    - ����, **������ �ʿ��� ��û�� ������ ���� ������ �ڿ����� �߻�**�Ѵ�.

---

## Refresh Token

> **Refresh Token </br>
�� Access Token�� �Ȱ��� ������ JWT��, ó���� �α����� �Ϸ����� �� Access Token�� ���ÿ� �߱޵ȴ�.**

- ***�� ��ȿ�Ⱓ�� �����鼭, Access Token�� ������� �� ���� �߱����ִ� ����***�� �ȴ�.
    - Refresh Token�� ��ȿ�Ⱓ�� ����Ǿ��ٸ�, ����ڴ� ���� �α��� �ؾ� �Ѵ�.

</br>

</br>

### ���� ����

<img width="630" alt="image" src="https://user-images.githubusercontent.com/106216912/226192179-a68cae08-ddac-4c0c-b472-aef18f034483.png">

1. ����ڰ� ID, PW�� ���� �α����Ѵ�.
2. ���������� ȸ�� DB���� ���� ���Ѵ�.
3. �α����� �Ϸ�Ǹ� Access Token, Refresh Token�� �߱��Ѵ�.
    - �� ��, �Ϲ������δ� ȸ�� DB�� Refresh Token�� �����صд�.
4. �߱޹��� Access Token, Refresh Token�� �������� ����ڰ� �ް�, Refresh Token�� ������ ����ҿ� �����Ѵ�.
5. ����ڴ� Access Token�� ����� �Ǿ� ��û�� ������.
6. ������ Access Token�� �����Ѵ�.
7. �� ��, �̿� �´� �����͸� �����ش�.
8. �� ��, Access Token�� ����Ǿ��ٰ� �����ϸ�,
9. ����ڴ� ������ �����ϰ� Access Token�� ����� �Ǿ� ��û�� ������.
10. ������ Access Token�� ����Ǿ����� Ȯ���Ѵ�.
    - ���е忣�� �ܿ��� Access Token�� Payload�� ���� ��ȿ�Ⱓ�� �� �� �����Ƿ�, ����Ʈ ���� �ܿ��� API ��û ���� ��ū�� ����Ǿ��ٸ� �ٷ� ��߱� ��û�� �� ���� �ִ�.
11. �� ��, �������� ������ ������ ����ڿ��� ������.
12. ����ڴ� Refresh Token�� Access Token�� �Բ� ������ ������.
13. ������ ���� Access Token�� ���� ���θ� Ȯ�� ��, ���� Refresh Token�� ȸ�� DB�� ����Ǿ� �ִ� Refresh Token�� ���ϰ�, ���ο� Access Token�� �߱����ش�.
14. ������ ���ο� Access Token�� ����� �Ǿ� �ٽ� API ��û�� �����Ѵ�.

</br>

</br>

### �����

> **����**
> 
1. ������ Access Token�� ���� ������ ***����***�ϴ�.

</br>

> **����**
> 
1. ������ �����ϴ�.

</br>

2. Access Token�� ����� ������ ���Ӱ� �߱��ϴ� �������� ����� HTTP ��û ȸ���� ����.
    - ������ �ڿ� ���� �� �� �ִ�.