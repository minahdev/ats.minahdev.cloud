---
layout: default
title: 시스템 설계
permalink: /design/
---

<style>
.dsn { max-width: 64rem; margin: 2.5rem auto 4rem; }

.dsn__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.dsn__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.dsn__crumb a { color: #9ca3af; }
.dsn__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; word-break: keep-all; }
.dsn__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

.dsn__sec { margin-bottom: 3.25rem; }
.dsn__sec > h2 {
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
.dsn__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.dsn__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }
.dsn__p { margin: 0 0 1rem; color: #374151; font-size: .92rem; line-height: 1.8; word-break: keep-all; }
.dsn__p:last-child { margin-bottom: 0; }
.dsn__note code, .dsn__p code { font-size: .82rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }
.dsn__sub {
  margin: 2rem 0 .8rem;
  font-size: .92rem;
  font-weight: 700;
  color: #111827;
  word-break: keep-all;
}

/* 담당자 색 — 사이트 전체에서 사람마다 고정이다 */
.who {
  display: inline-block;
  padding: .06rem .4rem;
  border-radius: 3px;
  font-size: .72rem;
  font-weight: 700;
  letter-spacing: .02em;
  white-space: nowrap;
}
.who-b { background: #d1fae5; color: #065f46; }
.who-c { background: #fce7f3; color: #9d174d; }
.who-d { background: #fef3c7; color: #92400e; }
.who-e { background: #e0f2fe; color: #075985; }

/* 수치 요약 */
.dsn__stat {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(8.5rem, 1fr));
  gap: .6rem;
  margin-bottom: 2.75rem;
}
.stat { border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .85rem; }
.stat__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.stat__v { font-size: 1.05rem; font-weight: 700; color: #111827; word-break: keep-all; font-variant-numeric: tabular-nums; }
.stat__v small { font-size: .78rem; font-weight: 400; color: #9ca3af; margin-left: .15rem; font-variant-numeric: normal; }

/* 표 공통 — schedule.md 와 같은 규격 */
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
.tbl__num { text-align: right; font-variant-numeric: tabular-nums; white-space: nowrap; }
.tbl__nw { white-space: nowrap; }
.tbl--wide { min-width: 48rem; }

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
.tag--now { background: #dbeafe; color: #1e40af; }
.tag--off { background: #f3f4f6; color: #6b7280; }

/* 계층 상자 */
.layer { border: 1px solid #e5e7eb; border-radius: 6px; overflow: hidden; }
.layer__row { padding: .8rem 1rem; border-bottom: 1px solid #f3f4f6; }
.layer__row:last-child { border-bottom: 0; }
.layer__row--base { background: #f9fafb; }
.layer__k {
  display: block;
  font-size: .72rem;
  color: #9ca3af;
  letter-spacing: .03em;
  margin-bottom: .4rem;
}
.layer__v { margin: 0; font-size: .87rem; line-height: 1.75; color: #374151; word-break: keep-all; }
.layer__v code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 채택 / 거부 2단 */
.scope { display: grid; grid-template-columns: repeat(auto-fit, minmax(17rem, 1fr)); gap: .75rem; }
.scope__box { border: 1px solid #e5e7eb; border-radius: 6px; padding: .9rem 1rem; }
.scope__box--in { background: #f0fdf4; border-color: #bbf7d0; }
.scope__box--out { background: #f9fafb; }
.scope__box h3 { margin: 0 0 .6rem; font-size: .9rem; color: #111827; }
.scope__box ul { margin: 0; padding-left: 1.1rem; }
.scope__box li { font-size: .85rem; line-height: 1.75; color: #374151; word-break: keep-all; }
.scope__box--out li { color: #6b7280; }
.scope__box code { font-size: .79rem; background: rgba(0, 0, 0, .045); padding: .05rem .3rem; border-radius: 3px; }

/* 규칙 카드 */
.items { display: grid; grid-template-columns: repeat(auto-fit, minmax(16.5rem, 1fr)); gap: .7rem; }
.item { border: 1px solid #e5e7eb; border-radius: 6px; padding: .85rem 1rem; }
.item__t { margin: 0 0 .35rem; font-size: .9rem; font-weight: 700; color: #111827; word-break: keep-all; }
.item__t code { font-size: .83rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; font-weight: 400; }
.item__d { margin: 0; font-size: .85rem; line-height: 1.75; color: #6b7280; word-break: keep-all; }
.item__d code { font-size: .79rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 색 견본 */
.sw {
  display: inline-block;
  width: .78rem;
  height: .78rem;
  border-radius: 2px;
  border: 1px solid rgba(0, 0, 0, .18);
  vertical-align: -.08em;
  margin-right: .35rem;
}

.dsn__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }

@media (max-width: 34rem) {
  .dsn__stat { grid-template-columns: repeat(2, 1fr); }
}
</style>

<div class="dsn">

<div class="dsn__head">
  <p class="dsn__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 4. 시스템 설계</p>
  <h1>시스템 설계</h1>
  <p>Arda (Eval-ATS) &middot; 헥사고날 부분 적용 4 컨텍스트 &middot; 28 테이블 &middot; 107 라우트
     &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="dsn__stat">
  <div class="stat"><span class="stat__k">컨텍스트</span>
    <span class="stat__v">4<small>ADR-0035</small></span></div>
  <div class="stat"><span class="stat__k">테이블</span>
    <span class="stat__v">28<small>ERD v2.8</small></span></div>
  <div class="stat"><span class="stat__k">alembic 리비전</span>
    <span class="stat__v">26<small>0001~0026</small></span></div>
  <div class="stat"><span class="stat__k">HTTP 라우트</span>
    <span class="stat__v">107<small>+ WS 1</small></span></div>
  <div class="stat"><span class="stat__k">라우터 파일</span>
    <span class="stat__v">24<small>main.py 등록</small></span></div>
  <div class="stat"><span class="stat__k">디자인 토큰</span>
    <span class="stat__v">87<small>tokens.css</small></span></div>
</div>

<div class="dsn__sec">

  <h2><span class="dsn__num">1.</span> 시스템 아키텍처</h2>
  <p class="dsn__note">
    설계의 기준 문서는 <b>ADR-0035</b>(헥사고날 부분 적용 &middot; Bounded Context, 2026. 09. 12. 확정)다.
    아래 수치는 저장소 <code>backend/app/</code> 를 직접 센 값이고, 문서와 코드가 어긋나는 지점은
    어긋난 대로 적었다.
  </p>

  <p class="dsn__p">
    재편 전 <code>backend/app/</code> 는 레이어 분리가 없었다. 라우터 22개 &middot; SQLAlchemy 엔티티 23개
    (<code>models.py</code> 1,137줄) &middot; 도메인 로직 &middot; 인프라 어댑터가 한 패키지에 평평하게 놓여
    있었고, 그 상태가 네 가지 통증을 낳았다 &mdash; <b><code>app.models</code> 가 71개 파일에서 89회
    import</b> 되어 스키마 변경 파급을 볼 수 없었고, 큰 라우터가 500~900줄
    (<code>interviews</code> 885 &middot; <code>agent</code> 698 &middot; <code>schedules</code> 569)까지 자라
    유스케이스를 라우터가 직접 조립했으며, "단계 전이" 하나가 <code>screening.py</code> &middot;
    <code>stages.py</code> &middot; <code>stage_service.py</code> 세 파일에 흩어졌고, LLM 백엔드 스위치가
    환경변수로만 갈려 인터페이스로 승격돼 있지 않았다.
  </p>

  <p class="dsn__p">
    해법으로 <b>Full DDD 를 도입하지 않았다.</b> 팀 4명 &middot; 발표 임박 &middot; main 머지 2분 후 자동 배포라는
    조건에서 Aggregate Root &middot; Domain Events &middot; DTO 이중 레이어의 유지비가 이득을 넘기 때문이다.
    대신 <b>Ports &amp; Adapters + Repository + Bounded Context</b> 셋만 취했다. 컨텍스트를 4개로 나눈
    이유는 Arda 에 자연 허브가 하나가 아니라 <b>넷</b>이기 때문이다 &mdash; 하나로 몰면 나머지 셋이
    위성으로 왜곡된다.
  </p>

  <p class="dsn__sub">4개 Bounded Context</p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr>
        <th>컨텍스트</th>
        <th>자연 허브</th>
        <th>폴더</th>
        <th class="tbl__num">모델</th>
        <th class="tbl__num">라우트</th>
        <th>무엇을 쥐고 있나</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__nw"><b>Application</b> <span class="tag tag--now">가장 큰 스타</span></td>
        <td class="tbl__nw"><code>Application</code></td>
        <td class="tbl__nw"><code>app/application/</code></td>
        <td class="tbl__num">10</td>
        <td class="tbl__num">38</td>
        <td>접수 &rarr; 심사 &rarr; 단계 이동 &rarr; 결정. 단계 이력 &middot; 채점 &middot; 메일 &middot; 메모 &middot; 통합 검색 &middot; 아르 채팅</td>
      </tr>
      <tr>
        <td class="tbl__nw"><b>Interview</b></td>
        <td class="tbl__nw"><code>InterviewSession</code></td>
        <td class="tbl__nw"><code>app/interview/</code></td>
        <td class="tbl__num">7</td>
        <td class="tbl__num">32</td>
        <td>면접관 배정 &middot; 가용 시간 &middot; 일정 제안 &middot; 세션 실행 &middot; 채점 &middot; 실시간 소켓</td>
      </tr>
      <tr>
        <td class="tbl__nw"><b>Hiring</b></td>
        <td class="tbl__nw"><code>JobPosting</code></td>
        <td class="tbl__nw"><code>app/hiring/</code></td>
        <td class="tbl__num">5</td>
        <td class="tbl__num">7</td>
        <td>공고 CRUD &middot; 마감일 &middot; 공개 링크 &middot; 회사 프로필 &middot; 심사 가중치 <b>제공</b>(계산은 안 한다)</td>
      </tr>
      <tr>
        <td class="tbl__nw"><b>Talent</b></td>
        <td class="tbl__nw"><code>User</code></td>
        <td class="tbl__nw"><code>app/talent/</code></td>
        <td class="tbl__num">3</td>
        <td class="tbl__num">11</td>
        <td>담당자 인증 &middot; 계정 &middot; 권한, 그리고 지원자 로그인(별도 토큰 종류)</td>
      </tr>
      <tr>
        <td class="tbl__nw"><b>shared</b> <span class="tag tag--off">컨텍스트 아님</span></td>
        <td class="tbl__nw">&mdash;</td>
        <td class="tbl__nw"><code>app/shared/</code></td>
        <td class="tbl__num">3</td>
        <td class="tbl__num">20</td>
        <td>파일 &middot; 무결성 원장 &middot; <code>/internal/*</code> &middot; 메일 &middot; S3 &middot; 해시 사슬 계산</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="dsn__note" style="margin-top:1.1rem;">
    합계 모델 <b>28</b>개 &middot; 라우트 <b>108</b>개(HTTP 107 + WebSocket 1)다.
    에이전트 코드(<code>app/agent/</code>)는 <b>컨텍스트 폴더 밖에 남겼다</b> &mdash; 채팅 엔드포인트와
    오케스트레이션은 Application 에 있고(<code>api/agent.py</code> &middot; <code>agent_service.py</code>),
    프롬프트 &middot; 도구 &middot; 추출기 &middot; 임베더 &middot; STT 는 여기 있다. 소유 도메인이 다르기 때문이다.
    소유는 도메인 오너제를 그대로 따른다:
    <span class="who who-b">우정 B</span> <code>backend/</code>(agent 제외) &middot;
    <span class="who who-d">소연 D</span> <code>backend/app/agent/</code> +
    <code>application/api/agent.py</code> &mdash; <b>폴더가 갈려도 오너는 따라간다</b> &middot;
    <span class="who who-c">민아 C</span> <code>frontend/</code> &middot; <code>mobile/</code> &middot;
    <span class="who who-e">수택 E</span> <code>infra/</code> &middot; <code>.github/</code>.
  </p>

  <p class="dsn__sub">포트와 어댑터</p>

  <div class="layer">

    <div class="layer__row">
      <span class="layer__k">인바운드 &mdash; 밖에서 들어오는 길</span>
      <p class="layer__v">
        FastAPI 라우터 24개(<code>*/api/*.py</code>) + WebSocket 1개. <b><code>adapter/inbound/</code> 는
        만들지 않았다</b> &mdash; 흡수할 것이 REST 하나뿐인데 폴더를 미리 파면 빈 껍데기가 규약처럼 남는다.
      </p>
    </div>

    <div class="layer__row">
      <span class="layer__k">도메인 &mdash; 컨텍스트 4개</span>
      <p class="layer__v">
        점수 계산은 <code>application/screening.py</code> 안에서 <b>DB 를 만지지 않는 순수 함수</b>
        (<code>doc_score_from</code> &middot; <code>interview_score_from</code> &middot;
        <code>final_score</code> &middot; <code>grade</code>)로 뽑혀 가중치를 인자로 받는다 &mdash;
        <b>분리가 끝난 것은 아니다.</b> 같은 파일에 DB 를 쓰는 판정&middot;배정
        (<code>decide_document</code> &middot; <code>pick_interviewer</code>)이 함께 있다.
        단계 전이는 <code>stage_service.apply_stage_change</code>
        <b>하나만이 진실</b>이다 &mdash; REST 와 에이전트 도구(<code>change_stage</code>)가 같은 함수를
        통과한다. 이 모듈을 뺀 이유가 사고다(#148) &mdash; 두 경로가 각자 구현하던 때
        에이전트 쪽은 <code>email_logs</code> 행만 만들고 큐로 발행하지 않아
        <b>메일이 영영 안 나가는데 응답은 성공</b>이었다. 2026. 08. 31. 에 고쳤다.
      </p>
    </div>

    <div class="layer__row">
      <span class="layer__k">출력 포트 &mdash; 도메인이 요구하는 밖의 계약 (6개, ABC)</span>
      <p class="layer__v">
        <code>ports/output/</code> 에 Repository 4종(<code>application</code> &middot; <code>hiring</code> &middot;
        <code>interview</code> &middot; <code>talent</code>) + <code>llm_port</code> +
        <code>mail_dispatcher_port</code>.
      </p>
    </div>

    <div class="layer__row layer__row--base">
      <span class="layer__k">아웃바운드 어댑터 &mdash; 구현</span>
      <p class="layer__v">
        <code>adapter/outbound/pg/</code> 에 <code>Pg*Repository</code> 4종,
        <code>adapter/outbound/mail/</code> 에 디스패처 3종(<code>n8n</code> &middot; <code>smtp</code> &middot;
        <code>sqs</code>), <code>adapter/outbound/llm/</code> 는 <b>지금은 re-export 껍데기</b>다 &mdash;
        실체가 아직 <code>app/agent/backends/</code>(Anthropic &middot; Ollama)에 있고, 옛 import 경로를
        깨뜨리지 않으려고 이름만 먼저 옮겼다.
      </p>
    </div>

  </div>

  <p class="dsn__sub">채택한 것과 버린 것</p>

  <div class="scope">

    <div class="scope__box scope__box--in">
      <h3>채택</h3>
      <ul>
        <li>Ports &amp; Adapters &mdash; <code>agent/backends/base.py</code> 의 Protocol 패턴을 전 도메인으로 확장</li>
        <li>Repository &mdash; 71개 파일이 <code>models.py</code> 를 직접 참조하던 결합을 끊는다</li>
        <li>Bounded Context 4개 &mdash; 스타를 넷으로 인정</li>
        <li>SQLAlchemy 2.0 모델을 <b>그대로 도메인으로</b> 쓴다 &mdash; 컨텍스트는 폴더 이름으로만 표기</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>거부</h3>
      <ul>
        <li>Full DDD 파편(Aggregate Root &middot; Domain Events &middot; Event Sourcing) &mdash; CRUD + 워크플로 성격에 과하다</li>
        <li>DTO &harr; Pydantic 이중 레이어 &mdash; 스키마를 고칠 때마다 두 곳을 고쳐야 하고 어긋나면 런타임에만 드러난다</li>
        <li><code>domain/entities/</code> 순수 dataclass 분리 &mdash; 매핑 코드가 배로 늘고 얻는 것은 순수성뿐</li>
        <li><code>grpc/</code> &middot; <code>scheduler/</code> 폴더 선제 생성</li>
      </ul>
    </div>

  </div>

  <p class="dsn__sub">아직 안 된 것</p>
  <p class="dsn__p">
    <b>Phase 2(대형 라우터 3개를 UseCase 로 분리)는 실행하지 않았다</b> &mdash; <code>app/use_cases/</code>
    디렉터리가 저장소에 없다. 다만 셋 중 둘은 UseCase 가 아니라 <b>서비스 파일을 빼는 것으로</b>
    얇아졌다 &mdash; <code>agent.py</code> 698&rarr;<b>324</b>줄(<code>agent_service.py</code> 384),
    <code>schedules.py</code> 569&rarr;<b>444</b>줄(<code>schedule_service.py</code>).
    <code>interviews.py</code> 만 885&rarr;<b>915</b>줄로 되레 늘었다 &mdash;
    <code>session_service.py</code>(436)를 뺐는데도 그 사이 붙은 기능이 더 많았다.
    <code>shared/api/internal.py</code> 가 <code>interview/api/interview_rtc.py</code> 를 참조하는
    <b>역방향 의존이 3곳</b> 남아 있고(<code>interview/README.md</code> 는 4곳으로 적어 뒀다 &mdash;
    문서가 코드보다 한 걸음 늦다. <code>app.interview</code> 전체로 넓히면 5곳이다),
    실시간 소켓은 모듈 레벨 <code>_ROOMS</code> dict 로 상태를 들고
    있어 프로세스를 늘리면 방이 갈린다 &mdash; 컨텍스트 README 에 후속 1순위로 적어 뒀다.
    각 Phase 는 <b>스스로 CI 초록 &middot; main 배포 가능</b>해야 한다는 규칙 때문에 여기서 끊었고,
    끊긴 자리를 문서에 남겨 두는 쪽을 택했다.
  </p>

  <p class="dsn__sub">물리 배치</p>
  <p class="dsn__p">
    프론트(React/Vite)는 <b>Vercel</b>, 나머지는 <b>EC2 한 대</b>의 docker compose
    다섯 컨테이너(<code>db</code> &middot; <code>api</code> &middot; <code>caddy</code> &middot;
    <code>lie-detection</code> &middot; <code>n8n</code>)다. 443 앞의 Caddy 가 경로로 갈라
    FastAPI &middot; <code>/ai/*</code> &middot; <code>/n8n/*</code> 로 보낸다. 이력서는 presigned URL 로
    <b>브라우저에서 S3 로 직행</b>해 API 서버를 지나가지 않고, 실시간 면접 영상도 WebRTC 라
    <b>서버는 연결을 맺는 쪽지(SDP &middot; ICE)만 나른다.</b> 무거운 바이트를 API 가 들지 않는 것이
    이 배치의 골자다. AWS 사용 서비스는 8종에서 <b>3종(EC2 &middot; S3 &middot; IAM)</b>으로 줄였다
    (ADR-0031 &middot; 0036).
  </p>
  <p class="dsn__note" style="margin-top:-.6rem;">
    인스턴스는 t3.micro &rarr; t3.small &rarr; t3.medium(09. 07.) &rarr; <b>t3.large</b>(09. 09.)로
    올라왔고, <b>마지막 이관은 오진이었다.</b> 전사 컨테이너가 죽던 진짜 원인은 코드 기본값이
    CPU 에서 <code>float32</code> 로 잡히던 것이었다 &mdash; <code>int8</code> 로 바꾸자 로드 시
    RSS 가 <b>3,835MB 에서 891MB</b> 로 떨어졌고, 그 사실을 알기까지 메모리 상한 상향 5번과
    인스턴스 이관 1번을 썼다. 규모를 키워 덮는 것이 원인을 가린 사례로 문서에 남겼다.
  </p>

</div>

<div class="dsn__sec">

  <h2><span class="dsn__num">2.</span> 데이터베이스 설계 (ERD)</h2>
  <p class="dsn__note">
    전체 정의는 저장소 <code>docs/00_overview/01-erd.md</code>(<b>v2.8 &middot; 2026. 09. 17.</b>)가 진실이다.
    여기서는 핵심 엔티티와 관계, 그리고 <b>왜 그렇게 나눴는가</b>만 추린다.
  </p>

  <p class="dsn__p">
    <b>지원서(<code>applications</code>)가 축</b>이다. 지원자는 로그인 없이 지원하므로 인물 테이블을
    따로 두지 않고 지원서가 사람 정보를 안는다 &mdash; 인재풀 기능을 하게 되면 그때 분리한다.
    테이블은 <b>28개</b>이고 스키마 이행은 <b>alembic 리비전 26개</b>(<code>0001</code>~<code>0026</code>)로
    관리한다. 09. 12. 에 한 파일이던 <code>models.py</code> 를 컨텍스트별 파일
    (<code>application</code> 10 &middot; <code>interview</code> 7 &middot; <code>hiring</code> 5 &middot;
    <code>shared</code> 3 &middot; <code>talent</code> 3)로 쪼갰다.
  </p>

  <p class="dsn__sub">핵심 관계</p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr><th>관계</th><th>카디널리티</th><th>왜 이 모양인가</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__nw"><code>job_postings</code> &rarr; <code>applications</code></td>
        <td class="tbl__nw">1 : N</td>
        <td>지원서 1건은 공고 1건에 묶인다. 그래서 AI 요약이 공고 요건에 종속돼도 별도 테이블 없이 <code>applications</code> 에 직접 둘 수 있다</td>
      </tr>
      <tr>
        <td class="tbl__nw"><code>applications</code> &rarr; <code>stage_history</code></td>
        <td class="tbl__nw">1 : N</td>
        <td>단계는 덮어쓰지 않고 쌓는다. <code>changed_by</code> 가 NULL 이면 시스템&middot;자동 판정이고, 값이 있으면 사람이다 &mdash; 이 한 칸이 자동 심사의 개입 여부를 가른다</td>
      </tr>
      <tr>
        <td class="tbl__nw"><code>applications</code> &rarr; <code>evaluations</code> / <code>application_notes</code></td>
        <td class="tbl__nw">1 : N (둘 다)</td>
        <td><b>일부러 두 표로 갈랐다.</b> 평가는 1~5점이 필수인 행이라, 점수 없는 서술형이 섞이면 평가 목록과 평균이 오염된다</td>
      </tr>
      <tr>
        <td class="tbl__nw"><code>applications</code> &rarr; <code>files</code> &rarr; <code>document_anchors</code></td>
        <td class="tbl__nw">1 : N : 0..1</td>
        <td>파일 1건에 앵커 1건. 앵커에는 <b>원본이 없고 지문(SHA-256)만</b> 있어 이 표가 유출돼도 이력서 내용은 새지 않는다</td>
      </tr>
      <tr>
        <td class="tbl__nw"><code>document_anchors</code> &rarr; <code>chain_publications</code></td>
        <td class="tbl__nw">1 : N (FK 없음)</td>
        <td>각 고리가 앞 고리를 재료로 쓰므로 <b>머리 하나가 앞 전부를 덮는다</b> &mdash; 머클 트리도 고리별 증명도 필요 없다. FK 대신 <code>chain_hash</code> + <code>covered_through_seq</code> 로 잇고, <b>같은 머리라도 네트워크가 다르면 각각 한 행</b>이다(<code>(network, chain_hash)</code> 부분 유일 인덱스)</td>
      </tr>
      <tr>
        <td class="tbl__nw"><code>applications</code> &rarr; <code>interview_sessions</code> &rarr; <code>interview_turns</code></td>
        <td class="tbl__nw">1 : N : N</td>
        <td>재발송이 <b>새 행</b>이라 옛 링크가 죽지 않는다. 회차마다 질문&middot;음성&middot;전사&middot;응답 시각이 붙는다</td>
      </tr>
      <tr>
        <td class="tbl__nw"><code>interview_sessions</code> &rarr; <code>interview_findings</code></td>
        <td class="tbl__nw">1 : N</td>
        <td>서류 주장 &harr; 면접 발언 대조. <b>점수 컬럼이 없다</b> &mdash; 값은 일치&middot;불일치&middot;확인필요 셋뿐이고 판단은 사람이 한다</td>
      </tr>
      <tr>
        <td class="tbl__nw"><code>applications</code> &rarr; <code>application_embeddings</code></td>
        <td class="tbl__nw">1 : 0..1</td>
        <td>768차원 pgvector 1개. <b>파생 데이터라 지우고 백필로 다시 만들 수 있다</b></td>
      </tr>
      <tr>
        <td class="tbl__nw"><code>users</code> &harr; <code>applications</code></td>
        <td class="tbl__nw">N : M</td>
        <td><code>interviewer_assignments</code> 가 잇는다. 역할이 아니라 "그 건의 면접관"이라는 관계라 배정 대상의 role 은 검사하지 않는다</td>
      </tr>
      <tr>
        <td class="tbl__nw"><code>company_profile</code> &rarr; <code>integration_clients</code> &rarr; <code>applications</code></td>
        <td class="tbl__nw">1 : N : N</td>
        <td>회사 시스템이 서버 대 서버로 밀어 넣는 경로. <code>external_id</code> 가 멱등 키다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="dsn__sub">단계(stage)</p>
  <p class="dsn__p">
    <code>applied</code> &rarr; <code>screening</code> &rarr; <code>interview</code> &rarr;
    <code>accepted</code> / <code>rejected</code> 5종 고정이다. <b>DB enum 이 아니라 체크 제약 + 코드
    상수</b>로 관리한다 &mdash; enum 타입을 쓰면 값 하나 늘릴 때마다 마이그레이션이 붙기 때문이다.
    <code>rejected</code> 는 어느 단계에서든 진입할 수 있고, 그 외 전진은 순서대로만 간다. 규칙 강제는
    DB 가 아니라 <b>백엔드 서비스 레이어</b>가 한다.
  </p>

  <p class="dsn__sub">설계 규칙</p>

  <div class="items">

    <div class="item">
      <p class="item__t">원장은 고칠 수 있는 칸이 하나도 없다</p>
      <p class="item__d">
        <code>document_anchors</code> 는 <b>DB 트리거가 UPDATE &middot; DELETE &middot; TRUNCATE 를 거부</b>한다
        (<code>0006</code> &middot; <code>0008</code>). <code>0005</code> 가 2단계 타임스탬프용으로
        비워 두고 <code>0006</code> 의 트리거가 유일한 예외로 열어 뒀던
        <code>ots_status</code> &middot; <code>ots_proof</code> 두 칸은 공개 체인 기록을
        <code>chain_publications</code> 로 빼면서 <code>0008</code> 에서 없앴다 &mdash;
        <b>열린 칸 하나가 곧 원장의 유일한 구멍</b>이기 때문이다. TRUNCATE 는 행 트리거를 안 타므로
        문장 트리거로 따로 막았다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">인덱스는 비용을 적고 넣는다</p>
      <p class="item__d">
        최신순 목록&middot;커서 페이지네이션용 <code>(created_at DESC, id DESC)</code> 는
        <b>3.2MB &middot; 쓰기 +19%</b> 를 대가로 적어 두고 넣었다. 그 밖에
        <code>(job_posting_id, current_stage)</code>(칸반&middot;단계 필터) &middot; <code>email</code>(앱 로그인) &middot;
        <code>ix_..._hnsw</code>(<code>vector_cosine_ops</code>). 더미 10만 건 기준 검색은
        <b>111ms &rarr; 7.8ms</b> 로 줄었다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">중복은 제약 하나로 막는다</p>
      <p class="item__d">
        복합 UNIQUE 가 코드보다 먼저 막는다 &mdash; <code>applications(job_posting_id, email)</code>(중복 지원) &middot;
        <code>applications(integration_client_id, external_id)</code>(통합 멱등) &middot;
        <code>interviewer_assignments(application_id, interviewer_id)</code>.
        자기소개 앵커는 Postgres 가 NULL 을 서로 다른 값으로 보기 때문에 UNIQUE 하나로 안 되어
        <b>부분 인덱스</b>로 막았다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">해시로 저장하는 것과 평문으로 두는 것</p>
      <p class="item__d">
        일정&middot;인적성&middot;면접 조회 링크 토큰은 <b>평문</b>이다 &mdash; 새어 봐야 "내 지원 현황이 보인다"다.
        반면 <code>applicant_password_tokens.token_hash</code> 와
        <code>integration_clients.api_key_hash</code> 는 <b>bcrypt 해시만</b> 남긴다 &mdash;
        이 링크가 새면 계정이 통째로 넘어간다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">행을 지우는 대신 표시를 남긴다</p>
      <p class="item__d">
        <code>users</code> 는 삭제가 없고 <code>is_active</code> 로 끈다 &mdash; <code>users.id</code> 가
        <code>created_by</code> &middot; <code>evaluator_id</code> &middot; <code>changed_by</code> 로 도처에 박혀
        물리 삭제가 이력을 부순다. 회수한 API key 도, 이미 쓴 비밀번호 링크도 행은 남긴다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">문서 &middot; 코드 &middot; 이행은 같은 커밋</p>
      <p class="item__d">
        스키마를 바꾸면 <code>01-erd.md</code> 갱신 + alembic 리비전이 <b>한 묶음</b>이다.
        <code>0023</code> 번호가 두 번 쓰여 운영 DB 에 표가 안 생긴 사고 뒤,
        <b>번호 중복은 <code>tests/test_alembic_revisions.py</code> 가 CI 에서 막는다.</b>
        그 사고가 CI 초록인 채로 난 이유는 테스트가 <code>create_all</code> 로 표를 만들어
        이행을 안 타기 때문이었다. 그래서 CI 에 <code>alembic upgrade head</code> 를 따로 넣어
        이행 자체의 회귀를 잡는다. <b>다만 모델과 이행 결과를 대조하지는 않는다</b> &mdash;
        모델에만 넣고 리비전을 빠뜨린 것은 지금도 사람이 막는다.
      </p>
    </div>

  </div>

</div>

<div class="dsn__sec">

  <h2><span class="dsn__num">3.</span> API 설계</h2>
  <p class="dsn__note">
    접두사 <code>/api/v1</code> &middot; 인증 JWT Bearer. 요청&middot;응답의 진실은 <b>Swagger(<code>/docs</code>)</b>이고
    <code>02-api.md</code> 는 "무엇이 있는가"만 유지한다 &mdash; 같은 것을 두 곳에 적으면 반드시 갈린다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>메서드</th><th class="tbl__num">개수</th><th>성격</th></tr>
    </thead>
    <tbody>
      <tr><td><code>POST</code></td><td class="tbl__num">51</td><td>생성 + <b>동사형 행위</b>(발송&middot;확정&middot;앵커&middot;게시&middot;재전사)</td></tr>
      <tr><td><code>GET</code></td><td class="tbl__num">41</td><td>조회. 만료 판정이 여기 얹힌다</td></tr>
      <tr><td><code>PATCH</code></td><td class="tbl__num">6</td><td>부분 수정(단계&middot;공고&middot;평가&middot;메모&middot;역할)</td></tr>
      <tr><td><code>DELETE</code></td><td class="tbl__num">6</td><td>세션&middot;메모&middot;배정 해제&middot;템플릿 복귀 등 되돌릴 수 있는 것만</td></tr>
      <tr><td><code>PUT</code></td><td class="tbl__num">3</td><td>통째 교체(질문 목록&middot;메일 템플릿&middot;채점 설정)</td></tr>
      <tr><td><code>WS</code></td><td class="tbl__num">1</td><td><code>/ws/interview/&#123;token&#125;/rtc</code> &mdash; 실시간 면접 시그널링</td></tr>
    </tbody>
  </table>
  </div>

  <p class="dsn__sub">인증은 네 종류다</p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr><th>주체</th><th>자격</th><th>수명</th><th>왜 따로 두나</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__nw">담당자</td>
        <td>JWT Bearer (<code>sub=user_id</code>)</td>
        <td class="tbl__nw">12시간</td>
        <td>비활성 계정은 로그인만이 아니라 <b>이미 발급된 토큰도 401</b> 이다 &mdash; 로그인만 막으면 만료까지 그대로 쓴다</td>
      </tr>
      <tr>
        <td class="tbl__nw">지원자</td>
        <td>JWT (<code>typ</code> 이 다름)</td>
        <td class="tbl__nw">2시간</td>
        <td><b>같은 비밀키로 서명하므로 서명 검증이 이걸 못 막는다</b> &mdash; 양쪽 의존성에서 종류를 확인해 서로의 경로를 못 타게 한다</td>
      </tr>
      <tr>
        <td class="tbl__nw">비로그인 지원자</td>
        <td>URL 안 일회성 토큰</td>
        <td class="tbl__nw">링크마다</td>
        <td>공고 공개 링크&middot;일정 제안&middot;인적성&middot;AI 면접이 <b>같은 패턴</b>을 쓴다. 지원자에게 계정을 강요하지 않기 위해서다</td>
      </tr>
      <tr>
        <td class="tbl__nw">우리 서비스끼리</td>
        <td><code>X-Service-Token</code> / 회사 API key</td>
        <td class="tbl__nw">&mdash;</td>
        <td><code>/internal/*</code> 는 <b>환경변수가 없으면 전부 401</b>(기본 닫힘). 회사 통합은 bcrypt 대조 + 분당 상한</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="dsn__p">
    권한은 <b><code>admin</code> &middot; <code>member</code> 2종</b>이고 위계가 아니다(ADR-0017).
    <b>조회는 로그인만 하면 전부 열려 있고</b>, <code>admin</code> 에게만 남은 것은 넷뿐이다 &mdash;
    면접관 배정&middot;해제 &middot; 계정 생성 &middot; 메일 템플릿 &middot; <b>남의</b> 가용 시간.
    <code>member</code> 의 유일한 제한은 <b>평가 작성을 배정된 건에만</b> 할 수 있다는 것이다.
    "면접관은 배정된 지원자만 조회"라는 옛 규칙(A3)은 폐지했다.
  </p>

  <p class="dsn__sub">전역 규약</p>

  <div class="items">

    <div class="item">
      <p class="item__t">스케줄러를 두지 않는다 &mdash; 조회 시점 판정</p>
      <p class="item__d">
        마감 &middot; 링크 만료 &middot; 제안 만료를 <b>읽는 순간에</b> 판정한다. 공고를 조회할 때
        <code>deadline &lt; 오늘</code> 이고 <code>open</code> 이면 그 자리에서 <code>closed</code> 로 바꿔
        저장한다. 크론 하나가 죽어 전 기능이 조용히 멈추는 상태를 만들지 않으려는 것이다.
        대가도 적어 둔다 &mdash; 아무도 안 열면 기한이 지나도 상태가 안 바뀌어,
        <b>지원자 현황 목록은 상태가 아니라 <code>expires_at</code> 으로 거른다.</b>
      </p>
    </div>

    <div class="item">
      <p class="item__t">일괄 변경은 전부 성공하거나 전부 실패한다</p>
      <p class="item__d">
        <code>POST /applications/bulk-stage</code> 는 한 번에 <b>200명</b>까지고, 한 건이라도 전환 규칙에
        걸리면 <b>전체 롤백 + 409</b> 에 실패 id 목록을 실어 준다. 30명만 바뀌고 끝나면 담당자가 무엇이
        됐는지 알 수 없다. 이미 그 단계인 건은 실패가 아니라 <code>skipped</code> 로 센다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">없는 것도 있는 것과 똑같이 답한다</p>
      <p class="item__d">
        지원 이력이 없는 이메일로 비밀번호 링크를 요청해도 <b>202</b> 다. 만료된 링크와 이미 쓴 링크는
        <b>둘 다 410, 문구까지 같다.</b> 다르게 답하면 그것만으로 "이 사람이 여기 지원했는가"를 확인하는
        도구가 된다 &mdash; 이직 준비 중인 사람에게는 지원 사실 자체가 알려지면 안 되는 정보다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">되돌릴 수 없는 조작은 사람의 확인을 통과한다</p>
      <p class="item__d">
        에이전트의 쓰기 도구는 실행되지 않고 <code>pending_action</code> 으로 돌아온다. 사용자가 확인
        카드를 승인해 <code>POST /agent/confirm</code> 을 부를 때 비로소 실행된다 &mdash;
        <b>메일 발송도 이 경로를 탄다.</b>
      </p>
    </div>

    <div class="item">
      <p class="item__t">무거운 바이트는 API 를 지나가지 않는다</p>
      <p class="item__d">
        이력서는 presigned URL 로 브라우저 &rarr; S3 직행이고 서버는 키 발급과 레코드만 만든다.
        면접 답변 음성은 <b>이력서 업로드 경로를 쓰지 않는다</b> &mdash; 그쪽은 토큰 없이 누구나 부를 수
        있어서, 허용 목록에 <code>.webm</code> 을 넣으면 아무나 버킷에 미디어를 올리고
        <b>이력서 자리에 음성이 박힌다.</b> 그래서 면접 토큰이 필요한 별도 경로를 뒀다
        (음성 50MB / 이력서 10MB 로 상한도 따로).
      </p>
    </div>

    <div class="item">
      <p class="item__t">큰 목록은 커서로 넘긴다</p>
      <p class="item__d">
        통합 검색은 <code>limit</code>(&le;200) + <code>cursor</code> 이고,
        <code>with_total=false</code> 를 주면 <code>total</code> 이 <code>null</code> 이 되는 대신
        <b>검색이 크게 빨라진다</b> &mdash; 10만 건에서 전체 개수를 세는 것이 목록을 뽑는 것보다 비싸다.
      </p>
    </div>

  </div>

  <p class="dsn__note" style="margin-top:1.4rem; margin-bottom:0;">
    <b>CORS 는 2026. 09. 01. 에야 들어왔다.</b> 그 전에는 <code>vercel.json</code> 의 rewrite 로
    <code>/api</code> 를 우회시켰는데, 그 구조에서는 <b>지원자 자소서를 포함한 모든 요청이 제3자
    서버를 통과</b>했다. 지금은 브라우저가 API 를 직접 부르고, 쿠키를 안 쓰므로
    <code>allow_credentials</code> 는 꺼져 있으며 토큰은 <code>Authorization</code> 헤더로만 간다.
  </p>

</div>

<div class="dsn__sec">

  <h2><span class="dsn__num">4.</span> 화면 설계 (UI/UX)</h2>
  <p class="dsn__note">
    기준 문서는 <code>docs/00_overview/05-design.md</code>다. 색&middot;간격&middot;폰트 크기&middot;radius&middot;
    그림자&middot;모션 시간&middot;z-index를 <b>전부 토큰(CSS 변수)으로</b> 두고,
    <b>모든 색에 선택 이유를 붙인다</b> &mdash; 이유를 설명할 수 없는 색은 쓰지 않는다.
  </p>

  <p class="dsn__sub">화면 지도 &mdash; 테이블이 메인, 칸반은 보조</p>
  <p class="dsn__p">
    1,000명 이상 규모를 전제로 <b>테이블을 주 뷰</b>로 놓았다. 근거는 경쟁 제품의 실제 구조다 &mdash;
    Greenhouse 는 목록 + 단계 요약, Airtable &middot; Jira 는 같은 데이터의 뷰 전환이고,
    칸반은 카드 수십 장까지만 유효하다. Lever 만 칸반 네이티브인데 그마저 대량 구간은 큐로 처리한다.
    그래서 칸반은 <b>토글로 여는 보조 뷰</b>이고, 드래그는 공고의 지원자 화면에서만 살아 있다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr><th>메뉴</th><th>무대</th><th>설계 결정</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__nw">대시보드</td>
        <td>진입점</td>
        <td>숫자 카드 + 지원자 현황(리스트 &harr; 칸반 토글, <b>여기 칸반은 보기 전용</b>) + 공고별 퍼널 레일 + 이번 주 면접 축소판. 통계 차트는 범위 밖</td>
      </tr>
      <tr>
        <td class="tbl__nw">공고의 지원자</td>
        <td><b>본 작업 화면</b></td>
        <td>테이블 메인(검색&middot;정렬&middot;페이지네이션&middot;체크박스 일괄 변경) + 칸반 토글. 퍼널 레일이 곧 단계 필터. 상세는 <b>페이지 이동 없는 우측 패널</b>과 "다음 지원자 &rarr;" 연속 심사</td>
      </tr>
      <tr>
        <td class="tbl__nw">지원자</td>
        <td>전 공고 통합 검색</td>
        <td>10만 건 복합 필터 무대. <b>칸반 없음.</b> 행을 누르면 같은 상세 패널이 옆에서 열린다 &mdash; 검색 맥락을 잃지 않게 페이지를 옮기지 않는다</td>
      </tr>
      <tr>
        <td class="tbl__nw">캘린더</td>
        <td>월 그리드</td>
        <td>확정된 면접만. 셀은 3건에서 끊고 나머지는 <code>+N건</code>, 날짜를 누르면 <b>우측 패널</b>에 그날 목록. 등록&middot;수정&middot;삭제가 없는 조회 전용이다</td>
      </tr>
      <tr>
        <td class="tbl__nw">종합 평가</td>
        <td>확정 화면</td>
        <td>공고별 지원자 수&middot;평가 완료&middot;평균 종합 점수(서류 + 면접 &middot; 등급). <b>최종 합불을 사람이 확정하는 자리</b></td>
      </tr>
      <tr>
        <td class="tbl__nw">설정</td>
        <td>계정&middot;운영</td>
        <td>내 계정&middot;면접 가능 시간은 전원, 사용자&middot;권한&middot;메일 템플릿은 admin. 프로필 사진은 없다 &mdash; <code>users</code> 에 사진 컬럼이 없어 이니셜 아바타로 대신한다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="dsn__sub">오른쪽 패널은 한 자리다</p>
  <p class="dsn__p">
    아르(에이전트) &middot; 캘린더의 그날 일정 &middot; 지원자 상세 &middot; 평가 <b>넷이 화면 오른쪽 끝의
    같은 자리</b>에 서고 한 번에 하나만 열린다(나중에 연 쪽이 이긴다). 폭은
    <code>--right-panel-w</code> <b>360px 하나</b>로 합쳤다 &mdash; 아르 360 / 상세&middot;평가 420 으로
    갈려 있으면 사이드바 216 + 420 = 636 이라 PC 최소 1280 에서 좌우 여백(48&times;2)을 빼고
    <b>548px</b> 밖에 안 남아 메인인 테이블이 눌린다. 360 이면 <b>608px</b> 이 남는다.
    <b>여닫는 모션은 없다</b> &mdash; 폭은 레이아웃 값이라 애니메이션하면 매 프레임 본문이 다시 흐르고
    테이블 컬럼까지 재배치된다. 내용 페이드만 남겼다.
  </p>

  <p class="dsn__sub">토큰 &mdash; 87개, <code>:root</code> 한 블록</p>
  <p class="dsn__p">
    2026. 09. 04. 에 <b>라이트 "새싹"에서 다크 "딥 네트워크"로 뒤집었다.</b> 마크의 의미&middot;색온도&middot;
    재질 셋이 화면의 나머지(데이터망&middot;쿨 네온)와 어긋났기 때문이다. 전환은
    <code>tokens.css</code> 의 <code>:root</code> <b>한 블록 교체</b>로 끝났다 &mdash; 토큰이 시맨틱
    네이밍이라 그 시점 26개 CSS 모듈 중 <b>색을 직접 박아 둔 곳이 하나도 없었다.</b>
    바뀐 것은 색만이 아니라 재질이다: 면이 불투명한 흰 판에서 <b>뒤가 비치는 유리</b>가 됐다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr><th>토큰</th><th class="tbl__nw">값</th><th>이유</th></tr>
    </thead>
    <tbody>
      <tr><td><code>--bg</code></td>
        <td class="tbl__nw"><span class="sw" style="background:#070B14"></span><code>#070B14</code></td>
        <td>바탕. 위에 오로라 4겹이 깔린다 &mdash; 빈 공간이 그냥 검으면 "우주"가 아니라 어두운 화면이다</td></tr>
      <tr><td><code>--bg-elev</code></td>
        <td class="tbl__nw"><code>rgba(13,19,34,.62)</code></td>
        <td>카드&middot;패널의 얼굴. 불투명하면 패널이 화면의 90%를 덮어 배경이 여백에만 토막으로 남는다</td></tr>
      <tr><td><code>--accent</code></td>
        <td class="tbl__nw"><span class="sw" style="background:#22D3EE"></span><code>#22D3EE</code></td>
        <td>시안 &mdash; 면&middot;채움&middot;레일&middot;선택. 배경 노드망의 팔레트를 그대로 UI 로 가져온다</td></tr>
      <tr><td><code>--accent-text</code></td>
        <td class="tbl__nw"><span class="sw" style="background:#7DD3FC"></span><code>#7DD3FC</code></td>
        <td>같은 시안이 <b>글자로는 탁하다</b> &mdash; 글자&middot;테두리는 한 톤 밝게</td></tr>
      <tr><td><code>--accent-fill</code></td>
        <td class="tbl__nw"><span class="sw" style="background:#fff"></span><code>#FFFFFF</code></td>
        <td>주 동작 버튼은 <b>흰 판 + 어두운 글자</b>. 네온이 이미 배경에 깔려 있어 버튼까지 빛나면 무엇이 동작인지 안 읽힌다</td></tr>
      <tr><td><code>--neutral</code></td>
        <td class="tbl__nw"><span class="sw" style="background:#7D8CA8"></span><code>#7D8CA8</code></td>
        <td>판단 전(접수&middot;서류&middot;면접) 공용 &mdash; <b>"색 없음"이 곧 의미</b>다</td></tr>
      <tr><td><code>--ok</code> / <code>--danger</code></td>
        <td class="tbl__nw"><span class="sw" style="background:#34D399"></span><code>#34D399</code>
          <span class="sw" style="background:#F0A38F;margin-left:.4rem"></span><code>#F0A38F</code></td>
        <td>합격에만 연두, 불합격에만 살구. 라이트의 벽돌색은 어두운 바탕에 먹혀 안 읽혀 살구로 올렸다</td></tr>
      <tr><td><code>--ai</code></td>
        <td class="tbl__nw"><span class="sw" style="background:#FCD34D"></span><code>#FCD34D</code></td>
        <td><b>앰버 점선 = AI 제안 / 시안 실선 = 사람 확정</b>. 앰버는 <b>승인을 기다리는 것에만</b> 쓴다 &mdash; 읽기만 하는 요약문에 쓰면 "뭘 눌러야 하나"로 읽힌다</td></tr>
    </tbody>
  </table>
  </div>

  <p class="dsn__p" style="margin-top:1.1rem;">
    퍼널 램프 <code>--stage-1</code>~<code>--stage-4</code> 는 2026. 09. 07. 에 <b>밝기 간격을 벌렸다.</b>
    이전 값은 인접 색 사이 ΔE(OKLab&times;100)가 <b>9.6</b> 이라 정상 시야에서도 세 칸이 다 회색으로
    보였다 &mdash; 구분 기준이 15 다. 지금은 <b>15.9</b> 다. 무채 규칙이 있어 손댈 수 있는 것은
    밝기뿐이었다.
  </p>

  <p class="dsn__sub">타이포 &middot; 간격 &middot; 반응형</p>

  <div class="items">

    <div class="item">
      <p class="item__t">스케일 7단 외 크기 금지</p>
      <p class="item__d">
        Material Design 3 타입 스케일 기준 &mdash; display 26 / h1 22 / h2 18 / body 16 / sm 14 /
        caption 12 / num 14px. 간격은 <code>--sp-1~8</code> = 4&middot;8&middot;12&middot;16&middot;24&middot;32&middot;40&middot;48px
        <b>4px 배수만</b>. 통일감은 같은 토큰을 쓰는 것으로 달성한다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">숫자 폰트를 따로 들인 이유</p>
      <p class="item__d">
        Pretendard Variable(본문) + <b>JetBrains Mono(숫자)</b> 2종. 표의 숫자는 자리 폭이 고정돼야
        값이 갱신될 때 흔들리지 않는데 <code>tabular-nums</code> 만으로는 열이 미세하게 어긋났다.
        대신 <b>한글이 섞인 자리엔 안 쓴다</b> &mdash; 공백&middot;괄호&middot;가운뎃점을 mono 가 그려
        <code>"09.04 (금) 14:00"</code> 칩이 18px 부풀었고 카드가 26px 넘쳤다(실측).
      </p>
    </div>

    <div class="item">
      <p class="item__t">브레이크포인트는 셋뿐</p>
      <p class="item__d">
        <b>1100px</b> 상세 패널이 나란히 &rarr; 덮는 오버레이 &middot; <b>768px</b> 여기부터 모바일
        (사이드바 접기 &middot; 칸반 대신 단계 탭 + 리스트 &middot; 테이블은 카드형) &middot;
        <b>1280px</b> PC 최소 검증 기준선. <b>이 셋 외 임의 미디어 쿼리 금지.</b>
        모바일에서 칸반을 가로 스크롤로 밀어 넣지 않는다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">"완성"의 정의를 못 박았다</p>
      <p class="item__d">
        인터랙티브 컴포넌트는 default / hover / press / focus / disabled 전부, 데이터 화면은
        loading(스켈레톤) / empty / error 전부 정의해야 완성이다. 드래그는 원본 자리 표시 + 고스트 +
        드롭 영역까지, <b>실패 롤백은 토스트로</b> &mdash; 조용히 지나가면 안 된다.
        터치 타깃 최소 44&times;44px(HIG), 대비 WCAG AA.
      </p>
    </div>

    <div class="item">
      <p class="item__t">등장 애니메이션은 한 곳에만</p>
      <p class="item__d">
        <code>--dur-fast</code> 120 / <code>--dur-base</code> 200 / <code>--dur-slow</code> 320ms.
        시그니처 모션은 <b>퍼널 레일 하나</b>뿐이고, 로그인 다이브만 예외 2종
        (<code>--dur-dive</code> 1600ms &middot; <code>--dur-land</code> 280ms)을 쓴다 &mdash;
        로그인 응답을 기다리는 동안 60%까지 진행하다 응답이 오면 착지하는 구조라
        <b>연출이 로딩 표시를 대신한다.</b> <code>prefers-reduced-motion</code> 대응 필수.
      </p>
    </div>

    <div class="item">
      <p class="item__t">금지 목록을 문서에 박았다</p>
      <p class="item__d">
        보라&rarr;파랑 그라데이션 기본값 &middot; 생성물 그대로 출고 &middot; 전부 가운데 정렬 &middot;
        의미 없는 01/02/03 &middot; 이모지 남발 &middot; 주제 무관 패럴랙스 &middot; 개발 중임을 드러내는 문구.
        <b>의미 없는 장식을 멋대로 붙이지 않는다</b> &mdash; 필요하다고 느끼면 먼저 제안한다.
      </p>
    </div>

  </div>

  <p class="dsn__note" style="margin-top:1.4rem; margin-bottom:0;">
    <b>구현 규모</b> &mdash; 프론트는 페이지 25개 &middot; 공통 컴포넌트 18개 &middot; CSS 모듈 38개이고
    색&middot;간격&middot;모션 값은 전부 <code>tokens.css</code> 의 토큰 <b>87개</b>에서 나온다.
    <b>토큰에 없는 값은 쓰지 않고 토큰으로 추가한다</b>는 규칙이 다크 전환을 한 블록으로 끝내 준 장치다.
  </p>

</div>

<a class="dsn__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
