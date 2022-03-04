# habitpalette-api-document

python - django / MS SQL

## 1. login

HabitPalette는 구글, 애플 소셜 로그인을 사용합니다.

https://github.com/HabitPalette/habitpalette-api-document/blob/main/login

<br><br>

## 2. habit (습관)


<table>
  <tr>
    <th>URL</th>
    <th>Method</th>
    <th>제목</th>
    <th>설명</th>
    <th>Request Body</th>
    <th>Response Body</th>
  </tr>
  
  <tr>
    <td>/habits/list</td>
    <td>GET</td>
    <td>전체 습관 조회</td>
    <td>습관 전체 목록을 조회한다.</td>
    <td></td>
    <td></td>
  </tr>
  
  <tr>
    <td>/habits</td>
    <td>POST</td>
    <td>습관 생성</td>
    <td>습관을 생성한다.</td>
      <td>
      "{<br>
        "authorEmail": "aaaa@email.com",<br>
        "title": "공부하기",<br>
        "createdDate": dateType으로<br>
        "duration": 30,<br>
        "color": Enum? string<br>
       }"<br>
    </td>
    <td></td>
  </tr>
  
  <tr>
    <td>/habits/:id</td>
    <td>GET</td>
    <td>습관 조회</td>
    <td>습관 1개를 조회한다.</td>
    <td></td>
    <td></td>
  </tr>
  
  <tr>
    <td>/habits/:id</td>
    <td>PUT</td>
    <td>습관 수정</td>
    <td>습관을 수정한다. 제목과 색깔만 변경할 수 있다.</td>
    <td>
    "{<br>
      "authorEmail": "aaaa@email.com",<br>
      "title": "공부하기",<br>
      "color": Enum? string<br>
    }"<br>
    </td>
    <td></td>
  </tr>
  
  <tr>
    <td>/habits/:id</td>
    <td>DELETE</td>
    <td>습관 삭제</td>
    <td>습관을 삭제한다.</td>
    <td></td>
    <td></td>
  </tr>
</table>

<br><br>

## 3. 습관 메모

<table>
  <tr>
    <th>URL</th>
    <th>Method</th>
    <th>제목</th>
    <th>설명</th>
    <th>Request Body</th>
    <th>Response Body</th>
  </tr>
  
  <tr>
    <td>/habits/:id/habitmemos</td>
    <td>POST</td>
    <td>습관메모 생성</td>
    <td>
      매일 쓰는 습관 메모를 생성합니다.<br>
      익일 새벽 5시까지만 작성 가능.
    </td>
    <td>
    "{<br>
      "authorEmail": "aaaa@email.com",<br>
      "score": 5,<br>
      "content"": "공부 열공함"<br>
    }"<br>
    </td>
    <td></td>
  </tr>
</table>


<br><br><br>

# habitpalette-db-document

## habits

<table>
  <tr>
    <th>id</th>
    <th>설명</th>
    <th>type</th>
    <th>details</th>
  </tr>
  <tr>
    <td>id</td>
    <td>습관 id</td>
    <td>Long</td>
    <td>pk / not null / auto increment : 0</td>
  </tr>
  
  <tr>
    <td>title</td>
    <td>습관 이름</td>
    <td>varchar</td>
    <td>not null</td>
  </tr>
  
  <tr>
    <td>start_date</td>
    <td>시작 일자</td>
    <td>date</td>
    <td>not null</td>
  </tr>
  
  <tr>
    <td>end_date</td>
    <td>종료 일자</td>
    <td>date</td>
    <td>not null</td>
  </tr>
  <tr>
    <td>duration</td>
    <td>지속기간</td>
    <td>Long</td>
    <td>not null</td>
  </tr>
  
  <tr>
    <td>is_completed</td>
    <td>완료여부</td>
    <td>boolean</td>
    <td>not null</td>
  </tr>
  
  <tr>
    <td>color</td>
    <td>색깔</td>
    <td>varchar</td>
    <td>not null</td>
  </tr>
  
  <tr>
    <td>not null</td>
    <td>작성자 (id) </td>
    <td>Long</td>
    <td>fk / not null</td>
  </tr>
  
  <tr>
    <td>score</td>
    <td>약속점수</td>
    <td>Float</td>
    <td>not null</td>
  </tr>
</table>

<br>

## users

<table>
  <tr>
    <th>id</th>
    <th>설명</th>
    <th>type</th>
    <th>details</th>
  </tr>

  <tr>
    <td>id</td>
    <td>id</td>
    <td>Long</td>
    <td>pk / not null / auto increment : 0</td>
  </tr>
  
  <tr>
    <td>email</td>
    <td>이메일</td>
    <td>varchar</td>
    <td>unique / not null </td>
  </tr>
  
  <tr>
    <td>user_name</td>
    <td>이름 / 닉네임</td>
    <td>varchar</td>
    <td>not null</td>
  </tr>
  
  <tr>
    <td>morning_notification</td>
    <td>아침 알림</td>
    <td>boolean</td>
    <td>not null</td>
  </tr>
  
  <tr>
    <td>night_notification</td>
    <td>저녁 알림 </td>
    <td>boolean </td>
    <td>not null (백엔드에서 디폴트로)</td>
  </tr>
</table>


<br>

## habit history

<table>
  <tr>
    <tr>
      <th>id</th>
      <th>설명</th>
      <th>type</th>
      <th>details</th>
    </tr>
  </tr>

  <tr>
    <td>id</td>
    <td>id</td>
    <td>Long</td>
    <td>pk / not null / auto increment : 0</td>
  </tr>
  
  <tr>
    <td>habit_id</td>
    <td>습관 id</td>
    <td>Long</td>
    <td>fk / not null</td>
  </tr>
  
  <tr>
    <td>score</td>
    <td>각 날의 점수 </td>
    <td>Long</td>
    <td></td>
  </tr>
  
  <tr>
    <td>created_date</td>
    <td>생성 날짜</td>
    <td>date</td>
    <td></td>
  </tr>
  
  <tr>
    <td>content</td>
    <td>각 날의 메모 </td>
    <td>text</td>
    <td></td>
  </tr>
  
  <tr>
    <td>day</td>
    <td>요일</td>
    <td>varchar</td>
    <td></td>
  </tr>
  
  <tr>
    <td>week</td>
    <td>주차</td>
    <td>Long</td>
    <td></td>
  </tr>
</table>

