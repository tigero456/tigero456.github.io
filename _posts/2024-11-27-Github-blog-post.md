---
title: "마크다운 문법"

writer: Changhee Kim
categories:
    - Github Blog
tags:
    - [Blos, jekyll, Github, Git, markdown]

toc: true
toc_sticky: true

date: 2024-11-27
last_modified_at: 2024-11-27
---
 마크다운 문법을 이용해 md파일을 작성하여 Github blog에 포스팅 해보자.
<br/>

### 1. 제목
> #### 제목
> ##### 제목
> ###### 제목

<br/>

### 2. 목록
> - 항목 1
> - 항목 2

<br/>

### 3. 링크
> [google](https://google.com)<br/>
[naver](https://naver.com)<br/>
문서 내 [참조 링크] 사용가능<br/>

[참조 링크]: https://tigero456.github.io
<br/>

### 인용문
> Text

<br/>

### 강조
> normal<br/>
**Bold**<br/>
_Italic_<br/>
<u>underline</u><br/>
~~LineThrough~~

<br/>

### 줄바꿈
> 줄<br/>바<br/>꿈

<br/>

### 수평선

---
<br/>

### 코드블럭
```java
public class A {
    public static void main(String[] args) {
        System.out.println("Hello, Honeymon");
    }
}
```
<br/>

### 표

| 열1 | 열2 | 열3 |
| --: | :-- |:--:|
| 행1 | --: | 우측 정렬 |
| 행2 | :-- | 좌측 정렬 |
| 행3 | :--: | 가운데 정렬 |

</br>

### 이미지
![Github image](/image/github.png)