---
name: typescript-conventions-minahview
description: "minahview TS 규칙은 .claude/typescript.md에 있고, 코드베이스 실측으로 도출됐다"
metadata: 
  node_type: memory
  type: reference
  originSessionId: 0a076544-e4cd-4621-8574-cbe66b46816d
  modified: 2026-07-29T02:40:46.328Z
---

`minahview/` TypeScript 규칙 파일: `/home/ec2-user/projects/cloud.minahdev/.claude/typescript.md` (frontmatter `paths: **/*.ts, **/*.tsx`).

2026-07-29에 코드베이스 실측으로 작성했다 — `strict: true`, 명시적 `: any` 0건, `type` 112건 vs `interface` 2건(shadcn `use-toast.ts`), `: unknown` 80+건, `type Props = {}`, 문자열 리터럴 유니온(enum 없음), `@/` 별칭, 세미콜론 없음/큰따옴표.

**How to apply:** TS 작업 전 이 파일을 읽는다. 규칙을 바꿀 일이 생기면 추측하지 말고 같은 방식으로 실측(grep 카운트)해서 근거를 남긴다. 미해결 예외는 [[pending-as-any-cleanup]] 참고.