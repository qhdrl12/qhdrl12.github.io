---
layout: default
title: FaceAuth
parent: Kakaopay
grand_parent: Projects
permalink: /docs/projects/kakaopay/faceauth/
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

## Roles

<div class="code-example" markdown="1">
솔루션 내부 구축을 위한 전체 서비스 구성 및 이슈 대응 
내부 인프라 사용을 위한 InfraAdaptor 라이브러리 개발 및 솔루션 적용
인증 수단 적용을 위한 계정계 연동  
로그 수집을 위한 파이프라인(카프카-하둡) 구성
</div>

## Components

#### api
```markdown
- IP 기반 국가코드, 도시 정보를 제공 하는 API
- 업데이트 database 정보가 카프카로 컨슈밍 되ㄴ면, 해당 database 를 카카오 스토리지에서 다운로드 하며 메모리에 업로드 합니다.
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


## Skills

