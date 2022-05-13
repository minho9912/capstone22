## 201840135 최민호

```
팀명: Double (더블)

팀원: 최민호(팀장 | 웹퍼블리싱) , 오승엽(팀원 | 웹디자인)
```

- 졸업작품 소개사이트 : https://minho9912.github.io/DoubleProject/
- 졸업작품 링크 : 수정중

---

## [졸업작품소개]

- 작품명 : All About Coffee (AAC)

- 개발환경 : HTML / CSS / JAVASCRIPT / PHOTOSHOP / XD

---

### [작품 소개]

```
코로나19로 인해 바깥 외출이 부담스러운 요즘,
커피 한잔을 위해 카페에 방문하는 것을 지양하기위해
집에서 커피를 직접 내려먹는 '홈카페'가 유행이다.
홈카페를 하기위해 필요한 장비, 커피의 핵심인 나라별 원두,
커피 내리는 방법등의 정보를 담고있는 사이트이다.
```

---

### [작품의 특징]

|      기능       |                                                설명                                                |
| :-------------: | :------------------------------------------------------------------------------------------------: |
| 나만의 원두찾기 |              MBTI테스트처럼<br>자신의 입맛에 맞는 나라별 원두를<br>찾아주는 기능이다.              |
| 나라별 원두소개 | 원두 이미지를 클릭하면 해당 원두에 대한 <br>산미,당도,바디감 등에 대한 상세페이지<br>가 출력된다.  |
|  홈카페 라이브  | Youtube API를 통해 커피를 내리는 과정<br>에 대한 영상이 각 장비의<br>상세페이지 별로 재생되고있다. |

---

## [개발일지]

### [5월 11일]

```
▶ 메인 홈페이지 나라별 원두 슬라이드 박스 제거 및 배경이미지 수정완료
   ▶ 세계지도를 활용해 지도 위에 나라별 국기를 올려놓은 형태로 제작
▶ 원두 블렌딩 시스템 구현완료
   ▶ js DOM, css before 등을 활용함. footer에 나라별 원두를 위치시키고 고를 수 있게하였고, 조합기능 및 재선택 기능 추가.(함수사용)

```

<a href="https://user-images.githubusercontent.com/80302108/168191882-99121a39-e086-4376-9d86-959ff96206e2.PNG">이미지 링크</a>

```jsx
// footer의 선택한 원두별 함수 부분, 이하생략
function kenya() {
  if (box_list.length < 2) {
    box_list.push('kenya');
    document.querySelector('.kenya').style.display = 'none';
  } else {
    alert('두개만 선택가능합니다');
    return;
  }

  if (fst_value == false) {
    fst_beh.style.display = 'none';
    fst_value = true;
    fst_top.innerHTML = 'Kenya';
    fst_cen.innerHTML = "'신맛과 단맛의 조화, 모든 부분에 밸런스가 좋은 커피'";
    fst_bot.src = '../img/나라/국기/케냐.png';
  } else {
    sec_beh.style.display = 'none';
    sec_value = true;
    sec_top.innerHTML = 'Kenya';
    sec_cen.innerHTML = "'신맛과 단맛의 조화, 모든 부분에 밸런스가 좋은 커피'";
    sec_bot.src = '../img/나라/국기/케냐.png';
  }
}
```

```jsx
//조합 기능함수
function mix() {
  if (box_list.length <= 1) {
    alert('조합할 원두가 없습니다.');
  }

  if (box_list.includes('kenya') && box_list.includes('ethiopia')) {
    thd_beh.style.display = 'none';
    thd_fst.style.height = '200px';
    thd_fst.style.backgroundColor = '#d67474';
    thd_sec.style.height = '180px';
    thd_sec.style.backgroundColor = '#d67474';
    thd_thd.style.height = '100px';
    thd_thd.style.backgroundColor = '#d67474';
  }
  if (box_list.includes('kenya') && box_list.includes('brazil')) {
    thd_beh.style.display = 'none';
    thd_fst.style.height = '150px';
    thd_fst.style.backgroundColor = '#d67474';
    thd_sec.style.height = '120px';
    thd_sec.style.backgroundColor = '#d67474';
    thd_thd.style.height = '130px';
    thd_thd.style.backgroundColor = '#d67474';
  }
  //if...이하생략
}
// 위와같은 if문과 includes 사용, 모든 조합 가능한 원두 if문 생성함, 이하 생략
```

```jsx
// 재선택 버튼
function reset() {
  if (box_list.length >= 1) {
    window.location.reload();
  } else {
    alert('선택된 항목이 없습니다.');
  }
}
//재선택 버튼을 클릭했을때의 조건, 아래에서 설명.
```

- footer의 나라별 원두 박스 선택시, box_list배열의 크기가 2보다 작으면 원두를 블렌딩 박스에 넣으면서 선택한 원두는 display를 none처리한다.<br> 만약 첫번째 박스가 차있으면 두번째 박스에 원두를 넣는다.
- mix함수의 경우 box_list배열의 크기가 1보다 작거나 같으면(블렌딩 박스 두개가 모두 차있지 않으면)<br>alert로 경고문을 출력한다. 그렇지 않다면 조합그래프의 첫번째~세번째 그래프의 height값을 각각 다르게 증가시킨다.
- reset함수의 경우 box_list배열의 크기가 1보다 크거나 같다면(한개라도 선택되어있다면) 해당 브라우저를 새로고침 시킨다.(초기화)<br>그렇지 않다면 alert로 경고문을 출력한다.

---

### [5월 4일]

```
▶ 메인 홈페이지 나라별 원두 슬라이드 박스 제거 및 배경이미지 수정
▶ 커피의 효능 부분 타 사이트 벤치마킹 자료 활용해 수정
▶ 원두 블렌딩 시스템 구현하기로함.(원두를 섞어서 내려마시는 사람을 위한 기능)

```

- 배경이미지의 경우 디자인 담당이 포토샵을 활용해 제작하기로 함
- 스타벅스, 이디야, 커피빈 등 다양한 카페 사이트를 참고해 커피의 효능 영역을 수정할 예정임.
- 원두 블렌딩 시스템의 경우 부트스트랩을 사용해 구현할 예정.

---

### [5월 1일]

```
▶ 자유게시판 (소통) 기능 구현
▶ 도메인 구축을 통한 DB연동 실패
▶ 로컬스토리지를 활용한 임시적인 데이터 저장 기능 구현

```

```jsx
<section>
      <script src="../js/board.js"></script>
  </section>
  <section class="page">

  </section>
  <section style="margin-top:2vh; margin-left:5vw; margin-bottom:1vh;">
      <a href="write.html"><input type="button" value="글쓰기" class="btn btn-board"></input></a> &nbsp;
  </section>

  <div id="body-wrapper">
    <div id="body-content"></div>
    </div>

let list = localStorage.getItem('postings');
let parsedList = JSON.parse(list);
let number;
if (parsedList !== null) {
  number = parsedList.length - 1;
}

function makeTable(variable, variable2) {
  let table = document.createElement('table');
  table.style.marginTop = '3vh';
  table.style.marginLeft = '5vw';
  table.style.marginRight = '5vw';

  let firstRow = document.createElement('tr');
  firstRow.style.textAlign = 'center';
  firstRow.style.color = '#fff';
  firstRow.style.fontWeight = 'bold';
  firstRow.style.fontSize = '1.8rem';
  firstRow.style.backgroundColor = 'rgb(141, 180, 141)';

  let index = document.createElement('td');
  let indexText = document.createTextNode('번호');
  index.appendChild(indexText);
  index.style.width = '15vw';
  index.style.paddingTop = '1.5vh';
  index.style.paddingBottom = '1.5vh';
  index.style.border = '1px #e3e3e3 solid';
  firstRow.appendChild(index);

  let title = document.createElement('td');
  let titleText = document.createTextNode('제목');
  title.appendChild(titleText);
  title.style.border = '1px #e3e3e3 solid';
  title.style.width = '60vw';
  firstRow.appendChild(title);

  let date = document.createElement('td');
  let dateText = document.createTextNode('작성일');
  date.appendChild(dateText);
  date.style.width = '50vw';
  date.style.border = '1px #e3e3e3 solid';
  firstRow.appendChild(date);

  table.appendChild(firstRow);
 // ..이하 샐략
```

- 로컬스토리지를 사용해 getItem으로 write.html의 입력값을 읽어온다.
- 받아온 입력값을 DOM을 사용한 createElement,appendChild를 사용해 표에 넣어준다.

---

- body의 background-image를 커피사진으로 변경.
- 회원가입 각 요소는 input태그가 합쳐진 것으로, 처음것과 끝부분 것만 radius적용

---

### [4월 27일]

```
▶ 회원가입 페이지 디자인 수정
▶ 정돈되지 않은 느낌의 회원가입 페이지의 body에 이미지를 삽입
▶ border radius를 활용해 회원가입 창 부분을 모서리가 둥근 사각형으로 제작
▶ 사진 위에 화면이 떠있는 효과를 주었음
▶ 주말동안 나라별 원두 카드박스 부분 디자인을 직관적으로 수정할 예정
```

```css
<style >
body {
  background-image: url('../img/커피고화질2.jpg');
  background-repeat: no-repeat;
  background-size: cover;
}
 .sign > .sign-box {
  width: auto;
  display: flex;
  justify-content: center;
  padding: 10px 0px;
  background-color: rgb(255, 255, 255);
}
.sign > .sign-box:nth-child(1) {
  border-radius: 10px 10px 0px 0px;
}
.sign > .sign-box:nth-child(7) {
  border-radius: 0px 0px 10px 10px;
}
</style >
```

---

- body의 background-image를 커피사진으로 변경.
- 회원가입 각 요소는 input태그가 합쳐진 것으로, 처음것과 끝부분 것만 radius적용

---

### [4월 20일]

```
▶ 사이트에 들어갈 컨텐츠 요소가 부족하다고 생각되어 나라별 원두 블렌딩 시스템 구현결정함.
▶ 신맛,단맛으로 구분되어 있는 원두별 그림을 클릭하면 프로세스바가 올라가고, 블렌딩원두의 비율이 나타나게 구현할 예정.
▶ 나라별 원두 슬라이드 가로로 정렬 후 이미지 변경.
▶ heroku 도메인을 사용해 node.js , express를 활용한 db연동 예정


```

---

---

### [4월 14일]

```
▶ 밋밋한 메인화면 디자인 수정 방안 회의
▶ 나만의원두 문항 수정관련 회의
▶ 원두는 섞어서 분쇄하면 블렌드라고 불리는데, 이를 자바스크립트를 활용해
나만의 블렌드 시스템을 구현하기로 함


```

```javascript
var num = 1; // 첫 문제 번호
var q = {
  1: { title: '평소에 어떤 방식으로 커피를 즐기시나요?', type: 'BN', A: '핸드드립', B: '커피머신' },
  2: {
    title: '다음중 선호하는 커피의 맛은?(1)',
    type: 'ST',
    A: '신맛',
    B: '단맛',
  },
  3: {
    title: '다음중 선호하는 커피의 맛은?(2)',
    type: 'RE',
    A: '단맛',
    B: '쓴맛',
  },
  4: {
    title: '다음중 선호하는 커피의 맛은?(3)',
    type: 'BN',
    A: '쓴맛',
    B: '신맛',
  },
  5: {
    title: '당신이 선호하는 커피의 향은?',
    type: 'RE',
    A: '진한 향',
    B: '은은한 향',
  },
};
```

- 문항같은 경우, 커피의 1.단맛 2.쓴맛 3.신맛을 골고루 답변할 수 있도록 만들었음.

---

### [4월 13일]

```
▶ 커피의 효능 부분 4가지 효능 박스 스크롤 이벤트 추가
▶ .throttle을 사용해 스크롤 값이 박스부분을 넘어갈 경우
translateY값 제어를 통해 아래에서 위로 올라오는 효과를 주었음
```

```javascript
const move_item = document.querySelectorAll('.info-box');

// _.throttle (함수, 시간)
window.addEventListener(
  'scroll',
  _.throttle(function () {
    console.log(window.scrollY);
    if (window.scrollY > 350) {
      //배지 숨기기
      //gsap.to(요소, 지속시간, 옵션)

      //버튼 보이기
      gsap.to(move_item, 0.2, {
        y: 0,
      });
    } else {
      // 배지 보여주기
      //gsap.to(요소, 지속시간, 옵션)

      //버튼 숨기기

      gsap.to(move_item, 0, {
        y: 200,
      });
    }
  }, 300)
);
```

- window.scrollY를 통한 스크롤값을 콘솔을 통해 알 수 있도록 만든다.
- 그리고 if조건문을 활용해 특정 영역의 스크롤값을 넘게되면 요소가 일정 시간동안 올라오고, 넘지 않게되면 다시 내려간다

---

### [4월 10일]

```
▶ 원두 크롤링 페이지에 원두별 페이지 추가 구현
▶ 나라별 원두 이름 클릭시 그것에 맞는 크롤링결과가 출력되게함.
```

<a href="https://user-images.githubusercontent.com/80302108/162610617-0b54ea2b-a967-4481-a4b8-9ea9f261ca60.PNG">검색</a> <br>

```python
import json

import crawler as crawl
import pars as parse

pageString = crawl.crawl('')
products = parse.parse(pageString)


file = open("./columbia.json","w+")
file.write(json.dumps(products))
```

```html
<table id="table" border="1" cellpadding="10" rules="rows">
  <h1 class="search-box">원두 검색결과</h1>
  <div class="search-beans inner">
    <a onclick="first()">케냐</a>
    <a onclick="second()">탄자니아</a>
    <a onclick="third()">산토스</a>
    <!-- ...이하생략 -->
  </div>

  <tr></tr>
</table>
```

```javascript
let beans_grp = '../himart.json';
let table_grp = document.querySelector('#table');

xhttp.open('GET', beans_grp, true);
xhttp.send();

first = () => {
  while (table_grp.firstChild) {
    table_grp.removeChild(table_grp.lastChild);
  }
  xhttp.open('GET', '../kenya.json', true);
  xhttp.send();
};
```

- beans 버튼을 누름과 동시에 파이썬 코드가 실행되면서 나라별 원두에 맞는 크롤링결과를 검색.
- 검색된 크롤링 결과를 각 원두이름에맞는 json파일로 저장함.
- 원두 검색결과 상세페이지에서 나라별 원두 버튼을 클릭하면 해당 json파일을 실시간으로 불러옴.

---

### [4월 9일]

```
▶ 공지사항 게시판 디자인 구상
▶ 스타벅스, 이디야커피 홈페이지 벤치마킹결과 심플한 디자인으로 만들기로 함
▶ 덧글달기기능이나, 게시판 등록같은 백엔드기능은 추후 시도해볼예정
```

<a href="https://user-images.githubusercontent.com/80302108/162608615-3a9890a7-a706-479c-bc94-4c866ed055e5.PNG">게시판</a> <br>

```html
<div class="board_wrap">
  <div class="board_title">
    <strong>공지사항</strong>
    <p>공지사항을 빠르고 정확하게 안내해드립니다.</p>
  </div>
  <div class="board_list_wrap">
    <div class="board_list">
      <div class="top">
        <div class="num">번호</div>
        <div class="title">제목</div>
        <div class="writer">글쓴이</div>
        <div class="date">작성일</div>
        <div class="count">조회</div>
      </div>
      <div>
        <div class="num">1</div>
        <div class="title"><a href="./notice_list/notice1.html">첫번째 공지사항</a></div>
        <div class="writer">관리자</div>
        <div class="date">2022.3.19</div>
        <div class="count count_1">0</div>
      </div>
      <!-- 이하생략.. -->
    </div>
  </div>
</div>
```

- 공지사항 게시판의 메인 행 부분에는 번호,제목,글쓴이,작성일,조회가 등록되어있다.
- 제목 부분 공지사항을 클릭하면 각각 등록된 HTML파일 경로로 이동한다.

---

### [4월 8일]

```
▶ 나라별 원두 슬라이드 형태 수정 회의
▶ 기존의 슬라이드 형태는 매우 평범했음, 카드형태로 구현하기로함
▶ swiper라이브러리 기능을 활용하기로 결정
```

<a href="https://user-images.githubusercontent.com/80302108/162464002-9a49727e-7e9f-4290-9ead-1b894f6af06b.PNG">슬라이드</a> <br>
<a href="https://user-images.githubusercontent.com/80302108/162464121-0f71492d-0e99-4274-b35a-8726588e9eec.PNG">나만의원두</a>

```javascript
var swiper = new Swiper('.beans-slide', {
  effect: 'cards',
  grabCursor: true,
  pagination: {
    el: '.beans-slide > .swiper-pagination',
    clickable: true,
  },
  navigation: {
    nextEl: '.swiper-button-next',
    prevEl: '.swiper-button-prev',
  },
});
```

- swiper라이브러리에서 지원하는 cards모드 사용

```javascript
 var result = {
        SBR: {
          beans: '신맛과 단맛의 조화, <strong> 케냐 </strong>',
          explain:
            '케냐는 커피를 생산하기에 아주 적합한 기후조건을 가지고있다.<br>덕분에 풍부한 향과 맛의 밸런스가 아주 훌륭하다.누구에게나 무난하게 추천하는 원두이다',
          img: '../img/나라별원두/케냐.png',
        },
        SBE: {
          beans: '레몬, 감귤과 같은 기분 좋은 사미! <strong> 예가체프 </strong>',
          explain: '부드럽고 다양한 향이 감도는것이 특징"커피의 귀부인"이라는 별칭이 있을 만큼최상의 원두로 평가받고있다.',
          img: '../img/나라별원두/에티오피아.png',
        },
      function next() {
        if (num == 7) {
          $('.question').hide();
          $('.result').show();
          var mbti = '';
          $('#ST').val() < 1 ? (mbti += 'S') : (mbti += 'T');
          $('#BN').val() < 1 ? (mbti += 'B') : (mbti += 'N');
          $('#RE').val() < 1 ? (mbti += 'R') : (mbti += 'E');
          $('#img').attr('src', result[mbti]['img']);
          $('#champion').html(result[mbti]['beans']);
          $('#explain').html(result[mbti]['explain']);
          $('#img2').attr('src', result[mbti]['img2']);
          $('#img3').attr('src', result[mbti]['img3']);
          $('#img4').attr('src', result[mbti]['img4']);
          $('.coffee-box').hide();
        } else {
          $('.progress-bar').attr('style', 'width: calc(100/7*' + num + '%');
          $('#title').html(q[num]['title']);
          $('#type').val(q[num]['type']);
          $('#A').html(q[num]['A']);
          $('#B').html(q[num]['B']);
          num++;
        }
      }
```

- 문제마다 A에 해당하는 답변 버튼을 클릭시 ST,BN,RE중 하나의 변수값이 +1 증가한다.
- 2개씩 총 6문제가 존재하며 중첩된 값에 따라 mbti라는 변수에 앞 혹은 뒷 글자를 넣는다.
- 합쳐진 글자가 result변수와 같은것이 있으면 이를 바탕으로 원두사진과 설명을 출력한다.

---

### [4월 6일]

```
▶ 쇼핑몰 검색결과 크롤링json파일 html에서 불러오기 구현
▶ XMLHttpRequest속성을 사용해 Array와 for, dom의 createElement를 사용하여
   table의 tr,td내용으로 삽입해주었음.
▶ 원두별 상세페이지에 유튜브api를 활용한 영상을 넣으려했으나,api를 사용하면 한페이지에 한개씩밖에 못넣음.
▶ iframe태그를 활용해서 영상을 넣었음
```

<a href="https://user-images.githubusercontent.com/80302108/161999524-25123779-b7e8-4994-91f3-9fa777e0e053.PNG">크롤링</a>

```javascript
let xhttp = new XMLHttpRequest();

xhttp.onreadystatechange = function () {
  if (xhttp.readyState == 4 && xhttp.status == 200) {
    jsonfunc(this.responseText);
  }
};

let beans_grp = '../himart.json';
let table_grp = document.querySelector('#table');

xhttp.open('GET', beans_grp, true);
xhttp.send();

first = () => {
  while (table_grp.firstChild) {
    table_grp.removeChild(table_grp.lastChild);
  }
  xhttp.open('GET', '../kenya.json', true);
  xhttp.send();
};
second = () => {
  while (table_grp.firstChild) {
    table_grp.removeChild(table_grp.lastChild);
  }
  xhttp.open('GET', '../tanzania.json', true);
  xhttp.send();
};
//이하생략..

function jsonfunc(jsonText) {
  let arrTitle = new Array();
  let arrPrice = new Array();
  let arrImg = new Array();
  let arrIink = new Array();

  let json = JSON.parse(jsonText);

  for (i = 0; i < json.length; i++) {
    // 값 전체 가져오는법
    arrTitle[i] = json[i].alt;
    arrPrice[i] = json[i].price;
    arrImg[i] = json[i].img;
    arrIink[i] = json[i].link;
  }
  let table = document.getElementById('table');

  for (i = 0; i < arrTitle.length; i++) {
    let tr = document.createElement('tr');

    let td1 = document.createElement('td');
    let link = document.createElement('a');
    td1.appendChild(link);
    link.setAttribute('href', 'http://www.e-himart.co.kr' + arrIink[i]);
    link.appendChild(document.createTextNode(arrTitle[i] + ''));

    let td2 = document.createElement('td');
    td2.appendChild(document.createTextNode(arrPrice[i] + ''));

    let td3 = document.createElement('td');
    let img = document.createElement('img');
    img.setAttribute('src', arrImg[i]);

    td3.appendChild(img);

    tr.appendChild(td3);
    tr.appendChild(td1);
    tr.appendChild(td2);

    table.appendChild(tr);
  }
}
```

- json의 변수 갯수만큼 Array객체를 생성함
- for문을 사용해 각 Array객체의[i]값에 json파일의 변수를 넣어줌.
- getElementById를 사용해 table을 지정하고 이 table에 createElement,createTextNode를 사용하여 요소를 생성하게함.

---

### [4월 5일(2)]

```
▶ (2) 회사소개 상세페이지 구현
▶ 카카오맵 API를 활용해 대림대학교 전산관 위치로 지도를 출력하게 하고
자가용 및 도보와 같은 방식의 약도를 구현함.
```

<a href="https://user-images.githubusercontent.com/80302108/161799176-e7c1d45d-eeb6-4d96-a7c4-eb08d4c8c781.png">회사소개</a>

```javascript
<script type="text/javascript" src="//dapi.kakao.com/v2/maps/sdk.js?appkey=9287b9973450a6e825755a3446a897cb"></script>
    <script>
     var mapContainer = document.getElementById('map'), // 지도를 표시할 div
    mapOption = {
        center: new kakao.maps.LatLng(37.40402, 126.93060), // 지도의 중심좌표
        level: 3 // 지도의 확대 레벨
    };

var map = new kakao.maps.Map(mapContainer, mapOption); // 지도 생성

// 마커를 표시할 위치와 내용을 가지고 있는 객체 배열
var positions = [
    {
        content: '<div style="text-align:center; padding-left:35px">대림대학교<br>전산관</div>',
        latlng: new kakao.maps.LatLng(37.40402, 126.93060)
    },

];

for (var i = 0; i < positions.length; i ++) {
    // 마커 생성
    var marker = new kakao.maps.Marker({
        map: map, // 마커를 표시할 지도
        position: positions[i].latlng // 마커의 위치
    });

    // 마커에 표시할 인포윈도우를 생성
    var infowindow = new kakao.maps.InfoWindow({
        content: positions[i].content // 인포윈도우에 표시할 내용
    });

    // 마커에 mouseover 이벤트와 mouseout 이벤트를 등록
    // 이벤트 리스너로는 클로저를 만들어 등록
    // for문에서 클로저를 만들어 주지 않으면 마지막 마커에만 이벤트가 등록
    kakao.maps.event.addListener(marker, 'mouseover', makeOverListener(map, marker, infowindow));
    kakao.maps.event.addListener(marker, 'mouseout', makeOutListener(infowindow));
}

// 인포윈도우를 표시하는 클로저를 만드는 함수
function makeOverListener(map, marker, infowindow) {
    return function() {
        infowindow.open(map, marker);
    };
}

// 인포윈도우를 닫는 클로저를 만드는 함수
function makeOutListener(infowindow) {
    return function() {
        infowindow.close();
    };
}
    </script>
```

- 회사소개에 위치는 필수라고 생각하여 전산관으로 등록함
- 고객마다 회사에 방문하는 방식이 다를 수 있어 다양한 루트별 약도를 표시함

---

### [4월 5일]

```
▶ (1) 나라별 원두 상세페이지 구현
▶ html파일을 여러개 만드는 것 보다 js를 사용해 쿼리스트링값에 따른 내용변경 기능 구현하기로 함
```

<a href="https://user-images.githubusercontent.com/80302108/161799168-b9f3616d-732b-43ee-9b2e-fac4486f66da.png">나라별원두</a>

```javascript
//common.js
kenya = () => {
  location.href = '../beans-info/beans-info.html?beans=kenya';
};
tan = () => {
  location.href = '../beans-info/beans-info.html?beans=tanzania';
};
// ..일부생략
// beans.js
let url = new URL(window.location.href).searchParams;
let url_name = url.get('beans');
let bean_name = document.querySelector('.beans-info > .beans-name');
let bean_img = document.querySelector('.beans-info > img');
let bean_sub = document.querySelector('.beans-sub');

if (url_name == 'kenya') {
  bean_name.innerHTML = '원두이름';
  bean_img.src = '이미지경로';
  bean_sub.innerHTML = '원두소개 내용';
}
```

- JSP시간에 배운 쿼리스트링을 떠올려 a태그 버튼을 누르면 그 원두에 맞는 값이 beans-info.html의 쿼리스트링값으로 들어간다.
- URL메소드를 사용해 받아온 url값을 searchParams속성으로 받아 온 후 , get방식으로 beans라는 쿼리스트링의 변수이름을 가져온다.
- 그 후 dom과 if문을 활용해 변수이름에 따라 상세페이지에 출력될 원두이름과 사진, 원두소개 내용이 바뀌면서 출력된다.

---

### [4월 4일]

```
▶ 드리퍼, 그라인더, 커피메이커 화면 구상
▶ 나라별 원두 슬라이드와 비슷한 hover효과를 주기로함
▶ 상세페이지는 파이썬 크롤링 결과 화면과 함께 추후 제작 예정

```

<a href="https://user-images.githubusercontent.com/80302108/161595246-6d81dc09-3d3a-47af-b18a-ace1acbeac20.PNG">드리퍼,그라인더,메이커</a>

```css
#eq-box > .eq-hover {
  position: absolute;
  transform: translateY(0px);
  width: 300px;
  height: 50px;
  /* border-radius: 20px; */
  background-color: rgba(0, 0, 0, 0.674);
  text-align: center;
  line-height: 50px;
  color: #fff;
  font-weight: 600;
  font-size: 1.7rem;
  transition: transform 0.5s;
  animation: ease-in-out;
}
#eq-box {
  transition: transform 0.5s;
  animation: ease-in-out;
  box-sizing: border-box;
}
#eq-box:hover {
  transform: translateY(-10px);
}

#eq-box:hover > .eq-hover {
  display: block;
  transform: translateY(-50px);
}
```

- 박스 hover시 transition과 transform을 활용한 animation효과를 주었다.
- translate값을 조절하여 hover시 위로 자연스럽게 올라가는 효과이다.

---

### [4월 1일]

```
▶ 원두, 드리퍼, 그라인더, 커피메이커 검색결과 화면 회의
▶ 네이버쇼핑API, 11번가API를 활용하기로해봄
   - php, node.js를 활용하려 했으나 오류로 실패
▶ 파이썬을 활용해 상위 5개항목만 크롤링하기로함

```

```python
from itertools import product
from lib2to3.pgen2.token import AT
from bs4 import BeautifulSoup


def getProductInfo(li):
  # print(li)
  img = li.find("img")
  alt = img['alt']
  imgSrc = img['src']
  aTag = li.find("a", {"class":"prdLink"})
  aHref = aTag['href']

  priceNum = li.find("span", {"class":"discountPrice"})


  return {"img":imgSrc, "alt": alt, 'link': aHref , 'price': priceNum.text.replace(",","")}


def parse(pageString):
  bs0bj = BeautifulSoup(pageString, "html.parser")
  ul = bs0bj.find("ul", {"class":"thumnailType"})
  lis = ul.findAll("li")

  products = []
  for li in lis[:5]:
      product = getProductInfo(li)
      products.append(product)

  return products


```

- 위 코드는 크롤링결과를 파싱해주는 파이썬코드이다.
- BeautifulSoup을 활용해 html.parser기능으로 쇼핑몰의 ul과 li태그의 내용을 추출한다.
- 추출된 내용은 products라는 빈배열에 담기고, 호출 파이썬파일에서 불러올수있다.
- json으로 저장하고 html에서 불러오고 화면에 출력하는 것은 구현중이다.

---

### [3월 31일]

```
▶ 로그인 페이지 디자인
▶ 버튼 hover시 transition ease 효과
▶ 헤더 sidebar 상세구현
▶ 헤더 sidebar는 js가아닌 css로만 구현하기로 결정
▶ 헤더 sidebar는 클릭시 화면 뷰포트를 기준으로 왼쪽에서 나오도록 구현

```

<a href="https://user-images.githubusercontent.com/80302108/161104859-c525542c-9d20-499d-8a96-59cfd64be6b9.PNG">사이드바</a>
,
<a href="https://user-images.githubusercontent.com/80302108/161105223-3c9a8ea5-b013-4bf2-a5be-1269322485bc.PNG">로그인</a>

```css
/* 사이드바 */
input[id='menuicon'] {
  display: none;
}
input[id='menuicon'] + label {
  display: block;
  margin: 30px;
  width: 20px;
  height: 20px;
  position: absolute;
  cursor: pointer;
  top: -13.5px;
  right: 0;
}
input[id='menuicon'] + label span {
  display: block;
  position: absolute;
  width: 100%;
  height: 5px;
  border-radius: 30px;
  background: #000;
  transition: all 0.35s;
}

div[class='sidebar'] {
  width: 300px;
  height: 100%;
  background: rgba(255, 255, 255);
  position: fixed;
  top: 0;
  left: -300px;
  /* 왼쪽에 있다가 나오도록 동작하는 부분 */
  z-index: 9999;
  transition: all 0.35s;
  border-right: 1px solid #ccc;
}
```

---

### [3월 30일]

```
▶ 회원가입,나만의 원두찾기 박스 디자인
▶ 버튼 hover시 transition ease 효과
▶ 회원가입 상세페이지 제작
▶ 회원가입 상세페이지는 input태그를 주로 활용
▶ 나만의 원두찾기는 mbti테스트와 비슷하게 구현하기로 결정

```

<a href="https://user-images.githubusercontent.com/80302108/160864330-3e1f1a03-6ec2-46f3-9fec-83164dbe4e65.PNG">박스</a>
<a href="https://user-images.githubusercontent.com/80302108/160871073-18b25614-aa04-4b2a-8334-fd510b495842.png">회원가입</a>

```html
<p>회원가입</p>
<div class="sign-box">
  <label for="">
    <span>아이디</span>
    <br /><input type="text" name="user_id" id="user-id" />
  </label>
</div>
<div class="sign-box">
  <label for="" id="pass">
    <span class="user-pwd">비밀번호 </span>
    <br /><input type="password" name="user_pwd" id="user-pass" />
  </label>
</div>
```

```css
.info-box > .info-box-two > .inner > a > .sigin-box {
  font-family: 'Noto Sans KR', sans-serif;
  cursor: pointer;
  width: 150px;
  height: 70px;
  border-radius: 10px;
  border: 2px solid #fff;
  text-align: center;
  margin-left: 20px;
  line-height: 70px;
  color: #fff;
  font-weight: bold;
  font-size: 20px;
  letter-spacing: 4px;
  background-color: #aad2da;
  box-shadow: 1px 1px 3px #fff;
  transition: background-color 0.5s ease;
}
.info-box > .info-box-two > .inner > a > .sigin-box:hover {
  background-color: #000;
}
```

---

### [3월 27일]

```
▶ 커피의 효능 이미지 제작 회의
▶ 인터넷 서칭을 통한 커피의 대표적인 효능 4가지 선정
▶ background-size: cover를 사용해 스크롤시 이미지도 스크롤되는 효과추가
▶ 4가지 효능 박스 opacity값 사용해 투명도 추가
▶ 개발은 html과 css로 하기로 결정

```

<a href="https://user-images.githubusercontent.com/80302108/160671833-57df4331-015e-452c-8f56-9d5da129ec9d.PNG">이미지</a>

```css
section.back-img > .coffee-info {
  width: 100%;
  height: 400px;
  background-image: url('../img/커피배경.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
  padding: 50px 20px 0px 20px;
  box-sizing: border-box;
  align-items: center;
}
section.back-img > .coffee-info > .info-1 {
  margin: 0 auto;
  text-align: center;
  width: 500px;
  line-height: 40px;
  height: 40px;
  color: #fff;
  font-size: 1.5rem;
  font-weight: 600;
  background-color: rgba(255, 255, 255, 0.418);
  border: 4px dashed #fff;
}
```

---

### [3월 26일]

```
▶ 나라별 원두 슬라이드 박스 제작
▶ swiper라이브러리 사용 결정
▶ hover 효과 추가 (하단에서 올라오는)
▶ 헤더의 sidebar 클릭시 next,prev버튼 DOM제어
```

```javascript
var swiper2 = new Swiper('.beans-slide', {
  slidesPerView: 3, //한번에 보여줄 슬라이드 개수
  spaceBetween: -50,
  pagination: {
    el: '.beans-slide > .swiper-pagination',
    clickable: true,
  },
  navigation: {
    nextEl: '.swiper-button-next',
    prevEl: '.swiper-button-prev',
  },
});
// 총 7개의 나라별 원두 박스를 제작했다.
// 3개만 화면에 노출되고 나머지 슬라이드는 버튼을통해 확인이 가능하다.
```

```javascript
var count2 = 9;
var nxt = document.querySelector('.beans-box > .swiper-container > .swiper-button-next');
var prev = document.querySelector('.beans-box > .swiper-container > .swiper-button-prev');
function nxtprev() {
  count2 += 1;
  if (count2 % 2 == 0) {
    nxt.style.display = 'none';
    prev.style.display = 'none';
  } else {
    nxt.style.display = 'block';
    prev.style.display = 'block';
  }
}
//count2라는 변수에 9라는 임의의값을 지정해준다.
//querySelector를 통해 원두박스 버튼들을 각각 지정해준다.
//sidebar가 클릭되면 nxtprev함수가 자동으로 호출된다.
//함수가 호출되면 count2변수의 값의 홀/짝여부에 따라 display값이 변경된다.
```

---

### [3월 25일]

```
▶ 사이트 메인 슬라이드 제작
▶ 슬라이드 디자인 회의
▶ 개발은 swiper라이브러리 사용 결정
```

```javascript
var swiper = new Swiper('.mySwiper', {
  spaceBetween: 30,
  centeredSlides: true,
  loop: true,
  autoplay: {
    delay: 2500,
    disableOnInteraction: false,
  },
  pagination: {
    el: '.mySwiper > .swiper-pagination',
    clickable: true,
  },
  navigation: {
    nextEl: '.mySwiper > .swiper-button-next',
    prevEl: '.mySwiper > .swiper-button-prev',
  },
});
// spaceBetween은 슬라이드 사이의 여백값
// centeredSlides는 중간 슬라이드가 가운데 오게하는것
// loop는 반복여부
// autoplay의 delay는 슬라이드가 반복되는 시간주기이다.
//pagination은 슬라이드 숫자만큼 불릿을 생성하는것이다.
//navigation은 해당 스와이퍼 슬라이드의 next,prev버튼을 지정하는것이다.
```

---

### [3월 24일]

```
▶ 사이트 메인 및 서브 색상선정
▶ 헤더 및 로고 디자인 회의
▶ 스크롤 값에 따라 헤더의 GNB메뉴가 position absolute로
   상단에 붙게(위치하게) 설정 / ScrollMagic 라이브러리 사용
```

```javascript
var ctrl = new ScrollMagic.Controller();

new ScrollMagic.Scene({
  triggerElement: this,
  duration: 250,
  triggerHook: 0.25,
})
  .setClassToggle('.header', 'show')
  .addTo(ctrl);
// header의 position값은 absolute이며 show라는 클래스는
// absolute이다. 이는 스크롤이 header가 가려질때까지 내려가면
// show 클래스가 사라지면서 자동으로 header의 position값으로 바뀌게끔 하는것이다.
```

---

### [3월 23일]

```
▶ 팀 편성 및 팀명작
▶ 사이트 주제 회의
▶ 역할 분담 결정
▶ 개발 환경 회의
```

---
