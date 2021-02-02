# Panorama film animation

브레이킹 뉴스나 필름처럼 긴 컨텐츠가 우측에서 좌측으로 슥 지나가는 효과가 필요하다!

## STEP01. 마크업

1. 컨텐츠를 감싸고 overflow:hidden을 실행할 컨테이너 필요
2. 컨텐츠를 담고있는 요소 필요
3. 개별 items 필요 

```
<!-- 컨테이너 -->
<div class="container">
  <!-- 아이템 리스트 시작 -->
  <ul class="list list-first"> 
    <!-- 개별 아이템s -->
    <li class="item">#hash01</li>
    <li class="item">#hash02</li>
    <li class="item">#hash03</li>
    <li class="item">#hash04</li>
    <li class="item">#hash05</li>
    <li class="item">#hash06</li>
    <li class="item">#hash07</li>
    <li class="item">#hash08</li>
    <li class="item">#hash09</li>
    <li class="item">#hash10</li>
  </ul>
  <!-- 아이템 리스트 마지막 -->
  <ul class="list list-first">
    <li class="item">#hash01</li>
    <li class="item">#hash02</li>
    <li class="item">#hash03</li>
    <li class="item">#hash04</li>
    <li class="item">#hash05</li>
    <li class="item">#hash06</li>
    <li class="item">#hash07</li>
    <li class="item">#hash08</li>
    <li class="item">#hash09</li>
    <li class="item">#hash10</li>
  </ul>
</div>
```

## STEP02. CSS로 위치 잡기

```
// 컨테이너 width 값 설정. overflow:hidden; white-space:nowrap;는 필수 
.container{
  width:995px; 
  height:40px; 
  margin: 0 auto; 
  margin-top:150px; 
  background-color:#eee; 
  border-radius:20px; 
  font-size:0; 
  overflow:hidden; 
  white-space:nowarp; 
}

// 여러 요소 한줄로 정렬. font-size:0으로 여백없음.
.hash_list{
  display:inline-block; 
  vertical-align:top; 
  white-space:nowrap; 
  font-size:0; 
}

.hash_list.list_first{
  -webkit-animation:30s linear infinite slidePanoramaFirst;
  animation:30s linear infinite slidePanoramaFirst;
}
.hash_list.list_last{
  -webkit-animation:30s linear infinite slidePanoramaLast;
  animation:30s linear infinite slidePanoramaLast;
}

.hash_item{ 
  position:relative; 
  display:inline-block; 
  vertical-align:top; 
  padding-right:20px; 
  color:#202020; 
  font-size:15px; 
  line-height:30px; 
  font-family: 'Noto Sans KR', sans-serif;
}

.hash_item:after{
  content:''; 
  position:absolute; 
  top:50%; 
  right:10px; 
  width:1px; 
  height:14px; 
  margin-top:-7px; 
  background-color:#fff;
}
  
```

## STEP3. CSS 애니메이션 

```
.list_first{
  -webkit-animation:30s linear infinite slidePanoramaFirst; 
  animation:30s linear infinite slidePanoramaFirst;
}
.list_last{
  -webkit-animation:30s linear infinite slidePanoramaLast; 
  animation:30s linear infinite slidePanoramaLast;
}  
```
↑ 축약을 쓴거고 풀어서 쓰자면 
이러하다 ↓
```
.list_first{
  animation-name:slidePanoramaFirst; // 애니메이션 이름을 정의 @keyframes 규칙을 이용하여 기술
  animation-duration:30s; // 애니메이션 한 사이클 완료하는데 걸리는 시간
  animation-count:infinite; // 애니메이션 반복 횟수
  animation-timing-function:linear;  // 중간 상태들의 전환을 어떤 시간 간격으로 진행할지 지정
}

```

## STEP4. keyframes  

keyframes 만든다
list가 두개이므로 from과 to를 제외하고 중간 타임라인은 1개만 둔다.
list가 더 있다? 그럼 더 있는 만큼 추가한다. 100 / n 의 값만큼 중간 타임라인을 만든다. 
ex) 100/2 = 50

ㄴ 그러므로 중간 타임라인 50%이다.

```
@keyframes slidePanoramaFirst{
  from{}
  50%{transform:translateX(-100%); opacity:1;}
  50.1%{transform:translateX(100%); opacity:0;}
  50.2%{transform:translateX(100%); opacity:1;}
  99.9%{transform:translateX(0); opacity:1;}
  to{transform:translateX(0); opacity:1;}
}

@keyframes slidePanoramaLast{
  from{transform:translateX(0); opacity:1;}
  50%{transform:translateX(-100%); opacity:1;}
  50.1%{transform:translateX(100%); opacity:0;}
  50.2%{transform:translateX(100%); opacity:1;}
  99.9%{transform:translateX(0); opacity:1;}
  to{transform:translateX(0); opacity:1;}
}
```





## STEP4. CSS 애니메이션 


[결과물 보러가기](https://codepen.io/ju-dayoung/pen/ExNjXXr)
