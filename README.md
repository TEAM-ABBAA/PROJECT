<img width="1920" height="1079" alt="image" src="https://github.com/user-attachments/assets/7b211f3b-40c5-4655-9531-ab3edac01cef" />

## 신한은행 금융인증서
```
💡 금융인증서 발급·검증 서비스의 보안 인프라 분석 및 설계 프로젝트
📆 2026/06/10/수 ~ 2026/07/01/수
🏆 1차 프로젝트 2등상
```
<img width="1913" height="1078" alt="image" src="https://github.com/user-attachments/assets/faecb1dc-96e3-4ce4-af40-88da53a86e83" />

---

### 🏦 금융인증서 발급부터 검증까지

본 프로젝트는 금융인증서 발급 및 검증 서비스를 대상으로 사용자 인증부터 인증서 발급·검증, 상태 확인, 감사 로그까지의 전체 처리 흐름을 분석하고 보안 인프라를 설계했습니다.

금융인증서를 단순한 인증 수단이 아닌 신뢰 기반의 인증 인프라로 바라보고,
네트워크 분리·접근 제어·암호화·로그 관리·취약점 대응 정책을 함께 설계했습니다.

---

### 🔎 왜 금융인증서인가?

금융인증서는 사용자의 신원을 증명하고 금융 서비스 접근 권한을 결정하는 핵심 수단입니다.
```
- 인증 과정에서 개인정보 및 금융정보 처리
- 인증서와 개인키에 대한 높은 수준의 보호 필요
- 인증서 위·변조 및 폐기 상태 검증 필요
- 인증 실패와 이상 접근에 대한 추적 및 감사 필요
```
따라서 인증서 발급과 검증 과정 전체를 보호하는 인프라 설계를 프로젝트의 핵심 과제로 선정했습니다.

---

### 🛡️ 우리가 설계한 보안 구조
1️⃣ 금융인증서 발급
> 사용자 본인 확인 → SMS/ARS/OTP 인증 → PIN 검증 → 인증서 생성 및 저장

2️⃣ 금융인증서 검증
> 인증서 상태 확인 → CRL/OCSP 검증 → 서명 및 PIN 검증 → 인증 성공 처리

3️⃣ 4-Zone 네트워크 분리
> Public → DMZ → Application → Data  
> 외부 접근 구간과 핵심 데이터 구간을 분리하여 공격 확산을 최소화했습니다.

4️⃣ 관리자 접근 통제
> 관리자 PC → VPN/VDI → Bastion Server → 내부 시스템  
> 일반 사용자 경로와 관리자 접근 경로를 분리하고 MFA 및 RBAC 기반으로 접근을 통제했습니다.

---

### 🔐 주요 보안 설계
HTTPS / TLS 1.3 및 내부 구간 mTLS
개인정보 및 DB 암호화
KMS / HSM 기반 암호키 보호
RBAC 기반 최소 권한 적용
MFA 및 인증 시도 제한
CRL / OCSP 기반 인증서 상태 검증
Audit Log 중앙 관리 및 Append-Only 저장
SIEM 기반 이상 행위 탐지
관리자 Bastion Server 접근 통제

---

### ⚠️ OWASP Top 10 기반 취약점 분석

금융인증 서비스의 특성을 고려하여 OWASP Top 10 전 항목을 검토하고,
발급 및 검증 과정에서 영향도가 높은 주요 위협을 중심으로 분석했습니다.

주요 분석 영역

A01 접근 제어 오류
A04 암호화 오류
A07 인증 실패
A08 무결성 오류

외부 공격뿐만 아니라 권한 오남용·내부자 악성 행위·운영 실수·물리적 위협까지 구분하여 대응 방안을 설계했습니다.

---

### 📋 주요 정책

사용자 식별 및 본인인증 정책
PIN 및 인증 시도 제한 정책
MFA 정책
관리자 계정 및 DB 접근 권한 정책
개인정보 및 DB 암호화 정책
키 관리 정책
로그 기록·보관 및 SIEM 연계 정책
백업 및 장애 대응 정책

---

👥 Team ABBAA
| PM | 팀원 A | 팀원 B | 팀원 C | 팀원 D |
| :---: | :---: | :---: | :---: | :---: |
| <img width="120px" src="https://avatars.githubusercontent.com/u/111678149?v=4" /> | <img width="120px" src="https://avatars.githubusercontent.com/u/308309430?v=4" /> | <img width="120px" src="" /> | <img width="120px" src="https://avatars.githubusercontent.com/u/327895597?v=4" /> | <img width="120px" src="https://avatars.githubusercontent.com/u/308302765?v=4" /> |
| 노정희 | 박신규 | 유수연 | 원태현 | 피준원 |
| [@and-noh](https://github.com/and-noh) | [@Sin919](https://github.com/Sin919) | [@] | [@home9534](https://github.com/home9534) | [@pijunwon-cell](https://github.com/pijunwon-cell) |
| 프로젝트 관리<br> 문서 검수<br> 인프라 구성도<br> PPT 디자인 | 서비스 시퀀스<br> OWASP 분석 | 자료 조사<br> 용어 정리 | OWASP 분석<br> 발표 | 서버 구성<br> 네트워크 구성 |
> [!NOTE]
> ABBAA는 팀원들의 혈액형을 조합하여 '아빠'라는 이름을 유머러스하게 표현한 팀명입니다.  
> 아빠처럼 든든하게 인프라를 지키겠다는 목표를 포함하고 있습니다.

---

### 🎯 Project Outcome

금융인증서의 발급부터 검증까지 전체 흐름을 분석하고,
네트워크·서버·인증·데이터·로그를 하나의 보안 아키텍처로 연결하여 설계하는 경험을 확보했습니다.

단순한 기능 구현을 넘어
“인증을 어떻게 만들 것인가”가 아닌 “인증을 어떻게 안전하게 보호할 것인가”​에 집중한 프로젝트입니다.
