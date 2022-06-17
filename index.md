---
title: 온라인 호스팅 지침
permalink: index.html
layout: home
ms.openlocfilehash: 0c2c63aea8926ec06e02203a9ff9a9a5d5cc9b85
ms.sourcegitcommit: 9f66e4932aaf188d3be327646561dc7fe8e5c7a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2022
ms.locfileid: "143996842"
---
# <a name="content-directory"></a>콘텐츠 디렉터리

다음은 각 랩 연습 및 데모의 하이퍼링크입니다.

## <a name="labs"></a>랩

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| 모듈 | 랩 |
| --- | --- | 
{% for activity in labs  %}| {{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
