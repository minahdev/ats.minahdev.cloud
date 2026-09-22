---
layout: default
title: 결론 및 향후 과제
permalink: /conclusion/
---

<style>
.ccl { max-width: 62rem; margin: 2.5rem auto 4rem; }

.ccl__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 1.6rem; }
.ccl__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.ccl__crumb a { color: #9ca3af; }
.ccl__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; word-break: keep-all; }
.ccl__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

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

/* 성과 수치 타일 */
.ccl__stat {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(8.5rem, 1fr));
  gap: .6rem;
  margin-bottom: 1.6rem;
}
.stat { border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .85rem; }
.stat__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.stat__v { font-size: 1.05rem; font-weight: 700; color: #111827; word-break: keep-all; }
.stat__v small { font-size: .78rem; font-weight: 400; color: #9ca3af; margin-left: .15rem; }

.ccl__sec { margin-bottom: 3.25rem; }
.ccl__sec > h2 {
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
.ccl__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.ccl__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }
.ccl__p { margin: 0 0 1rem; color: #374151; font-size: .92rem; line-height: 1.8; word-break: keep-all; }
.ccl__p:last-child { margin-bottom: 0; }
.ccl__p code, .ccl__note code { font-size: .84rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

.ccl__sub {
  margin: 2rem 0 .8rem;
  font-size: .86rem;
  font-weight: 700;
  color: #111827;
  letter-spacing: .01em;
  word-break: keep-all;
}

/* 표 공통 — schedule.md 패턴 */
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
.metric { min-width: 44rem; }
.metric td:first-child { white-space: nowrap; font-weight: 600; color: #111827; }
.next { min-width: 46rem; }
.next td:first-child { white-space: nowrap; }

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
.tag--part { background: #fef3c7; color: #92400e; }
.tag--plan { background: #f3f4f6; color: #6b7280; }
.tag--drop { background: #fee2e2; color: #991b1b; }

/* 한계점 카드 */
.lim { display: grid; gap: .7rem; }
.lim__item { border: 1px solid #e5e7eb; border-left: 3px solid #dc2626; border-radius: 6px; padding: .9rem 1.1rem; }
.lim__item--soft { border-left-color: #d97706; }
.lim__item--info { border-left-color: #9ca3af; }
.lim__t { margin: 0 0 .4rem; font-size: .93rem; font-weight: 700; color: #111827; word-break: keep-all; }
.lim__d { margin: 0 0 .6rem; font-size: .87rem; line-height: 1.8; color: #4b5563; word-break: keep-all; }
.lim__d:last-child { margin-bottom: 0; }
.lim__d code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

.ccl__close {
  border: 1px solid #e5e7eb;
  border-radius: 6px;
  background: #f9fafb;
  padding: 1rem 1.15rem;
  margin-top: 1.4rem;
}
.ccl__close p { margin: 0; font-size: .89rem; line-height: 1.8; color: #374151; word-break: keep-all; }

.ccl__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }

@media (max-width: 34rem) {
  .ccl__stat { grid-template-columns: repeat(2, 1fr); }
}
</style>

<div class="ccl">

<div class="ccl__head">
  <p class="ccl__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 11. 결론 및 향후 과제</p>
  <h1>결론 및 향후 과제</h1>
  <p>필수 27기능을 채우고 확장까지 배포했으나 온프레미스는 접었다 &mdash; 수치로 남긴 성과와 접은 이유
     &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="ccl__sec">

  <h2><span class="ccl__num">1.</span> 개발 성과</h2>
  <p class="ccl__note">
    2026. 08. 20. 착수, 09. 20. <b>해커톤 제출 프리즈로 코드를 동결</b>했다. 전체 69일 중 32일 시점이고,
    남은 구간은 심사(09. 20.~10. 17.)와 종료 인계(10. 27.)다. 아래 수치는 09. 22. 기준이며
    저장소 <code>Seuk-Team/Arda</code>(커밋 <code>8071fd9</code>)와 실배포본에서 확인한 값이다.
  </p>

  <div class="ccl__stat">
    <div class="stat"><span class="stat__k">기획 필수 기능</span>
      <span class="stat__v">27/27<small>09. 03. 달성 후 유지</small></span></div>
    <div class="stat"><span class="stat__k">API 라우트</span>
      <span class="stat__v">107<small>Swagger</small></span></div>
    <div class="stat"><span class="stat__k">DB 테이블</span>
      <span class="stat__v">28<small>ERD v2.8</small></span></div>
    <div class="stat"><span class="stat__k">백엔드 테스트</span>
      <span class="stat__v">1,165<small>건 통과</small></span></div>
    <div class="stat"><span class="stat__k">결정 기록</span>
      <span class="stat__v">36<small>ADR</small></span></div>
    <div class="stat"><span class="stat__k">커밋</span>
      <span class="stat__v">1,095<small>누적</small></span></div>
  </div>

  <p class="ccl__note" style="margin:-1.1rem 0 1.4rem;">
    타일 밖의 규모 지표 &mdash; 웹 화면 25 &middot; 앱 화면 23 &middot; alembic 리비전 26 &middot;
    AI 프롬프트 18 &middot; 앱 위젯 테스트 30파일.
  </p>

  <p class="ccl__p">
    <b>기획 필수 27기능은 09. 03.에 27/27을 채우고 그대로 유지했다.</b> 그 뒤의 개발은 기획서 밖으로 나간
    것을 전부 ADR로 정식 편입해 배포까지 끝낸 구간이다 &mdash; 도구 호출 에이전트 아르(도구 12종),
    요약&rarr;평가&rarr;추천 3단 체인과 자동 서류 심사(ADR-0034), RAG 시맨틱 검색(ADR-0021),
    면접 일정 자동화와 FAQ 챗봇, AI 면접(1:1 WebRTC &middot; STT &middot; 참고 지표, ADR-0029 &middot; 0032 &middot; 0038),
    인적성 설문(ADR-0027), 지원자 로그인(ADR-0033), 제출물 무결성 원장과 Sepolia 앵커(ADR-0028),
    헥사고날 재편(ADR-0035), 심사위원 데모 계정. 기획서에 없던 기능을 그냥 붙이는 대신
    <b>붙일 때마다 결정 문서를 먼저 쓰는 방식</b>이었고, 그 결과가 ADR 36편이다.
  </p>

  <p class="ccl__p">
    <b>4인 병렬 개발을 지탱한 것은 계약 문서였다.</b> ERD(<code>01-erd.md</code>)와 API 문서(<code>02-api.md</code>)를
    코드와 같은 커밋에서 갱신하는 규칙을 세우고, 09. 17.에는 모델&harr;alembic 이행 결과를 CI가 비교하게 해
    (표 목록과 이름 붙은 CHECK 제약 &middot; 인덱스 이름까지) 모델과 스키마가 갈라지는 경로 자체를 막았다.
    배포본 OpenAPI를 main과 대조한 08. 31. 실측은
    <b>경로 35/35 &middot; 스키마 62/62 일치 &middot; 필드 불일치 0</b>이었고,
    <code>02-api.md</code> 계약과 배포본을 무인증 GET으로 대조하는 스크립트도 따로 세웠다(PR #122).
    프론트와 앱이 목데이터 필드명을 ERD와 같게 맞춰 둔 덕에 연동이 필드 교체로 끝난 것도 같은 규칙에서 나왔다.
  </p>

  <p class="ccl__p">
    <b>성능과 원가는 전부 실측으로 남겼다.</b> 감으로 "빨라졌다"고 쓰지 않는 것이 이 프로젝트의 규칙이었다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl metric">
    <thead>
      <tr>
        <th>항목</th>
        <th>전</th>
        <th>후</th>
        <th>조치</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>지원자 검색 (더미 10만 건)</td>
        <td class="tbl__num">111ms</td>
        <td class="tbl__num">7.8ms</td>
        <td>인덱스 튜닝 &middot; 커서 페이지네이션</td>
      </tr>
      <tr>
        <td>STT 컨테이너 메모리</td>
        <td class="tbl__num">3.0~3.8GB</td>
        <td class="tbl__num">223MB</td>
        <td>faster-whisper <code>default</code>(CPU float32) &rarr; <code>int8</code> 명시 &middot; 속도 2.3배</td>
      </tr>
      <tr>
        <td>실시간 전사 지연 (GPU 이관)</td>
        <td class="tbl__num">7.5초</td>
        <td class="tbl__num">~1초</td>
        <td>T4 실측 STT 275ms/3초 &middot; ViT 75ms/crop &middot; 8명 동시에도 대기줄 0</td>
      </tr>
      <tr>
        <td>아르 도구 호출 정확도 (동일 채점기 23건)</td>
        <td class="tbl__num">26.1%</td>
        <td class="tbl__num">73.9%</td>
        <td>Qwen3-8B QLoRA v9 &mdash; 손실이 공통 프롬프트에 쏠리던 구조 교정</td>
      </tr>
      <tr>
        <td>정적 발화 1건당 AI 원가</td>
        <td class="tbl__num">~$0.02</td>
        <td class="tbl__num">$0</td>
        <td>규칙 의도 라우터 캔드 응답 &mdash; 실사용 평균은 호출당 $0.0075</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="ccl__p" style="margin-top:1.2rem;">
    <b>사고마다 규칙 하나가 남았다.</b> 깨진 main을 하루 두 번 우연히 발견한 뒤 CI를 넣었고(현재 5잡 &mdash;
    ruff F &middot; pytest &middot; 프론트 빌드 &middot; AI 서버 &middot; Flutter), pytest가 24분간 조용히 멈춘 뒤
    <code>pytest-timeout</code> 60초로 침묵을 실패로 바꿨으며, 미정의 이름 2건이 프로덕션 500을 낸 뒤
    <code>ruff --select F</code>를 CI에 올렸다. n8n이 웹훅만 받고 죽어 메일이 <code>queued</code>로 남은 사고는
    API가 5분마다 SMTP로 재발송(최대 3회)하는 장치가 됐다. 09. 02. 팀장 이탈로 AWS &middot; GitHub &middot; 도메인 &middot;
    API 키가 전부 한 사람 개인 명의였던 것이 드러났을 때도 <b>ADR-0025로 권한을 사람이 아니라 역할에 붙여</b>
    새 계정으로 이전하고 시크릿을 전부 재발급했다 &mdash; 서비스는 멈추지 않았다.
  </p>

  <p class="ccl__p">
    <b>모델 전략을 감이 아니라 같은 자로 결정한 것이 이 프로젝트의 대표 성과다.</b> 자체 채점기
    <code>judge.py</code>와 동일 케이스 23건으로 Qwen 학습 전 26.1% &rarr; Claude Haiku 4.5 69.6% &rarr;
    Qwen v9 73.9%를 측정하고, pass/fail 너머로 판정 항목별 &middot; 질문 유형별 &middot; 실패의 질 &middot;
    요약 어댑터 정성 품질까지 분해했다. 세 모델 모두 <b>위험한 실패(임의 실행 &middot; 지어낸 도구)는 0건</b>이었다.
    그 결과를 근거로 09. 18. 심사 서빙을 클라우드 + Claude로 확정했다.
  </p>

</div>

<div class="ccl__sec">

  <h2><span class="ccl__num">2.</span> 한계점</h2>
  <p class="ccl__note">
    안 된 것은 안 됐다고 쓴다. 아래는 프리즈(09. 20.) 시점에 <b>해결되지 않은 채로 남긴 것</b>과,
    해결했다고 말하면 과장이 되는 것들이다.
  </p>

  <div class="lim">

    <div class="lim__item">
      <p class="lim__t">온프레미스 sLLM 은 구축까지 갔지만 심사 직전에 접었다 &mdash; 애초 목표를 달성하지 못했다</p>
      <p class="lim__d">
        애초 목표는 <b>지원자 개인정보가 외부 API로 나가지 않는 '데이터 반출 없는 채용 에이전트'</b>였다.
        09. 16.~18. 학원 PC 3대에 Cloudflare Tunnel &middot; Ollama 어댑터 3갈래 &middot; MinIO 로 실제 온프레미스를
        구축해 운영까지 했으나, 09. 18. 폐쇄하고 심사 서빙을 AWS + Claude 로 되돌렸다. 결정타는 넷이다.
      </p>
      <p class="lim__d">
        <b>① 다단계 도구 흐름을 못 지켰다.</b> 아르 채팅 이력서 접수에서 <code>list_postings</code>로 공고 id를
        확인하지 않고 <code>create_application</code>을 한 번에 호출하며 <code>posting_id</code>를 추측했다
        (<code>rounds=1</code>). 안내 문구를 줘도 반복했다.
        <b>② 프롬프트 예시 숫자를 그대로 베꼈다.</b> <code>chain_evaluate.v2</code>의 출력 예시 70/40/60을
        소형 모델이 복사해 <b>전 지원자가 요건 70 &middot; 우대 40~50 &middot; 인재상 60, 총점 64~65점으로 수렴</b>해
        변별력을 잃었다. 예시 숫자를 지우고 채점 구간표를 명시한 v3로 85 &middot; 85 &middot; 40 &middot; 15 까지 갈렸지만,
        <b>같은 프롬프트에서 Claude는 애초에 베끼지 않았다</b> &mdash; 프롬프트가 아니라 모델 쪽 문제였다는 뜻이다.
        <b>③ JSON 이 깨졌다.</b> 56명 재생성 중 2명이 문자열 안 이스케이프 안 된 따옴표로 파싱에 실패해
        서류점수가 NULL 이 됐다. Ollama <code>format</code> 스키마도 못 막아 파서에 복구 폴백을 붙여야 했다.
        <b>④ 지연과 동시성.</b> 콜드 스타트 78초, 동시 접속 8명에서 STT 대기가 15초 &rarr; 42초로 밀렸다.
      </p>
      <p class="lim__d">
        네 오류 모두 <b>"AWS 에선 안 나던" 것</b>이었고 심사 직전에 누적됐다. 코드 &middot; 어댑터 &middot; GPU 이미지는
        R&amp;D 자산으로 보존했지만, <b>개인정보 반출 없는 완결 구성은 이번 기간에 서비스로 세우지 못했다.</b>
      </p>
    </div>

    <div class="lim__item">
      <p class="lim__t">모델 비교의 표본은 23건이다 &mdash; 통계적으로 유의하다고 말할 수 없다</p>
      <p class="lim__d">
        26.1% &rarr; 69.6% &rarr; 73.9% 라는 수치는 <b>동일 케이스 23건</b> 위에서 나왔다. 23건에서 한 건이
        뒤집히면 4.3%p가 움직인다 &mdash; Claude 69.6%와 Qwen v9 73.9%의 차이(4.3%p = 정확히 1건)는
        표본 안에서 구별되지 않는다. 보고서에 <b>"v9 가 Claude 보다 낫다"가 아니라 "동급"</b>이라고 적은 것은
        그것이 이 표본 크기에서 정직한 표현이기 때문이다.
      </p>
      <p class="lim__d">
        <b>채점기 자체에도 편향이 있다.</b> <code>judge.py</code>의 정답(gold)이 Qwen 학습 데이터 기준으로
        만들어져 있어, 절대 점수가 아니라 <b>같은 자로 잰 상대 궤적만 유효</b>하다. 실제로 Claude 의
        쓰기(write) 유형 0/5 는 모델 실패가 아니라 <b>단일턴으로 채점한 하네스의 한계</b>였다 &mdash;
        확인 카드를 거치는 정상 동작이 단일턴에서는 미완성으로 집계된다. 같은 이유로 v9 의 fail 6건 중
        5건도 UX 상 정상 동작이었다. 이 주의사항은 보고서에 명시했지만, <b>편향 없는 제3의 채점기로
        다시 재는 일은 하지 못했다.</b>
      </p>
    </div>

    <div class="lim__item lim__item--soft">
      <p class="lim__t">표정 &middot; 음성 지표는 화면에만 있고 점수에는 들어가지 못했다 &mdash; 성능이 아니라 공정성 판단이다</p>
      <p class="lim__d">
        ViT + MediaPipe 표정 분석과 음성 신호는 구현해 배포했고 담당자 화면에 수치로 표시되지만,
        <b>점수 재료나 합불 판정 입력으로는 쓰지 않는다</b>(ADR-0029 &middot; 0032). 이것은 모델이 부정확해서가
        아니라 ADR-0002 의 원 근거를 뒤집지 못했기 때문이다 &mdash; <b>표정 신호의 직무성과 예측 기여가
        0.25% 미만</b>이고, 차별 위험이 있으며, HireVue 가 2021년에 같은 기능을 폐기한 선례가 있다.
        ADR-0029 로 도입을 개정하면서도 원 근거는 문서에서 지우지 않고 그대로 남겼다.
      </p>
      <p class="lim__d">
        결과적으로 <b>"AI 면접 분석"이라는 이름에 비해 실제 판정에 쓰이는 신호는 STT 전사 텍스트와
        서류 대조뿐</b>이다. 면접 영상 거짓말 탐지도 판정이 아니라 담당자 참고용 보조 지표다.
        기능은 있으나 의사결정에 닿지 않는 층이 하나 있다는 뜻이고, 이를 성과로 포장하지 않았다.
      </p>
    </div>

    <div class="lim__item lim__item--soft">
      <p class="lim__t">서류 자동 판정은 가상 데이터 24명으로만 검증했다</p>
      <p class="lim__d">
        가중치 개정(요건 50&rarr;60 &middot; 우대 20&rarr;10 &middot; 문화 30 유지, 요건 &ge;70 이면 문화 하한 50)은
        fit-check 지원자 <b>24명 실측</b>을 근거로 했지만, 이 24명은 시연 &middot; 리허설용으로 만든
        <b>전부 가상 데이터</b>다. 실제 채용 데이터로는 한 번도 재지 않았다. 표본 안에서도
        <b>인수인계 문서의 "자동 불합격 3명"이 실제로는 8명</b>이었던 오류가 뒤늦게 드러났다 &mdash;
        판정 결과를 사람이 세어 본 것 자체가 그때가 처음이었다.
      </p>
      <p class="lim__d">
        경계 케이스를 사람이 다시 보게 하는 <code>hold</code> 상태는 <b>도입하지 않고 자동 판정을 유지</b>하기로
        했다(팀장 결정). 1점 차이로 갈리는 케이스가 실측에서 나왔는데도 그렇게 둔 것이라, 임계
        근처의 판정 품질은 검증되지 않은 채 남아 있다. 안전장치는 사후적인 것 셋뿐이다 &mdash;
        단계 역행 항상 허용 &middot; 자동 탈락 메일은 마감 뒤 일괄 발행(번복 여지) &middot; 사람이 한 번 손대면
        이후 자동 판정에서 제외.
      </p>
    </div>

    <div class="lim__item lim__item--info">
      <p class="lim__t">프리즈 시점에 고치지 못한 결함 둘을 그대로 남겼다</p>
      <p class="lim__d">
        <b>면접관 자동 배정이 0명으로 떨어지는 결함</b>과 <b>받아쓰기 정확도가 실제 음성에서 흔들리는 것</b>
        &mdash; 둘 다 '부분'으로 표시해 남겼다. 재현 클라이언트로 실험실 조건(한국어 TTS 4종, 직결 &middot;
        터널 경유)에서는 12/12 정확 전사가 나왔지만, 실제 사람 음성에서의 흔들림은 별개 문제로 남는다.
        테스트를 통과시키려고 우회하거나 주석 처리하지 않는 것이 팀 규칙이었고, 같은 규칙으로
        <b>못 고친 것을 고쳤다고 적지 않았다.</b>
      </p>
    </div>

    <div class="lim__item lim__item--info">
      <p class="lim__t">구조적 제약 &mdash; 워커 1개 &middot; 1:1 면접 &middot; 문서 포맷</p>
      <p class="lim__d">
        실시간 면접의 <b>방 상태가 프로세스 메모리에 있어 API 워커를 1개로 묶어 두었다</b> &mdash; 수평 확장이
        불가능한 상태다. 지원자 로그인 실패 잠금 카운터도 파이썬 딕셔너리라 같은 전제에 묶여 있고,
        워커를 늘리려면 둘 다 Redis 로 옮겨야 한다(ADR-0033). 화상 면접은 <b>1:1 P2P 만</b> 도입했고(둘이면 SFU 가 필요 없다), 3인 이상 집단
        면접은 시연 뒤 ADR 로 미뤘다. 이력서는 PDF &middot; DOCX &middot; HWPX 만 처리하고 <b>구형 HWP 는 미지원</b>이며,
        이미지 이력서는 받지 않는다. 기획서의 권장 &middot; 여유 기능은 09. 03. 기준 <b>22/30 &middot; 0/23</b> 이었고,
        이후의 개발은 그 목록이 아니라 ADR 편입 범위로 진행했다 &mdash; 권장 &middot; 여유 목록 자체를
        다시 채우지는 않았다.
      </p>
    </div>

    <div class="lim__item lim__item--info">
      <p class="lim__t">09. 18. 멘토 피드백 4건 중 반영을 끝낸 것은 1건이다</p>
      <p class="lim__d">
        정량 비교 기준을 세우라는 피드백(진수택)은 Qwen vs Claude 정량 &middot; 품질 보고서로 09. 22. 반영을
        마쳤지만, 나머지 3건 &mdash; 모델 학습 방법 공부(박소연), 문제 해결 과정 파고들기(이우정),
        사용 중인 프레임워크의 개념 학습(김민아) &mdash; 은 <b>각자 진행 중</b>이다. 개인 학습 성격이라
        코드로 닫히지 않는 항목이고, 프리즈 이후에도 남아 있다.
      </p>
    </div>

  </div>

</div>

<div class="ccl__sec">

  <h2><span class="ccl__num">3.</span> 향후 개선 방향</h2>
  <p class="ccl__note">
    프리즈(09. 20.) 이후 남은 일은 <b>심사 대응</b>과 <b>종료 인계</b>(10. 27.)다. 아래 목록은 희망 사항이
    아니라 위 한계점에서 그대로 이어지는 것들이고, 각 항목에 담당 도메인이 붙어 있다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl next">
    <thead>
      <tr>
        <th>상태</th>
        <th>무엇</th>
        <th>왜</th>
        <th>담당</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><span class="tag tag--part">부분</span></td>
        <td>면접관 자동 배정이 0명으로 떨어지는 결함</td>
        <td>member 의 평가 작성은 배정된 건만이라, 배정이 비면 평가를 쓸 사람이 없다.
            풀이 비거나 가용 시간이 없으면 <code>needs_manual_assignment</code> 로 남아 admin 이 수동 배정해야 한다(ADR-0013 &middot; 0034)</td>
        <td><span class="who who-b">우정 B</span> 백엔드</td>
      </tr>
      <tr>
        <td><span class="tag tag--part">부분</span></td>
        <td>받아쓰기 정확도 &mdash; 실제 음성에서 흔들림</td>
        <td>재현 클라이언트로는 12/12 였으나 실제 발화에서 달랐다. 전사 텍스트가 판정 입력이라 정확도가 곧 판정 품질이다</td>
        <td><span class="who who-b">우정 B</span> 백엔드 &middot;
            <span class="who who-e">수택 E</span> 인프라</td>
      </tr>
      <tr>
        <td><span class="tag tag--plan">계획</span></td>
        <td>방 상태를 Redis 로 이관 &mdash; API 워커 1개 제약 해제</td>
        <td>메모리에 방 상태가 있어 워커를 못 늘린다. 동시 면접이 늘면 가장 먼저 막히는 곳</td>
        <td><span class="who who-b">우정 B</span> 백엔드</td>
      </tr>
      <tr>
        <td><span class="tag tag--plan">계획</span></td>
        <td>집단 면접(지원자 여러 명 + 면접관 1명) ADR</td>
        <td>3인 이상은 SFU 견적 4주라 1:1 만 넣었다. 시연 결과를 보고 결정 문서부터 쓴다</td>
        <td><span class="who who-b">우정 B</span> 백엔드</td>
      </tr>
      <tr>
        <td><span class="tag tag--plan">계획</span></td>
        <td>ADR-0011(에이전트 모델)을 코드 실제값(haiku)에 맞춰 개정</td>
        <td>결정 문서와 코드가 어긋난 채로 남아 있다 &mdash; 계약 우선 원칙의 예외를 방치하지 않는다</td>
        <td><span class="who who-d">소연 D</span> 에이전트</td>
      </tr>
      <tr>
        <td><span class="tag tag--plan">계획</span></td>
        <td>DB 권한 분리 적용 &mdash; 앱 전용 롤</td>
        <td>매 배포 권한 스크립트 &middot; 이행 관리자 연결 &middot; 절차서까지 준비는 끝났고 적용만 남았다</td>
        <td><span class="who who-e">수택 E</span> 인프라 &middot;
            <span class="who who-b">우정 B</span> 백엔드</td>
      </tr>
      <tr>
        <td><span class="tag tag--plan">계획</span></td>
        <td><code>career_years_source</code> 표식이 재생성 시 사라지는 문제</td>
        <td>AI 추정값이 지원자 신고값처럼 보이면 공정성 문제다. 표식을 붙인 것이 PR #311 후속으로 남았다</td>
        <td><span class="who who-d">소연 D</span> 에이전트</td>
      </tr>
      <tr>
        <td><span class="tag tag--plan">계획</span></td>
        <td>AWS 잔여 리소스 폐기 &middot; 종료 인계 (10. 27.)</td>
        <td>계정이 살아 있는 한 비용이 계속 난다. 인계 문서까지가 종료 조건</td>
        <td><span class="who who-e">수택 E</span> 인프라</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="ccl__sub">한계점에서 이어지는 과제 &mdash; 수치로 닫아야 할 것</p>

  <p class="ccl__p">
    <b>표본을 늘리고 채점기를 바꿔야 한다.</b> 23건 &middot; Qwen gold 기준이라는 두 제약을 그대로 둔 채로는
    모델 비교 결론을 확장할 수 없다. 케이스를 늘리는 것과, <b>단일턴 채점을 멀티턴으로 바꿔
    확인 카드를 거치는 정상 동작이 fail 로 집계되지 않게 하는 것</b>이 같은 무게로 필요하다.
    지금 하네스로는 Claude write 0/5 같은 값이 계속 나온다.
  </p>

  <p class="ccl__p">
    <b>서류 자동 판정은 가상 24명 밖으로 나가야 한다.</b> 임계(기본 60) 근처에서 1점 차이로 갈리는 케이스가
    실측에서 나왔으므로, 표본을 늘려 임계 부근의 오판정률을 재고 나서야 <code>hold</code> 상태를
    넣지 않기로 한 결정을 유지할지 판단할 수 있다. 채점기 편향을 서류 판정 쪽에서도 같은 방식으로
    점검해야 한다.
  </p>

  <p class="ccl__p">
    <b>온프레미스는 폐쇄이지 폐기가 아니다.</b> Qwen3-8B QLoRA 어댑터 3갈래(chat v9 &middot; summary &middot; interview)와
    학습 파이프라인 &middot; GPU 이미지를 보존했고, <code>AGENT_*_BACKEND=ollama</code> 스위치로 교체할 수 있게
    코드 경로를 남겼다. 남은 과제는 <b>이번에 갈린 세 지점 &mdash; 다단계 도구 흐름 &middot; 수치 추론 &middot;
    JSON 형식 안정성 &mdash; 을 어댑터 쪽에서 고칠 수 있는지</b>다. 정확도는 이미 동급까지 왔으므로
    거기서 갈릴 문제가 아니다.
  </p>

  <p class="ccl__sub">결정이 남아 있는 것</p>

  <p class="ccl__p">
    멘토링에서 나온 항목 중 결정이 안 난 것이 셋 있다 &mdash; <b>면접 질문 음성 재생(TTS)</b>은 마이크
    오염 함정이 있어 보류했고, <b>면접 시간 상한</b>은 전역 기본값을 둘지 정하지 못했으며,
    <b>답변 기반 즉석 후속 질문</b>은 사전 생성 방식으로 대체한 채 후보로만 남겼다.
    셋 다 시연 결과를 보고 ADR 로 닫는 것이 순서다.
  </p>

  <div class="ccl__close">
    <p>
      측정할 수 있게 만들고, 같은 자로 재고, 근거로 결정하고, 문서로 남겼다 &mdash; 착수(08. 20.)부터
      프리즈(09. 20.)까지 32일 동안 반복한 절차였다. 학습 손실의 모순을 풀어 v9 를 만들었고, 그 v9 를 같은 채점기로 Claude 와 견줘
      클라우드를 택했다. <b>온프레미스는 만들어 봤기 때문에 접을 수 있었다.</b> 접은 것을 성공으로
      포장하지 않고, 왜 접었는지의 오류 목록을 종합보고로 남긴 것이 이 프로젝트가 내놓을 수 있는
      가장 정직한 산출물이다.
    </p>
  </div>

</div>

<a class="ccl__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
