> **통합 안내:** 현재 개발은 [DYNOSTY/dynosty](https://github.com/DYNOSTY/dynosty)에서 진행합니다.
> 아래 내용은 이전 4개 레포 구성의 기록입니다. 최신 구조와 역할은 통합 레포 README를 확인해 주세요.

# DYNOSTY Infra — 배포와 서버 운영

DYNOSTY는 웹 브라우저에서 즐기는 3D 생존·도시 경영 게임입니다.
이 레포는 **게임과 서버를 이용할 수 있도록 실행 환경을 준비하고 관리**합니다.

> 현재는 개발 계획을 정리한 단계입니다. 아래 구성은 앞으로 준비합니다.

## 맡은 일

- Web과 API를 배포하는 설정·절차를 관리합니다.
- API와 데이터베이스가 서버에서 실행되도록 준비합니다.
- HTTPS 연결, 서비스 상태 확인, 데이터 백업·복구 절차를 관리합니다.

## 사용할 환경과 기술

| 환경·기술 | 쉽게 말하면 |
| --- | --- |
| Hostinger KVM 2 | API와 데이터베이스를 실행할 초기 가상 서버 후보 |
| PostgreSQL | 계정·저장 기록을 보관하며 백업해야 할 데이터베이스 |
| HTTPS | 브라우저와 서버가 안전하게 통신하는 연결 |
| 배포·운영 설정과 문서 | 실행·업데이트·장애 복구 방법을 기록한 자료 |

## 다른 레포와의 연결

```text
플레이어 PC: Web + Core → 3D 화면·게임 계산
                    ↕ HTTPS
서버: API + PostgreSQL → 계정·온라인 저장

Infra는 배포와 서버 운영 환경을 관리
```

- [Web](https://github.com/DYNOSTY/dynosty-web)과 [API](https://github.com/DYNOSTY/dynosty-api)의 배포할 버전을 관리합니다.
- [Core](https://github.com/DYNOSTY/dynosty-core)는 Web·API에 포함되며 별도 서버가 필요하지 않습니다.
- 3D 그래픽은 플레이어 PC에서 처리하므로 별도 GPU 서버를 전제로 하지 않습니다.

KVM 2는 초기 후보입니다. 최종 서버 구성과 수용 인원은 실제 부하 측정 후 결정합니다.
이 레포에는 **비밀번호·토큰·실제 사용자 데이터와 백업 파일을 올리지 않습니다.**
