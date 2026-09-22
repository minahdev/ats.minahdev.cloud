---
layout: default
title: 부록
permalink: /appendix/
---

<style>
.apx { max-width: 64rem; margin: 2.5rem auto 4rem; }

.apx__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.apx__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.apx__crumb a { color: #9ca3af; }
.apx__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; word-break: keep-all; }
.apx__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

.apx__sec { margin-bottom: 3.25rem; }
.apx__sec > h2 {
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
.apx__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.apx__h3 {
  margin: 2rem 0 .7rem;
  font-size: .9rem;
  color: #111827;
  word-break: keep-all;
}
.apx__h3:first-of-type { margin-top: 1.4rem; }
.apx__h3 small { font-weight: 400; color: #9ca3af; margin-left: .35rem; font-size: .8rem; }
.apx__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.75; word-break: keep-all; }
.apx__note code { font-size: .82rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }
.apx__note:last-child { margin-bottom: 0; }

/* 이름 풀이 박스 */
.apx__box {
  border: 1px solid #e5e7eb;
  border-left: 3px solid #2a7ae2;
  border-radius: 6px;
  padding: 1rem 1.15rem;
  margin-bottom: 1.6rem;
  background: #f9fafb;
}
.apx__box h3 { margin: 0 0 .5rem; font-size: .95rem; color: #111827; word-break: keep-all; }
.apx__box p { margin: 0 0 .6rem; font-size: .86rem; line-height: 1.8; color: #374151; word-break: keep-all; }
.apx__box p:last-child { margin-bottom: 0; }

/* 서식 실물 */
.apx__pre {
  background: #f9fafb;
  border: 1px solid #e5e7eb;
  border-radius: 6px;
  padding: .85rem 1rem;
  overflow-x: auto;
  margin: 0 0 1.2rem;
}
.apx__pre code {
  display: block;
  font-family: ui-monospace, SFMono-Regular, Menlo, monospace;
  font-size: .78rem;
  line-height: 1.85;
  color: #374151;
  white-space: pre;
  background: none;
  padding: 0;
}
.apx__cap { margin: 0 0 .45rem; font-size: .78rem; color: #9ca3af; letter-spacing: .02em; }

/* 표 공통 — 개발 일정 페이지와 같은 패턴 */
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

/* 용어표 — 첫 칸은 줄바꿈하지 않는다 */
.terms { min-width: 46rem; }
.terms td:first-child { white-space: nowrap; font-weight: 600; color: #111827; }

/* 서식표 */
.forms { min-width: 52rem; }
.forms td:first-child { white-space: nowrap; font-weight: 600; color: #111827; }
.forms td:nth-child(2) { font-size: .82rem; color: #6b7280; }

/* 링크표 */
.links { min-width: 52rem; }
.links td:first-child { white-space: nowrap; font-weight: 600; color: #111827; }
.links td a { word-break: break-all; }

/* ADR 목록 */
.adr { min-width: 50rem; }
.adr td:first-child { white-space: nowrap; font-variant-numeric: tabular-nums; font-weight: 700; color: #111827; }
.adr td:last-child { color: #6b7280; font-size: .82rem; }
.adr .dash { color: #d1d5db; }

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
.tag--rev { background: #fef3c7; color: #92400e; }

.apx__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }
</style>

<div class="apx">

<div class="apx__head">
  <p class="apx__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 12. 부록</p>
  <h1>부록</h1>
  <p>본문에 실제로 쓰인 용어 &middot; 산출물이 따르는 서식 &middot; 근거 자료의 원문 위치
     &middot; 기준 저장소 <code>Seuk-Team/Arda</code> &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="apx__sec">

  <h2><span class="apx__num">1.</span> 용어 정의</h2>
  <p class="apx__note">
    일반 IT 용어 사전이 아니라 <b>이 보고서 본문에 실제로 나온 말</b>만 모았고,
    그 말이 Arda 안에서 가리키는 좁은 뜻을 적었다. 같은 단어라도 범위가 다르기 때문이다 &mdash;
    예를 들어 "무결성 원장"은 블록체인 일반이 아니라 이력서·자소서의 SHA-256 을 쌓는
    추가 전용 테이블 하나를 가리키고, "참고 지표"는 화면에 수치로 보이되
    점수 재료가 아닌 값만을 말한다.
  </p>

  <div class="apx__box">
    <h3>시스템명 &mdash; Arda</h3>
    <p>
      Arda(아르다)는 톨킨의 요정어(퀘냐)로 <b>"영역(Realm)"</b>을 뜻한다.
      톨킨 세계관에서 모든 종족이 살아가는 터전의 이름이고, 보통명사로는
      "경계가 정해진 하나의 영역"을 가리킨다(ADR-0014).
    </p>
    <p>
      이 이름을 고른 이유는 둘이다. 하나는 <b>"사람들이 모여 사는 터전"</b>이라는 뜻이
      채용과 곧바로 이어진다는 것이다. 다른 하나는 <b>심판자가 아니라는 것</b>이다 &mdash;
      후보였던 Argus(감시자)·Themis(정의의 여신)를 뺀 이유가 "판정하는 존재라서
      우리 원칙과 충돌한다"였다. Arda 는 판단하는 주체가 아니라 판단이 일어나는 장소다.
      AI 요약·파싱·에이전트는 심사를 돕는 무대를 깔 뿐이고, 최종 합격·불합격을 가르는 것은
      언제나 채용 담당자다(ADR-0003 &rarr; 0034).
    </p>
  </div>

  <h3 class="apx__h3">1-1. 채용 프로세스 <small>본문 3·6장에서 쓰인 말</small></h3>

  <div class="tbl__scroll">
  <table class="tbl terms">
    <thead>
      <tr><th>용어</th><th>정의</th></tr>
    </thead>
    <tbody>
      <tr>
        <td>ATS</td>
        <td>Applicant Tracking System &mdash; 지원자 추적 관리 시스템. 공고 등록부터 접수 · 단계별 심사 · 합불 통보까지를 하나의 시스템에서 다룬다</td>
      </tr>
      <tr>
        <td>칸반 보드</td>
        <td>지원자 카드를 단계별 열에 놓고 드래그로 옮기는 화면. 모든 이동은 누가 · 언제 · 왜까지 단계 이력으로 남는다</td>
      </tr>
      <tr>
        <td>채용 단계</td>
        <td>지원 접수(<code>applied</code>) &rarr; 서류 검토(<code>screening</code>) &rarr; 면접(<code>interview</code>) &rarr; 최종 합격(<code>accepted</code>) / 불합격(<code>rejected</code>) 다섯. DB enum 이 아니라 코드 상수 + 체크 제약이고, 전환 규칙은 서비스 레이어가 강제한다</td>
      </tr>
      <tr>
        <td>전환 규칙</td>
        <td>전진은 한 칸씩 · 역행은 항상 허용 · 불합격은 어느 단계에서든 가능하되 사유 없으면 422 · 일괄 변경은 전부 아니면 전무(부분 실패 시 409 전체 롤백) · 사용자는 삭제하지 않고 비활성화만</td>
      </tr>
      <tr>
        <td>3축 채점</td>
        <td>서류 심사 점수 체계 &mdash; 자격요건 60 · 우대사항 10 · 인재상 30 = 100점. 임계(기본 60) 이상은 면접으로, 미만은 서류 탈락으로 자동 이동한다(ADR-0034)</td>
      </tr>
      <tr>
        <td>수동 우선</td>
        <td>사람이 한 번 손댄 지원자는 이후 자동 판정 대상에서 빠지는 규칙. AI 판정을 사람이 되돌릴 수 있게 하는 안전장치다</td>
      </tr>
      <tr>
        <td>확인 카드</td>
        <td>에이전트의 쓰기 도구(단계 변경 · 면접관 배정 · 메일 발송)가 즉시 실행되지 않고 초안(<code>pending_action</code>)으로 반환되어 사람 승인을 받는 UI. 읽기 도구는 즉시 실행된다</td>
      </tr>
      <tr>
        <td>fit-check</td>
        <td>지원자 24명으로 3축 판정이 사람이 매긴 기대 등급(A/B/C)과 같은 순서로 나오는지 본 실측(<code>docs/07_eval/fit-check-2026-09.md</code>). 이 분석이 PR #182 가중치 개정으로 이어졌다</td>
      </tr>
      <tr>
        <td>인적성 설문</td>
        <td>접수 · 서류 검토 단계 지원자에게 메일로 보내는 10문항 5점 척도 설문. 카테고리 통계는 코드가 계산하고 AI 는 응답을 관찰 문장으로 재서술만 한다 &mdash; 성격 유형 판정 · 점수화 금지, 미응답 불이익 없음(ADR-0027)</td>
      </tr>
      <tr>
        <td>게이트</td>
        <td>일정을 끊는 두 판정 시점 &mdash; 초기 버전 2026. 09. 04. · 1차 완성 09. 30. 문서 근거가 아니라 배포본 대조와 관통 테스트로 판정한다</td>
      </tr>
      <tr>
        <td>수직 슬라이스</td>
        <td>초기 버전 게이트의 합격 조건 하나 &mdash; 공개 지원 폼 제출 &rarr; DB 저장 &rarr; 담당자 확인까지 실데이터로 관통하는 경로. 화면 · API 를 따로 세는 대신 끝에서 끝까지 하나를 뚫었는지로 본다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <h3 class="apx__h3">1-2. AI · 모델 <small>본문 7장에서 쓰인 말</small></h3>

  <div class="tbl__scroll">
  <table class="tbl terms">
    <thead>
      <tr><th>용어</th><th>정의</th></tr>
    </thead>
    <tbody>
      <tr>
        <td>아르</td>
        <td>도구 호출 에이전트의 이름. 담당자 화면에서는 채팅 패널(Ctrl+K)로, 지원자 메일에서는 서명 "채용 에이전트 아르"로 나타난다. 도구 12종을 쓰고 쓰기 작업은 확인 카드를 거친다</td>
      </tr>
      <tr>
        <td>도구 호출 (Tool-Calling)</td>
        <td>자연어 한 문장을 검색 &rarr; 조회 &rarr; 단계 변경 같은 도구 호출로 분해해 순차 실행하는 방식. "백엔드 공고에서 3년차 이상 찾아서 상위 2명 면접으로 올려줘"가 한 단위다</td>
      </tr>
      <tr>
        <td>RAG</td>
        <td>Retrieval-Augmented Generation &mdash; 먼저 문서를 찾아 근거로 붙이고 그 근거 안에서 LLM 이 답하는 방식. Arda 는 ko-sroberta 임베딩 + pgvector 시맨틱 검색에 키워드 폴백을 병행한다(ADR-0021)</td>
      </tr>
      <tr>
        <td>프롬프트 체이닝</td>
        <td>한 번에 묻지 않고 요약 &rarr; 평가 &rarr; 추천 3단으로 나눠 호출하는 구성(ADR-0022). 프롬프트 18개는 코드로 버전 관리한다(v2 · v3)</td>
      </tr>
      <tr>
        <td>규칙 의도 라우터</td>
        <td>인사 · 능력 · 기본 FAQ 처럼 뻔한 요청을 LLM 없이 코드로 답하는 앞단. 기본 질문 구간은 $0 이고, LLM 을 타는 아르 호출은 실측 평균 $0.0075 다</td>
      </tr>
      <tr>
        <td>STT</td>
        <td>Speech-to-Text &mdash; 음성을 글로 옮기는 것. 프로덕션 기본은 OpenAI Whisper API(<code>whisper-1</code>)이고 <code>STT_BACKEND=faster_whisper</code> 면 서버 내 로컬 전사로 바뀐다(ADR-0038)</td>
      </tr>
      <tr>
        <td>sLLM</td>
        <td>경량 LLM. 지원자 개인정보를 외부 API 로 내보내지 않는 온프레미스 자체 서빙의 후보였고, 실측 후 심사 서빙에서는 뺐다</td>
      </tr>
      <tr>
        <td>QLoRA</td>
        <td>4-bit 양자화 + 저랭크 어댑터로 대형 모델을 작은 GPU 에서 파인튜닝하는 기법. Qwen3-8B 어댑터 3갈래(chat · summary · interview) 학습에 썼다</td>
      </tr>
      <tr>
        <td>judge.py</td>
        <td>모델이 무엇이든 같은 규칙(도구 이름 · no-tool 위반 · 확인 문구 · 인자 · 응답)으로 채점하는 자체 채점기(<code>ai/qwen-training/judge.py</code>). 같은 23건으로 학습 전 26.1% &rarr; Claude Haiku 69.6% &rarr; Qwen v9 73.9% 를 쟀다</td>
      </tr>
      <tr>
        <td>회귀 하네스</td>
        <td>띄워 둔 <b>로컬</b> 백엔드의 <code>/agent/chat</code> 에 시나리오 40개(정형 10 + 표현 변형 30)를 실호출해 정답 · 속도 · 창작 여부를 보는 자체 도구(<code>backend/tests/prompt_regression/</code>). 모델 · 프롬프트를 바꿀 때마다 돌리고, 운영 주소로는 돌리지 않는다 &mdash; 만든 지원서 · 평가가 추가 전용 원장에 영구히 남기 때문이다</td>
      </tr>
      <tr>
        <td>ko-sroberta</td>
        <td>한국어 문장 임베딩 모델. 스킬 · 학력 · 경력 문장을 768차원 벡터로 만들어 저장한다</td>
      </tr>
      <tr>
        <td>pgvector</td>
        <td>PostgreSQL 확장 &mdash; 벡터 임베딩 저장과 유사도 검색. 운영 DB 이미지도 <code>pgvector/pgvector:pg16</code> 으로 맞췄다</td>
      </tr>
      <tr>
        <td>ViT · MediaPipe</td>
        <td>표정 분류(Vision Transformer)와 얼굴 랜드마크 추출. lie-detection 서비스가 쓰며 결과는 담당자 참고 지표로만 표시된다(ADR-0029 · 0032)</td>
      </tr>
      <tr>
        <td>참고 지표</td>
        <td>담당자 화면에 수치로 보이되 <b>점수 · 합불 판정의 재료가 아닌</b> 값. 표정 · 음성 신호가 여기에 해당한다</td>
      </tr>
      <tr>
        <td>AI 추정</td>
        <td>지원자가 폼에 적지 않아 이력서에서 추출해 채운 값에 붙이는 표식. 사람이 적은 값과 구분하기 위한 것이다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <h3 class="apx__h3">1-3. 아키텍처 · 운영 · 보안 <small>본문 4·5·9장에서 쓰인 말</small></h3>

  <div class="tbl__scroll">
  <table class="tbl terms">
    <thead>
      <tr><th>용어</th><th>정의</th></tr>
    </thead>
    <tbody>
      <tr>
        <td>ADR</td>
        <td>Architecture Decision Record &mdash; 결정 하나를 문제 · 결정 · 결과로 남긴 문서. 36편이며 "안 한 것"에도 ADR 이 있다(Kubernetes 제외 0001 · 실시간 공동편집 제외 0005)</td>
      </tr>
      <tr>
        <td>도메인 오너제</td>
        <td>한 사람이 도메인(폴더) 하나를 소유하고 그 로드맵이 작업의 기준이 되는 운영 방식(ADR-0007). 도메인 안의 판단은 묻지 않고 진행하며 승인 게이트가 없다</td>
      </tr>
      <tr>
        <td>계약 우선</td>
        <td>ERD(<code>01-erd.md</code>)와 API 문서(<code>02-api.md</code>)를 전원의 계약으로 두고, 코드와 <b>같은 커밋</b>에서 갱신하는 규칙. 문서 갱신 없는 스키마 변경은 금지다</td>
      </tr>
      <tr>
        <td>헥사고날 (Ports &amp; Adapters)</td>
        <td>도메인이 요구하는 계약을 포트(<code>ports/output/*</code> ABC)로 두고 구현을 어댑터(<code>adapter/outbound/{pg,llm,mail}</code>)로 갈아끼우는 구조. 전면이 아니라 부분 적용이다(ADR-0035)</td>
      </tr>
      <tr>
        <td>Bounded Context</td>
        <td>용어와 모델이 일관되게 통하는 경계. Arda 는 허브가 하나가 아니라서 hiring · talent · application · interview 4개로 나눴다</td>
      </tr>
      <tr>
        <td>alembic</td>
        <td>스키마 이행(마이그레이션) 도구. 리비전 26개이며 스키마 변경은 코드 · ERD 와 같은 커밋에 리비전을 함께 넣는다. 배포 때는 서버의 <code>deploy-arda.sh</code> 가 pull &rarr; build &rarr; <code>alembic upgrade head</code> &rarr; <code>up</code> 순으로 돌리고, 이행이 실패하면 거기서 멈춰 기존 컨테이너가 계속 산다</td>
      </tr>
      <tr>
        <td>드리프트 검사</td>
        <td>모델 정의와 alembic 이행 결과를 CI 가 비교해 이행 누락을 잡는 검사(2026-09-17 도입). 손 SQL 로 스키마를 맞추던 시절의 사고를 막기 위한 것이다</td>
      </tr>
      <tr>
        <td>자동 CD</td>
        <td><code>main</code> 머지 &rarr; 서버 systemd 타이머가 2분마다 확인 &rarr; pull · build · <code>up -d</code>. 머지가 곧 배포이므로 CI 빨간불인 PR 은 머지하지 않는다</td>
      </tr>
      <tr>
        <td>CI 5잡</td>
        <td>push · PR 마다 도는 GitHub Actions &mdash; 백엔드 린트(<code>ruff --select F</code>) · 백엔드 pytest(실제 PostgreSQL + pgvector 에 이행 후) · 프론트 <code>oxlint + tsc -b + vite build</code> · AI 면접 서버 pytest · <code>flutter test</code></td>
      </tr>
      <tr>
        <td>presigned URL</td>
        <td>S3 가 발급하는 일회성 업로드 URL. 브라우저가 S3 로 직접 올리므로 이력서 파일이 API 서버를 거치지 않는다</td>
      </tr>
      <tr>
        <td>n8n</td>
        <td>오픈소스 워크플로 자동화 도구. API 가 쏘는 웹훅을 받아 SMTP 로 메일을 보내고, n8n 이 멈춰도 API 가 5분마다 밀린 메일을 최대 3회 재발송한다(ADR-0030)</td>
      </tr>
      <tr>
        <td>Caddy</td>
        <td>리버스 프록시 · 인증서 자동 발급. 443 을 받아 FastAPI · lie-detection(<code>/ai/</code>) · n8n(<code>/n8n/</code>)으로 경로를 나눈다</td>
      </tr>
      <tr>
        <td>SES · SQS</td>
        <td>AWS 메일 발송 · 메시지 큐 서비스. 초기 메일 경로였으나 폐기했고 현재는 n8n 웹훅 + SMTP 단일 경로다(ADR-0031 · 0036)</td>
      </tr>
      <tr>
        <td>무결성 원장</td>
        <td>이력서 · 자소서의 파일 지문(SHA-256)을 해시 사슬로 쌓는 <b>추가 전용</b> 테이블. DB 트리거가 UPDATE · DELETE · TRUNCATE 를 거부한다(ADR-0028)</td>
      </tr>
      <tr>
        <td>앵커링</td>
        <td>사슬 머리 해시를 외부 체인에 올려 그 시점 이후의 위 · 변조를 밖에서 검증할 수 있게 하는 것. 서명 개인키는 서버가 아니라 GitHub Actions 에 둔다</td>
      </tr>
      <tr>
        <td>Sepolia · OpenTimestamps</td>
        <td>못 박는 곳이 둘이다 &mdash; Sepolia(이더리움 테스트넷)는 탐색기 링크로 <b>보여주는 쪽</b>, OpenTimestamps 는 비트코인에 <b>남기는 쪽</b>. 운영 체인은 Polygon Amoy 무료 가스가 말라 Sepolia 로 옮겼다(2026-09-07)</td>
      </tr>
      <tr>
        <td>JWT</td>
        <td>담당자 인증 토큰(12시간). 비활성 계정은 이미 발급된 토큰이어도 401 이다</td>
      </tr>
      <tr>
        <td>RBAC</td>
        <td>Role-Based Access Control &mdash; 역할 기반 접근 제어. Arda 의 등급은 위계가 아니라 조작 권한의 유무이며 <code>admin</code> · <code>member</code> 둘뿐이다(ADR-0017). 조회는 로그인만 하면 전부 허용된다</td>
      </tr>
      <tr>
        <td>서비스 토큰</td>
        <td>n8n · 판정 워커 같은 기계가 <code>/internal/*</code> 를 부를 때 쓰는 토큰. 사람 계정과 경로가 분리돼 있다</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="apx__sec">

  <h2><span class="apx__num">2.</span> 관련 서식</h2>
  <p class="apx__note">
    사람 승인 게이트가 없는 팀이라 <b>기록이 곧 리뷰</b>다(2026-08-28 리뷰 게이트 폐지 &rarr;
    09-04 브랜치&rarr;PR&rarr;자체 머지). 서식은 그 기록이 사람마다 다른 모양이 되지 않게 하는 장치이고,
    아래 아홉 중 여덟은 코드 저장소에 파일로 있어 복사해 쓴다(마지막 칸반 · 피드백 YAML 만
    팀 문서 사이트 저장소에 있다). 서식을 문서로 정한 이유는 단순하다 &mdash;
    나중에 왜 그렇게 했는지 묻는 사람이 읽을 것이 PR 본문과 이 문서들밖에 없기 때문이다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl forms">
    <thead>
      <tr><th>서식</th><th>원본 위치</th><th>반드시 들어가는 것</th></tr>
    </thead>
    <tbody>
      <tr>
        <td>작업 지시서</td>
        <td><code>docs/02_tasks/_template.md</code></td>
        <td>배경 / <b>선행 조건 &mdash; 없으면 중단</b> / 측정 가능한 완료 조건 / 완성 예시 실물 하나 / 진행 원장 표 / 참고 문서 / Claude 에게 붙여넣을 지시문 / 검증 방법 / 막히면 · 되돌리기 / PR 체크리스트. <b>지시서 하나 = PR 하나</b>이고, 2026-08-24 오너제 전환(ADR-0007) 뒤로는 각 도메인 오너가 자기 지시서를 쓴다</td>
      </tr>
      <tr>
        <td>결정 기록 (ADR)</td>
        <td><code>docs/03_decision/NNNN-제목.md</code></td>
        <td>머리말에 상태 · 확정일 · 작성 도메인 · <b>개정 대상 ADR 번호</b> · 연계 문서, 본문은 문제 &rarr; 결정(채택 / 거부) &rarr; 결과. 개정할 때 원문을 지우지 않고 절을 덧붙인다 &mdash; 반박되지 않은 근거는 "남은 숙제"로 그대로 남긴다</td>
      </tr>
      <tr>
        <td>주차 계획</td>
        <td><code>docs/00_overview/06-weekly.md</code> §양식</td>
        <td>주 마감 게이트 하나 + 도메인별 이번 주 한 줄 + 도메인 간 조율 표. <b>한 번 쓴 절은 고치지 않고</b> 하위 절(<code>WN-2</code>)로 덧붙이며, 하위 절이 3개를 넘으면 그 주 계획이 틀렸다는 신호로 다음 주차 절에 원인을 한 줄 적는다</td>
      </tr>
      <tr>
        <td>커밋 메시지</td>
        <td><code>docs/00_overview/03-conventions.md</code></td>
        <td><code>&lt;type&gt;(&lt;기능번호|도메인&gt;): &lt;한국어 요약&gt;</code> &mdash; type 은 feat · fix · docs · test · chore · refactor 여섯. 무엇이 왜 바뀌었는지와 실행 · 테스트 결과 한 줄을 넣는다</td>
      </tr>
      <tr>
        <td>브랜치 · PR</td>
        <td><code>docs/00_overview/03-conventions.md</code></td>
        <td>브랜치 <code>&lt;type&gt;/&lt;주제&gt;</code> &rarr; 실행 · 테스트 &rarr; push &rarr; PR 오픈 &rarr; CI 초록 확인 &rarr; 자체 머지. <code>main</code> 직접 push · force push 는 GitHub 브랜치 보호가 차단한다. PR 본문이 곧 기록이라 무엇을 왜 바꿨는지와 검증 결과를 붙인다</td>
      </tr>
      <tr>
        <td>QA 시나리오</td>
        <td><code>docs/00_overview/qa-scenarios.md</code></td>
        <td>항목마다 <b>전제</b>(어떤 상태에서) &rarr; <b>절차</b>(누가 뭘 클릭 · 입력) &rarr; <b>기대 결과</b>(무엇이 보이면 성공) 셋. 확정되지 않은 UI 는 "(화면 확정 후 갱신)"으로 표시해 빈칸을 상상으로 채우지 않는다</td>
      </tr>
      <tr>
        <td>메일 문구</td>
        <td><code>docs/00_overview/email-templates.md</code></td>
        <td>단계별 4종 + 접수 확인 1종의 제목 · 본문. 변수는 {% raw %}<code>{{지원자명}}</code> <code>{{공고명}}</code> <code>{{회사명}}</code> <code>{{면접일시}}</code> <code>{{서명}}</code>{% endraw %} 다섯이고, 서명은 발송 주체에 따라 사람 · 아르 · 채용팀 세 갈래로 채워지되 <b>합격 · 불합격은 주체와 무관하게 사람 이름</b>이다. 운영 문구는 설정 화면에서 편집하며 <code>email_templates</code> 테이블의 오버라이드가 우선한다</td>
      </tr>
      <tr>
        <td>스키마 이행</td>
        <td><code>backend/alembic/</code></td>
        <td>스키마를 바꾼 커밋에 리비전 하나. 손 SQL 을 문서에 적던 방식은 2026-09-01 에 끝냈다 &mdash; 그날 로컬 테스트 101건 error 와 운영 AI 요약 전건 실패를 손 SQL 로 수습한 것이 도입 이유다. 남들은 <code>uv run alembic upgrade head</code> 한 줄로 따라온다</td>
      </tr>
      <tr>
        <td>칸반 · 피드백</td>
        <td>팀 문서 사이트의<br><code>_data/kanban/&lt;아이디&gt;.yml</code><br><code>_data/feedback/&lt;아이디&gt;.yml</code><br><small>규약은 <code>03-conventions.md</code></small></td>
        <td>사람마다 <b>자기 파일만</b> 고친다 &mdash; 소유 파일을 갈라 충돌을 구조적으로 없앴다. 칸반은 "지금 무엇을 하고 있나", 로드맵(<code>docs/01_role/</code>)은 "범위 · 마일스톤 · 큐 순서"로 역할을 나눠 진행률을 이중 관리하지 않는다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <h3 class="apx__h3">2-1. 지시서 골격</h3>
  <p class="apx__note">
    절 이름이 곧 체크리스트다. "완성 예시"에 형식을 글로 설명하지 않고 완성된 실물 하나를 붙이는 것이
    이 서식의 핵심이다 &mdash; 나머지는 그것과 똑같이 만들면 되기 때문이다.
  </p>
  <div class="apx__pre"><code># [기능번호] 제목
&gt; 담당: (이름) · 브랜치: feat/&lt;기능번호&gt;-&lt;슬러그&gt; · PR 단위: (어디까지 끝내고 PR 을 올리는지)

## 배경                    ← 전체 그림에서 어디에 끼는지 2~3줄
## 선행 조건 — 없으면 중단   ← 하나라도 없으면 시작하지 않는다. 없는 것을 상상해서 만들지 않는다
## 완료 조건                ← "POST /… 호출 시 …가 저장된다" 처럼 측정 가능하게
## 완성 예시                ← 설명이 아니라 완성품 하나(경로 + 내용)
## 진행 원장                ← 배치로 나눠 맡는 작업에만. 이어받는 사람은 이 표만 보면 된다
## 참고 문서                ← 01-erd.md 의 해당 테이블 · 02-api.md 의 해당 경로
## Claude에게 시키기        ← 그대로 붙여넣을 지시문. 한 번에 안 되면 완료 조건을 하나씩
## 검증 방법                ← 실행 명령 + 무엇이 보이면 성공인지
## 막히면 · 되돌리기         ← 30분 룰 · git checkout -- . · 브랜치째 버리기
## PR 체크리스트</code></div>

  <h3 class="apx__h3">2-2. 브랜치 · 커밋 실물</h3>
  <p class="apx__note">
    기능 번호가 있는 작업은 번호를, 없으면 도메인명을 접두어로 쓴다.
    아래는 실제 <code>main</code> 이력에서 가져온 것이다.
  </p>
  <div class="apx__pre"><code>git switch -c feat/front-logout-in-account-menu

feat(J7): 더미 지원서 10만 건 생성기
feat(front): React 라우팅 뼈대
fix(agent): 무관 질문 거절을 '데이터 근거' 기준으로 명확화
fix(front): PC 에서 AI 면접 카메라가 얼굴만 확대돼 보이던 것 (도메인 밖 편집)</code></div>
  <p class="apx__note" style="margin-bottom:0;">
    마지막 줄처럼 <b>남의 도메인 폴더를 고쳤으면 커밋 메시지에 명시</b>하고 팀 채널에 사후 한 줄 공지한다.
    스키마 · API · 공용 문서(<code>docs/00_overview/</code> · <code>CLAUDE.md</code> · <code>.github/</code>)도 같은 취급이다.
  </p>

</div>

<div class="apx__sec">

  <h2><span class="apx__num">3.</span> 참고 자료</h2>
  <p class="apx__note">
    이 보고서의 수치와 판단은 아래 원문에서 왔다. 배포본 · 저장소 · 결정 기록 순으로 적었고,
    서로 어긋날 때 <b>무엇이 진실인지</b>도 함께 적었다 &mdash;
    요청 · 응답의 진실은 Swagger 이고, 스키마의 진실은 <code>01-erd.md</code> 이며,
    담당 배정의 진실은 <code>04-team.md</code> 다.
  </p>

  <h3 class="apx__h3">3-1. 서비스 · 저장소</h3>

  <div class="tbl__scroll">
  <table class="tbl links">
    <thead>
      <tr><th>자료</th><th>주소</th><th>내용</th></tr>
    </thead>
    <tbody>
      <tr>
        <td>프로젝트 저장소</td>
        <td><a href="https://github.com/Seuk-Team/Arda">github.com/Seuk-Team/Arda</a></td>
        <td>코드 · 문서 · ADR 전부. 2026-09-04 에 <code>Team-Seuk</code> 에서 이관했고 구 조직은 삭제됐다</td>
      </tr>
      <tr>
        <td>서비스 (웹)</td>
        <td><a href="https://seuk.suvisdev.cloud">seuk.suvisdev.cloud</a></td>
        <td>React · Vercel 배포(<code>main</code> 머지 후 1~2분 내 자동 반영). 담당자 화면과 공개 지원 폼이 모두 여기에 있다</td>
      </tr>
      <tr>
        <td>API 문서</td>
        <td><a href="https://api.seuk.suvisdev.cloud/docs">api.seuk.suvisdev.cloud/docs</a></td>
        <td>Swagger &mdash; 라우트 107개의 요청 · 응답 <b>진실은 여기</b>다. 접두사는 <code>/api/v1</code> 이고 배포 · 모니터링용 <code>/health</code> 가 따로 열려 있다</td>
      </tr>
      <tr>
        <td>팀 문서 사이트</td>
        <td><a href="https://ats.suvisdev.cloud/">ats.suvisdev.cloud</a></td>
        <td>사업 개요 · 프로젝트 소개 · 개발 요구사항 · 수행 지침 · 문제와 극복 · 개발 로그 원문</td>
      </tr>
      <tr>
        <td>팀 칸반</td>
        <td><a href="https://ats.suvisdev.cloud/kanban/">ats.suvisdev.cloud/kanban/</a></td>
        <td>각자의 진행 상태(todo / doing / done). 사람마다 자기 YAML 파일만 고친다</td>
      </tr>
      <tr>
        <td>피드백 트래커</td>
        <td><a href="https://ats.suvisdev.cloud/feedback/">ats.suvisdev.cloud/feedback/</a></td>
        <td>멘토링 · 리허설에서 받은 지적과 처리 결과</td>
      </tr>
      <tr>
        <td>본 보고서</td>
        <td><a href="https://ats.minahdev.cloud">ats.minahdev.cloud</a></td>
        <td>이 사이트 &mdash; 12장 구성의 개발 보고서</td>
      </tr>
      <tr>
        <td>표정 분류 모델</td>
        <td><a href="https://huggingface.co/cloverky/arda-expression-vit">huggingface.co/cloverky/arda-expression-vit</a></td>
        <td>lie-detection 서비스가 쓰는 ViT 표정 가중치(ADR-0032). 결과는 참고 지표 전용이다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <h3 class="apx__h3">3-2. 저장소 안의 원문</h3>

  <div class="tbl__scroll">
  <table class="tbl links">
    <thead>
      <tr><th>경로</th><th>내용</th></tr>
    </thead>
    <tbody>
      <tr><td><code>docs/00_overview/00-overview.md</code></td><td>프로젝트 개요 &mdash; 범위와 진행 순서의 정의</td></tr>
      <tr><td><code>docs/00_overview/01-erd.md</code></td><td>테이블 정의서 28개(v2.8 · 2026-09-17). <b>전원의 스키마 계약</b>이며 <code>01-erd.png</code> 다이어그램이 붙는다</td></tr>
      <tr><td><code>docs/00_overview/02-api.md</code></td><td>API 엔드포인트 목록 &mdash; "무엇이 있는가"만 유지하고 요청 · 응답 상세는 Swagger 가 진실이다</td></tr>
      <tr><td><code>docs/00_overview/03-conventions.md</code></td><td>협업 규칙 &mdash; 커밋 · PR · 사후 공지 · ADR 개정 절차</td></tr>
      <tr><td><code>docs/00_overview/04-team.md</code></td><td>작업 분배(도메인 오너제) &mdash; <b>현재 배정의 진실</b></td></tr>
      <tr><td><code>docs/00_overview/05-design.md</code></td><td>디자인 규칙 · 토큰 · 화면 지도</td></tr>
      <tr><td><code>docs/00_overview/06-weekly.md</code></td><td>주차별 계획과 주간 계획 프롬프트(오너용)</td></tr>
      <tr><td><code>docs/00_overview/07-deploy.md</code></td><td>실서버 구성과 사용법 &mdash; compose · 자동 CD · 백업 · 경보</td></tr>
      <tr><td><code>docs/00_overview/08-local-setup.md</code></td><td>로컬 환경 셋업과 이행 체크리스트 &mdash; "코드가 아니라 내 환경이 원인인 것"을 모은 곳</td></tr>
      <tr><td><code>docs/00_overview/09-handover.md</code></td><td>인수인계(2026-09-02 팀장 이탈 시점)</td></tr>
      <tr><td><code>docs/00_overview/10-team-setup.md</code></td><td>새 인프라 기준 팀원 셋업(2026-09-04)</td></tr>
      <tr><td><code>docs/00_overview/qa-scenarios.md</code></td><td>필수 기능 QA 시나리오 &mdash; 게이트 판정의 기준</td></tr>
      <tr><td><code>docs/00_overview/email-templates.md</code></td><td>단계별 자동 발송 메일 문구의 기본값</td></tr>
      <tr><td><code>docs/01_role/*.md</code></td><td>도메인별 로드맵 5편(infra · backend · frontend · agent · app) &mdash; 범위 · 마일스톤 · 작업 큐</td></tr>
      <tr><td><code>docs/02_tasks/</code></td><td>작업 지시서와 <code>_template.md</code>. 대부분 W1~W2 에 쓰였고 README 가 "그때의 체계"와 지금의 차이를 대조해 둔다</td></tr>
      <tr><td><code>docs/03_decision/</code></td><td>ADR 36편 원문 &mdash; 아래 3-3 목록의 출처</td></tr>
      <tr><td><code>docs/04_planning/</code></td><td>기획 단계 시장조사 &mdash; <code>00_summary_ko.md</code> · <code>01-시장조사-방향성.md</code> · 초기 프로토타입 <code>05_prototype.html</code>. 아래 3-4 의 법령 근거가 여기서 나왔다</td></tr>
      <tr><td><code>docs/07_eval/</code></td><td><code>fit-check-2026-09.md</code>(지원자 24명 서류 판정 정확성 분석) · <code>eval_cases.yaml</code></td></tr>
      <tr><td><code>ai/qwen-training/</code></td><td>Qwen3-8B QLoRA 학습 · <code>judge.py</code> 채점기 · Qwen vs Claude 비교 보고서</td></tr>
      <tr><td><code>ai/lie-detection/</code></td><td>실시간 전사 · 표정/음성 참고 지표 서비스(별도 컨테이너 · <code>/ai/*</code>)</td></tr>
      <tr><td><code>infra/</code></td><td><code>docker-compose.prod.yml</code> · <code>Caddyfile</code> · <code>deploy-arda.sh</code> · <code>backup-arda-db.sh</code> · <code>cloudwatch-alarms.yml</code></td></tr>
      <tr><td><code>.github/workflows/ci.yml</code></td><td>CI 5잡. 같은 폴더에 무결성 앵커 발행과 15분 외부 헬스체크 워크플로가 있다</td></tr>
      <tr><td><code>backend/alembic/README.md</code></td><td>이행 도구가 들어온 이유(2026-09-01 사고 2건)와 사용법</td></tr>
      <tr><td><code>CLAUDE.md</code></td><td>저장소 작업 규칙 &mdash; 시작 전 읽을 것 · 범위 · 반영 방식 · 금지 · 검증</td></tr>
    </tbody>
  </table>
  </div>

  <h3 class="apx__h3">3-3. 결정 기록 (ADR) 36편 <small>2026-09-22 기준</small></h3>
  <p class="apx__note">
    번호 0018~0020 은 결번이고, 0030 은 같은 번호로 두 건이 있다(n8n 분리 · 거짓말 탐지 미결 확정).
    개정된 ADR 도 목록에서 빼지 않는다 &mdash; 원 결정과 개정 결정이 함께 남아야
    "왜 뒤집었나"를 설명할 수 있기 때문이다. 원문은 <code>docs/03_decision/</code> 에 있다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl adr">
    <thead>
      <tr><th>번호</th><th>결정</th><th>비고</th></tr>
    </thead>
    <tbody>
      <tr><td>0001</td><td>Kubernetes 제외 &mdash; "한 달 안에 굴렸다고 말할 수 없는 것은 넣지 않는다"</td><td class="dash">&mdash;</td></tr>
      <tr><td>0002</td><td>실시간 표정분석 제외</td><td><span class="tag tag--rev">개정</span> 0029 로</td></tr>
      <tr><td>0003</td><td>AI 는 추천까지만 &mdash; 확정은 사람</td><td><span class="tag tag--rev">개정</span> 0034 로 범위 조정(서류 · 면접 자동 판정, 최종 합불만 사람)</td></tr>
      <tr><td>0004</td><td>음성은 STT + 기존 텍스트 에이전트 (speech-to-speech 제외)</td><td class="dash">&mdash;</td></tr>
      <tr><td>0005</td><td>실시간 공동편집 제외 &mdash; 메모는 행 추가 방식</td><td class="dash">&mdash;</td></tr>
      <tr><td>0006</td><td>프론트 React 확정 &mdash; 서버 템플릿(Jinja) 기각</td><td class="dash">&mdash;</td></tr>
      <tr><td>0007</td><td>작업 분배를 도메인 오너제로 전환</td><td class="dash">&mdash;</td></tr>
      <tr><td>0008</td><td>에이전트 · 앱 정식 트랙 승격</td><td class="dash">&mdash;</td></tr>
      <tr><td>0009</td><td>에이전트 UI 위치 (+ 음성 입력 위치)</td><td class="dash">&mdash;</td></tr>
      <tr><td>0010</td><td>앱 Flutter 확정</td><td class="dash">&mdash;</td></tr>
      <tr><td>0011</td><td>에이전트 모델 · 비용 (Haiku · 원가 실측)</td><td>2026-09-15 실측으로 채팅 · 요약 기본 모델을 <code>claude-haiku-4-5</code> 로 유지하기로 했고, 그 개정은 후속으로 남았다</td></tr>
      <tr><td>0012</td><td>서류심사 AI 분류 기준</td><td class="dash">&mdash;</td></tr>
      <tr><td>0013</td><td>면접관 배정 정책</td><td class="dash">&mdash;</td></tr>
      <tr><td>0014</td><td>프로젝트 이름 &mdash; Arda</td><td>위 1절 "시스템명" 참조</td></tr>
      <tr><td>0015</td><td>엔티티 리졸버 한글 수사 오탐 방지</td><td class="dash">&mdash;</td></tr>
      <tr><td>0016</td><td>면접 일정 자동화 &mdash; 토큰 공개 페이지 + 기존 메일 파이프라인 재사용</td><td class="dash">&mdash;</td></tr>
      <tr><td>0017</td><td>역할을 admin · member 2종으로 이분화 &mdash; 면접관 조회 제한 폐지</td><td class="dash">&mdash;</td></tr>
      <tr><td>0021</td><td>RAG 파이프라인 &mdash; 임베딩 기반 시맨틱 검색</td><td class="dash">&mdash;</td></tr>
      <tr><td>0022</td><td>프롬프트 체이닝 &mdash; 요약 &rarr; 평가 &rarr; 추천 단계별 파이프라인</td><td class="dash">&mdash;</td></tr>
      <tr><td>0023</td><td>에이전트 평가 프레임워크 &mdash; 답변 품질 자동 측정</td><td class="dash">&mdash;</td></tr>
      <tr><td>0024</td><td>sLLM 로컬 모델 전략 &mdash; 하이브리드 구성</td><td>Qwen 어댑터는 R&amp;D 자산으로 보존, 프로덕션은 Claude</td></tr>
      <tr><td>0025</td><td>운영 권한을 팀장 개인 계정에서 떼어낸다</td><td class="dash">&mdash;</td></tr>
      <tr><td>0026</td><td>AI 면접은 한다 &mdash; 단 음성으로 긴장도 · 거짓말을 판별하지 않는다</td><td><span class="tag tag--rev">개정</span> 0029 로</td></tr>
      <tr><td>0027</td><td>인적성 검사는 한다 &mdash; AI 는 응답 요약만, 성격 판정 금지</td><td class="dash">&mdash;</td></tr>
      <tr><td>0028</td><td>이력서 · 자소서는 해시 사슬로 못 박는다</td><td>공개 체인(Sepolia) 앵커는 2단계</td></tr>
      <tr><td>0029</td><td>표정 · 음성으로 진위를 판별한다 &mdash; 0002 · 0026 개정</td><td>점수 미반영 참고 지표까지만</td></tr>
      <tr><td>0030</td><td>알림 · 메일 자동화를 n8n 워크플로로 분리</td><td>AWS 를 떠나도 돌게</td></tr>
      <tr><td>0030</td><td>거짓말 탐지 운영 전 미결 사항 확정 &mdash; 0029 보완</td><td>동일 번호 두 건</td></tr>
      <tr><td>0031</td><td>AWS 를 EC2 · S3 로 줄이고 나머지는 self-host 교체 가능하게</td><td class="dash">&mdash;</td></tr>
      <tr><td>0032</td><td>추론 모델 3종 확정 &mdash; ViT · Whisper large-v3-turbo · Qwen3-8B</td><td>온프레미스 기준</td></tr>
      <tr><td>0033</td><td>지원자 앱 로그인 &mdash; 이메일 + 생년월일 8자리</td><td class="dash">&mdash;</td></tr>
      <tr><td>0034</td><td>에이전트 자동 심사 &mdash; 서류 · 면접은 아르가 판정, 최종 합불만 사람</td><td class="dash">&mdash;</td></tr>
      <tr><td>0035</td><td>헥사고날 부분 적용 · Bounded Context 다중 스타 · Full DDD 는 안 함</td><td class="dash">&mdash;</td></tr>
      <tr><td>0036</td><td>SQS 메일 워커 폐기 &mdash; n8n 단일 발송 경로로 고정</td><td class="dash">&mdash;</td></tr>
      <tr><td>0037</td><td>회사 통합 API · 지원자 흡수 경로 4갈래 · 코어는 API push 하나</td><td class="dash">&mdash;</td></tr>
      <tr><td>0038</td><td>실시간 면접 전사 &mdash; 프로덕션 기본을 OpenAI API 로</td><td><code>STT_BACKEND</code> 한 변수로 결정</td></tr>
    </tbody>
  </table>
  </div>

  <h3 class="apx__h3">3-4. 외부 근거</h3>
  <p class="apx__note">
    "안 한다"는 결정에 붙은 바깥 근거들이다. 기능을 뺀 이유를 발표에서 질문받았을 때
    구현 난이도가 아니라 <b>이 근거</b>로 답하기 위해 ADR &middot; 기획 문서 본문에 그대로 적어 두었다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl links">
    <thead>
      <tr><th>근거</th><th>어디에 쓰였나</th></tr>
    </thead>
    <tbody>
      <tr>
        <td>HireVue 표정분석 중단 (2021년 3월) &mdash; 독립 감사에서 표정 데이터의 직무성과 예측 기여도 0.25% 미만</td>
        <td>ADR-0002 표정분석 제외의 1순위 근거. ADR-0029 로 도입을 개정한 뒤에도 이 근거를 지우지 않고 "점수 재료로는 쓰지 않는다"는 제약으로 남겼다</td>
      </tr>
      <tr>
        <td>얼굴 움직임만으로 감정을 추론하기 어렵다는 학계 정리 (Barrett 외, 2019)</td>
        <td>같은 ADR-0002. 안면마비 · 자폐 · 시선 패턴 차이를 결함으로 점수화하는 차별 위험과 함께 적혀 있다</td>
      </tr>
      <tr>
        <td>채용절차법 제4조의3 · 개인정보보호법 제15조 &mdash; 구직자 개인정보 수집을 <b>직무 관련 최소한</b>으로 제한</td>
        <td>기획 단계 시장조사(<code>docs/04_planning/</code>)에 적힌 컴플라이언스 근거. 지원자 SNS 크롤링은 ADR-0002 에서 범위 밖으로 두었고 개정 없이 유지 중이다</td>
      </tr>
      <tr>
        <td>개인정보보호법 2023년 개정 &mdash; 완전 자동화된 결정에 대한 <b>거부 · 설명 요구권</b></td>
        <td>음성으로 긴장도를 추론해 탈락시키면 근거를 설명할 수 없다는 것이 ADR-0026 제외 사유였고, ADR-0027(성격 판정 금지) · ADR-0029(점수 미반영 제약)도 같은 조항을 근거로 든다. ADR-0030 은 "최종 결정은 사람"이라 이 조항에 걸리지 않는다고 정리한다</td>
      </tr>
      <tr>
        <td>Ethereum Sepolia 테스트넷 · OpenTimestamps(비트코인)</td>
        <td>제출물 무결성 앵커의 두 경로(ADR-0028). 보여주는 쪽과 남기는 쪽을 나눠 같은 사슬 머리라도 네트워크마다 한 행으로 기록한다</td>
      </tr>
      <tr>
        <td>Qwen3-8B · Whisper large-v3-turbo · ViT</td>
        <td>온프레미스 추론 모델 3종(ADR-0032). 학습 · 실측 후 심사 서빙에서는 빠졌고 R&amp;D 자산으로 보존한다</td>
      </tr>
      <tr>
        <td>Anthropic Claude(<code>claude-haiku-4-5</code>) · OpenAI Whisper API(<code>whisper-1</code>)</td>
        <td>2026-09-18 확정된 심사 서빙 구성. 정확도가 아니라 수치 추론 · 형식 안정성 · 지연 · 동시성에서 갈렸다</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<a class="apx__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
