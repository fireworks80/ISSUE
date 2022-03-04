# UI ISSUE

어떻게 만들었는지 궁금한 것들 prototype으로 만들어 봄

## apple 주문 트래커 [예제](/order-tracker/index.html)

작은 화면에서 가로로 스크롤 되는 트래커
하지만 가로 스크롤이 보이지 않는다.

![Alt text](/order-tracker/img-tracker.png)

<hr/>

**몰랐던 부분**

![Alt text](/order-tracker/img-block-box.png)

A 요소(부모) padding: 0 10vw
B 요소(자식) width: 900 이기 떄문에
A 요소의 오른쪽은 초록색으로 보이다시피 여백을 갖게 되지만 자식요소가 overflow 된다.

**해결**
A 요소(부모)의 너비를 inline-block일 경우 포함블록의 너비가 된다. 즉 자신은 inline 요소의 성격을 띄는 블록 요소가 된다. [display 링크](https://www.w3.org/TR/CSS22/visuren.html#propdef-display)

**가로스크롤 안보이기**
처음에는 스크롤 높이 만큼을 숨기는 줄 알았지만... 브라우져별 스크롤 모양이나 크기가 다르므로 불가능 함.

```
 .요소::-webkit-scrollbar {
    display: none;
  }
```

를 하게되면 해당 요소의 스크롤을 안보이게 한다.

<hr />

## safari thead gradient issue

![image](https://user-images.githubusercontent.com/8033966/156692728-cfd7c9da-12dd-4a8b-8ba1-6eb8ed4e0c12.png)

```
background: linear-gradient(90deg, #121212 0%, #874ECC 100%);
```
thead에 gradien 를 넣었지만 각 th 셀마다 그라이언트가 적용이 됨

**해결**
```
background-attachment: fixed;
```
로 해결

```
