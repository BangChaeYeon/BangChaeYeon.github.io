---
title: Jekyll Markdown 문법 정리
author: BCY
date: 2022-10-16 15:30:00 +0900
categories: [jekyll, markdown]
tags: [writing]
render_with_liquid: false
---

## 개요

GitHub 블로그에 글을 등록할 때는 .md 파일을 작성하여 _post 폴더에 업로드하는 방식을 사용합니다.  
Jekyll에서 제공하는 .md는 기본 Markdown 문법과 다른 점이 있어서, 따로 문법을 정리해두려고 합니다.  
정리 내용은 계속 추가되거나 변경될 수 있습니다.  

## Basic Format
.md 파일을 작성할 때는 파일 상단에 기본 포맷을 작성해야 합니다.
* title: 게시물의 제목을 지정할 수 있습니다.
* author: 게시물의 작성자를 지정할 수 있습니다. authors 사용 시, 작성자를 여러 명 지정할 수 있습니다.
* date: 게시물 작성 날짜를 지정할 수 있습니다. 날짜는 타임존을 고려하기 때문에, 현재 지역의 타임존을 지정해야 합니다.
* categories: 게시물의 카테고리를 지정할 수 있습니다. 카테고리를 2개 지정할 시, 앞에 나오는 카테고리가 뒤에 나오는 카테고리의 부모가 됩니다.
* tags: 게시물의 태그를 지정할 수 있습니다. 태그는 소문자로 작성되어야 합니다.


> 카테고리는 최대 2개까지 지정할 수 있고, 태그는 개수에 제한이 없으며 지정하지 않을 수 있습니다.
{: .prompt-tip }

---
FORMAT

```yaml
---
title: TITLE
author: <author_id>
OR
authors: [<author1_id>, <author2_id>]
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [TOP_CATEGORIE, SUB_CATEGORIE]
tags: [TAG] 
---
```

> date에 작성한 일자가 현재보다 이후일 경우, 포스팅을 해도 게시글이 보이지 않을 수가 있습니다.
{: .prompt-warning }

### author 설정
`_data/authors.yml`에 설정된 author_id를 author에 지정하면 등록한 정보를 사용할 수 있습니다.

---
FORMAT

```yaml
{author_id}:
    name: {full name}
    twitter: {twitter_of_author}
    url: {homepage_of_author}
```

---
EXAMPLE

```yaml
BCY:
  name: Bang Chae Yeon
#  twitter: no twitter id
  url: https://github.com/BangChaeYeon/
```

## Code
강조하고자 하는 구문을 `로 감싸 표시할 수 있습니다.

---
FORMAT

```md
> `[TEXT]`
```

---
EXAMPLE

```md
> `hello world!`
```

`hello world!`


## Blockquote

`>`를 사용하여 인용문을 표시할 수 있습니다.

---
FORMAT

```md
> [TEXT]
```

---
EXAMPLE

```md
> 하나
>> 둘
>>> 셋
```

> 하나
>> 둘
>>> 셋


## Horizon
`-`를 3개 사용하여 구분선을 그을 수 있습니다.

---
FORMAT

```md
---
```

---
EXAMPLE

```md
문장1

---

문장2
```

문장1

---

문장2


## Code Block

코드나 스크립트 작성 시, 해당 언어에 맞는 뷰어를 사용하여 가독성을 높일 수 있습니다.

---
FORMAT

````md
```[file type]
[CODE TEXT]
```
````

---
EXAMPLE

```java
System.out.println("Hello World.");
```

## Prompt

작성한 텍스트의 유형을 나타내거나 강조를 할 때 사용할 수 있습니다.  

---
FORMAT

```md
> [TEXT]
{: .prompt-[tip, info, warning, danger] }
```

---
EXAMPLE

```md
> 팁 표시
{: .prompt-tip }
```

> 팁 표시
{: .prompt-tip }

```md
> 정보 표시
{: .prompt-info }
```

> 정보 표시
{: .prompt-info }

```md
> 경고 표시
{: .prompt-warning }
```

> 경고 표시
{: .prompt-warning }

```md
> 위험 표시
{: .prompt-danger }
```

> 위험 표시
{: .prompt-danger }


## Table
`-`와 `|`를 사용하여 표를 그릴 수 있습니다.

> 표를 그리기 위해서는 `_config.yml`에서 `toc: true`로 설정해야 합니다.
{: .prompt-info }

---
FORMAT

```md
|[head1]|[head2]|[head3]| ...etc
|---|---|---| ...etc
|[cell1]|[cell2]|[cell3]| ...etc
```

---
EXAMPLE

```md
|1|2|3|
|---|---|---|
|A|B|C|
```

|1|2|3|
|---|---|---|
|A|B|C|

--- 
> 출처
> * 2019-08-08-write-a-new-post.md(Jekyll 기본 제공 md)