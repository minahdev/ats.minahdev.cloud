---
layout: default
title: 테스트
permalink: /testing/
---

<style>
.tst { max-width: 64rem; margin: 2.5rem auto 4rem; }
.tst__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.tst__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; }
.tst__crumb { margin: 0 0 .55rem; font-size: .82rem; color: #9ca3af; }
.tst__crumb a { color: #9ca3af; }
.tst__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

.tst__sec { margin-bottom: 3.25rem; }
.tst__sec > h2 {
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
.tst__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.tst__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.75; word-break: keep-all; }
.tst__note code { font-size: .82rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }
.tst__note:last-child { margin-bottom: 0; }
.tst__sub {
  margin: 1.8rem 0 .7rem;
  font-size: .93rem;
  color: #111827;
  font-weight: 700;
  word-break: keep-all;
}

/* 요약 수치 띠 */
.tst__stat {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(9rem, 1fr));
  gap: .75rem;
  margin-bottom: 2.5rem;
}
.tst__statbox { border: 1px solid #e5e7eb; border-radius: 6px; padding: .8rem .9rem; }
.tst__statk { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .3rem; }
.tst__statv { display: block; font-size: 1.35rem; font-weight: 700; color: #111827; font-variant-numeric: tabular-nums; }
.tst__statv small { display: block; font-size: .72rem; font-weight: 400; color: #6b7280; margin-top: .2rem; letter-spacing: 0; }

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
.who-all { background: #f3f4f6; color: #4b5563; }

/* 표 공통 */
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
.tbl--wide { min-width: 52rem; }
.tbl--layer { min-width: 56rem; }
.tbl td.num { font-variant-numeric: tabular-nums; white-space: nowrap; }
.tbl td.nowrap { white-space: nowrap; }

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
.tag--wait { background: #fef3c7; color: #92400e; }
.tag--open { background: #fee2e2; color: #991b1b; }

/* 사고 → 장치 카드 */
.fix { display: grid; grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr)); gap: .75rem; }
.fix__item { border: 1px solid #e5e7eb; border-left: 3px solid #dc2626; border-radius: 6px; padding: .85rem .95rem; }
.fix__item--kept { border-left-color: #2a7ae2; }
.fix__k { display: block; font-size: .73rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.fix__item h3 { margin: 0 0 .45rem; font-size: .9rem; color: #111827; line-height: 1.5; word-break: keep-all; }
.fix__item p { margin: 0; font-size: .84rem; color: #4b5563; line-height: 1.7; word-break: keep-all; }
.fix__item p code { font-size: .78rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 규칙 상자 */
.rule { border: 1px solid #e5e7eb; border-radius: 6px; overflow: hidden; margin-bottom: 1.2rem; }
.rule__row { padding: .8rem 1rem; border-bottom: 1px solid #f3f4f6; }
.rule__row:last-child { border-bottom: 0; }
.rule__row--base { background: #f9fafb; }
.rule__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .35rem; }
.rule__v { margin: 0; font-size: .87rem; line-height: 1.75; color: #374151; word-break: keep-all; }
.rule__v code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

.tst__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }
</style>

<div class="tst">

<div class="tst__head">
  <p class="tst__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 8. 테스트</p>
  <h1>테스트</h1>
  <p>사람 승인 게이트를 없앤 대신 CI 를 안전망으로 세웠다 &mdash; 자동 5잡 &middot;
     백엔드 pytest 1,165건 &middot; QA 시나리오 34개 &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="tst__stat">
  <div class="tst__statbox"><span class="tst__statk">CI 잡</span>
    <span class="tst__statv">5<small>push &middot; PR 마다</small></span></div>
  <div class="tst__statbox"><span class="tst__statk">백엔드 pytest</span>
    <span class="tst__statv">1,165<small>건 통과 · <code>a650123</code></small></span></div>
  <div class="tst__statbox"><span class="tst__statk">앱 위젯 시험</span>
    <span class="tst__statv">373<small>건 · 파일 30개</small></span></div>
  <div class="tst__statbox"><span class="tst__statk">AI 면접 서버</span>
    <span class="tst__statv">110<small>건 / 50초</small></span></div>
  <div class="tst__statbox"><span class="tst__statk">QA 시나리오</span>
    <span class="tst__statv">34<small>필수 27 + 실패 7</small></span></div>
</div>

<div class="tst__sec">

  <h2><span class="tst__num">1.</span> 테스트 계획</h2>

  <p class="tst__note">
    이 프로젝트에는 <b>사람 리뷰 게이트가 없다.</b> 2026. 08. 28. 개정으로 사전 확인을
    없앴고, 09. 04.부터는 브랜치 &rarr; PR &rarr; <b>자체 머지</b>다 &mdash; 승인자가 없고
    자기 PR 을 자기가 머지한다. 그리고 <b>main 머지 = 2분 후 프로덕션 배포</b>(서버
    systemd timer 자동 CD)다. 사람이 빠진 자리에 무엇을 놓을지가 이 장의 전제였고,
    답은 <b>CI 초록 하나</b>였다. 규약에 그대로 적혀 있다 &mdash;
    "CI 빨간불인 PR 은 머지하지 않는다. main 이 빨간불이면 다른 작업보다 우선 수정."
  </p>

  <p class="tst__note">
    계기는 사고다. <b>2026. 09. 01. 하루에 깨진 main 을 두 번 발견했고 둘 다 우연이었다</b>
    (<code>d7fdd10</code> &middot; <code>d96749e</code>). 그래서 CI 를 넣을 때의 목적을
    "게이트"가 아니라 <b>"깨졌다는 사실만 즉시 보이게"</b>로 잡았다 &mdash;
    <span class="who who-b">우정 B</span> 가 09. 02. 게이트(09. 04.)를 앞두고 먼저 올렸고,
    파일 소유는 인프라 도메인이라 사후 공지로 처리했다.
  </p>

  <div class="rule">
    <div class="rule__row rule__row--base">
      <span class="rule__k">규칙 1 &mdash; 검증 없는 push 없음</span>
      <p class="rule__v">
        코드를 바꿨으면 해당 파트의 실행/테스트를 돌리고, <b>결과를 커밋 메시지에 한 줄</b>
        남긴다. 리뷰어가 없으므로 <b>이력이 곧 기록</b>이다.
      </p>
    </div>
    <div class="rule__row">
      <span class="rule__k">규칙 2 &mdash; 우회 금지</span>
      <p class="rule__v">
        <b>테스트를 통과시키려고 주석 처리하거나 우회하지 않는다.</b> 실패하면 실패한 대로
        커밋 메시지와 팀 채널에 적는다. 초록을 만드는 것이 목적이 아니라 상태를 아는 것이
        목적이기 때문이다.
      </p>
    </div>
    <div class="rule__row">
      <span class="rule__k">규칙 3 &mdash; 깨진 main 은 묻지 않고 처리</span>
      <p class="rule__v">
        발견한 사람이 고치거나(fix-forward) revert 한다. 2분 뒤 배포되므로
        <b>합의를 기다리는 시간이 곧 장애 시간</b>이다.
      </p>
    </div>
  </div>

  <p class="tst__sub">층위 &mdash; 무엇을 어느 시점에 재는가</p>

  <div class="tbl__scroll">
  <table class="tbl tbl--layer">
    <thead>
      <tr>
        <th>층위</th>
        <th>대상</th>
        <th>도구</th>
        <th>시점</th>
        <th>실측</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="nowrap">백엔드 린트</td>
        <td>미정의 이름 &middot; 미사용 import</td>
        <td><code>ruff check --select F</code></td>
        <td class="nowrap">push &middot; PR</td>
        <td>배포 후 500 의 주원인을 1초에 잡는다</td>
      </tr>
      <tr>
        <td class="nowrap">백엔드 단위 &middot; API</td>
        <td>실제 PostgreSQL + pgvector 에 alembic 이행 후 실행</td>
        <td><code>pytest</code> + pytest-timeout(60초)</td>
        <td class="nowrap">push &middot; PR</td>
        <td class="num">1,165건 통과</td>
      </tr>
      <tr>
        <td class="nowrap">프론트</td>
        <td>타입 &middot; 린트 &middot; 빌드</td>
        <td>oxlint + <code>tsc -b</code> + vite build</td>
        <td class="nowrap">push &middot; PR</td>
        <td>테스트가 없어 <b>빌드가 회귀 그물</b></td>
      </tr>
      <tr>
        <td class="nowrap">앱</td>
        <td>위젯 &middot; API 클라이언트</td>
        <td><code>flutter analyze</code> + <code>flutter test</code></td>
        <td class="nowrap">push &middot; PR</td>
        <td class="num">파일 30개 &middot; 373건</td>
      </tr>
      <tr>
        <td class="nowrap">AI 면접 서버</td>
        <td>실시간 전사 &middot; 판정 중계 &middot; 화자 매칭</td>
        <td><code>pytest</code> (Python 3.13)</td>
        <td class="nowrap">push &middot; PR</td>
        <td class="num">110건 / 50초</td>
      </tr>
      <tr>
        <td class="nowrap">에이전트 회귀 하네스</td>
        <td>실서버 <code>/agent/chat</code> 시나리오 &mdash; 정답 &middot; 속도 &middot; 창작 여부</td>
        <td>자체 하네스 (<code>-m regression</code>)</td>
        <td class="nowrap">모델 &middot; 프롬프트 변경 시</td>
        <td class="num">55건 (10 + 30 + 15)</td>
      </tr>
      <tr>
        <td class="nowrap">계약 대조</td>
        <td>배포본 OpenAPI &harr; main 경로 &middot; 스키마 &middot; 인증</td>
        <td><code>check_public_contract.py</code></td>
        <td class="nowrap">배포 후</td>
        <td class="num">09. 02. 경로 55/55 &middot; 스키마 75/75</td>
      </tr>
      <tr>
        <td class="nowrap">스키마 대조</td>
        <td>alembic 이행 결과 &harr; 모델</td>
        <td><code>check_schema_drift.py</code></td>
        <td class="nowrap">pytest 직전 (CI)</td>
        <td>이행 누락 2건을 잡아낸 뒤 상설화</td>
      </tr>
      <tr>
        <td class="nowrap">모델 채점</td>
        <td>동일 케이스 23건을 <b>같은 자</b>로 &mdash; 도구 이름 &middot; no-tool 위반 &middot;
            확인 문구 &middot; 인자 &middot; 응답</td>
        <td><code>judge.py</code></td>
        <td class="nowrap">모델 &middot; 어댑터 비교 시</td>
        <td>학습 전 Qwen <b>26.1%</b> &middot; Claude Haiku <b>69.6%</b> &middot;
            Qwen v9 <b>73.9%</b></td>
      </tr>
      <tr>
        <td class="nowrap">E2E &middot; QA</td>
        <td>필수 27기능 시나리오 (전제 &rarr; 절차 &rarr; 기대)</td>
        <td>qa-scenarios 문서</td>
        <td class="nowrap">게이트 판정</td>
        <td>09. 04. 1차 게이트 4항목 충족 &middot; 09. 30. 2차 예정</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="tst__note" style="margin-top:1.1rem;">
    <b>안 한 것도 적는다.</b> 프론트엔드에는 테스트 코드가 없다 &mdash; <code>tsc -b</code> 가
    사실상의 회귀 그물이고, 그 이상은 남은 기간에 넣지 않기로 했다. AI 면접 서버에도 린트를
    아직 붙이지 않았다: 기존 오류 5건(<code>analyze_file</code> &middot; <code>app</code> &middot;
    <code>deception_vit</code> &middot; <code>interview_ws</code> &middot;
    <code>test_interview_ws</code>)이 남아 있어 지금 붙이면 <b>아무도 안 보는 빨간 CI</b> 가
    되기 때문이다. 다음 <code>ai/</code> 변경 때 정리한 뒤 붙인다.
  </p>

</div>

<div class="tst__sec">

  <h2><span class="tst__num">2.</span> 단위 및 통합 테스트</h2>

  <p class="tst__note">
    CI(<code>.github/workflows/ci.yml</code>)는 <b>잡 5개</b>다. 같은 브랜치에 연달아 push 하면
    앞의 실행을 취소한다(<code>concurrency</code> + <code>cancel-in-progress</code>) &mdash;
    무료 러너 분을 아끼기 위해서다. 아래 표의 칩은 <b>그 잡을 실제로 올린 사람</b>이다 &mdash;
    파일 자체는 인프라 도메인이라, 남이 올린 경우는 사후 공지로 처리했다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr><th>잡</th><th>하는 일</th><th>들어온 계기</th><th>추가</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="nowrap"><b>lint</b><br><span class="who who-e">수택 E</span></td>
        <td><code>uvx ruff@0.16.7 check --select F app tests</code></td>
        <td>헥사고날 이동 뒤 <b>NameError 2건이 프로덕션까지 갔다</b> &mdash;
            <code>schedules.py</code> 의 <code>timedelta</code> 미import,
            <code>assignments.py</code> 의 함수 밖 <code>PgTalentRepository</code>.
            둘 다 그 줄을 타는 테스트가 없어 pytest 초록, 배포 뒤 500</td>
        <td class="nowrap">09. 12.</td>
      </tr>
      <tr>
        <td class="nowrap"><b>backend</b><br><span class="who who-b">우정 B</span></td>
        <td><code>uv sync --frozen</code> &rarr; pgvector 확장 &rarr;
            <code>alembic upgrade head</code> &rarr; <b>모델&harr;이행 비교</b> &rarr;
            <code>pytest -q</code></td>
        <td>깨진 main 을 하루 두 번 우연히 발견</td>
        <td class="nowrap">09. 02.</td>
      </tr>
      <tr>
        <td class="nowrap"><b>frontend</b><br><span class="who who-b">우정 B</span></td>
        <td><code>npm ci</code> &rarr; oxlint &rarr; <code>tsc -b</code> + vite build (Node 22)</td>
        <td>같음 &mdash; 백엔드 잡과 <b>같은 커밋</b>으로 첫 CI 에 함께 들어왔다</td>
        <td class="nowrap">09. 02.</td>
      </tr>
      <tr>
        <td class="nowrap"><b>ai</b><br><span class="who who-e">수택 E</span></td>
        <td>apt 5개(opencv &middot; mediapipe &middot; soundfile) 후
            <code>pytest</code> 3파일</td>
        <td>실시간 면접 서버 시험 110개가 <b>CI 밖에 있었다.</b> 09. 01. 이후 51번 바뀌었는데
            매번 각자 로컬 컨테이너로만 확인했다 &mdash; 깨졌는지가 머지한 사람의 기억에
            달려 있었다. <span class="who who-b">우정 B</span> 가 로컬에서
            110 passed / 50초를 실측한 뒤 요청했다</td>
        <td class="nowrap">09. 17.</td>
      </tr>
      <tr>
        <td class="nowrap"><b>mobile</b><br><span class="who who-e">수택 E</span></td>
        <td>Flutter 3.44.8 &mdash; <code>flutter analyze</code> + <code>flutter test</code></td>
        <td><b>09. 15. 앱 시험 15건이 깨진 채 며칠 지나갔다 &mdash; 아무도 몰랐다.</b>
            Issue #254 &mdash; <span class="who who-c">민아 C</span> 원안</td>
        <td class="nowrap">09. 17.</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="tst__sub">백엔드 &mdash; 목 DB 를 안 쓴다</p>

  <p class="tst__note">
    테스트 DB 를 흉내로 대체하지 않았다. CI 는 <code>pgvector/pgvector:pg16</code> 서비스
    컨테이너를 띄운다 &mdash; <b>순정 <code>postgres</code> 를 쓰면 vector 확장이 없어
    <code>conftest</code> 가 <code>application_embeddings</code> 를 건너뛰고, 그러면 임베딩
    경로가 CI 에서 통째로 안 돈다.</b> 로컬 docker-compose 와 같은 이미지를 쓰는 이유가 그것이다.
    격리는 트랜잭션으로 한다 &mdash; <code>db</code> fixture 가 각 테스트를 트랜잭션으로 감싸고
    끝나면 롤백해서 DB 에 흔적이 남지 않는다.
  </p>

  <p class="tst__note">
    파일 52개에 <code>def test_</code> 가 <b>1,084개</b>이고, parametrize 확장까지 포함해
    <b>1,165건이 통과</b>한다(커밋 <code>a650123</code> &mdash; 같은 실행에서 55건은 skip,
    그 로컬에 pgvector 가 없어서다). 09. 02. 실측 기준으로는 486건에
    <b>CI 14.5초 &middot; 로컬 88.6초</b>였다 &mdash; 로컬이 느린 것은 WSL 이
    <code>/mnt/c</code> 를 읽는 속도 탓이지 테스트 탓이 아니다. 백엔드 로드맵의 W5 완료
    기준("<code>uv run pytest</code> 30초 내")은 <b>러너에서는 이미 만족</b>한다.
  </p>

  <p class="tst__sub">CI 가 잡은 것 &mdash; pytest 만으로는 안 보이던 두 종류</p>

  <div class="rule">
    <div class="rule__row rule__row--base">
      <span class="rule__k">이행 누락 &mdash; <code>check_schema_drift.py</code> (09. 17.)</span>
      <p class="rule__v">
        <code>alembic upgrade head</code> 스텝만 있으면 초록이 거짓이 된다.
        <b>pytest 의 <code>conftest</code> 가 <code>create_all</code> 로 이행에 빠진 표를
        채워 넣기 때문</b>이다. 실제로 두 번 그랬다 &mdash; 09. 16. <code>email_logs.stage</code> 의
        <code>password_setup</code> 을 모델에만 넣어 운영에서 메일 행 INSERT 가 거부됐고,
        09. 17. 이행 번호 <code>0023</code> 중복(#282)으로 운영 DB 에 <code>file_blobs</code> 가
        안 생길 뻔했다. 그래서 <b>이행 직후 &middot; pytest 전에</b> 표 &middot; 컬럼 &middot;
        NULL 허용 &middot; CHECK 허용값 &middot; UNIQUE &middot; 인덱스 이름 다섯 가지를 비교하고,
        다르면 종료 코드 1 이다. 번호 중복 자체는 별도로
        <code>tests/test_alembic_revisions.py</code> 가 막는다 &mdash; DB 없이 파일만 읽고,
        <b>번호를 짓는 사람이 둘 이상이면 언제든 다시 나기 때문</b>이다.
      </p>
    </div>
    <div class="rule__row">
      <span class="rule__k">로컬 초록 &middot; CI 빨강 &mdash; <code>conftest.py</code> 의 스위치 선점</span>
      <p class="rule__v">
        개발자 <code>.env</code> 에만 있는 키가 판정을 갈랐다. <code>ANTHROPIC_API_KEY</code> 가
        있으면 백엔드가 "사용 가능"으로 보이지만 CI 에는 없어 503 으로 갈린다 &mdash; 이 갈림으로
        실제 사고가 났고 <code>d4580e2</code> 로 사후 복구했다. 그래서 <code>conftest</code> 가
        <b>알려진 스위치 12개를 빈 값으로 선점</b>하고 <code>COMPANY_NAME</code> 은
        CI 의 실효값 <code>"Arda"</code> 로 못 박는다. 지우는 것으로는 안 된다 &mdash;
        <code>app/main.py</code> 의 <code>load_dotenv()</code> 가
        <b>없는 키에는 <code>.env</code> 값을 넣기</b> 때문에, <b>미리 값을 잡아두는 것이
        유일하게 확실한 방법</b>이다.
      </p>
    </div>
    <div class="rule__row">
      <span class="rule__k">멈춤 &mdash; pytest-timeout 60초</span>
      <p class="rule__v">
        09. 04. 로컬에서 Docker Desktop 이 죽어 DB connect 대기로
        <b>pytest 가 24분간 조용히 멈췄다.</b> 침묵을 실패로 바꿨다 &mdash; 타임아웃이 걸리면
        어떤 테스트가 어디서 기다렸는지 스택과 함께 드러난다.
      </p>
    </div>
  </div>

  <p class="tst__sub">회귀 하네스 &mdash; 기본 스위트 밖에 둔 이유</p>

  <p class="tst__note">
    <span class="who who-d">소연 D</span> 도메인의 에이전트는 "되냐"가 아니라 "얼마나 잘 되냐"를
    재야 한다. 그래서 <code>backend/tests/prompt_regression/</code> 는 실 백엔드
    (<code>localhost:8000</code>)에 <b>실호출</b>하고, <code>@pytest.mark.regression</code> 이
    붙어 <b>기본 <code>pytest -q</code> 에서 자동으로 제외</b>된다 &mdash;
    시나리오 하나당 5~40초라 CI 기본 스위트에 끼면 매 PR 이 몇 분씩 밀린다.
    <code>-m regression</code> 을 명시해야만 돈다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>세트</th><th>건수</th><th>재는 것</th><th>기준</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="nowrap"><code>test_step0</code></td>
        <td class="num">10</td>
        <td>인사 &middot; 자기소개 &middot; 목록 &middot; 이름 검색 &middot; 역량 검색 &middot;
            단계 변경 요청 등 정형 문장</td>
        <td>Ollama qwen3:4b &middot; Guard 도입 후 <b>10/10 &middot; 평균 15초</b>가 회귀 기준선</td>
      </tr>
      <tr>
        <td class="nowrap"><code>test_intent_variations</code></td>
        <td class="num">30</td>
        <td>존칭(씨 &middot; 님) &middot; 오타 &middot; 존댓말 &middot; 조사 변형 &mdash;
            <b>정형 10개는 regex 가 잡게 만든 것이라 진짜 정확도는 변형에서 드러난다</b></td>
        <td>의도 정확도 wrong &le; 5% &middot; p50 &le; 4s</td>
      </tr>
      <tr>
        <td class="nowrap"><code>test_faq</code></td>
        <td class="num">15</td>
        <td>지원자용 공개 챗 &mdash; 공고 정보 &middot; 본인 상태 응답,
            차단 주제(연봉 &middot; 합격 가능성 &middot; 다른 지원자) 거절,
            <b>프롬프트 주입 방어</b></td>
        <td>거절 문구로 답하고 주입에 넘어가지 않을 것</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="tst__note" style="margin-top:1.1rem;">
    하네스의 <code>assert</code> 는 최소한만 건다. 대신 <b>구조적 기준 두 가지</b>는 깨지면
    채택 불가로 못 박았다 &mdash; ① 렌더된 답변에 <b>시드 밖 이름이 없어야 한다</b>(도구 결과
    창작 차단) ② <code>change_stage</code> 확인 카드는 <b>기대한 지원자를 가리켜야 한다</b>
    (다른 레코드 차단). 성공률 &middot; 응답 시간은 <code>results/*.jsonl</code> 에 append 로
    쌓여, 프롬프트를 고친 뒤 다시 돌리면 같은 파일의 diff 로 개선이 보인다.
    쓰기 의도는 확인 카드까지만 만들고 실행하지 않으므로 <b>하네스가 DB 를 바꾸지 않는다.</b>
  </p>

  <p class="tst__sub">계약과 구조도 스크립트로 잰다</p>

  <p class="tst__note">
    <code>check_public_contract.py</code> 는 배포본 <code>/openapi.json</code> 에서 GET 을 전부
    뽑아 <b>토큰 없이 한 번씩 때려 본다.</b> 경로 목록을 코드에 박지 않은 이유는 명시적이다
    &mdash; <b>박아두면 새로 생긴 엔드포인트가 대조에서 빠져 무의미해진다.</b> 경로 변수에는
    존재하지 않는 값을 넣어 실지원자 데이터에 닿지 않고, 읽기만 한다.
    실측은 08. 31. 경로 35/35 &middot; 스키마 62/62, 09. 02. <b>경로 55/55 &middot; 스키마 75/75
    &middot; 필드 불일치 0</b> 이다.
  </p>

  <p class="tst__note">
    <code>check_architecture.py</code> 는 ADR-0035 헥사고날 적용 상태를 AST 로 센다.
    이유를 스크립트가 직접 적고 있다 &mdash; <b>"포트 &middot; 어댑터로 바꿨다"는 말은 폴더를
    만든 것만으로도 참이 되어 버린다.</b> 2026. 09. 12. 실측값을 기준선으로 박아
    <code>--strict</code> 는 원시 DB 접근이 늘면 실패한다. 그때 판정은
    "구조는 갖췄지만 실질은 절반"이었고, 그 숫자를 남겨 뒀다.
  </p>

</div>

<div class="tst__sec">

  <h2><span class="tst__num">3.</span> 사용자 인수 테스트</h2>

  <p class="tst__note">
    인수 기준은 <code>docs/00_overview/qa-scenarios.md</code> 한 곳이다. 2026. 08. 24. 작성했고,
    <b>그 시점에 화면이 아직 없어서</b> 05-design 의 화면 지도를 기준으로 썼다 &mdash;
    확정되지 않은 UI 디테일은 <b>"(화면 확정 후 갱신)"</b> 으로 표시해 둔다.
    각 시나리오는 <b>전제 &rarr; 절차 &rarr; 기대 결과</b> 세 줄이다: 어떤 상태에서,
    누가 무엇을 클릭 &middot; 입력하고, 무엇이 보이면 성공인가.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>군</th><th>건수</th><th>담는 것</th></tr>
    </thead>
    <tbody>
      <tr><td class="nowrap">A. 인증 &middot; 권한</td><td class="num">3</td>
          <td>JWT 가입 &middot; 로그인, 역할 2종(관리자 &middot; 멤버), <b>조작 제어</b></td></tr>
      <tr><td class="nowrap">B. 채용 공고</td><td class="num">3</td>
          <td>생성 &middot; 수정 &middot; 삭제, 상태 3종, 공고별 지원자 수 집계</td></tr>
      <tr><td class="nowrap">C. 지원 (로그인 없음)</td><td class="num">3</td>
          <td>공개 링크 지원서 제출, 이력서 업로드, 개인정보 수집 동의</td></tr>
      <tr><td class="nowrap">D. 지원자 관리</td><td class="num">6</td>
          <td>테이블 &middot; 칸반 &middot; 드래그 단계 이동 &middot; 상세 &middot; 단계 이력 &middot;
              담당자 직접 등록</td></tr>
      <tr><td class="nowrap">E. 평가</td><td class="num">2</td>
          <td>점수(1~5) + 코멘트 작성, 목록 조회와 평균 점수</td></tr>
      <tr><td class="nowrap">F. 파일</td><td class="num">2</td>
          <td>presigned URL 로 브라우저 &rarr; S3 직행 업로드, 다운로드</td></tr>
      <tr><td class="nowrap">G. 알림 &middot; 메일</td><td class="num">3</td>
          <td>단계 변경 메일, 비동기 처리(200ms 내 응답), 실패 시 재시도</td></tr>
      <tr><td class="nowrap">H. 검색 &middot; 필터</td><td class="num">2</td>
          <td>이름 &middot; 이메일 검색, 단계별 필터</td></tr>
      <tr><td class="nowrap">J. 시스템 &middot; 운영</td><td class="num">3</td>
          <td>Docker 구성, AWS 배포, Swagger <code>/docs</code></td></tr>
      <tr><td class="nowrap"><b>실패 케이스</b></td><td class="num">7</td>
          <td>중복 지원(409) &middot; 허용 안 되는 형식 &middot; 용량 초과 &middot; 권한 없는 접근(403)
              &middot; 마감 공고 지원 &middot; 로그인 실패 &middot; 필수 항목 미입력</td></tr>
    </tbody>
  </table>
  </div>

  <p class="tst__note" style="margin-top:1.1rem;">
    <b>시나리오는 결정이 바뀌면 같이 고친다.</b> A3 "면접관은 배정된 지원자만 조회"는
    08. 31. ADR-0017(등급 이분화)로 폐지됐고, 확인할 것이 "무엇이 열렸는가 &middot; 무엇이
    남았는가"로 바뀌어 <b>세 갈래로 쪼갰다</b> &mdash; A3-1 조회는 전원 열려 있다(미배정
    10명 포함 12명 전원이 보인다), A3-2 멤버는 배정된 건만 평가를 쓴다(그 외 403),
    A3-3 면접관 배정 &middot; 남의 가용 시간은 관리자만(단 본인 가용 시간은 멤버도 가능).
    시나리오가 낡은 채 남아 있으면 인수 기준이 아니라 오해의 근거가 된다.
  </p>

  <p class="tst__sub">1차 게이트 (09. 04.) &mdash; 09. 02. 수직 슬라이스 실측</p>

  <p class="tst__note">
    게이트 판정은 문장이 아니라 <b>실데이터 한 번 관통</b>으로 했다. 공개 지원 폼 제출 &rarr;
    DB 저장 &rarr; 담당자 확인까지다. 게이트 4항목 중 마지막까지 미충족이던 것이 이
    수직 슬라이스였고, <b>판정일(09. 04.)보다 이틀 앞선 09. 02.에 관통해 닫았다</b> &mdash;
    코드 변경 없이 브라우저로 실제 경로를 한 번 통과한 것이다. 기존 공고를 쓰지 않고
    검증용 공고(<code>id 3</code>)를 새로 만들어 관통한 뒤 <code>closed</code> 로 내렸다:
    C6 의 <code>UNIQUE(job_posting_id, email)</code> 에 걸릴 수 있고, 공개 링크 발급이
    <b>재발급이라 그 공고의 기존 토큰을 즉시 무효화</b>하기 때문이다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead><tr><th>단계</th><th>결과</th></tr></thead>
    <tbody>
      <tr><td>공개 링크로 공고 조회 (로그인 없음)</td>
          <td><span class="tag tag--done">통과</span> <code>GET /public/postings/by-token/{token}</code></td></tr>
      <tr><td>이력서 PDF 첨부 &rarr; 브라우저에서 S3 직행 PUT</td>
          <td><span class="tag tag--done">통과</span></td></tr>
      <tr><td>제출</td>
          <td><span class="tag tag--done">통과</span> 지원자 <code>id 24</code> &middot;
              <code>source=form</code> &middot; <code>files</code> 1행</td></tr>
      <tr><td>담당자 화면 표시</td>
          <td><span class="tag tag--done">통과</span> 목록 &middot; 상세 모두</td></tr>
      <tr><td>접수 확인 메일</td>
          <td><span class="tag tag--done">sent</span> 기존 15건이 <code>failed</code> 인 것과 달리 성공</td></tr>
      <tr><td>단계 이력</td>
          <td><code>(없음) &rarr; applied</code></td></tr>
      <tr><td>담당자의 첨부 열람</td>
          <td><span class="tag tag--done">통과</span> 실측 시점엔 <b>받아보는 쪽 화면이 없었고</b>,
              프론트 오너에게 넘겨 같은 날 <code>f4d7a1b</code> 로 닫혔다 &mdash;
              826 B PDF 원문이 그대로 렌더</td></tr>
    </tbody>
  </table>
  </div>

  <p class="tst__note" style="margin-top:1.1rem;">
    <b>검증 방법 자체를 기록으로 남겼다.</b> 첨부를 눌러도 브라우저에서 아무 일이 없어 보일 수
    있는데, 그것이 기능 실패인지 환경 탓인지 구분하려면 <b>같은 URL 을 iframe 으로 불러 렌더되는지
    본다</b>(iframe 로드는 CORS 검사를 안 받는다). 오류 표시와 콘솔이 비어 있는데 화면만 안 바뀌면
    환경 쪽이다. 실제로 버킷 CORS 의 <code>AllowedMethods</code> 가 <code>PUT</code> 뿐이라
    브라우저 <code>fetch</code> GET 은 막히고, 이 판별법 없이는 서버가 멀쩡하고 로그에도 안 남는
    함정에 다시 빠진다.
  </p>

  <p class="tst__sub">2차 게이트 (09. 30.) &mdash; 아직 안 돌았다</p>

  <p class="tst__note">
    조건은 필수 27개 기능 전부 프로덕션 동작 &middot; 에이전트와 앱도 데모 가능 &middot;
    <b>QA 시나리오 전 항목 통합 리허설 2회</b> &middot; 09. 28.~30. 전 도메인 공통 버퍼(코드
    프리즈와 잔여 버그)다. 통합 리허설은 W5(09. 21.~25.)에 프로덕션 URL 과 실기기에서 도는
    일정이고, <b>09. 22. 현재 아직 수행 전</b>이다
    <span class="tag tag--wait">예정</span>.
  </p>

  <p class="tst__sub">외부 인수 &mdash; 멘토링이 실질적인 수용 심사였다</p>

  <p class="tst__note">
    내부 QA 와 별개로 IBM 강사 멘토링이 사실상의 인수 창구였다. 09. 10. 멘토가
    <b>21개 항목</b>을 짚었고(서류 &middot; AI 요약 6 &middot; 면접 7 &middot; 지원자 쪽 4 &middot;
    화면 &middot; 앱 &middot; 학습 4), 팀이 항목마다 현황과 대조해 "이미 동작 / 결정 필요 /
    실측 필요"로 갈랐다. 09. 11. 숙제는 <b>"지원자 &middot; 관리자 입장에서 각각 시연 가능하도록
    준비"</b>였다 &mdash; 두 역할로 갈라 시연한다는 인수 기준이 여기서 나왔다.
    09. 18. 피드백의 "모델 비교를 정량적으로"는 09. 22. 같은 채점기 기반 정량 보고서로
    반영됐다 &mdash; 같은 날짜의 나머지 세 항목은 트래커에서 아직 <code>doing</code> 이다.
  </p>

</div>

<div class="tst__sec">

  <h2><span class="tst__num">4.</span> 결함 추적 및 조치</h2>

  <p class="tst__note">
    추적 창구는 <b>셋</b>이다. 하나는 GitHub 이슈 &middot; PR, 하나는 피드백 트래커,
    하나는 사람이 아니라 기계다.
  </p>

  <div class="rule">
    <div class="rule__row rule__row--base">
      <span class="rule__k">① GitHub 이슈 &middot; PR &mdash; PR 이 곧 기록</span>
      <p class="rule__v">
        리뷰 게이트가 없으므로 <b>브랜치 &middot; 커밋 메시지 &middot; PR 본문이 전부 사후 참고
        대상</b>이다. 09. 22. 기준 <code>main</code> 의 커밋 <b>1,095개</b> &middot;
        머지된 PR <b>236건</b>(번호는 #354 까지).
        커밋 제목에는 기능 번호(D3 &middot; G1 &middot; J7)나 도메인 접두어를 붙이고,
        type 은 <code>feat</code> <code>fix</code> <code>docs</code> <code>test</code>
        <code>chore</code> <code>refactor</code> 다.
      </p>
    </div>
    <div class="rule__row">
      <span class="rule__k">② 피드백 트래커 &mdash; <code>_data/feedback/&lt;GitHub 아이디&gt;.yml</code></span>
      <p class="rule__v">
        멘토링 &middot; 강의 피드백은 <b>반영 담당자가 자기 파일에</b> 적는다 &mdash;
        칸반과 같은 원칙(한 사람 = 파일 하나)이라 git 충돌이 없다. 접수 시점에는
        <code>received</code> &middot; <code>from</code> &middot; <code>content</code> &middot;
        <code>status: todo</code> 만 채우고, 반영이 끝나면 <b>같은 항목에</b>
        <code>fixed</code> &middot; <code>fix</code> 를 채워 <code>done</code> 으로 바꾼다 &mdash;
        <b>접수와 반영이 한 줄에서 추적</b>된다.
      </p>
    </div>
    <div class="rule__row">
      <span class="rule__k">③ 외부 헬스체크 &mdash; 기계가 이슈를 연다</span>
      <p class="rule__v">
        서버 안의 지표는 "서버가 살아 있다"까지만 안다. DNS &middot; TLS &middot; Caddy &middot;
        보안그룹이 죽어 <b>밖에서만</b> 안 되는 경우는 못 잡는다. 그래서 GitHub 러너가
        <b>15분마다 공개 주소를 사용자와 같은 경로로</b> 부르고, 실패하면 이슈를 열거나 열린
        이슈에 코멘트, 복구되면 "복구됨"을 달고 닫는다. <b>열린 이슈는 항상 최대 하나</b>다.
        공개 저장소라 비용 0.
      </p>
    </div>
  </div>

  <p class="tst__sub">도메인 밖 결함은 고치지 않고 넘긴다</p>

  <p class="tst__note">
    다른 도메인에서 문제를 발견하면 직접 고치지 않고 <b>이슈로 오너에게 넘긴다.</b>
    실례 &mdash; 백엔드가 앱 쪽 프레임 전송 문제를 09. 16.에 <b>이슈 #260</b> 으로 넘기면서
    <b>PR #154 를 닫고 살아 있는 항목 둘만 추렸다.</b> 같은 건에서
    "얼굴 114/114 <code>no_face</code>" 추적은 <b>앱이 안 보내는 것과 서버가 못 찾는 것을
    가르려면 양쪽을 같이 봐야 해서</b> 서버 로그 대조를 백엔드가 맡기로 나눴다.
    경계를 넘는 수정보다 경계를 넘는 <b>정보 교환</b>이 싸다.
  </p>

  <p class="tst__sub">사고 하나에 장치 하나 &mdash; 재발 방지 규칙으로 승격된 것</p>

  <div class="fix">

    <div class="fix__item">
      <span class="fix__k">사고</span>
      <h3>깨진 main 을 하루 두 번, 둘 다 우연히 발견</h3>
      <p><b>장치</b> &mdash; CI 도입. 이후 09. 04. 브랜치 &rarr; PR &rarr; 자체 머지로
         main 에 닿는 경로를 하나로 좁혔다. 지금 5개 잡이 push &middot; PR 마다 돈다.</p>
    </div>

    <div class="fix__item">
      <span class="fix__k">사고</span>
      <h3>미정의 이름 2건이 프로덕션 500</h3>
      <p><b>장치</b> &mdash; CI <code>ruff --select F</code>. 스타일 규칙까지 켜지 않은 것이
         핵심이다 &mdash; 기존 파일 수백 줄이 빨개지면 <b>아무도 안 보는 빨간 CI</b> 가 된다.
         잡는 것은 실제로 터지는 것뿐.</p>
    </div>

    <div class="fix__item">
      <span class="fix__k">사고</span>
      <h3>Docker 가 죽어 pytest 가 24분간 침묵</h3>
      <p><b>장치</b> &mdash; pytest-timeout 60초. 멈춤을 침묵이 아니라 <b>실패</b>로 바꿨다.</p>
    </div>

    <div class="fix__item">
      <span class="fix__k">사고</span>
      <h3>디스크 고갈로 배포가 죽음</h3>
      <p><b>장치</b> &mdash; 컨테이너 로그 상한 20MB&times;3 &middot; 배포 때 이미지 &middot;
         캐시 prune &middot; EBS 29 &rarr; 50GB(09. 10.). 이 건과 위 두 장치(멈춤 &middot;
         미정의 이름)를 묶어 <b>세 부류 모두 재발 0</b> 이다.</p>
    </div>

    <div class="fix__item">
      <span class="fix__k">사고</span>
      <h3>n8n 이 웹훅은 받고 죽어 메일이 <code>queued</code> 로 잔류</h3>
      <p><b>장치</b> &mdash; API 가 스스로 5분마다 밀린 메일을 SMTP 로 재발송(최대 3회, 초과는
         <code>failed</code> 로 접어 사람이 확인). 합격 &middot; 불합격 통보가 통째로 멎던
         단일 장애점을 없앴다.</p>
    </div>

    <div class="fix__item">
      <span class="fix__k">사고</span>
      <h3><code>.env</code> 를 고쳤는데 반영이 안 됨</h3>
      <p><b>장치</b> &mdash; <code>docker compose restart</code> 는 <code>env_file</code> 을 다시
         읽지 않는다. <code>up -d --force-recreate</code> 를 규칙으로 문서화했다.</p>
    </div>

  </div>

  <p class="tst__sub">대조가 잡아낸 결함, 실측이 뒤집은 판정</p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr><th>결함</th><th>어떻게 드러났나</th><th>조치</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="nowrap">#59 면접관이 공고 수정 가능<br>#97 draft 공고 무인증 노출</td>
        <td>무인증 GET 대조 &mdash; <b>지금까지 나온 권한 결함이 전부 이 대조에서 나왔다</b></td>
        <td>대조를 스크립트로 굳혀(<code>check_public_contract.py</code>) 엔드포인트가 늘 때마다
            자동으로 대상이 되게 했다</td>
      </tr>
      <tr>
        <td class="nowrap">#282 이행 번호 <code>0023</code> 중복<br>#283 <code>file_blobs</code> 누락</td>
        <td>운영에만 표가 없는데 CI 는 초록 &mdash; <code>create_all</code> 이 가렸다</td>
        <td>모델&harr;이행 비교를 CI 상설 스텝으로. 09. 22. DB 권한 분리 이후에는
            <b>누락이 곧 기동 실패</b>라 더 중요해졌다</td>
      </tr>
      <tr>
        <td class="nowrap">요건 우수 지원자가 우대 부족만으로 탈락</td>
        <td>fit-check 지원자 <b>24명 3축 점수 실측</b> &mdash; 인수인계의
            "자동 불합격 3명"이 실제로는 <b>8명</b>이었다</td>
        <td><b>PR #182</b> &mdash; 가중치 요건 50&rarr;60 &middot; 우대 20&rarr;10 &middot;
            문화 30 유지 + 요건 &ge;70 이면 문화 하한 50</td>
      </tr>
      <tr>
        <td class="nowrap">자료가 없는 지원자를 채점하려 함</td>
        <td>자소서 1줄 &middot; 전부 미기재인 지원자가 판정 없이 남거나
            사유 불명 「불합격」으로 보였다</td>
        <td><b>PR #349 &middot; #351</b> &mdash; 요약 <code>insufficient=true</code> 면
            「서류 탈락」 라벨로. <code>false</code> 인 지원자는 안 건드려 대량 탈락 방지</td>
      </tr>
      <tr>
        <td class="nowrap">AI 추정값이 신고값처럼 보임</td>
        <td>폼에 경력을 안 적으면 AI 가 이력서에서 연차를 추출하는데
            <b>표식이 없어 구별 불가</b> (공정성)</td>
        <td><code>career_years_source="ai"</code> 표식 &rarr; 프론트 「AI 추정」 배지.
            재생성 시 표식이 사라지는 문제는 <b>PR #311 로 후속 &mdash; 09. 22. 현재 미머지</b></td>
      </tr>
      <tr>
        <td class="nowrap">인터뷰방 답변 저장 실패 &middot; 서류 대조 &middot; CONFLICT 409</td>
        <td>09. 10. 멘토링 21항목 점검 + 시연 리허설 중 실측
            (Q9 시도 후 Q1 로 되돌아감)</td>
        <td><b>PR #174 &middot; #175 &middot; #178</b> 로 해결, <b>PR #183</b> 으로
            Qwen 학습 파이프라인 착수</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="tst__sub">닫지 못한 것</p>

  <p class="tst__note">
    <b>안 된 것은 안 됐다고 적는다.</b> 09. 15. 세션 75 에서 CPU 전사가 180초 상한을 넘겨
    답변이 <code>[전사 지연]</code> 자리표시자로 저장됐다. 전사 속도 자체는 OpenAI API 전환으로
    풀렸지만 <b>이미 자리표시자로 남은 답변을 되살리는 경로는 없다</b>
    <span class="tag tag--open">미해결</span> &mdash; 기능 미비가 아니라 <b>지원자 데이터
    손실</b>이라 백엔드 큐 23번으로 남은 기간 맨 위에 뒀다. AI 면접 서버 린트 5건도 아직
    CI 에 안 붙어 있다 <span class="tag tag--wait">대기</span>.
    이 둘은 초록을 만들어 가리지 않고 <b>빨간 채로 문서에 남긴다</b> &mdash; 그것이
    "테스트를 통과시키려고 우회하지 않는다"는 규칙의 실제 모습이다.
  </p>

</div>

<a class="tst__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
