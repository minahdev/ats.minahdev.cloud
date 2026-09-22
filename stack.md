---
layout: default
title: 기술 스택 및 개발 환경
permalink: /stack/
---

<style>
.stk { max-width: 64rem; margin: 2.5rem auto 4rem; }

.stk__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 1.6rem; }
.stk__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.stk__crumb a { color: #9ca3af; }
.stk__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; word-break: keep-all; }
.stk__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

.stk__stat {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(8.5rem, 1fr));
  gap: .6rem;
  margin-bottom: 2.75rem;
}
.stat { border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .85rem; }
.stat__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.stat__v { font-size: 1.05rem; font-weight: 700; color: #111827; word-break: keep-all; font-variant-numeric: tabular-nums; }
.stat__v small { font-size: .78rem; font-weight: 400; color: #9ca3af; margin-left: .15rem; }

.stk__sec { margin-bottom: 3.25rem; }
.stk__sec > h2 {
  font-size: 1.05rem;
  color: #2a7ae2;
  margin: 0 0 1.1rem;
  padding-bottom: .5rem;
  border-bottom: 1px solid #e5e7eb;
  display: flex;
  gap: .5rem;
  align-items: baseline;
  word-break: keep-all;
}
.stk__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.stk__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }
.stk__note code { font-size: .82rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }
.stk__sub {
  margin: 2rem 0 .9rem;
  font-size: .82rem;
  color: #9ca3af;
  letter-spacing: .04em;
  font-weight: 700;
}

/* 선정 근거 카드 */
.case { display: grid; gap: .7rem; }
.case__box { border: 1px solid #e5e7eb; border-left: 3px solid #2a7ae2; border-radius: 6px; padding: .9rem 1.1rem; }
.case__box--drop { border-left-color: #9ca3af; }
.case__box--fix { border-left-color: #dc2626; }
.case__t { margin: 0 0 .1rem; font-size: .95rem; font-weight: 700; color: #111827; word-break: keep-all; }
.case__adr { display: block; font-size: .74rem; color: #9ca3af; letter-spacing: .02em; margin-bottom: .55rem; }
.case__p { margin: 0 0 .7rem; font-size: .87rem; line-height: 1.8; color: #374151; word-break: keep-all; }
.case__p:last-child { margin-bottom: 0; }
.case__p code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }
.case__q { color: #6b7280; }

/* 함정 목록 */
.trap { display: grid; grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr)); gap: .7rem; }
.trap__item { border: 1px solid #e5e7eb; border-radius: 6px; padding: .8rem .9rem; background: #f9fafb; }
.trap__item h3 { margin: 0 0 .35rem; font-size: .88rem; color: #111827; word-break: keep-all; }
.trap__item p { margin: 0; font-size: .83rem; line-height: 1.7; color: #6b7280; word-break: keep-all; }
.trap__item code { font-size: .78rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 명령 블록 */
.cmd {
  background: #f9fafb;
  border: 1px solid #e5e7eb;
  border-radius: 6px;
  padding: .85rem 1rem;
  margin: 0 0 1.1rem;
  font-family: ui-monospace, SFMono-Regular, Menlo, monospace;
  font-size: .8rem;
  line-height: 1.85;
  color: #374151;
  overflow-x: auto;
  white-space: pre;
}
.cmd i { color: #9ca3af; font-style: normal; }

/* 표 공통 — 개발 일정 페이지와 같은 값 */
.tbl__scroll { overflow-x: auto; padding-bottom: .3rem; }
.tbl { width: 100%; border-collapse: collapse; font-size: .87rem; }
.tbl th {
  background: #f9fafb;
  text-align: left;
  padding: .6rem .7rem;
  font-size: .74rem;
  color: #6b7280;
  letter-spacing: .03em;
  border-bottom: 1px solid #e5e7eb;
  white-space: nowrap;
}
.tbl td {
  padding: .6rem .7rem;
  border-bottom: 1px solid #f3f4f6;
  vertical-align: top;
  color: #374151;
  line-height: 1.65;
  word-break: keep-all;
}
.tbl code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }
.tbl--stack { min-width: 52rem; }
.tbl--stack td:first-child { white-space: nowrap; font-weight: 600; color: #111827; }
.tbl--era { min-width: 50rem; }
.tbl--era td:first-child { white-space: nowrap; font-variant-numeric: tabular-nums; }
.tbl--ci { min-width: 48rem; }
.tbl__num { text-align: right; font-variant-numeric: tabular-nums; white-space: nowrap; }

.tag {
  display: inline-block;
  padding: .04rem .38rem;
  border-radius: 3px;
  font-size: .7rem;
  font-weight: 700;
  letter-spacing: .02em;
  white-space: nowrap;
  vertical-align: .05em;
}
.tag--done { background: #d1fae5; color: #065f46; }
.tag--drop { background: #f3f4f6; color: #6b7280; }
.tag--now { background: #dbeafe; color: #1e40af; }

.stk__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }

@media (max-width: 34rem) {
  .stk__stat { grid-template-columns: repeat(2, 1fr); }
}
</style>

<div class="stk">

<div class="stk__head">
  <p class="stk__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 5. 기술 스택 및 개발 환경</p>
  <h1>기술 스택 및 개발 환경</h1>
  <p>무엇을 썼는가보다 <b>왜 그것이어야 했는가</b>를 남긴다 &middot; 기준 시점 저장소
     <code>Seuk-Team/Arda</code> <code>8071fd9</code> &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="stk__stat">
  <div class="stat"><span class="stat__k">결정 문서</span>
    <span class="stat__v">36<small>편 ADR</small></span></div>
  <div class="stat"><span class="stat__k">API 라우트</span>
    <span class="stat__v">107<small>개</small></span></div>
  <div class="stat"><span class="stat__k">테이블</span>
    <span class="stat__v">28<small>개 v2.8</small></span></div>
  <div class="stat"><span class="stat__k">alembic 리비전</span>
    <span class="stat__v">26<small>개</small></span></div>
  <div class="stat"><span class="stat__k">CI 잡</span>
    <span class="stat__v">5<small>개 · push·PR마다</small></span></div>
  <div class="stat"><span class="stat__k">백엔드 테스트</span>
    <span class="stat__v">1,165<small>건</small></span></div>
</div>

<div class="stk__sec">

  <h2><span class="stk__num">1.</span> 기술 스택 선정 및 근거</h2>
  <p class="stk__note">
    기술 &middot; 범위 &middot; 윤리 결정 36건을 ADR(<code>docs/03_decision/</code>)로 남겼다.
    <b>안 한 것에도 ADR 이 있다</b> &mdash; Kubernetes 제외(0001) &middot; 실시간 공동편집
    제외(0005) &middot; SQS 워커 폐기(0036). 개정은 원문을 지우지 않고 절을 덧붙이므로,
    <b>뒤집힌 결정도 원래 근거가 그대로 남아 있다.</b>
    아래 표는 2026. 09. 22. 기준 현행 스택이고, 이어지는 카드가 갈림길이 있었던 항목의 근거다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--stack">
    <thead>
      <tr>
        <th>영역</th>
        <th>스택</th>
        <th>근거 파일</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>백엔드</td>
        <td>Python 3.12 &middot; FastAPI &middot; SQLAlchemy 2.0 &middot; psycopg 3 &middot;
            PostgreSQL 16 + pgvector(<code>pgvector/pgvector:pg16</code>) &middot;
            alembic &middot; uv(의존 잠금) &middot; pytest + pytest-timeout(60초) &middot;
            ruff <code>--select F</code></td>
        <td><code>backend/pyproject.toml</code></td>
      </tr>
      <tr>
        <td>아키텍처</td>
        <td>헥사고날 부분 적용 &mdash; Bounded Context 4개(hiring &middot; talent &middot;
            application &middot; interview) + <code>ports/output</code> 포트 &middot;
            <code>adapter/outbound/{pg,llm,mail}</code> 어댑터 (ADR-0035)</td>
        <td><code>backend/app/</code></td>
      </tr>
      <tr>
        <td>프론트엔드</td>
        <td>React 19 &middot; Vite 8 &middot; TypeScript 6 &middot; react-router 7 &middot;
            three.js(아르 3D 캐릭터) &middot; CSS Modules + 디자인 토큰 &middot; oxlint</td>
        <td><code>frontend/app/package.json</code></td>
      </tr>
      <tr>
        <td>앱</td>
        <td>Flutter(CI 3.44.8 &middot; Dart SDK ^3.12) &middot; http &middot;
            flutter_secure_storage(토큰은 Android Keystore) &middot; Android APK</td>
        <td><code>mobile/pubspec.yaml</code></td>
      </tr>
      <tr>
        <td>AI &middot; 판단</td>
        <td>Anthropic Claude(<code>claude-haiku-4-5</code>) &mdash; 서류 요약 &middot; 평가 &middot;
            추천 3단 체인(ADR-0022) &middot; 아르 도구 호출 에이전트 &middot; 지원자 FAQ.
            규칙 의도 라우터가 빈출 요청 &middot; 기본 질문을 LLM 없이 처리($0)</td>
        <td><code>backend/app/agent/</code></td>
      </tr>
      <tr>
        <td>AI &middot; 검색</td>
        <td>sentence-transformers(ko-sroberta) 임베딩 + pgvector 시맨틱 검색 (ADR-0021)</td>
        <td><code>backend/app/agent/embedder.py</code></td>
      </tr>
      <tr>
        <td>AI &middot; 음성 &middot; 표정</td>
        <td>OpenAI Whisper API(<code>whisper-1</code>) STT &mdash; <code>STT_BACKEND</code> 로
            로컬 faster-whisper 전환 가능(ADR-0038) &middot; lie-detection 서비스(Python 3.13 &middot;
            MediaPipe 얼굴 랜드마크 &middot; ViT 표정 &middot; librosa) &mdash;
            담당자 화면 참고 지표 전용, 점수 미반영(ADR-0029 &middot; 0032)</td>
        <td><code>ai/lie-detection/</code></td>
      </tr>
      <tr>
        <td>AI &middot; R&amp;D 자산</td>
        <td>Qwen3-8B QLoRA 어댑터 3갈래(chat v9 &middot; summary &middot; interview) &mdash;
            동일 채점기로 학습 전 26.1% &rarr; v9 73.9%. 심사 서빙엔 쓰지 않고
            <code>AGENT_*_BACKEND=ollama</code> 스위치로 교체 가능
            <span class="tag tag--drop">보존</span></td>
        <td><code>ai/qwen-training/</code></td>
      </tr>
      <tr>
        <td>무결성</td>
        <td>web3 &middot; Ethereum Sepolia 테스트넷 앵커 &middot; OpenTimestamps &mdash;
            제출물 SHA-256 해시 사슬을 추가 전용 원장에 쌓고 DB 트리거가 수정 &middot; 삭제를
            거부(ADR-0028). 서명 개인키는 서버 밖(GitHub Actions)</td>
        <td><code>backend/app/chain.py</code></td>
      </tr>
      <tr>
        <td>메일</td>
        <td>n8n 웹훅 + SMTP &mdash; n8n 이 죽어도 API 가 5분마다 밀린 메일을 재발송(최대 3회).
            SES &middot; SQS 는 폐기 <span class="tag tag--drop">폐기</span>
            (ADR-0030 &middot; 0031 &middot; 0036)</td>
        <td><code>backend/app/shared/mail_smtp.py</code></td>
      </tr>
      <tr>
        <td>인프라</td>
        <td>Docker Compose(db &middot; api &middot; caddy &middot; lie-detection &middot; n8n) &middot;
            AWS EC2 t3.medium(서울 &middot; Elastic IP &middot; EBS 50GB) &middot;
            S3(presigned URL 직접 업로드) &middot; Caddy(443, 인증서 자동) &middot;
            Vercel(프론트) &middot; systemd 타이머 자동 CD &middot; CloudWatch + SNS 경보 &middot;
            매일 S3 DB 백업(30일 수명주기)</td>
        <td><code>infra/</code> &middot; 07-deploy</td>
      </tr>
      <tr>
        <td>CI</td>
        <td>GitHub Actions 5잡 &mdash; ① 백엔드 린트(ruff F) ② 백엔드 테스트(alembic 이행
            &rarr; 모델↔이행 비교 &rarr; pytest) ③ 프론트 빌드&middot;린트
            ④ AI 면접 서버 시험 ⑤ 앱 시험</td>
        <td><code>.github/workflows/ci.yml</code></td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="stk__sub">갈림길이 있었던 것 &mdash; 무엇과 비교했고 무엇을 기준으로 잘랐는가</p>

  <div class="case">

    <div class="case__box">
      <p class="case__t">백엔드 &mdash; Python &middot; FastAPI</p>
      <span class="case__adr">선정 ADR 없음 &middot; 남은 근거는 결과 쪽이다</span>
      <p class="case__p">
        <b>FastAPI 자체에는 비교 ADR 이 없다.</b> 기획 단계에서 스택 표에 그대로 적혀 시작했고,
        갈림길로 기록된 것은 그 위의 프론트(ADR-0006)와 앱(ADR-0010)이다. 지어내지 않고
        <b>실제로 값을 한 자리</b>만 적는다.
      </p>
      <p class="case__p">
        첫째, <b>계약의 진실이 코드에서 나온다.</b> Swagger <code>/docs</code> 가 라우트 107개의
        요청 &middot; 응답을 자동 생성하고, <code>02-api.md</code> 는 "무엇이 있는가"만 유지한다.
        프론트 &middot; 앱 두 클라이언트가 이 문서 하나로 병렬 개발했고,
        배포본 OpenAPI 를 main 과 대조하는 스크립트(<code>check_public_contract.py</code>)가
        08/31 실측에서 <b>35/35 &middot; 62/62 일치</b>를 확인했다.
      </p>
      <p class="case__p">
        둘째, <b>에이전트가 같은 런타임 안에 있다.</b> <code>backend/app/agent/</code> 는 별도
        서비스가 아니라 같은 Python 프로세스이고, Claude SDK &middot; sentence-transformers &middot;
        pypdf 가 API 코드와 한 의존 묶음에 들어간다. 에이전트가 백엔드에 제공하는 요약 생성
        함수도 프로세스 안 호출이라 <b>두 오너 간 인터페이스가 HTTP 가 아니라 함수 시그니처</b>다.
      </p>
      <p class="case__p">
        셋째, 그 한 덩어리가 커지자 <b>헥사고날 부분 적용</b>으로 Bounded Context 4개와
        <code>adapter/outbound/{pg,llm,mail}</code> 을 갈랐다(ADR-0035). 지금 모델 &middot;
        메일 &middot; 큐 &middot; 스토리지 공급자를 환경변수 스위치
        (<code>AGENT_CHAT_BACKEND</code> &middot; <code>MAIL_DISPATCH</code> &middot;
        <code>QUEUE_BACKEND</code> &middot; <code>S3_ENDPOINT_URL</code>)로 갈아 끼울 수 있는 것이
        그 재편의 결과다.
      </p>
    </div>

    <div class="case__box">
      <p class="case__t">프론트엔드 &mdash; React, 서버 템플릿(Jinja) 기각</p>
      <span class="case__adr">ADR-0006 &middot; 확정 2026. 08. 23.</span>
      <p class="case__p">
        목업이 순수 정적 HTML 이라 두 갈래가 가능했다. <b>Jinja</b> 는 FastAPI 가 HTML 을 완성해
        내려주므로 프론트 서버 &middot; 빌드 &middot; API 호출 &middot; CORS 가 통째로 없다.
        <b>React</b> 는 프로젝트를 따로 세우고 팀원 HTML 을 JSX 로 다시 쓴다.
      </p>
      <p class="case__p">
        <b>이식 비용은 쟁점이 아니었다</b> &mdash; HTML → JSX 는 기계적 변환이다. 실제 무게는
        <b>딸려오는 층</b>이었다: 개발 서버 두 개 &middot; 빌드 &middot; CORS &middot; 배포 대상 두 곳.
        그 층이 막히면 데모 자체가 안 뜬다. 그래서 판단 기준을 하나로 잡았다 &mdash;
        <b class="case__q">"프론트가 안 뜰 때 혼자 고칠 수 있는가."</b>
      </p>
      <p class="case__p">
        React 를 택했다. 그 층들이 이미 손에 익어 있었고, <b>익숙하지 않은 스택을 새로 배우는
        비용이 그 층을 유지하는 비용보다 크다</b>고 봤다. 딸린 결정 하나 &mdash;
        <b>공통 조각(사이드바 &middot; 테이블 행 &middot; 버튼 &middot; 입력)을 먼저 컴포넌트로
        만든 뒤</b> 화면을 이식한다. 안 그러면 화면마다 같은 마크업을 네 번 다시 친다.
      </p>
    </div>

    <div class="case__box">
      <p class="case__t">앱 &mdash; Flutter, Expo 에서 재확정</p>
      <span class="case__adr">ADR-0010 &middot; 08. 25. Expo 1차 확정 &rarr; 08. 26. Flutter 재확정</span>
      <p class="case__p">
        <b>학습 비용은 판단 기준으로 삼지 않았다.</b> AI 코딩 보조를 쓰면 새 언어의 문법 학습
        비용이 예전만큼 크지 않고, Dart 를 처음 본다는 것이 그 자체로 Flutter 를 기각할 근거가
        못 된다. 기준은 <b class="case__q">"팀 폰에서 돌아가는 데모를 09/30 까지 만들 수 있는가"</b>
        하나였다.
      </p>
      <p class="case__p">
        <b>08. 25. 에는 이 기준이 Expo 를 가리켰다.</b> 완료 기준이 "팀 전원 기기에서 실행 확인"
        이었고 팀 기기가 <b>iOS 1대 &middot; Android 4대</b>라, Mac &middot; Xcode 가 필요한
        Flutter 로는 그 1대를 올릴 수 없었기 때문이다. <b>08. 26. 에 팀이 데모 범위를 좁혀</b>
        iOS 1대를 시연 대상에서 뺐고, 그 순간 Expo 를 골랐던 유일한 근거가 사라졌다.
        <b>바뀐 것은 기술 비교가 아니라 데모 범위다.</b>
      </p>
      <p class="case__p">
        대신 감수한 것을 숨기지 않고 적었다 &mdash; <b>팀에 Dart 사용자가 0명</b>이고 앱은 1인
        트랙이라 막히면 혼자 푼다. 팀 배포는 매번 APK 를 만들어 전달한다(Expo Go 의 QR 즉시
        반영이 없다). <b>iOS 호환은 끝까지 미검증으로 남는다</b> &mdash; iOS 지원 플러그인만 쓰고
        <code>Platform.isAndroid</code> 분기를 넣지 않지만, Mac 이 없어
        <code>flutter build ios</code> 를 실행해 본 적이 없다. 그래서 발표 문구까지 고정했다:
        "iOS 도 됩니다"가 아니라 <b>"포팅 가능한 상태로 뒀고, 빌드 검증은 장비가 없어 못 했습니다."</b>
      </p>
      <p class="case__p">
        패키지도 같은 방식으로 골랐다. <code>http</code> &mdash; dio 는 인터셉터 &middot; 재시도가
        필요할 때 값을 하는데 <b>서버에 리프레시 토큰이 없어 갱신 로직이 없고 처리할 것이 401
        하나뿐</b>이다. <code>flutter_secure_storage</code> &mdash; shared_preferences 는 평문이라
        쓰지 않는다, <b>12시간짜리 토큰이라도 남의 계정</b>이다.
        <code>url_launcher</code> &mdash; 이력서를 앱 안에서 보려면 PDF 렌더러가 또 필요하고
        이미지 &middot; docx 는 각각 다르다, 서버가 준 presigned URL 을 브라우저로 넘긴다.
      </p>
    </div>

    <div class="case__box case__box--fix">
      <p class="case__t">스키마 이행 &mdash; 손 SQL 에서 alembic 으로</p>
      <span class="case__adr">2026. 09. 01. 전환 &middot; 사고가 먼저 있었고 도구는 그 뒤에 왔다</span>
      <p class="case__p">
        전환 이유는 취향이 아니다. <code>create_all</code> 은 <b>없는 테이블을 만들 뿐</b>
        기존 테이블에 컬럼을 붙이거나 타입을 넓히지 않는다. <b>2026. 09. 01. 하루에 그 대가를
        두 번 치렀다.</b>
      </p>
      <p class="case__p">
        &middot; 로컬 DB 의 <code>users.role</code> 체크 제약이 옛 값이라 <b>테스트 101건이 error</b><br>
        &middot; 운영 <code>applications.ai_summary_model</code> 이 <code>varchar(50)</code> 이라
        <b>AI 요약이 전건 실패</b> &mdash; Claude 호출 3번을 다 끝낸 뒤 저장에서 죽어
        <b>돈은 쓰고 결과는 버렸고</b>, <code>BackgroundTasks</code> 라 화면에 에러도 안 떴다
      </p>
      <p class="case__p">
        두 번 다 "각자 손으로 SQL 을 돌려라"로 수습했다. <b>코드는 pull 로 따라오지만 DB 는
        안 따라온다</b> &mdash; 문서에 손 SQL 을 적는 방식은 사람마다 스키마가 갈리는 것을 막지
        못한다. 지금은 리비전 26개가 쌓여 있고 <code>uv run alembic upgrade head</code> 한 줄로
        따라온다.
      </p>
      <p class="case__p">
        도입 자체도 한 번 뒤집었다. 처음에는 <code>uv run --with alembic</code> 으로 잠금 파일을
        건드리지 않았다 &mdash; Dockerfile 의 uv 핀과 <code>uv.lock</code> 형식이 어긋나 이미지
        빌드가 깨질까 봐 피한, 근거 있는 판단이었다. 뒤집은 이유는 <b>버전이 아무 데도 안 박힌다</b>
        는 것이다: <code>--with</code> 는 매번 최신을 받으므로 <b>사람마다 &middot; CI 마다 다른
        alembic 으로 같은 리비전을 돌리게 된다.</b> 그리고 걱정했던 위험은 실측해 보니 성립하지
        않았다(잠금 파일 형식 그대로, 기존 패키지 버전 이동 0건, 두 줄만 추가).
        <b>원래 판단이 틀렸던 게 아니라 전제가 이미 바뀌어 있었다.</b>
      </p>
      <p class="case__p">
        이후 alembic 은 dev 묶음에서 <b>운영 의존으로 올라갔다</b> &mdash; 배포가 컨테이너 안에서
        이행을 돌리므로(2026. 09. 04. 이슈 #17), dev 그룹에 두면 <code>--no-dev</code> 빌드에서
        빠져 이행이 아예 불가능하다.
      </p>
    </div>

    <div class="case__box case__box--drop">
      <p class="case__t">인프라 &mdash; Kubernetes 제외, AWS 8종 &rarr; 3종</p>
      <span class="case__adr">ADR-0001 &middot; ADR-0031 &middot; ADR-0036</span>
      <p class="case__p">
        <b>K8s 는 뺐다.</b> 한 달 안에 K8s 를 "굴렸다"고 말하려면 배포 전략 &middot; 오토스케일링
        &middot; 헬스체크 튜닝 중 최소 하나는 실제로 다뤄야 하는데, 서비스 기능까지 만들면서는
        매니페스트 쓰고 파드 뜨는 수준이 한계다. <b>그 수준은 면접에서 파고들면 방어가 안 된다.</b>
        그래서 Docker + AWS + GitHub Actions CI/CD 까지를 목표로 잡았다 &mdash;
        <b>"못 만들어서가 아니라, 한 달 규모에서 설명 가능한 깊이까지 못 가기 때문에 뺐다."</b>
      </p>
      <p class="case__p">
        <b>AWS 는 8종에서 3종(EC2 &middot; S3 &middot; IAM)으로 줄였다.</b> 이유는 기술이 아니라
        기한이다 &mdash; <b>예산이 $400 &middot; 2026. 10. 27. 까지</b>인데 그 뒤에도 서비스가
        돌아야 한다. 나머지 다섯(SES &middot; SQS &middot; CloudWatch &middot; SNS &middot;
        CloudFormation)은 self-host 대안으로 갈아 끼울 스위치를 만든 뒤 폐기 대상으로
        돌렸고(콘솔에서 지우는 것은 10. 27. 이후다), 메일은 n8n + SMTP 로 이관했다. 주장으로 두지 않고
        <b>PC 한 대에 운영과 같은 스택을 통째로 띄워 실증</b>했다(<code>infra/local/</code>, 2절).
      </p>
    </div>

    <div class="case__box case__box--drop">
      <p class="case__t">모델 &mdash; 자체학습 Qwen 과 Claude 를 같은 자로 재고 클라우드 확정</p>
      <span class="case__adr">ADR-0024 &rarr; 2026. 09. 18. 확정</span>
      <p class="case__p">
        Qwen3-8B 를 QLoRA 로 직접 학습해 어댑터 3갈래(chat &middot; summary &middot; interview)를
        만들었고, <b>동일 채점기(<code>judge.py</code>) &middot; 동일 23건</b>으로 쟀다 &mdash;
        <b>학습 전 26.1% &rarr; Claude Haiku 69.6% &rarr; Qwen v9 73.9%.</b>
        정확도는 동급까지 왔다.
      </p>
      <p class="case__p">
        그런데도 <b>심사 서빙은 클라우드 + Claude 로 확정했다.</b> 갈린 것은 정확도가 아니라
        <b>수치 추론 &middot; 형식 안정성 &middot; 콜드 스타트 78초 &middot; 동시성</b>이다.
        실제로 학원 PC 3대로 온프레미스를 구축해 운영까지 해 봤고,
        <b>도구 오호출 &middot; 프롬프트 예시 숫자 베끼기 &middot; JSON 따옴표 깨짐이 심사 직전에
        누적</b>돼 폐쇄했다. 학습 파이프라인과 어댑터는 버리지 않고
        <code>AGENT_*_BACKEND=ollama</code> 스위치로 교체 가능한 <b>R&amp;D 자산으로 보존</b>했다.
      </p>
    </div>

  </div>

</div>

<div class="stk__sec">

  <h2><span class="stk__num">2.</span> 개발 환경 구성</h2>
  <p class="stk__note">
    로컬 환경의 원칙은 하나다 &mdash; <b>기본값이 곧 기존 동작이고, 로컬 초록과 CI 초록이
    갈리지 않게 한다.</b> 로컬 전용 우회를 허용하면 "내 PC 에선 됐는데"가 배포까지 간다.
    아래 함정 목록은 전부 <b>실제로 겪은 것</b>이고, 겪을 때마다
    <code>docs/00_overview/08-local-setup.md</code> 에 쌓았다.
  </p>

  <p class="stk__sub">평소 셋업 &mdash; 네 줄</p>

  <div class="cmd">git pull
docker compose up -d --build      <i># DB 를 먼저 띄운다</i>
cd backend &amp;&amp; uv sync
uv run alembic upgrade head       <i># 스키마 최신화</i></div>

  <p class="stk__note">
    <b>순서를 2026. 09. 02. 에 바꿨다.</b> 전에는 <code>alembic</code> 이
    <code>docker compose up</code> 앞에 있었는데, <b>DB 가 떠 있지 않으면 마이그레이션이 붙을
    데가 없다.</b> 컨테이너가 하나도 없는 PC 에서 그대로 따라 하면 거기서 막힌다 &mdash;
    실제로 겪고 고친 순서다.
    로컬 compose 가 띄우는 것은 넷이다: <code>db</code>(<code>pgvector/pgvector:pg16</code>,
    5432) &middot; <code>api</code>(8000) &middot; <code>minio</code>(9000) &middot;
    <code>minio-init</code>. <b>DB 이미지는 CI &middot; 운영과 같은 것을 쓴다</b> &mdash;
    순정 <code>postgres</code> 에는 <code>vector</code> 확장이 없어 임베딩 경로가 통째로 안 돈다.
  </p>

  <p class="stk__sub">백엔드 스위치 &mdash; 아무것도 설정하지 않으면 지금까지와 동일하게 돈다</p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr>
        <th>환경변수</th>
        <th>기본</th>
        <th>로컬로 돌리려면</th>
        <th>비고</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>STT_BACKEND</code></td>
        <td>백엔드 <code>openai</code> (빈 값도) &middot;
            <b>실시간 면접 서버는 빈 값이면 로컬</b></td>
        <td><code>faster_whisper</code>
            (<code>uv sync --extra local</code> 필요)</td>
        <td><b>같은 변수, 두 해석</b> &mdash; 같은 <code>backend/.env</code> 를 두 컨테이너가
            다르게 읽는다. 로컬에서 비워 두면 백엔드는 API 로, 실시간 서버는 CPU 로 받아쓴다
            (ADR-0038)</td>
      </tr>
      <tr>
        <td><code>AGENT_CHAT_BACKEND</code></td>
        <td><code>anthropic</code></td>
        <td><code>ollama</code></td>
        <td>어댑터 유닛 테스트는 mock 기반이라 <b>Ollama 없이 돈다</b>. 실제 추론이 필요한
            사람은 에이전트 오너뿐</td>
      </tr>
      <tr>
        <td><code>AGENT_SUMMARY_BACKEND</code></td>
        <td><code>anthropic</code></td>
        <td><code>ollama</code></td>
        <td>GPU 가 없으면 <code>OLLAMA_HOST</code> 로 GPU 장비 한 대를 가리킨다 &mdash;
            포트를 열지 말고 SSH 터널</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="stk__note">
    <b>모르는 값을 넣으면 조용히 폴백하지 않고 즉시 예외로 죽는다.</b>
    오타 하나로 개인정보가 외부로 나가면 안 되기 때문이다 &mdash; 폴백이 친절해 보이지만,
    이 경우엔 <b>틀린 설정이 성공처럼 보이는 것</b>이 더 비싸다.
  </p>

  <p class="stk__sub">자주 물리는 함정 &mdash; 코드가 아니라 내 환경이 원인인 것들</p>

  <div class="trap">

    <div class="trap__item">
      <h3>5432 를 네이티브 PostgreSQL 이 선점</h3>
      <p>컨테이너 DB 가 정상 기동해도 연결이 그쪽으로 간다. <b>옛 스키마의 다른
         <code>arda</code> DB 에 붙어</b> DB 의존 테스트가 통째로 error 난다.
         개인 오버라이드로 다른 포트를 함께 매핑해 쓴다.</p>
    </div>

    <div class="trap__item">
      <h3><code>pytest</code> 가 <code>backend/.env</code> 를 읽는다</h3>
      <p>2026. 09. 07. 부터. 전에는 <code>.env</code> 에 다른 포트를 적어도 무시되고 5432 로
         붙었다. <b>단 에이전트 스위치는 여전히 빈 값으로 선점</b>된다 &mdash;
         <code>.env</code> 에 실제 키가 있어도 테스트엔 안 들어간다.
         <b>로컬 초록 &middot; CI 빨강이 갈리는 것을 막기 위해서다.</b></p>
    </div>

    <div class="trap__item">
      <h3>MinIO 버킷 이름</h3>
      <p>로컬 S3 는 <code>arda-local</code> 버킷을 만든다. <code>S3_BUCKET</code> 을 실 AWS
         이름으로 둔 채 업로드하면 <b>전건 404</b> 로 죽는데, 그 404 는 브라우저가 S3 로 직접
         PUT 하다 나는 것이라 <b>API 로그에 안 남는다.</b></p>
    </div>

    <div class="trap__item">
      <h3>요약 &middot; 임베딩은 응답 뒤에 돈다</h3>
      <p><code>BackgroundTasks</code> 라 접수 API 가 201 을 줘도 요약은 아직이다.
         <b>실패해도 화면에 안 뜬다</b> &mdash; DB 에서 건수를 세서 확인해야 한다.</p>
    </div>

    <div class="trap__item">
      <h3>WSL 에서 vite 가 변경을 못 본다</h3>
      <p>2026. 09. 08. Windows 쪽에서 고친 파일이 inotify 로 안 올라와
         <b>서버를 켤 때의 코드가 계속 나온다.</b> 고약한 것은 <b>틀린 화면이 그럴듯하게
         그려진다</b>는 점이다 &mdash; 코드를 읽으면 맞는데 화면이 다르다.
         <code>VITE_DEV_POLL=1</code> 로 폴링을 켜거나 개발 서버를 다시 띄운다.</p>
    </div>

    <div class="trap__item">
      <h3><code>.env</code> 를 고쳐도 반영이 안 된다</h3>
      <p><code>.env</code> 는 프로세스 시작 때 한 번만 읽는다. 그리고
         <b><code>docker compose restart</code> 는 <code>env_file</code> 을 다시 읽지 않는다</b>
         &mdash; <code>up -d --force-recreate</code> 로 컨테이너를 다시 만들어야 한다.
         실제로 이것 때문에 기능 하나가 "스위치가 없어서" 안 뜬 적이 있다.</p>
    </div>

  </div>

  <p class="stk__sub">운영 그대로 로컬 전체 스택 &mdash; <code>infra/local/</code></p>
  <p class="stk__note">
    위 네 줄은 <b>개발용</b> 최소 스택이다. 이와 별개로 <b>운영(EC2)과 같은 스택을 PC 한 대에
    그대로 띄우는 절차</b>를 2026. 09. 08. 에 만들었다. 목적이 분명하다 &mdash;
    <b>"AWS 를 떠나도 돈다"(ADR-0031)를 주장이 아니라 사실로 만드는 것</b>이다.
    db &middot; api &middot; lie-detection &middot; n8n &middot; caddy 가 뜨고, 운영 compose 의
    사본이라 차이는 TLS 없음 &middot; 포트뿐이다. 서버에서 <code>.env</code> 두 벌 &middot;
    <code>pg_dump</code> &middot; n8n 볼륨을 받아 복원한 뒤 <code>smoke.sh</code> 가
    <b>한 번에 자동 검증</b>한다 &mdash; 컨테이너 상태 &middot; api 직접과 caddy 경유의
    <code>/health</code> &middot; 내부 API &middot; 무결성 API 의 인증 게이트(401) &middot;
    lie-detection &middot; n8n Basic Auth 와 웹훅 &middot; alembic 이 head 인지 &middot;
    api 로그의 Traceback 0건.
    스택 검증은 dev 서버(5173)가 아니라 <b>프로덕션 번들 preview(4173)</b>에서 한다 &mdash;
    dev 모드에는 로그인 우회 &middot; 목데이터 폴백이 켜져 있어 부적합하다.
    <b>가져온 것은 운영 데이터 사본이다</b> &mdash; 지원자 실제 이메일이 들어 있고
    <code>MAIL_DISPATCH=n8n</code> 이라 단계를 바꾸면 진짜 메일이 나간다. 테스트는 이메일이
    팀원 것으로 바뀐 지원자로만 한다.
  </p>

  <p class="stk__sub">CI 환경은 로컬 &middot; 운영과 버전을 맞춰 못 박는다</p>
  <p class="stk__note">
    버전이 떠 있으면 <b>남의 커밋에서 CI 가 터진다.</b> 그래서 전부 이유를 달아 고정했다 &mdash;
    백엔드 Python <b>3.12</b>(Dockerfile 의 <code>python:3.12-slim</code> 과 맞춘다) &middot;
    프론트 Node <b>22</b>(로컬 실측 v22.23.1 과 맞춘다) &middot;
    AI 면접 서버 Python <b>3.13</b>(<code>ai/lie-detection/Dockerfile</code> 과 맞춘다) &middot;
    Flutter <b>3.44.8</b> &middot; ruff <b>0.16.7</b>(<code>uvx</code> 로 격리 실행 &mdash;
    dev 묶음에 넣으면 <code>uv.lock</code> 이 바뀌어 전원이 <code>uv sync</code> 를 다시 돌려야 한다).
    CI 의 DB 도 로컬 compose 와 같은 <code>pgvector/pgvector:pg16</code> 이다.
  </p>

</div>

<div class="stk__sec">

  <h2><span class="stk__num">3.</span> 형상 관리 및 브랜치 전략</h2>
  <p class="stk__note">
    저장소는 <code>Seuk-Team/Arda</code>(2026. 09. 04. 이관, 구 <code>Team-Seuk/Arda</code> 는
    삭제). main 기준 <b>커밋 1,095건 &middot; 머지 커밋 297건</b>(2026. 08. 20. ~ 09. 18.,
    <code>8071fd9</code>)이다.
    브랜치 전략은 <b>두 번 바뀌었고, 두 번 다 사고나 병목이 먼저 있었다.</b>
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--era">
    <thead>
      <tr>
        <th>시기</th>
        <th>규칙</th>
        <th>왜 바꿨는가</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>~ 2026. 08. 27.</td>
        <td>이슈 &rarr; 브랜치 &rarr; PR &rarr; <b>사람 리뷰 &middot; 승인</b></td>
        <td><b>전 PR 을 팀장 한 명이 리뷰</b>해, W1 실측에서 <b>프로젝트 속도를 코딩이 아니라
            팀장의 지시서 생산 &middot; 리뷰 속도가 결정한다</b>는 것이 드러났다(ADR-0007).
            인터페이스 리뷰 &middot; 머지가 기본 주 1회 일괄이라
            <b>선행 PR 이 밀리면 받는 쪽이 일주일을 논다.</b>
            도메인 오너제로 전환하면서 이 병목을 없애는 것이 목적이었다</td>
      </tr>
      <tr>
        <td>08. 28. ~ 09. 03.</td>
        <td><b>승인 게이트 전면 폐지</b> &mdash; 전원 main 직접 push</td>
        <td>근거는 "전원이 Claude 로 작업해 사람 검수가 형식화됐다"였다.
            대가가 바로 나왔다 &mdash; <b>09. 01. 하루에 깨진 main 을 두 번 발견했고
            둘 다 우연이었다</b>(<code>d7fdd10</code> &middot; <code>d96749e</code>)</td>
      </tr>
      <tr>
        <td>09. 04. ~ 현재 <span class="tag tag--now">현행</span></td>
        <td><b>main 직접 push 금지 &rarr; 브랜치 &rarr; PR &rarr; 자체 머지</b>
            (CI 초록 필수, 승인 불요)</td>
        <td>승인 게이트는 <b>여전히 없다</b> &mdash; 바뀐 것은 "main 에 닿는 경로가 PR 하나"
            라는 점뿐이다. GitHub 브랜치 보호가 직접 push &middot; force push 를 실제로 막으므로
            규칙을 외울 필요가 없다 (<code>818e693</code>)</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="stk__note">
    <b>전환이 숫자로 보인다.</b> main 의 머지 커밋 297건 중 <b>09. 04. 이전은 8건뿐</b>이고
    나머지 <b>289건이 그 이후</b>다. 그 전의 변경은 대부분 main 직접 push 였다는 뜻이다.
    PR 번호는 <b>#354</b>까지 갔다.
  </p>

  <p class="stk__note" style="margin-bottom:1.6rem;">
    <b>왜 승인 게이트를 되살리지 않았나.</b> 08. 28. 폐지의 근거(사람 검수의 형식화)는 그대로
    유효하다고 봤다. 되살린 것은 리뷰어가 아니라 <b>경로</b>다 &mdash; 안전망은 사람이 아니라
    <b>CI 초록</b>이고, <b>CI 빨간불 = 머지 불가</b>가 오너제의 유일한 강제다.
    대신 책임이 옮겨 갔다: <b>main 머지 = 2분 후 프로덕션 배포</b>이므로
    <b>main 이 항상 동작하는 상태여야 할 책임이 리뷰어에서 머지하는 사람에게 넘어왔다.</b>
    깨진 main 을 발견한 사람은 묻지 않고 고치거나(fix-forward) revert 한다 &mdash;
    <b>main 이 빨간불이면 다른 작업보다 우선</b>이다. 이의는 사후에 말하고, 합의가 안 되면
    revert 가 기본값이다.
  </p>

  <p class="stk__sub">CI 5잡 &mdash; 게이트가 아니라 "깨졌다는 사실만 즉시 보이게"</p>

  <div class="tbl__scroll">
  <table class="tbl tbl--ci">
    <thead>
      <tr>
        <th>잡</th>
        <th>무엇을</th>
        <th>왜 이 잡이 생겼는가</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>백엔드 린트</td>
        <td><code>ruff check --select F</code></td>
        <td>헥사고날 이동 뒤 <b>미정의 이름 2건이 프로덕션 500 까지 갔다</b> &mdash;
            그 줄을 타는 테스트가 없어 pytest 는 초록이었다.
            <b><code>--select F</code> 만 켠다</b>: 스타일까지 켜면 기존 파일 수백 줄이 빨개져
            <b>아무도 안 보는 빨간 CI</b> 가 된다</td>
      </tr>
      <tr>
        <td>백엔드 테스트</td>
        <td><code>alembic upgrade head</code> &rarr; 모델↔이행 비교 &rarr;
            pytest <b>1,165건</b> (실제 PostgreSQL + pgvector)</td>
        <td>모델↔이행 비교는 2026. 09. 17. 에 붙였다 &mdash; pytest 의 <code>conftest</code> 가
            <code>create_all</code> 로 <b>이행에 빠진 표를 채워 넣어</b> 이행 누락이 CI 에서
            가려지기 때문이다. <b><code>alembic check</code> 는 CHECK 제약의 값 목록을 안 봐서</b>
            09. 16.(메일 종류 <code>password_setup</code> 누락) &middot;
            09. 17.(#282 <code>file_blobs</code>) 두 번 새어 나갔다. 리비전 번호가 겹치면
            <code>test_alembic_revisions.py</code> 가 CI 에서 잡는다.
            <b><code>pytest-timeout</code> 60초</b>는 Docker 가 죽어 pytest 가 24분간 조용히
            멈춘 사고에서 나왔다 &mdash; <b>멈춤을 침묵이 아니라 실패로</b></td>
      </tr>
      <tr>
        <td>프론트 빌드 &middot; 린트</td>
        <td>oxlint + <code>tsc -b</code> + <code>vite build</code> (Node 22)</td>
        <td>타입 &middot; 린트 &middot; 빌드가 한 잡에서 다 도는 것이 요점이다 &mdash;
            빌드가 깨진 채 머지되면 Vercel 배포가 그대로 멈춘다</td>
      </tr>
      <tr>
        <td>AI 면접 서버 시험</td>
        <td>pytest 3파일 (Python 3.13) &mdash; 실시간 전사 &middot; 판정 중계 &middot;
            화자 매칭</td>
        <td>본체와 파이썬 버전 &middot; 시스템 라이브러리(opencv &middot; mediapipe &middot;
            soundfile)가 달라 별도 잡으로 뗐다</td>
      </tr>
      <tr>
        <td>앱 시험</td>
        <td><code>flutter analyze</code> + <code>flutter test</code> &mdash;
            테스트 파일 <b>30개</b> (Flutter 3.44.8)</td>
        <td>ADR-0010 의 iOS 호환 규율 중 <b>Mac 없이 가능한 검증이 <code>analyze</code>
            무경고까지</b>다. 그것만은 CI 가 대신 지킨다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="stk__note">
    같은 브랜치에 연달아 push 하면 앞의 실행을 취소한다(<code>concurrency</code> &middot;
    <code>cancel-in-progress</code>) &mdash; 무료 러너 분을 아끼기 위해서다.
  </p>

  <p class="stk__sub">커밋 &middot; 문서 &middot; 공지 규약</p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr>
        <th>항목</th>
        <th>규칙</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>커밋 메시지</td>
        <td><code>&lt;type&gt;(&lt;기능번호|도메인&gt;): &lt;한국어 요약&gt;</code> &mdash;
            <code>feat</code> <code>fix</code> <code>docs</code> <code>test</code>
            <code>chore</code> <code>refactor</code>.
            예: <code>feat(J7): 더미 지원서 10만 건 생성기</code> &middot;
            <code>fix(agent): 무관 질문 거절을 '데이터 근거' 기준으로</code>.
            <b>리뷰가 없으므로 이력이 곧 기록</b>이고, PR 본문에 무엇을 왜 바꿨는지 남긴다</td>
      </tr>
      <tr>
        <td>검증</td>
        <td>자기 파트 실행 &middot; 테스트 결과를 <b>커밋 메시지 한 줄</b>로 남긴다.
            <b>테스트를 통과시키려고 주석 처리 &middot; 우회 금지</b> &mdash;
            실패하면 실패한 대로 적는다</td>
      </tr>
      <tr>
        <td>스키마 변경</td>
        <td>코드 + <code>01-erd.md</code> + <b>alembic 리비전</b>을 <b>같은 커밋</b>에.
            문서 갱신 없는 스키마 변경은 금지한다 &mdash; <b>ERD 가 전원의 계약</b>이기 때문이다</td>
      </tr>
      <tr>
        <td>API 변경</td>
        <td>같은 커밋에서 <code>02-api.md</code> 갱신. 요청 &middot; 응답의 진실은 Swagger 이고
            <code>02-api.md</code> 는 <b>"무엇이 있는가"만</b> 유지한다 &mdash; 이중 관리하지 않는다</td>
      </tr>
      <tr>
        <td>사후 공지 (한 줄)</td>
        <td>스키마 &middot; API &middot; 공용 문서(<code>docs/00_overview/</code> &middot;
            <code>CLAUDE.md</code> &middot; <code>.github/</code>) &middot;
            <b>남의 도메인 폴더</b>를 고쳤을 때. 큰 변경이면 직접 고치지 말고 이슈로 오너에게 넘긴다</td>
      </tr>
      <tr>
        <td>시크릿</td>
        <td><code>.env</code>(git 제외) + <code>.env.example</code>(키 이름만).
            코드 &middot; 커밋 &middot; 로그에 키를 남기지 않는다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="stk__sub">머지에서 배포까지 &mdash; 요청이 필요 없다</p>
  <p class="stk__note" style="margin-bottom:0;">
    <b>백엔드</b>는 서버의 systemd 타이머(<code>arda-deploy.timer</code>)가 <b>2분마다 main 을
    폴링</b>해 새 커밋이면 pull &rarr; build &rarr; <code>alembic upgrade head</code> &rarr;
    <code>up -d</code> 를 순서대로 돈다(로그 <code>~/deploy.log</code>).
    <b>프론트</b>는 Vercel 이 1~2분 내 자동 배포한다.
    <b>스키마 이행은 api 이미지 안에서 돈다</b> &mdash; 2026. 09. 07. 에 호스트 마운트를 없애고
    이미지가 <code>alembic/</code> 을 갖게 했다(PR #20). <code>set -euo pipefail</code> 이라
    <b>이행이 실패하면 배포가 거기서 멈추고 기존 컨테이너는 계속 산다.</b> 그래서
    <b>"배포해 주세요" 요청이 사라졌고</b>, 동시에 <b>CI 초록인 PR 만 머지해야 할 이유</b>가
    생겼다 &mdash; 머지가 곧 프로덕션이다.
  </p>

</div>

<a class="stk__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
