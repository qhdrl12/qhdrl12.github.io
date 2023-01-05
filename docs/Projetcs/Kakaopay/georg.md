---
layout: default
title: GeoRG
parent: Kakaopay
nav_order: 1
---

# Typography
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
   {:toc}

---

## Introduction

IP 기반 국가 코드 및 대략적인 도시 정보를 제공하는 서비스

## Purpose

외국환거래 규정에 따라 해외결제 서비스가 지원되는 국가에서는 송금 받기가 제한 되어야 하는 등, 
각 서비스별로 클라이언트에서 받은 IP가 해외결제국인지에 대한 확인 니즈로 부터 시작된 프로젝트 입니다.   

[maxmind](https://www.maxmind.com/en/geoip2-services-and-databases) 사의 GeoIP를 데이터베이스로 사용하였습니다.
{: .fs-5 .ls-10 .code-example }

## Font stack

By default, Just the Docs uses a native system font stack for sans-serif fonts:

```scss
system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif
```

ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz
{: .fs-5 .ls-10 .code-example }

For monospace type, like code snippets or the `<pre>` element, Just the Docs uses a native system font stack for monospace fonts:

```scss
"SFMono-Regular", Menlo, Consolas, Monospace
```

ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz
{: .fs-5 .ls-10 .text-mono .code-example }

---

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

[View typography utilities]({{ site.baseurl }}{% link docs/utilities/utilities.md %}#typography){: .btn .btn-outline }