# Panorama film animation

브레이킹 뉴스나 필름처럼 긴 컨텐츠가 우측에서 좌측으로 슥 지나가는 효과가 필요하다!

## STEP01. 마크업

컨텐츠를 감싸고 overflow:hidden을 실행할 컨테이너 필요
컨텐츠를 담고있는 요소 
개별 요소들 : item

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
  <!-- 아이템 리스트 중간 -->
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


