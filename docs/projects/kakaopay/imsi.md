---
layout: default
title: Imsi
parent: Kakaopay
grand_parent: Projects
permalink: /docs/projects/kakaopay/imsi/
---

# 카카오페이 얼굴인식 서비스
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Introduction

카카오페이의 송금/결제/전자서명 등에서 비밀번호, 지문인식과 같이 사용자의 얼굴 이미지를 하나의 인증수단으로 활용할수 있도록 제공하기 위한 서비스 입니다.
Zoloz 솔루션을 사용합니다.(클라이언트 SDK, 서버 컴포넌트)

## ROLE

솔루션 내부 구축을 위한 전체 서비스 구성
내부 인프라 사용을 위한 InfraAdaptor 라이브러리 개발 및 솔루션 적용

## Components

#### api
```markdown
- IP 기반 국가코드, 도시 정보를 제공 하는 API
- 업데이트 database 정보가 카프카로 컨슈밍 되면, 해당 database 를 카카오 스토리지에서 다운로드 하며 메모리에 업로드 합니다.
```

#### algorithm
```markdown
- maxmind database 는 매주 화요일에 기준으로 업데이트 되며, 업데이트를 위해 [geoipupdate](https://github.com/maxmind/geoipupdate)를 사용합니다.
- Downloader 는 새로운 버전의 database 가 존재할 경우 다운로드 받으며, 카카오 스토리지에 업로드 합니다. 이후 업로드 된 database 와 시간을 카프카로 발행합니다.
- geoipupdate 라이브러리는 Dockerfile 에서 관리합니다.
```

#### decision
```markdown
- API, Downloader 공통으로 사용하는 Domain, Kafka, Storage Client 기능을 정의하는 라이브러리 모듈
```

#### admin 
```markdown

```

## Responsive type scale

Just the Docs uses a responsive type scale that shifts depending on the viewport size.

| Selector              | Small screen size `font-size`    | Large screen size `font-size` |
|:----------------------|:---------------------------------|:------------------------------|
| `h1`, `.text-alpha`   | 32px                             | 36px                          |
| `h2`, `.text-beta`    | 18px                             | 24px                          |
| `h3`, `.text-gamma`   | 16px                             | 18px                          |
| `h4`, `.text-delta`   | 14px                             | 16px                          |
| `h5`, `.text-epsilon` | 16px                             | 18px                          |
| `h6`, `.text-zeta`    | 18px                             | 24px                          |
| `body`                | 14px                             | 16px                          |

---

## Headings

Headings are rendered like this:

<div class="code-example">
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
</div>
```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

---

## Body text

Default body text is rendered like this:

<div class="code-example" markdown="1">
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</div>
```markdown
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
```

---

## Inline elements

<div class="code-example" markdown="1">
Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](another-page).
</div>
```markdown
Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](another-page).
```

---

## Typographic Utilities

There are a number of specific typographic CSS classes that allow you to override default styling for font size, font weight, line height, and capitalization.

[View typography utilities]({{ site.baseurl }}{% link docs/projects/kakaopay/georg.md %}){: .btn .btn-outline }