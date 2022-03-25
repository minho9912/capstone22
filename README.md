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

## [개발일지]

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
// header의 position값은 absolute이며 show라는 클래스는 absolute이다. 이는 스크롤이 header가 가려질때까지 내려가면 show 클래스가 사라지면서 자동으로 header의 position값으로 바뀌게끔 하는것이다.
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
