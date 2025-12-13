# 🛡️  MCP 서버 취약점 분석 및 보안 연구
<div align="center">
Model Context Protocol Server Vulnerability Analysis Project
</div>

## 📖 프로젝트 소개 (Introduction)

본 프로젝트는 K-Shield Jr. 15기에서 경로이탈(Off-course)이 진행한 MCP(Model Context Protocol) 서버 취약점 분석 프로젝트입니다.
최근 AI 에이전트의 확장을 위해 Anthropic, OpenAI 등이 채택한 표준 프로토콜인 MCP가 빠르게 확산됨에 따라, 이에 대한 보안 위협 또한 증가하고 있지만 MCP Server들은 무분별하게 생성되고 있습니다. 이에 MCP Server들이 가지는 취약점들을 조사하고 분석하여 이를 기반으로 실제 공개된 MCP Server 구현체에서 취약점을 찾아 생태계 보안 강화에 기여하고자 했습니다.


## 🎯 프로젝트 목표

1. 오픈소스 MCP 서버 취약점 발굴: 다양한 언어(Python, JS 등)로 구현된 MCP 서버 분석

2. 공격 시나리오 검증: LLM을 통한 간접 프롬프트 인젝션(Indirect Prompt Injection) 가능성 확인

3. 책임 있는 공개: 발견된 취약점 제보 및 CVE 발급 추진, PR을 통한 코드 수정 제안


## 🛠️ 분석 방법론 (Methodology)

저희 팀은 다음과 같은 단계적 접근 방식을 통해 취약점을 분석했습니다.

1. 정보 수집 (Information Gathering):

- GitHub 공개 MCP 서버 리스트업 및 기존 CVE 분석 (CVE-2025-XXXX 등)

2. 정적 분석 (Static Analysis):

- 소스 코드 리뷰를 통한 위험 함수(exec, eval, subprocess, open 등) 식별

- 입력값 검증 로직(Sanitization)의 미흡점 파악

3. 동적 분석 (Dynamic Analysis):

- 자동화 스크립트를 이용한 위험 함수 식별 자동화 및 Payload 전송 테스트

- MCP 프로토콜 메시지(JSON-RPC) 캡처 및 변조

4. PoC 개발 (Proof of Concept):

- 실제 LLM(Claude, Gemini) 환경에서의 공격 시나리오 구현

- 내부망 모의 서버 구축을 통한 SSRF 및 데이터 유출 시연


## 📂 리포트 및 자료 (Resources)
<div align="center">
더 자세한 기술적 내용과 PoC 코드는 첨부된 보고서 및 리포지토리 내 파일들을 참고해 주세요.
</div>

## CVE
- [CVE-2025-63603](https://www.cve.org/CVERecord?id=CVE-2025-63603)
- [CVE-2025-63604](https://www.cve.org/CVERecord?id=CVE-2025-63604)
- [CVE-2025-65512](https://www.cve.org/CVERecord?id=CVE-2025-65512)
- [CVE-2025-65513](https://www.cve.org/CVERecord?id=CVE-2025-65513)

## 👥 팀 소개 (Team Off-Course)

**K-Shield jr 15기 취약점 분석 과정, 경로이탈 (Off-course)**

 PM  | 안용준 | [@Polestar](https://github.com/P0LESTAR)

Team | 황덕연 | [@D30kY](https://github.com/D30kY)

Team | 최원우 | [@CHOE](https://github.com/choewonwoo1817)

Team | 문범수 | [@L1v0z](https://github.com/L1v0z)

Team | 이창민 | [@ChangminLee](https://github.com/brokenheadEDM)

