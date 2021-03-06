# HTTP Method

> 원래 HTTP 메소드는 총 8개이지만, 오늘은 자주 사용하는 4개만 정리한다

### HTTP Method

**GET**

* 요청하는 데이터를 Request Message의 헤더 부분 URI에 담아서 전송한다. URI라는 공간에 담겨서 데이터를 전송하기 때문에 크기가 제한적임
  * GET Method는 Request를 할 때, 데이터를 쿼리 스트링에 담아서 전송함.
* 서버 데이터나 상태를 변경하는 행위는 하지 않음

**POST**

* GET방식의 query string과 달리 글자 수 제약이 없으며, 파일 업로드 등의 동작이 가능함
  * HTTP Message의 Body에 데이터를 담아 전송, 전송가능한 데이터의 크기가 GET에 비해 크며 보안면에서 GET보다 상대적으로 좋음
    * https(http + secure socket layer)가 아닌경우 uri의 쿼리스트링에 데이터를 담아도 평문이고, body에 데이터를 담아도 평문으로 전송되기 때문에 보안상 좋다고 할 수 없음
* 서버의 상태나 값을 변경하거나 추가하는데 사용됨

**PUT**

* 자원을 수정할 것을 요청

> **PUT vs PATCH**
> PUT 메소드: 자원의 **전체**교체, 자원 내 모든 필드 필요
> (만약 전체가 아닌 일부만 전달할 경우 전달할 필드 null 처리가 될수도 있음)
>
> PATCH 메소드: 자원의 **부분**교체, 자원내 일부 필드 필요

**DELETE**

* 자원을 삭제할 것을 요청
* 특정 자원에 대한 delete의 경우 자원을 더 이상 이용할 수 없어야 하므로 Delete 요청을 다시 호출해도 자원은 여전히 사용할 수 없는 상태여야 함



![uri structure](C:\Users\kangsinhee\Desktop\programming\Study_Backend\HTTP Method\uri-structure.png)



---

### 총 정리

| HTTP메소드 | 요청에 Body가 있음 | 응답에 Body가 있음 | 멱등 | 캐시 가능 |
| :--------: | :----------------: | :----------------: | :--: | :-------: |
|    GET     |         X          |         O          |  O   |     O     |
|    POST    |         O          |         O          |  X   |     O     |
|    PUT     |         O          |         O          |  O   |     X     |
|   DELETE   |         X          |         O          |  O   |     X     |

