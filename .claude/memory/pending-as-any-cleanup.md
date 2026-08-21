---
name: pending-as-any-cleanup
description: "minahview의 `as any` 5곳 정리가 승인 거부로 미적용 상태 — 재요청 시 계획대로 진행"
metadata: 
  node_type: memory
  type: project
  originSessionId: 0a076544-e4cd-4621-8574-cbe66b46816d
  modified: 2026-07-29T02:40:29.521Z
---

2026-07-29 기준 `minahview/`에 `as any` 5곳이 남아 있고, 정리 편집이 승인 거부돼 **적용되지 않았다**.

- `app/api/titanic/james/upload/route.ts:29`
- `app/api/titanic/walter/passengers/route.ts:15`
- `app/api/vision/upload/route.ts:29`
- `app/api/vision/recognize/route.ts:29`
- `components/titanic-csv-upload.tsx:70`

**Why:** [[typescript-conventions-minahview]]의 "any 금지"와 현실이 어긋난 상태다. `.claude/typescript.md`에는 "레거시 — 늘리지 말 것"으로 기록해 뒀다.

**How to apply:** 사용자가 정리를 다시 요청하면 — route 4개는 `(data as any).detail` → `data.detail` (TS 5.7에서 `"detail" in data` 가드가 이미 좁혀주므로 캐스트 불필요), `titanic-csv-upload.tsx`는 `as any` → 명시적 응답 타입 별칭. 요청 없이 먼저 손대지 않는다.