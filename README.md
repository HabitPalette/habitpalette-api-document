# habitpalette-api-document

1. 로그인 관련 : /user
2. 습관 관련 : /habit
3. 습관 메모 관련 : /habitMemo


## 1. login

HabitPalette는 구글, 애플 소셜 로그인을 사용합니다.

https://github.com/HabitPalette/habitpalette-api-document/blob/main/login

<br><br>

## 2. habit (습관)


<table>
  <th>
    <td>URL</td>
    <td>Method</td>
    <td>제목</td>
    <td>설명</td>
    <td>Request Body</td>
    <td>Response Body</td>
  </th>
  
  <tr>
    <td>/habits/list</td>
    <td>GET</td>
    <td>전체 습관 조회</td>
    <td>습관 전체 목록을 조회한다.</td>
  </tr>
  
  <tr>
    <td>/habits</td>
    <td>POST</td>
    <td>습관 생성</td>
    <td>습관을 생성한다.</td>
      <td>
      "{
    "authorEmail": "thdmsdl87@gmail.com",
    "title": "공부하기",
    "createdDate": dateType으로
    "duration": 30, 
    "color": Enum? string
    }"
    </td>
  </tr>
  
  <tr>
    <td>/habits/:id</td>
    <td>GET</td>
    <td>습관 조회</td>
    <td>습관 1개를 조회한다.</td>
  </tr>
  
  <tr>
    <td>/habits/:id</td>
    <td>PUT</td>
    <td>습관 수정</td>
    <td>습관을 수정한다. 제목과 색깔만 변경할 수 있다.</td>
  </tr>
  
  <tr>
    <td>/habits/:id</td>
    <td>DELETE</td>
    <td>습관 삭제</td>
    <td>습관을 삭제한다.</td>
  </tr>
</table>


### a. list - 습관 게시물 목록 불러오기 


description: 해당 id 가진 습관 게시물을 목록을 불러오는 API입니다.


```text
GET
```


### b. post - 습관 게시물 생성


description: 습관 게시물을 생성하는 API입니다. 


```text
POST
```



### c. get - 습관 게시물 1개 불러오기 


description: 해당 id 가진 습관 게시물을 불러오는 API입니다.


```text
GET
```


### d. put - 습관 게시물 수정


description: 해당 id 가진 습관 게시물을 수정하는 API입니다.


```text
PUT
```


### e. delete - 습관 게시물 삭제


description: 해당 id 가진 습관 게시물을 삭제하는 API입니다.


```text
DELETE
```

https://github.com/HabitPalette/habitpalette-api-document/blob/main/habits/habit/README.md

<br><br>

## 3. habitMemo (매일 습관 메모)

### a. post - 습관메모(1일별) 생성 

description: 습관메모(1일별)을 생성하는 API입니다. 

```text
POST
```


### b. get - 습관메모 읽기

description: 해당 id 가진 습관메모(1일별) 하나를 불러오는 API입니다.

```text
GET
```

https://github.com/HabitPalette/habitpalette-api-document/blob/main/habits/habitMemo/README.md
