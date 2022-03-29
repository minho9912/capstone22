## 201840135 최민호

```
팀명: Double (더블)

팀원: 최민호(팀장 | 웹퍼블리싱) , 오승엽(팀원 | 웹디자인)
```

- 졸업작품 소개사이트 : (미완성)

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

---

### [3월 27일]

```
▶ 커피의 효능 이미지 제작 회의
▶ 인터넷 서칭을 통한 커피의 대표적인 효능 4가지 선정
▶ background-size: cover를 사용해 스크롤시 이미지도 스크롤되는 효과추가
▶ 4가지 효능 박스 opacity값 사용해 투명도 추가
▶ 개발은 html과 css로 하기로 결정
[이미지](https://user-images.githubusercontent.com/80302108/160671833-57df4331-015e-452c-8f56-9d5da129ec9d.PNG)
```

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
