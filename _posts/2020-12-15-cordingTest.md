---
title: 자바스크립트 코딩테스트
categories: [JavaScript]
comments: true
---

# 프로그래머스 코딩테스트
프로그래머스에서 나온 문제들을 풀어보고 해석해본것을 작성한 문서입니다.

## 1단계

### 가운데 글자 가져오기

- 문제
    [가운데글자가져오기](githubpage\assets\img\코테_가운데글자가져오기.png)

- 풀이
    [너굴의SURI블로그](https://blog.naver.com/tcloe8/221562781862)
    ``` javascript
    function solution(s) {
        var num = 0;
        var str = '';

        if(s.length%2 ==0) {
            num = parseInt(s.length/2)-1;
            str += s[num];
            str += s[num+1];

            return str;
        } else {
            num = parseInt(s.length/2);
            str += s[num];

            return str;
        }
    }
    ```

    받은 문자열이 짝수일때와 홀수일 때로 나눔

    - 짝수일 경우
        qwer란 문자가 있으면,  
        길이 4=>  
        we만 출력.  
        인덱스로 보면 [1], [2] =>  
        int(길이/2)-1를 변수 num에 받음 =>  
        시작 인덱스: s[num] =>  
        그 다음 인덱스: s[num+1]
    
    - 홀수인 경우
        abcde란 문자가 있으면,  
        길이 5=>  
        c만 출력.  
        인덱스로 보면 [2] =>  
        int(길이/2)를 변수 num에 받음 =>  
        시작 인덱스: s[num]