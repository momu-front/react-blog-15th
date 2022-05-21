
# 과제 제출

---
모무 프론트 <br> 전시원 김채림

### 목차

> 1. 어떻게 구현했는가 
> 2. css 서버사이드 렌더링 적용
> 3. pull request 내용

# 1. 어떻게 구현했는가

### Landing 


- 주소창 '/' <br>랜딩페이지, 들어오게 되면 게시물을 나열 <br> 제목과 게시한 날짜(월,일)을 표시함 <br>


### POST (CREATE)

- 주소창 '/post' <br>
게시글을 작성하게 되면 제목과 본문내용을 담아서 recoil 이 보관<br>
게시글 id 도 recoil 에서 전역관리하여 새로운 게시글이 만들어질 때마다
+1 시켜서 관리


### GET (READ)

- 주소창 '/get/[id]' <br>
랜딩페이지에서 게시글을 누르면 게시글의 id 값을 주소창에 담아서 넘김<br>
동적라우팅을 통해 주소창 설계 <br>
해당 id 값을 /get/[id] 페이지에서 받은 다음 recoil 에 저장된 데이터를 가져옴<br>
posts 객체를 가져오면 그대로 게시글에 대한 데이터를 렌더링
  
### EDIT (UPDATE)

- 주소창 '/edit/[id]' <br>
랜딩페이지에서 게시글을 누르고 나면 게시글을 상세히 볼 수 있음.<br>
그곳에서 수정하기 버튼을 눌러 접근<br>
get 과 동일한 논리로 게시글 가져온 다음 렌더링<br>
차이점은 input 창의 value 로 이미 작성되어 있는 내용을 넣어 줘야 함.
  
### 페이지 없음 (DELETE)
- 주소창 없음 <br>
지우기 버튼을 누르면 해당 아이디에 맞는 게시물을 posts 배열에서 삭제
  
### 데이터 구조

```json
{
  "posts": [
    {
      "id": "number",
      "title": "string",
      "contents": "string",
      "date": "string"
    }
  ]
}
```

