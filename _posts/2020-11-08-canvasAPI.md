---
title : "canvasAPI"
category :
    - JavaScript
tag :
    - JavaScript
toc : true
---

# canvas
css는 물론 js에서까지 사이즈를 정해줘야 정상적으로 선이 그려짐

### HTMLCanvasElement.getContext()
canvas의 드로잉 context를 반환하는 메소드
드로잉에 필요한 속성과 함수를 가진 객체를 생성함
context 식별자가 지원되지 않을 경우 null을 반환함

context의 뜻은 맥락, 문맥임!

- 파라미터(매개변수)
    - 2d
    - webgl (3d를 구현)

- 속성
    1. fill (채우기)
        - fill
        ```
        ctx.fill
        ```
        내부가 채워진 도형을 그리는 메서드

        - fillRect
        ```
        ctx.fillRect(x, y, width, height)
        ```
        색칠된 사각형을 그림
        x, y는 시작좌표를 width와 height는 사각형의 크기를 지정함

        - fillStyle
        ```
        ctx.fillStyle = '#fff'
        ```
        도형을 채울 색상을 정하는 메소드

    2. stroke
        - stroke
        ```
        ctx.stroke
        ```
        윤곽선을 이용하여 도형을 그리는 메소드

        - strokeRect
        ```
        ctx.strokeRect(x,y,width,height)
        ```
        윤곽선만 그림
        x, y는 시작좌표를 width와 height는 사각형의 크기를 지정함

        - strokeStyle
        ```
        ctx.strokeStyle = #fff;
        ```
        도형의 외곽선 색상을 지정하는 메소드

        - clearRect
        ```
        ctx.clearRect(x,y,width,height)
        ```
        지정된 사각형 영역을 지우고 완전히 투명하게 만드는 메소드
        x, y는 시작좌표를 width와 height는 지우고 싶은 영역의 크기를 지정함

    3. path
        - beginPath
        ```
        ctx.beginPath()
        ```
        새로운 경로를 만드는 메소드

        - closePath
        ```
        ctx.closePath()
        ```
        현재 하위 경로의 시작 부분과 연결된 직선을 추가하는 메소드

    4. 기타
        - moveTo
        ```
        ctx.moveTo(x, y)
        ```
        펜을 지정된 좌표로 옮기는 메소드
    
        - lineTo
        ```
        ctx.lineTo(x, y)
        ```
        현재 드로잉 위치에서 지정된 위치까지 선을 그리는 메소드
        시작점은 이전에 그려진 경로에 의해 결정되며, moveTo 메소드를 통해 시작점 변경이 가능


참조 [Jaeeun_새싹개발자](https://blog.naver.com/jaeeun_98/222098143439 '네이버 블로그')


.lineWidth
선의 두께를 설정함

```
ctx.lineWidth = value;
```