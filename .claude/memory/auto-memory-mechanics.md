---
name: auto-memory-mechanics
description: 자동 메모리 로드 규칙(MEMORY.md 200줄 제한)과 활성화/비활성화 방법
metadata: 
  node_type: memory
  type: reference
  originSessionId: 0a076544-e4cd-4621-8574-cbe66b46816d
  modified: 2026-07-29T02:49:15.601Z
---

## 로드 방식

- `MEMORY.md`의 **첫 200줄**이 매 세션 시작 시 시스템 프롬프트에 자동 로드된다.
- 200줄을 넘는 부분은 자동 로드되지 않는다 — 필요할 때 직접 읽어야 한다.
- 상세 내용은 주제별 파일로 분리하고, `MEMORY.md`에는 한 줄 포인터만 남긴다. 주제 파일은 **필요할 때만** 읽힌다.
- 200줄 제한은 `MEMORY.md`에만 적용된다. `CLAUDE.md`는 길이와 무관하게 전체가 로드된다 (다만 200줄 이내로 유지하면 지시사항 준수율이 올라간다).

## 활성화 / 비활성화

기본값은 활성화. 끄는 방법 두 가지:

```bash
export CLAUDE_CODE_DISABLE_AUTO_MEMORY=1
```

```json
{ "autoMemoryEnabled": false }
```

되돌리려면 환경변수를 지우거나 `autoMemoryEnabled`를 `true`로 둔다. `/memory` 명령어의 토글로도 전환된다.

## 이 프로젝트 현재 상태 (2026-07-29 확인)

- `CLAUDE_CODE_DISABLE_AUTO_MEMORY` 미설정, `settings.json`에 `autoMemoryEnabled` 없음 → **활성화 상태**.
- `MEMORY.md` 5줄 — 200줄 제한에 여유 있음.
- 루트 `CLAUDE.md`는 200줄을 넘는다. 전체 로드는 되지만, 준수율을 생각하면 §7~§12 확장분을 `_docs/`로 빼는 걸 검토할 만하다.

**How to apply:** `MEMORY.md`가 200줄에 가까워지면 내용을 주제 파일로 옮기고 인덱스 줄만 남긴다. 인덱스에 본문을 쌓지 않는다.