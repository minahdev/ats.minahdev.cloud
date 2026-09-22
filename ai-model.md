---
layout: default
title: AI 모델 적용
permalink: /ai-model/
---

<style>
.aim { max-width: 64rem; margin: 2.5rem auto 4rem; }

.aim__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 1.6rem; }
.aim__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.aim__crumb a { color: #9ca3af; }
.aim__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; word-break: keep-all; }
.aim__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

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
.who-a { background: #e0e7ff; color: #3730a3; }
.who-b { background: #d1fae5; color: #065f46; }
.who-c { background: #fce7f3; color: #9d174d; }
.who-d { background: #fef3c7; color: #92400e; }
.who-e { background: #e0f2fe; color: #075985; }

.aim__stat {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(8.5rem, 1fr));
  gap: .6rem;
  margin-bottom: 2.75rem;
}
.stat { border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .85rem; }
.stat__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.stat__v { font-size: 1.05rem; font-weight: 700; color: #111827; word-break: keep-all; }
.stat__v small { display: block; font-size: .74rem; font-weight: 400; color: #9ca3af; margin-top: .1rem; }

.aim__sec { margin-bottom: 3.25rem; }
.aim__sec > h2 {
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
.aim__num { font-variant-numeric: tabular-nums; font-weight: 700; }

.aim__sub {
  margin: 2rem 0 .7rem;
  font-size: .95rem;
  font-weight: 700;
  color: #111827;
  word-break: keep-all;
}
.aim__sub:first-of-type { margin-top: 0; }
.aim__sub code { font-size: .86rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; font-weight: 400; }

.aim__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }
.aim__p { margin: 0 0 .9rem; color: #374151; font-size: .92rem; line-height: 1.8; word-break: keep-all; }
.aim__p:last-child { margin-bottom: 0; }
.aim__p code, .aim__note code { font-size: .84rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 표 공통 — schedule.md 와 같은 패턴 */
.tbl__scroll { overflow-x: auto; padding-bottom: .3rem; margin-bottom: 1.1rem; }
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
.tbl__lead { white-space: nowrap; color: #111827; font-weight: 600; }
.tbl--wide { min-width: 46rem; }
.tbl--bench { min-width: 42rem; }
.tbl .is-pick { background: #f0fdf4; }
.tbl .is-weak { color: #9ca3af; }

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
.tag--warn { background: #fef3c7; color: #92400e; }
.tag--gate { background: #fee2e2; color: #991b1b; }

/* 해석 주의 박스 */
.caution {
  border: 1px solid #fcd34d;
  border-left: 3px solid #d97706;
  background: #fffbeb;
  border-radius: 6px;
  padding: .9rem 1.1rem;
  margin-bottom: 1.1rem;
}
.caution h3 { margin: 0 0 .5rem; font-size: .88rem; color: #92400e; word-break: keep-all; }
.caution ul { margin: 0; padding-left: 1.05rem; }
.caution li { font-size: .855rem; line-height: 1.75; color: #78350f; word-break: keep-all; margin-bottom: .3rem; }
.caution li:last-child { margin-bottom: 0; }
.caution code { font-size: .8rem; background: rgba(0, 0, 0, .05); padding: .05rem .3rem; border-radius: 3px; }

/* 카드형 항목 */
.items { display: grid; gap: .7rem; margin-bottom: 1.1rem; }
.item { border: 1px solid #e5e7eb; border-radius: 6px; padding: .85rem 1rem; }
.item__t { margin: 0 0 .35rem; font-size: .9rem; font-weight: 600; color: #111827; word-break: keep-all; }
.item__t code { font-size: .83rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; font-weight: 400; }
.item__d { margin: 0; font-size: .86rem; line-height: 1.75; color: #6b7280; word-break: keep-all; }
.item__d code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 파이프라인 단계 */
.flow { border: 1px solid #e5e7eb; border-radius: 6px; overflow: hidden; margin-bottom: 1.1rem; }
.flow__step { padding: .8rem 1rem; border-bottom: 1px solid #f3f4f6; }
.flow__step:last-child { border-bottom: 0; }
.flow__step--base { background: #f9fafb; }
.flow__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .35rem; }
.flow__v { margin: 0; font-size: .87rem; line-height: 1.75; color: #374151; word-break: keep-all; }
.flow__v code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

.aim__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }

@media (max-width: 34rem) {
  .aim__stat { grid-template-columns: repeat(2, 1fr); }
}
</style>

<div class="aim">

<div class="aim__head">
  <p class="aim__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 7. AI 모델 적용</p>
  <h1>AI 모델 적용</h1>
  <p>자체학습으로 검증하고 같은 자로 재서 클라우드 + Claude 로 확정했다 &middot;
     최종 갱신 2026. 09. 22.</p>
</div>

<div class="aim__stat">
  <div class="stat"><span class="stat__k">서빙 모델</span>
    <span class="stat__v">Haiku 4.5<small>claude-haiku-4-5</small></span></div>
  <div class="stat"><span class="stat__k">도구 호출 정확도</span>
    <span class="stat__v">73.9%<small>Qwen v9 &middot; 17/23</small></span></div>
  <div class="stat"><span class="stat__k">호출당 원가</span>
    <span class="stat__v">$0.0075<small>실사용 평균</small></span></div>
  <div class="stat"><span class="stat__k">자체학습 어댑터</span>
    <span class="stat__v">3갈래<small>chat &middot; summary &middot; interview</small></span></div>
  <div class="stat"><span class="stat__k">비교 채점기</span>
    <span class="stat__v">judge.py<small>5축 &middot; 동일 23건</small></span></div>
</div>

<div class="aim__sec">

  <h2><span class="aim__num">1.</span> 모델 선정 및 비교</h2>
  <p class="aim__note">
    모델을 한 번에 고르지 않았다. <b>용도별로 나눠 시작했고</b>(ADR-0011),
    로컬 sLLM 을 실측해 접었다가 장비 조건을 바꿔 되살렸으며(ADR-0024 &middot; 0032),
    마지막에 <b>자체학습 어댑터와 클라우드 API 를 같은 자로 견줘</b> 확정했다(2026. 09. 18.).
    이 절은 그 세 번의 비교다.
  </p>

  <p class="aim__sub">1-1. 용도별로 나눈다 &mdash; 비용이 데이터 양에 비례하는 쪽이 따로 있다</p>
  <p class="aim__p">
    LLM 호출이 생기는 자리는 둘이고 요구가 다르다. 도구 호출은 호출 수가 적지만 정확도가 데모 품질을
    결정하고, 이력서 요약은 건수가 지원자 수만큼 늘어 <b>단가가 지배적</b>이다. 하나로 고정하면 한쪽이
    손해라 용도별로 갈랐다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr><th>용도</th><th>모델</th><th>단가 (1M 토큰)</th><th>고른 이유</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__lead">도구 호출 에이전트</td>
        <td><code>claude-opus-5</code></td>
        <td class="tbl__num">입력 $5 / 출력 $25</td>
        <td>문장 &rarr; 도구 순차 호출의 정확도가 곧 데모다. 여기서 아끼면 발표가 깨진다</td>
      </tr>
      <tr>
        <td class="tbl__lead">이력서 요약 &middot; 구조화</td>
        <td><code>claude-haiku-4-5</code></td>
        <td class="tbl__num">입력 $1 / 출력 $5</td>
        <td>정해진 형식으로 요약하는 작업. 건수가 많아 단가가 지배적</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="aim__p">
    요약 1건을 입력 3K + 출력 0.5K 토큰으로 잡으면 opus ≈ $0.028, haiku ≈ $0.006 이다.
    더미 10만 건이면 <b>≈ $2,750 대 ≈ $550</b> &mdash; 어느 모델이든 사고다. 그래서 ADR-0011 의 본체는
    모델 선택이 아니라 <b>가드</b>다. 더미 데이터에는 LLM 을 호출하지 않고, 요약 생성 경로를
    접수 훅과 명시적 재생성 버튼 두 곳으로 막고, 호출마다 토큰&middot;비용을 로깅하고,
    생성에 쓴 모델명을 <code>applications.ai_summary_model</code> 에 남겨 어느 요약이 어느 모델
    산출인지 추적한다.
  </p>
  <p class="aim__p">
    실제로 opus 는 쓰지 않았다. 2026. 09. 15. <code>claude-opus-5</code> 를 실측했으나 비용상 미채택했고,
    <b>채팅&middot;요약 기본 모델은 <code>claude-haiku-4-5</code> 로 유지</b>된다.
  </p>

  <p class="aim__sub">1-2. 로컬 sLLM &mdash; 실측으로 접고, 조건을 바꿔 되살렸다</p>
  <p class="aim__p">
    출발점은 지원자 개인정보가 외부 API 로 나가지 않는 <b>&ldquo;데이터 반출 없는 채용 에이전트&rdquo;</b>였다.
    2026. 09. 01. 실측 조건은 RTX 3050 8GB &middot; DB 지원자 500건 &middot; 실제 도구 실행이다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--bench">
    <thead>
      <tr><th>질의</th><th class="tbl__num">claude-haiku-4-5</th>
          <th class="tbl__num">qwen3:4b</th><th class="tbl__num">qwen3:8b</th></tr>
    </thead>
    <tbody>
      <tr><td class="tbl__lead">읽기 도구 1개</td><td class="tbl__num"><b>13.6초</b></td>
          <td class="tbl__num">73.2초</td><td class="tbl__num is-weak">107.5초</td></tr>
      <tr><td class="tbl__lead">쓰기 (확인 카드까지)</td><td class="tbl__num"><b>2.9초</b></td>
          <td class="tbl__num">32.6초</td><td class="tbl__num is-weak">31.0초</td></tr>
      <tr><td class="tbl__lead">도구 연쇄 시도</td><td class="tbl__num"><b>6.6초</b></td>
          <td class="tbl__num">86.8초</td><td class="tbl__num is-weak">130.5초</td></tr>
      <tr><td class="tbl__lead">출력 tok/s</td><td class="tbl__num"><b>106</b></td>
          <td class="tbl__num">45</td><td class="tbl__num is-weak">7.4</td></tr>
    </tbody>
  </table>
  </div>

  <p class="aim__p">
    <b>병목은 프롬프트가 아니라 출력 길이였다.</b> 논의는 &ldquo;고정 프리픽스 17KB 가 무겁다&rdquo;에서
    출발했는데, 같은 질의에서 <code>qwen3:4b</code> 가 <b>3,248 출력 토큰</b>을 쓰는 동안 haiku 는
    1,450 토큰을 썼다. 사고 모드를 꺼도 3,444 &rarr; 3,248 로 거의 그대로여서 원인이 아니었다.
    Ollama <code>format</code> 에 결정 스키마를 걸어 출력 형식을 강제하자 형식 붕괴가 사라졌고,
    같은 읽기 질의에서 <code>qwen3:4b</code> 의 출력 토큰이 <b>2,653 &rarr; 252</b> 로 줄면서
    읽기 60.4 &rarr; <b>16.9초</b> &middot; 쓰기 42.9 &rarr; <b>3.5초</b> &middot; 연쇄 69.0 &rarr; <b>11.2초</b>가 됐다.
    문법 제약이 <code>&lt;think&gt;</code> 누출을 원천 차단하니 사고 모드를 꺼도 안전해졌고,
    그러자 남아 있던 사고 토큰까지 통째로 없어졌다 &mdash; 지우는 것과 안 만드는 것의 차이다.
  </p>
  <p class="aim__p">
    <code>qwen2.5:3b</code> 는 여기서 접었다 <span class="tag tag--drop">탈락</span> &mdash;
    &ldquo;10명&rdquo;을 &ldquo;5명&rdquo;이라 하고 도구가 주지 않은 학력을 지어낸다.
    <b>형식이 아니라 능력 문제라 문법 제약으로 안 잡힌다.</b>
    반대로 8B 의 7.4 tok/s 는 모델이 느린 값이 아니라 <b>8GB 카드에 KV 캐시 자리가 없어 레이어가
    CPU 로 흘러넘친 값</b>으로 봤다 &mdash; 4B 의 1/6 이라는 낙차가 그 신호다.
    시연 장비를 T4 16GB 로 잡으면서 ADR-0032 가 8B 를 되살렸다.
  </p>

  <p class="aim__sub">1-3. 추론 모델 3종 확정 (ADR-0032 &middot; 2026. 09. 08.)
    <span class="who who-d">소연 D</span></p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr><th>역할</th><th>모델</th><th>라이선스</th><th class="tbl__num">VRAM</th><th>비고</th></tr>
    </thead>
    <tbody>
      <tr><td class="tbl__lead">표정</td><td>ViT (Vision Transformer)</td><td>Apache 2.0</td>
          <td class="tbl__num">~0.35GB</td><td>판정기가 아니라 특징 벡터의 일부 (&sect;4)</td></tr>
      <tr><td class="tbl__lead">전사</td><td>Whisper large-v3-turbo + faster-whisper</td><td>MIT</td>
          <td class="tbl__num">~1.6GB</td><td>프로덕션 기본은 09. 15. API 로 전환</td></tr>
      <tr><td class="tbl__lead">sLLM</td><td>Qwen3-8B (Q4)</td><td>Apache 2.0</td>
          <td class="tbl__num">~5.2GB + KV ~1GB</td><td>자체학습 대상</td></tr>
      <tr><td class="tbl__lead">임베딩</td><td>ko-sroberta-multitask (768차원)</td><td>Apache 2.0</td>
          <td class="tbl__num">~0.5GB</td><td>이미 로컬 &mdash; 바꾸지 않았다</td></tr>
      <tr><td class="tbl__lead">합</td><td colspan="2">넷을 같이 올린다</td>
          <td class="tbl__num"><b>≈ 8.7GB</b></td><td>T4 16GB 에 7GB 를 남기고 들어간다</td></tr>
    </tbody>
  </table>
  </div>

  <p class="aim__p">
    CPU 실측(2026. 09. 08.)이 곧 <b>GPU 가 필요한 이유</b>였다. Whisper large-v3-turbo(int8)는 로딩 48초 &middot;
    1.8배속(35.6초 음성 &rarr; 19.5초) &middot; 메모리 ~1.0GB, ViT 는 로딩 1.4초 &middot; 130ms/장 &middot; ~0.9GB 다.
    백엔드 API 는 t3.micro(1GiB)라 <b>Whisper 하나가 들어가지 않는다.</b>
  </p>
  <p class="aim__p">
    전사는 2026. 09. 15. 프로덕션 기본을 갈아탔다(ADR-0038). t3.large 2 vCPU 에서 로컬 large-v3-turbo 가
    <b>43.9초 발화를 180초 상한 안에 끝내지 못했고</b>, 밀린 시간이 뒤 답변까지 연쇄로 죽였다.
    OpenAI <code>whisper-1</code>(분당 $0.006 &middot; 면접당 ≈ $0.06)은 CPU 를 쓰지 않아 줄에 서지 않는다.
    이후 GPU 로 옮긴 T4 실측은 STT 275ms/3초 &middot; ViT 75ms/crop, 전사 7.5초 &rarr; ~1초,
    <b>8명 동시 접속에도 대기줄 0</b>이다.
  </p>

  <p class="aim__sub">1-4. 자체학습 어댑터 vs 클라우드 API &mdash; 같은 자로 쟀다
    <span class="who who-e">수택 E</span></p>
  <p class="aim__p">
    Qwen3-8B 를 QLoRA(4-bit + 어댑터)로 자체학습해 <b>chat &middot; summary &middot; interview 어댑터 3갈래</b>를
    만들었다. 학습 데이터는 222건(실측 21 + 합성 192 + 인터뷰 chain 시드 9)이고, 초기 AWS G4dn(T4)에서
    시작해 v7~v9 는 Google Colab GPU(L4/T4)에서 훈련했다. 비교는 <b>동일 케이스 23건 &middot; 동일 채점기
    <code>judge.py</code></b> 로 했다 &mdash; 감이 아니라 근거로 정하기 위해서다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--bench">
    <thead>
      <tr><th>항목</th><th class="tbl__num">Qwen 학습 전<br>(09. 11.)</th>
          <th class="tbl__num">Claude Haiku 4.5<br>(09. 12.)</th>
          <th class="tbl__num">Qwen v9<br>(09. 17.)</th></tr>
    </thead>
    <tbody>
      <tr><td class="tbl__lead">도구 호출 정확도</td>
          <td class="tbl__num">26.1% (6/23)</td>
          <td class="tbl__num">69.6% (16/23)</td>
          <td class="tbl__num"><b>73.9% (17/23)</b></td></tr>
      <tr><td class="tbl__lead">도구 이름 일치</td>
          <td class="tbl__num">26%</td><td class="tbl__num">70%</td><td class="tbl__num is-weak">&mdash;</td></tr>
      <tr><td class="tbl__lead">no-tool 위반 없음</td>
          <td class="tbl__num">100%</td><td class="tbl__num">96%</td><td class="tbl__num is-weak">&mdash;</td></tr>
      <tr><td class="tbl__lead">위험한 실패<br>(임의 실행 &middot; 지어낸 도구)</td>
          <td class="tbl__num">0건</td><td class="tbl__num">0건</td><td class="tbl__num">0건</td></tr>
      <tr><td class="tbl__lead">비용</td>
          <td class="tbl__num">$0 + GPU $0.71/h</td>
          <td class="tbl__num">$0.0139 / eval건<br>$0.0075 / 실사용</td>
          <td class="tbl__num">$0 + GPU $0.71/h</td></tr>
      <tr><td class="tbl__lead">콜드 스타트</td>
          <td class="tbl__num">78초</td><td class="tbl__num is-weak">&mdash;</td><td class="tbl__num">78초</td></tr>
    </tbody>
  </table>
  </div>

  <div class="caution">
    <h3>해석 주의 &mdash; 이 표를 어디까지 믿는가</h3>
    <ul>
      <li><b>채점기에 편향이 있다.</b> <code>judge.py</code> 의 정답이 Qwen 쪽 gold 기준이라
          절대 수치가 아니라 <b>같은 자로 잰 상대 궤적만 유효</b>하다. 이 사실을 보고서에 명시했다.</li>
      <li><b>표본이 23건이다.</b> 73.9% 와 69.6% 의 차는 케이스 한 건이다 &mdash;
          &ldquo;Qwen 이 이겼다&rdquo;가 아니라 <b>&ldquo;동급&rdquo;이 정직한 표현</b>이다.</li>
      <li><b>분모 23 이 상한이 아니다.</b> 정답을 그대로 채점기에 넣어도 <b>20/23</b> 만 통과한다
          (채점기&middot;데이터 결함 3건을 고친 09. 14. 기준 · 그 전에는 19/23).
          같은 자로 보면 Claude 16/23 은 <b>상한 대비 80.0%</b> 다.</li>
      <li><b>학습 전 26.1% 는 결함을 고치기 전(09. 11.) 값이다.</b> 09. 14. 채점기 수정 뒤
          GPU 재기동이 필요해 재측정하지 못했다 &mdash; 세 값을 한 줄에 놓되
          <b>맨 왼쪽 칸만 채점기 판본이 다르다</b>는 것을 적어 둔다.</li>
      <li><b>Claude 의 write 유형 0/5 는 모델 실패가 아니다.</b> 쓰기 요청에 확인 카드를 띄우고 멈추는
          것이 정상 동작인데 채점기가 한 턴만 본다 &mdash; <b>단일턴 채점의 한계</b>다.
          실패 7건 대부분이 <code>change_stage</code> 를 부르지 않고 <code>search_applications</code> 뒤
          확인을 요청한 경우로, 도구를 <b>더</b> 부른 것이 아니라 <b>덜</b> 부른 것이라
          집합 완화로도 구제되지 않는다.</li>
    </ul>
  </div>

  <p class="aim__p">
    <b>결정(2026. 09. 18.) &mdash; 심사&middot;운영 서빙은 클라우드(AWS) + Claude 로 확정했다.</b>
    갈린 곳은 정확도가 아니었다. 요약 어댑터의 <b>경력 연수 오차(3년 &rarr; 5년)</b> &middot;
    프롬프트 예시 숫자 베끼기 &middot; JSON 따옴표 깨짐 같은 형식&middot;수치 안정성과,
    <b>콜드 스타트 78초</b> &middot; 동시 접속 8명에서 STT 대기 15초 &rarr; 42초 같은 지연&middot;동시성에서
    갈렸고, 그 오류들이 심사 직전(코드 프리즈 09. 20.)에 누적됐다.
    학원 PC 3대로 실제 구축&middot;운영까지 해 본 온프레미스도 같은 날 폐쇄했다.
    <b>학습 파이프라인과 어댑터 3갈래는 비용 절감 R&amp;D 자산으로 보존</b>하며, Ollama 스위치 하나로
    다시 끼울 수 있게 남겼다.
  </p>

</div>

<div class="aim__sec">

  <h2><span class="aim__num">2.</span> 프롬프트 및 파이프라인 설계</h2>
  <p class="aim__note">
    프롬프트를 한 덩어리로 두지 않았다. <b>작업 단위로 쪼개 실패를 격리하고</b>, 점수는 세 축으로
    나눠 근거를 남기며, <b>고정부를 캐시에 올려 원가를 관측</b>한다.
    &ldquo;프롬프트를 잘 쓴다&rdquo;가 아니라 <b>프롬프트가 곧 원가와 품질의 구조</b>라는 것이 이 절의 내용이다.
  </p>

  <p class="aim__sub">2-1. 요약을 3단 체인으로 쪼갰다 (ADR-0022)</p>
  <p class="aim__p">
    단일 프롬프트가 gist &middot; fit &middot; concerns 를 한 번에 뽑던 구조였다.
    한 프롬프트에 여러 작업을 요구할수록 출력 품질이 떨어지고, 중간 결과를 재사용할 수 없어
    요약만 필요할 때도 전체를 다시 호출해야 했다. 세 단계로 나눴다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead>
      <tr><th>단계</th><th>입력</th><th>출력</th><th class="tbl__num">비용/건</th></tr>
    </thead>
    <tbody>
      <tr><td class="tbl__lead">1. 요약</td><td>이름 &middot; 학력 &middot; 경력 &middot; 기술 &middot; 자기소개</td>
          <td>gist &middot; skills_extracted &middot; experience_summary</td><td class="tbl__num">~$0.001</td></tr>
      <tr><td class="tbl__lead">2. 평가</td><td>1단계 출력 + 채용 공고</td>
          <td>fit[] &middot; concerns[] &middot; fit_score</td><td class="tbl__num">~$0.002</td></tr>
      <tr><td class="tbl__lead">3. 추천</td><td>2단계 출력</td>
          <td>group (pass / review / reject) + 근거</td><td class="tbl__num">~$0.001</td></tr>
    </tbody>
  </table>
  </div>

  <p class="aim__p">
    전부 Haiku 로 합계 ~$0.004/건이라 단일 호출($0.001~0.005)과 비슷하다.
    얻은 것은 비용이 아니라 <b>구조</b>다 &mdash; 단계별 출력을 <code>ai_summary</code> JSON 에 구조화 저장해
    재호출 없이 재사용하고, <b>2단계가 실패해도 1단계 결과는 남는다.</b>
    <code>v</code> 필드로 버전을 구분해 기존 데이터 마이그레이션 없이 확장했다.
    호출이 3회로 늘어 지연이 커지지만 백그라운드 태스크라 담당자 화면에 보이지 않는다.
  </p>

  <p class="aim__sub">2-2. 점수는 3축 100점, 임계는 공고가 갖는다 (ADR-0034)</p>
  <p class="aim__p">
    2단계가 세 재료를 <b>따로</b> 채점한다 &mdash; 필수 요건(<code>job_postings.requirements</code> +
    <code>description</code>) &middot; 우대(<code>preferred</code>) &middot;
    인재상(<code>company_profile.talent_profile</code>). 각 0~100 을 회사 가중치로 합산해
    <code>applications.doc_score</code> 를 내고, 내역과 근거는 <code>doc_score_detail</code> JSON 에 남긴다.
    <b>합산 점수 하나만 남기면 왜 떨어졌는지 답할 수 없기 때문이다.</b>
  </p>

  <div class="flow">
    <div class="flow__step flow__step--base">
      <span class="flow__k">서류 &mdash; 자동 이동</span>
      <p class="flow__v">
        공고별 임계(<code>pass_threshold</code>, 기본 60) 이상이면
        <code>applied &rarr; screening &rarr; interview</code>, 미만이면 <code>rejected</code>.
        <code>stage_history</code> 에 <code>changed_by=NULL</code>(시스템)과
        &ldquo;아르 서류 심사 N점 (기준 M점)&rdquo; 사유를 남긴다.
        <code>screening_mode='manual'</code> 인 공고는 점수만 매기고 옮기지 않는다 &mdash; 자동을 끄는 스위치다.
      </p>
    </div>
    <div class="flow__step">
      <span class="flow__k">면접 &mdash; 답변 대조</span>
      <p class="flow__v">
        면접 종료 시 백그라운드로 <b>답변 요건 대조</b>(전사 텍스트 &harr; 공고 요건 &middot; 우대 &middot; 인재상,
        0~100)를 채점해 <code>interview_sessions.ai_score</code> 에 넣는다.
        ADR-0034 의 설계는 여기에 진위 일관성을 30% 얹는 것이었으나,
        <b>표정 &middot; 음성 신호를 점수 재료로 쓰지 않는 쪽으로 정리</b>되면서 지금은 담당자 참고 지표로만
        화면에 뜬다(&sect;4). 면접관은 점수를 넣지 않고 코멘트만 남긴다.
      </p>
    </div>
    <div class="flow__step">
      <span class="flow__k">종합 &mdash; 사람이 확정</span>
      <p class="flow__v">
        <code>final_score = doc_score &times; 50 + interview_ai_score &times; 50</code>(회사별 조정 가능),
        등급 S(85↑) &middot; A(70↑) &middot; B(55↑) &middot; C.
        <b>최종 합격 &middot; 불합격은 사람이 카드를 옮긴다</b> &mdash; 아르는 면접 단계에서 멈춘다.
      </p>
    </div>
  </div>

  <p class="aim__sub">2-3. 면접 분석 파이프라인 &mdash; STT &rarr; 근거 대조 &rarr; Claude
    <span class="who who-b">우정 B</span></p>
  <p class="aim__p">
    Whisper 가 답변 음성을 전사하면, 해당 지원자의 이력서 &middot; 자소서 &middot; 직무 요건에서 관련 근거를
    찾아 컨텍스트로 결합하고, Claude 가 <b>그 근거를 인용하며</b> 답변이 서류와 일치하는지 대조한다.
    <b>근거 문서 없이 모델이 단독으로 판단하는 경로를 두지 않았다.</b>
    대조는 원문을 인용하므로 지원자가 반박할 수 있는 유일한 AI 판단 근거이기도 하다(&sect;4).
  </p>
  <p class="aim__p">
    실시간 분석 신호는 세어서 AI 가 수치로 요약해 종합 평가에 표시하되,
    <b>수치에 없는 숫자나 사람을 단정하는 단어가 나오면 그 문장을 버리고 고정 틀로 대체</b>한다 &mdash;
    요약이 재료에 없는 것을 말하기 시작하면 참고 지표가 아니라 판정이 되기 때문이다.
  </p>

  <p class="aim__sub">2-4. 프롬프트가 곧 원가다</p>
  <p class="aim__p">
    2026. 08. 31. API 예산이 하루 만에 소진됐다. 모델은 haiku 였고, 원인은 요약이 아니라 <b>채팅</b>이었다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead><tr><th>원인</th><th>조치</th></tr></thead>
    <tbody>
      <tr><td>고정부(시스템 프롬프트 9.2KB + 도구 정의 11개 10.7KB ≈ 5~7K 토큰)를
              <b>매 호출 정가로 재과금</b></td>
          <td>프롬프트 캐싱 (<code>cache_control</code>)</td></tr>
      <tr><td>담당자 이름이 프롬프트 6번째 줄 &rarr; <b>사람마다 캐시가 갈림</b></td>
          <td>담당자 절을 맨 뒤로 &mdash; 앞 99.3% 가 전원 공통이 된다</td></tr>
      <tr><td>대화 이력 상한 없음 &mdash; 프론트가 전 이력을 보내고 서버도 자르지 않았다</td>
          <td><code>MAX_HISTORY_MESSAGES=20</code></td></tr>
      <tr><td><code>search_applications</code> 기본 50건 &middot; 최대 200건이 도구 결과로 들어와
              <b>이후 모든 라운드에 재전송</b></td>
          <td>기본 10 &middot; 최대 50</td></tr>
    </tbody>
  </table>
  </div>

  <p class="aim__p">
    캐싱에는 함정이 하나 있다. <code>claude-haiku-4-5</code> 의 <b>최소 캐시 가능 프리픽스는 4,096 토큰</b>이고
    (opus-5 512 &middot; sonnet-5 1,024 로 세대순이 아니다), 미달하면 <b>에러 없이 조용히 캐시가 안 걸린다.</b>
    그래서 <code>cache_read_tokens</code> 로 적중을 먼저 확인했다.
    결과는 같은 4단계 시나리오에서 2026. 08. 28. <b>$0.045</b> &rarr; 09. 17. 재측정 <b>$0.036</b>,
    캐시 읽기 58,088 토큰이다. 실사용 평균은 아르 호출당 <b>$0.0075</b>.
    다만 <b>이 낙차를 캐싱 하나의 효과로 말하지 않는다</b> &mdash; 아래 규칙 라우터 몫이 섞여 있고,
    측정된 고정부는 14,522 토큰이라 4,096 미달 걱정 자체는 해당이 없었다.
  </p>
  <p class="aim__p">
    아예 LLM 을 태우지 않는 길도 냈다. &ldquo;안녕&rdquo; &ldquo;뭘 할 수 있어&rdquo; 같은 정적 발화가
    호출당 ~$0.02 씩 나가던 것을 <b>규칙 의도 라우터의 고정 응답</b>으로 돌렸다
    (<code>^&hellip;$</code> 로 묶어 실제 요청이 붙으면 LLM 으로 넘긴다).
    지원자 FAQ 도 인사 &middot; 연봉 &middot; 합격 가능성 &middot; 감사는 규칙 응답이고, 나머지만 회사 프로필을
    근거로 Claude 가 답한다. 실측 3건 대화 8.4K 토큰 $0.04 &rarr; <b>기본 질문 구간 $0</b>.
  </p>
  <p class="aim__p">
    로깅에서 교훈 하나가 남았다. 토큰 &middot; 비용을 코드에서 넘기고 있었는데
    <code>JSONFormatter</code> 가 다섯 필드만 화이트리스트로 골라 담아 <b>전부 버려지고 있었다</b> &mdash;
    호출이 있었다는 사실만 남고 숫자가 없었다. <b>로깅은 넣은 것만으로 가드가 되지 않고 출력까지 눈으로
    확인해야 가드다.</b> 화이트리스트를 걷어내자 이번엔 <code>search_applications</code> 의 검색어에
    지원자 이름 &middot; 이메일이 찍혀서, 값 대신 <b>인자 키 이름만</b> 남기도록 바꿨다.
  </p>

</div>

<div class="aim__sec">

  <h2><span class="aim__num">3.</span> 정확도 평가 및 개선</h2>
  <p class="aim__note">
    <b>같은 자를 먼저 만들고 그 다음에 고쳤다.</b> 프롬프트를 바꿀 때마다 몇 개 질문을 손으로 던져
    보는 것으로는 나아졌는지 나빠졌는지 알 수 없다. 이 절은 채점기 &rarr; 학습 &rarr; 프롬프트 &rarr;
    판정 알고리즘 순으로 <b>무엇을 어떻게 재서 무엇이 바뀌었는지</b>를 적는다.
  </p>

  <p class="aim__sub">3-1. 채점기 먼저 &mdash; eval 프레임워크 (ADR-0023)</p>
  <p class="aim__p">
    ADR-0023 이 설계한 자리는 <code>backend/eval/</code>(케이스 YAML &middot; <code>runner.py</code> &middot;
    <code>judge.py</code> &middot; <code>report.py</code>)였다. <b>실제로 선 것은 그 디렉터리가 아니라
    <code>ai/qwen-training/</code></b> 이다 &mdash; 자체학습과 같은 자리에서 자라야 했기 때문이다.
    케이스는 <code>dataset.test.jsonl</code> 23건, 실행은 <code>eval.py</code>(로컬 어댑터 &middot; GPU 필요)와
    <code>eval_anthropic.py</code>(Claude &middot; GPU 불필요) 둘이며, 그 둘이 <code>judge.py</code> 한 벌을 공유한다.
    <b>2026. 09. 12. 채점 규칙을 <code>eval.py</code> 에서 떼어낸 것이 이 절의 출발점</b>이다 &mdash;
    채점기가 두 벌이면 두 모델의 숫자를 나란히 놓을 수 없다.
    CI 에는 넣지 않았다 &mdash; LLM 호출 비용과 실행 시간 때문에 로컬 수동 실행으로 정했다.
  </p>
  <p class="aim__p">
    채점기 자체도 한 번 고쳤다(2026. 09. 14.). <code>pending_action</code> 판정이 정답 도구 집합에서
    재유도되던 것을 데이터의 라벨만 보게 바꾸고, 도구 이름 <b>완전 일치</b>를
    <b>부분집합 + 추가분이 전부 읽기 도구면 통과</b>로 완화했으며
    (&ldquo;먼저 찾고 실행&rdquo;을 오답 처리하던 것), 정답 데이터에 있던 존재하지 않는 도구
    <code>update_candidate_stage</code> 를 <code>change_stage</code> 로 고쳤다.
    통과 수는 그대로였고 <b>정답 상한이 19/23 &rarr; 20/23 으로 정확해졌다.</b>
  </p>
  <p class="aim__p">
    판정은 <b>규칙 기반을 우선</b>한다. 도구 이름 &middot; 인자 비교, 응답 키워드 포함 / 미포함,
    도구 결과에 없는 정보를 생성했는지(할루시네이션)는 전부 규칙으로 보고 <b>비용 0</b>이다.
    응답 품질만 LLM-as-judge(~$0.002/건)로 보조한다 &mdash;
    <b>LLM 판정 자체의 편향</b>을 리스크로 적어 두고 그렇게 나눴다.
    최종 비교에 쓴 판정 축은 다섯이다: 도구 이름 &middot; no-tool 위반 &middot; 확인 문구 &middot; 인자 &middot; 응답.
  </p>

  <p class="aim__sub">3-2. 손실은 떨어지는데 도구 호출은 전멸했다
    <span class="who who-e">수택 E</span></p>
  <p class="aim__p">
    Qwen3-8B QLoRA 학습에서 <code>eval_loss</code> 가 <b>0.339 &rarr; 0.074</b> 로 교과서처럼 떨어졌는데,
    도구 호출 정확도는 <b>6/23 (26.1%)</b> 였다. 대부분 <code>&lt;think&gt;</code> 안에서
    &ldquo;search_applications 를 불러야 한다&rdquo;고 <b>추론까지 하고 실제 호출을 내지 않았다.</b>
  </p>
  <p class="aim__p">
    원인은 데이터 구성이었다. 177개 샘플이 거의 같은 <b>7,347자 시스템 프롬프트</b>를 공유해
    3 epoch 동안 <b>프롬프트를 외우는 것으로 손실이 떨어졌고</b>, 정작 배워야 할
    <code>&lt;tool_call&gt;</code> 은 전체 토큰의 <b>1.8%</b> 라 기울기가 거의 닿지 않았다.
    손실이 낮다는 것은 무언가를 잘 배웠다는 뜻이지 <b>우리가 원한 것을 배웠다는 뜻이 아니었다.</b>
  </p>
  <p class="aim__p">
    손실이 프롬프트에 쏠리는 구조를 교정하고 같은 채점기로 v6 &middot; v7 &middot; v8 &middot; v9 를 반복 측정해
    v9 에서 <b>17/23 = 73.9%</b> 를 얻었다 <span class="tag tag--done">해결</span>.
    실패 6건 중 5건은 확인 문구 &middot; 안전한 다단계처럼 <b>UX 상 정상 동작</b>이라 실질은 ~95%+ 다 &mdash;
    다만 이 보정치는 채점기가 아니라 사람이 실패 내용을 읽고 분류한 값이다.
  </p>

  <p class="aim__sub">3-3. 프롬프트로 고친 것 셋</p>

  <div class="items">
    <div class="item">
      <p class="item__t">① 서류 점수가 전원 64~65점으로 수렴했다</p>
      <p class="item__d">
        온프레미스 요약 재생성에서 모든 지원자가 요건 70 &middot; 우대 40/50 &middot; 인재상 60 으로 나와
        <b>변별력이 사라졌다.</b> 소형 모델이 <code>chain_evaluate.v2</code> 프롬프트의
        <b>출력 예시 숫자 70/40/60 을 그대로 베낀 것</b>이었고, Claude 는 베끼지 않아 드러나지 않았다.
        v3 에서 예시 숫자를 지우고 채점 구간표(85~100 / 65~84 / &hellip;)와 절차를 명시하자
        실측이 <b>85 &middot; 85 &middot; 40 &middot; 15</b> 로 갈렸고 Claude 의 78 &middot; 86 &middot; 44 와 같은 방향을 가리켰다.
      </p>
    </div>
    <div class="item">
      <p class="item__t">② 요약 JSON 이 깨져 점수가 NULL 이 됐다</p>
      <p class="item__d">
        56명 재생성 중 2명이 서류 점수 NULL 이었다. 소형 모델이 문자열 안에
        <b>이스케이프 안 된 따옴표</b>를 써서 파싱에 실패했고 Ollama <code>format</code> 스키마도 막지 못했다.
        파서에 문자열 내부 따옴표 복구 폴백을 넣어 <b>56/56 파싱에 성공</b>했다 &mdash;
        정상 JSON 경로는 손대지 않았다.
      </p>
    </div>
    <div class="item">
      <p class="item__t">③ 무관한 질문에 답을 다 해 버렸다</p>
      <p class="item__d">
        거절 규칙이 &ldquo;정치 &middot; 연예 &middot; 주식&rdquo; 식 <b>카테고리 열거</b>라 인물 &middot; 상식 유형은
        모델이 확률적으로 판단했고, 인물 설명을 다 생성한 뒤 거절 문구를 덧붙였다 &mdash;
        토큰 낭비이자 무관한 답의 유출이다. 판단 기준을 <b>&ldquo;답의 근거가 우리 데이터냐&rdquo;</b> 로
        재작성해, 외부 일반 지식은 내용 없이 한 문장으로 거절하고
        이력서 &middot; 자소서 속 인물 &middot; 프로젝트는 원문을 조회해 정상 답변한다.
      </p>
    </div>
  </div>

  <p class="aim__sub">3-4. 판정 알고리즘도 실측으로 고쳤다</p>
  <p class="aim__p">
    fit-check 지원자 <b>24명</b>을 실측해 판정이 아슬한 세 케이스를 찾았다 &mdash;
    요건이 우수한데 문화 한 문구로 탈락 &middot; <b>1점 차이로 탈락</b> &middot;
    필수는 통과인데 우대 부족으로 탈락. 인수인계 문서에 적힌 &ldquo;자동 불합격 3명&rdquo;도
    실제로는 <b>8명</b>이었다. 8명 각각의 3축 점수를 근거로 수치화해 붙였다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--bench">
    <thead><tr><th>가중치 &middot; 규칙</th><th class="tbl__num">전</th><th class="tbl__num">후</th><th>이유</th></tr></thead>
    <tbody>
      <tr><td class="tbl__lead">필수 요건</td><td class="tbl__num">50</td><td class="tbl__num"><b>60</b></td>
          <td>직무를 할 수 있는가가 먼저다</td></tr>
      <tr><td class="tbl__lead">우대 사항</td><td class="tbl__num">20</td><td class="tbl__num"><b>10</b></td>
          <td>있으면 좋음 &mdash; 없다고 떨어뜨릴 축이 아니다</td></tr>
      <tr><td class="tbl__lead">인재상 (문화)</td><td class="tbl__num">30</td><td class="tbl__num">30</td>
          <td>유지</td></tr>
      <tr><td class="tbl__lead">문화 점수 하한</td><td class="tbl__num is-weak">없음</td>
          <td class="tbl__num"><b>50</b></td>
          <td>요건 점수가 70 이상이면 적용 &mdash; <b>요건 우수 지원자를 문화 한 문구로 떨어뜨리지 않는다</b></td></tr>
    </tbody>
  </table>
  </div>

  <p class="aim__sub">3-5. 아직 못 잰 것</p>
  <p class="aim__p">
    <b>안 된 것은 안 됐다고 적는다.</b>
  </p>
  <div class="items">
    <div class="item">
      <p class="item__t">채점기 편향과 23건 표본 <span class="tag tag--warn">미해소</span></p>
      <p class="item__d">
        &sect;1 의 해석 주의가 그대로 남는다. 케이스를 늘리거나 중립 gold 를 따로 만들지 못했다.
      </p>
    </div>
    <div class="item">
      <p class="item__t">요약 어댑터는 정성 평가만 했다 <span class="tag tag--warn">미해소</span></p>
      <p class="item__d">
        JSON 형식 &middot; 요지 &middot; 역량은 정확했으나 <b>경력 연수를 3년 &rarr; 5년으로 틀렸다.</b>
        도구 호출처럼 채점기로 수치화하지는 못했고, 이 오차가 클라우드 확정의 근거 하나가 됐다.
      </p>
    </div>
    <div class="item">
      <p class="item__t">임베딩 교체 미착수 <span class="tag tag--warn">미해소</span></p>
      <p class="item__d">
        BGE-M3 비교는 손대지 못했고 <code>ko-sroberta</code> 의 <code>max_seq_length=128</code> 제약은
        그대로다.
      </p>
    </div>
  </div>

</div>

<div class="aim__sec">

  <h2><span class="aim__num">4.</span> 편향성 검토</h2>
  <p class="aim__note">
    채용은 <b>틀렸을 때 지원자가 대가를 치르는</b> 도메인이다. 그래서 이 절의 결정은 대부분
    &ldquo;쓸 수 있는데 쓰지 않기로 한 것&rdquo;이다. <b>무엇을 점수에 넣지 않았는지</b>와
    <b>누가 되돌릴 수 있는지</b>를 적는다.
  </p>

  <p class="aim__sub">4-1. 표정 &middot; 음성은 점수에 넣지 않는다
    <span class="who who-d">소연 D</span></p>
  <p class="aim__p">
    결정이 두 번 뒤집혔다. ADR-0002 가 표정 분석을, ADR-0026 결정 2 가 음성 기반 감정 &middot; 기만 추론을
    잘랐다. 그런데 <code>ai/lie-detection/</code> 이 이미 main 에 들어가 있었고 AI 면접 설계가 그 기능을
    전제로 짜이고 있었다. <b>문서만 반대로 남으면 아무도 지키지 않는 규칙이 된다</b>고 보고
    ADR-0029 로 개정했다(2026. 09. 07.).
  </p>
  <p class="aim__p">
    ADR-0029 는 개정하면서 <b>닫지 못한 것을 숨기지 않고 미결로 남겼다.</b> 모델은
    Michigan Real-Life Trial <b>121 표본에 교차검증 76%</b> 였고, ADR-0026 이 지적한 것은
    정확도 자체가 아니라 <b>누가 불리해지는가</b> &mdash;
    불안장애 &middot; 말더듬 &middot; 비원어민 &middot; 자폐 지원자를 결함으로 점수화하게 된다는 것이었다.
    2026. 09. 15. ADR-0030 이 세 항목에 답했다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl--wide">
    <thead><tr><th>ADR-0029 의 미결</th><th>ADR-0030 의 답 (2026. 09. 15.)</th></tr></thead>
    <tbody>
      <tr><td class="tbl__lead">① 정확도와 공정성</td>
          <td><b>참고 지표로만 쓰고 합불 근거로 쓰지 않는다.</b> 담당자 화면에
              &ldquo;참고용 수치입니다. 단독 판단 근거로 쓰지 마세요&rdquo; 를 표시한다</td></tr>
      <tr><td class="tbl__lead">② 지원자의 반박 경로</td>
          <td><b>지원자에게 보여주지 않는다.</b> 지원자가 볼 수 있는 AI 판단 근거는
              서류&harr;발언 대조 하나로 유지한다 &mdash; 원문을 인용하므로 반박할 수 있다</td></tr>
      <tr><td class="tbl__lead">③ 법 &middot; 제도</td>
          <td>EU AI Act(직장 감정 인식 금지) &middot; 미국 고용 목적 거짓말 탐지 금지법은
              <b>국내 한정 서비스라 범위 밖.</b> 국내 개인정보보호법의 자동화 결정 조항은
              AI 가 단독으로 합불을 결정할 때 적용되며, <b>최종 결정은 사람이 하므로 해당하지 않는다</b></td></tr>
    </tbody>
  </table>
  </div>

  <p class="aim__p">
    그래서 지금 운영은 이렇다 &mdash; 표정(ViT + MediaPipe) &middot; 음성 신호는 담당자 화면에
    <b>참고 지표로만 뜨고 점수 &middot; 합불 판정에 들어가지 않는다.</b>
    그 판단의 근거 하나를 ADR-0032 가 숫자로 남겼다. 법정 영상에 ViT 를 돌리면
    <b>거짓 영상이 happy 55% &middot; happy 64%</b> 로, <b>진실 영상이 fear 71%</b> 로 나온다.
    표정만으로는 갈리지 않는다. 그래서 ViT 출력은 판정이 아니라 특징 벡터의 일부이고,
    <b>발표에서 &ldquo;ViT 로 거짓말을 잡는다&rdquo;고 말하지 않기로</b> 문서에 못 박았다 &mdash;
    위 표가 그 문장을 반증하기 때문이다.
  </p>

  <p class="aim__sub">4-2. 진행 보조는 이유를 추론하지 않는다 &mdash; 테스트로 봉인했다</p>
  <p class="aim__p">
    답변 길이 &middot; 발화 속도를 보고 되묻거나 쉬어가기를 권하는 진행 보조
    (<code>backend/app/interview/pacing.py</code>)는 진위 분석 호출과 <b>같은 날 들어갔지만 성격이 다르다.</b>
    보는 것은 답변 길이 &middot; 발화 속도뿐이고, 내는 것은 다음에 할 행동 한 문장이며,
    <b>저장하지 않고 점수도 없다.</b>
  </p>
  <p class="aim__p">
    &ldquo;말이 느렸다&rdquo;까지만 말하고 이유를 추론하지 않게 하려고,
    메시지에 <b>&ldquo;긴장 &middot; 불안 &middot; 거짓 &middot; 의심 &middot; 점수&rdquo; 다섯 낱말 중 하나라도 들어가면
    테스트가 깨지도록</b> 해 뒀다
    (<code>backend/tests/test_interview_pacing.py</code>). 섞는 순간
    <b>&ldquo;점수에 안 들어간다&rdquo;는 약속이 어디까지 유효한지 아무도 모르게 되기 때문</b>이다.
    표정 라벨 하나도 같은 이유로 바꿨다 &mdash; 면접 맥락에 맞지 않는 <code>disgust</code> 라벨을
    「긴장」으로 교체하고 문서에 반영했다.
  </p>

  <p class="aim__sub">4-3. 최종 합불은 사람이 확정한다</p>
  <p class="aim__p">
    ADR-0003 이 &ldquo;AI 는 추천까지, 확정은 사람&rdquo;을 정했고, ADR-0034 가 그 범위를
    <b>최종 합격 &middot; 불합격 한 곳</b>으로 좁혔다. 서류 &middot; 면접 단계 이동은 아르가 점수로 판정하고,
    사람은 되돌린다. 좁아진 만큼 되돌릴 장치를 남겼다.
  </p>

  <div class="items">
    <div class="item">
      <p class="item__t">수동이 항상 이긴다</p>
      <p class="item__d">
        사람이 단계를 한 번 바꾸면 <code>decision_source='human'</code> 이 되고
        <b>그 지원자는 이후 자동 판정에서 빠진다.</b> 자동이 사람의 판단을 덮어쓰지 않는다.
      </p>
    </div>
    <div class="item">
      <p class="item__t">불합격 메일은 즉시 나가지 않는다</p>
      <p class="item__d">
        공고 마감 뒤 담당자가 일괄 발송한다. <b>오판했을 때 메일은 되돌릴 수 없어서</b>
        마감 전까지 번복 여지를 남겼다. 합격(면접) 안내는 일정 제안 메일이 대신한다.
      </p>
    </div>
    <div class="item">
      <p class="item__t">쓰기 작업은 확인 카드로만 실행된다</p>
      <p class="item__d">
        에이전트는 초안(<code>pending_action</code>)까지 만들고 사람이 누른다.
        23건 비교에서 <b>임의 실행 &middot; 지어낸 도구 같은 위험한 실패가 세 모델 모두 0건</b>이었던 것도
        이 구조 덕이다.
      </p>
    </div>
    <div class="item">
      <p class="item__t">인적성 설문은 점수에 넣지 않는다 (ADR-0027)</p>
      <p class="item__d">
        카테고리 통계는 코드가 계산하고 아르는 응답을 <b>관찰 문장으로 재서술만</b> 한다.
        성격 유형 판정 &middot; 점수화 &middot; 합불 의견을 만들지 않으며 <b>미응답 불이익도 없다.</b>
      </p>
    </div>
  </div>

  <p class="aim__sub">4-4. 자동 판정이 만든 불공정을 되돌린 사례</p>

  <div class="items">
    <div class="item">
      <p class="item__t">① AI 추정값이 지원자 신고값처럼 보였다</p>
      <p class="item__d">
        폼에 경력을 적지 않으면 AI 가 이력서에서 연차를 추출해 채우는데,
        <b>표식이 없어 신고값과 구별되지 않았다.</b>
        <code>career_years_source="ai"</code> 표식을 붙이고 프론트에 「AI 추정」 배지를 띄웠다.
        재생성 시 표식이 사라지는 문제는 후속으로 남아 있다.
      </p>
    </div>
    <div class="item">
      <p class="item__t">② 요건 우수자를 문화 한 문구로 떨어뜨렸다</p>
      <p class="item__d">
        가중치를 요건 60 &middot; 우대 10 &middot; 문화 30 으로 조정하고
        요건 ≥ 70 이면 문화 하한 50 규칙을 넣었다(&sect;3-4).
        <b>hold 상태는 도입하지 않고 자동 판정을 유지</b>했다 &mdash; 되돌리는 쪽을 사람에게 맡겼다.
      </p>
    </div>
    <div class="item">
      <p class="item__t">③ 자료가 없는 지원자를 채점하려 했다</p>
      <p class="item__d">
        자소서 1줄 &middot; 전부 미기재면 분석할 것이 없다. 요약 결과 <code>insufficient=true</code> 면
        <code>applied &rarr; screening &rarr; rejected</code> 로 옮겨 <b>「서류 탈락」 라벨</b>이 붙게 했다 &mdash;
        <code>applied &rarr; rejected</code> 직행이면 사유 불명의 「불합격」으로 보였다.
        실제 역량이 있는 지원자(<code>insufficient=false</code>)는 건드리지 않아 <b>대량 탈락을 막았다.</b>
      </p>
    </div>
  </div>

  <p class="aim__sub">4-5. 개인정보 &mdash; 모델에 넣지 않는 것, 남기지 않는 것</p>
  <p class="aim__p">
    프롬프트에 <b>연락처 &middot; 주민번호를 넣지 않는다.</b> 로그에는 검색어 값 대신
    인자 키 이름만 남긴다(&sect;2-4) &mdash; <code>search_applications</code> 의 검색어에 지원자
    이름 &middot; 이메일이 들어오기 때문이다. <b>면접 영상은 저장하지 않는다</b>;
    실시간으로 보고 흘려보내며 저장하는 것은 답변 음성 &middot; 전사 &middot; 대조 결과다.
    표정 &middot; 음성 진위는 <b>프레임과 개별 판정을 저장하지 않는다.</b>
  </p>
  <p class="aim__p">
    자체학습 노선을 끝까지 밀어 본 이유도 여기에 있었다 &mdash;
    <b>&ldquo;public API 없이도 갈 수 있는가&rdquo;에 실측으로 답하기 위해서였다.</b>
    답은 &ldquo;정확도는 동급까지 오지만 형식 안정성과 지연에서 갈린다&rdquo;였고(&sect;1-4),
    그래서 서빙은 클라우드로 두되 개인정보는 <b>모델을 바꾸는 것이 아니라 넣는 것을 줄이는 방식</b>으로
    지킨다.
  </p>

</div>

<a class="aim__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
