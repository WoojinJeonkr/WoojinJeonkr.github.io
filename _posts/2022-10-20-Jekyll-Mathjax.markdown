---
layout : post
title : Jekyll Mathjax
subtitle : Jekyll에서 수식을 사용하려면 어떻게 해야 할까?
categories : Jekyll
tags : [Jekyll, Skill, Mathjax]
use_math : true
---

## 01. Jekyll Mathjax
- MathJax가 수식 입력의 핵심이다.
- JavaScript 라이브러리로 Tex 문법으로 작성된 수식을 표시해주는 기능을 한다.
- 다른 내용에 inline으로 수식을 입력할 경우 `\\( 입력하고자 하는 내용 \\)` 의 형식으로 입력한다.
- 별도의 줄에 수식을 입력하는 경우 `$$ 입력하고자 하는 내용 $$` 의 형식으로 입력한다.

## 02. Tex 문법
TeX 문법에 대해 알아보고 싶다면 <a href="https://ko.wikipedia.org/wiki/%EC%9C%84%ED%82%A4%EB%B0%B1%EA%B3%BC:TeX_%EB%AC%B8%EB%B2%95" target="_blank" rel="noopener noreferrer" style="color:green">여기</a>를 클릭해보세요!

## 03. 설치
- 따로 설치하는 패키지는 없다.

jekyll blog 폴더의 layout에서 post의 head 부분에 다음 코드를 추가해준다.

```
{% raw %}
{% if page.use_math %}
<script type="text/javascript" id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"></script>
{% endif %}
{% endraw %}
```

그 다음 수식을 이용하고자 하는 페이지의 yaml 부분에 `use_math : true`라고 추가해주면 된다.

## 04. 결과

```
\\(x, x+h \in [a, b] \\)일 때 다음이 성립한다.

$$
F'(x)=\lim_{h \to 0}\frac{1}{h}\int_{x}^{x+h} f(t)dt
$$
```

\\(x, x+h \in [a, b] \\)일 때 다음이 성립한다.

$$
F'(x)=\lim_{h \to 0}\frac{1}{h}\int_{x}^{x+h} f(t)dt
$$

위와 같이 잘 출력된다.

## 05. 참고 자료
- [Jekyll 사이트에 수식 입력하기 (MathJax)](https://blog.studia.blue/web/jekyll-mathjax/)