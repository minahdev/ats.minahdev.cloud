---
name: verify-pasted-templates
description: 사용자가 붙여넣는 규칙·템플릿은 다른 스택 것일 수 있으니 구조만 차용하고 내용은 검증해서 채운다
metadata: 
  node_type: memory
  type: feedback
  originSessionId: 0a076544-e4cd-4621-8574-cbe66b46816d
  modified: 2026-07-29T02:40:38.765Z
---

사용자는 책·블로그의 예시 규칙을 그대로 붙여넣으며 "이 내용 참조해서 추가해줘"라고 요청한다. 그 예시가 이 저장소와 **다른 스택**을 전제할 때가 있다.

**Why:** 2026-07-29 루트 `CLAUDE.md` 작업에서 붙여넣은 템플릿이 Node.js REST API / PostgreSQL+Redis / Jest+Supertest / `src/legacy/` / payments PCI 기준이었다. 실제로는 FastAPI + Next.js 모노레포이고 `src/legacy/`도 payments도 없다. 그대로 넣었으면 CLAUDE.md에 거짓 정보가 들어가고 §4 "추측으로 invent 금지"에도 걸린다.

**How to apply:** 붙여넣은 템플릿은 **섹션 목록(체크리스트)으로만** 쓰고, 각 섹션 내용은 설정 파일에서 확인한 사실로 채운다 — `package.json`, `pytest.ini`, `.pre-commit-config.yaml`, `docker-compose.yaml`, `git branch -a`, 코드의 `process.env.*`/`os.getenv(*)`. 저장소에 없는 항목(예: `develop` 브랜치)은 지어내지 말고 "없음 + 필요하면 확인"으로 남긴다. 불일치는 응답 앞머리에서 한두 문장으로 짚되 작업은 끝까지 진행한다.