---
title: 온라인 호스팅 지침
permalink: index.html
layout: home
---

# 콘텐츠 디렉터리

다음은 각 랩 연습 및 데모의 하이퍼링크입니다.

> **참고**: 콘텐츠에 버그가 발견되면[GitHub 리포지토리에 새 이슈를 생성](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/issues/new/choose)하세요.

## 랩 연습

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| 모듈 | 랩 |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## 데모

{% assign demos = site.pages | where_exp:"page", "page.url contains '/Instructions/Demos'" %}

| 데모 |
| --- |
{% for activity in demos  %}| [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
