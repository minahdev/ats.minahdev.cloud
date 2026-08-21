---
paths:
  - "**/*.ts"
  - "**/*.tsx"
---

## TypeScript 규칙

`minahview/` (Next.js App Router)에서 이미 쓰는 패턴을 유지한다. 새 규칙을 발명하지 말고 주변 파일 스타일을 따른다.

### 기본

- **strict mode 필수** — `minahview/tsconfig.json`의 `"strict": true`를 끄거나 개별 옵션으로 완화하지 않는다.
- **`any` 타입 사용 금지** — 명시적 `: any` 어노테이션은 현재 0건이다. 유지한다.
  - 외부 JSON 등 모르는 값은 `unknown`으로 받고 좁힌다 (코드베이스에 `: unknown` 80+건).
    ```ts
    const data: unknown = await res.json().catch(() => ({}))
    if (data && typeof data === "object" && "detail" in data) { ... }
    ```
  - 기존 `as any` 5곳(`app/api/**/route.ts` 3곳, `app/api/vision/*`, `components/titanic-csv-upload.tsx`)은 레거시다. **늘리지 않는다.** 새 코드는 `as { detail?: unknown }`처럼 좁은 캐스트를 쓴다.
- **인터페이스보다 타입 별칭 선호** — `type` 112건 / `interface` 2건. 새 선언은 전부 `type`.

### 선언 패턴

- 컴포넌트 props: 파일 안에서 `type Props = { ... }` 또는 `type XxxProps = { ... }` (export 안 함).
- 도메인 값 집합은 문자열 리터럴 유니온으로. enum 쓰지 않는다.
  ```ts
  export type Gender = "male" | "female"
  export type WeeklyExerciseGoal = "1_2" | "3_4" | "5_plus"
  ```
- 공용 타입은 `lib/*.ts`에서 `export type`으로 내보내고, 소비처에서는 `import { fn, type LessonEntry } from "@/lib/pace-schedule-storage"` 형태의 inline type import로 가져온다.
- 함수는 반환 타입을 명시한다 (`Promise<Response>`, `Record<string, string>` 등).

### 스타일

- import 경로는 `@/` 별칭 (`@/lib/session`, `@/components/ui/button`).
- 세미콜론 없음, 큰따옴표.
- 파일명은 kebab-case.

### 검증

변경한 파일만 확인: `cd minahview && npx tsc --noEmit`