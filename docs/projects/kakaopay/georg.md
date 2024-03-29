---
layout: default
title: GeoRG
parent: Kakaopay
grand_parent: Projects
permalink: /docs/projects/kakaopay/georg/
---

# IP 기반 국가 코드 제공 서비스 
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Introduction

외국환거래 규정에 따라 해외결제 서비스가 지원되는 국가에서는 송금 받기가 제한 되어야 하는 등, 
각 서비스별로 클라이언트에서 받은 IP가 해외결제국인지에 대한 확인 니즈로 부터 시작된 프로젝트 입니다.   

IP <-> 국가 코드 변환 데이터베이스는 maxmind를 사용했습니다.

[maxmind](https://www.maxmind.com/en/geoip2-services-and-databases){: .btn .btn-outline }

## Components

#### GeoRG-API
```markdown
- IP 기반 국가코드, 도시 정보를 제공 하는 API
- 업데이트 database 정보가 카프카로 컨슈밍 되면, 해당 database 를 스토리지에서 다운로드 하며 메모리에 업로드 합니다.
```

#### GeoRG-Downloader
```markdown
- maxmind database 는 매주 화요일에 기준으로 업데이트 되며, 업데이트를 위해 [geoipupdate](https://github.com/maxmind/geoipupdate)를 사용합니다.
- Downloader 는 새로운 버전의 database 가 존재할 경우 다운로드 받으며, 스토리지에 업로드 합니다. 이후 업로드 된 database 와 시간을 카프카로 발행합니다.
- geoipupdate 라이브러리는 Dockerfile 에서 관리합니다.
```

#### GeoRG-Core
```markdown
- API, Downloader 공통으로 사용하는 Domain, Kafka, Storage Client 기능을 정의하는 라이브러리 모듈
```

## Skills
- Java, Spring, Gradle, K8S, Kafka, HDFS, Grafana