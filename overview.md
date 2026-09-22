---
layout: default
title: 사업 개요
permalink: /overview/
---

<style>
.ov { max-width: 64rem; margin: 2.5rem auto 4rem; }

.ov__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 1.6rem; }
.ov__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.ov__crumb a { color: #9ca3af; }
.ov__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; word-break: keep-all; }
.ov__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

/* 요약 타일 */
.ov__stat {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(8.5rem, 1fr));
  gap: .6rem;
  margin-bottom: 2.75rem;
}
.ov__tile { border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .85rem; }
.ov__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.ov__v { font-size: 1.05rem; font-weight: 700; color: #111827; word-break: keep-all; }
.ov__v small { display: block; font-size: .74rem; font-weight: 400; color: #9ca3af; margin-top: .1rem; }

.ov__sec { margin-bottom: 3.25rem; }
.ov__sec > h2 {
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
.ov__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.ov__sub {
  margin: 2.25rem 0 .85rem;
  font-size: .92rem;
  color: #111827;
  word-break: keep-all;
}

.ov__note { margin: -.4rem 0 1.2rem; max-width: 50rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }
.ov__p { margin: 0 0 1rem; max-width: 50rem; color: #374151; font-size: .92rem; line-height: 1.8; word-break: keep-all; }
.ov__p:last-child { margin-bottom: 0; }
.ov__p code, .ov__note code { font-size: .84rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 명제 인용 */
.ov__quote {
  border-left: 3px solid #2a7ae2;
  background: #f9fafb;
  border-radius: 0 6px 6px 0;
  padding: .9rem 1.1rem;
  margin: 0 0 1.4rem;
  max-width: 50rem;
}
.ov__quote p { margin: 0; font-size: .95rem; line-height: 1.75; color: #111827; word-break: keep-all; }
.ov__quote p + p { margin-top: .45rem; font-size: .86rem; color: #6b7280; }

/* 단계 흐름 */
.ov__flow {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: .4rem;
  margin: 0 0 1.2rem;
  font-size: .84rem;
  color: #374151;
}
.ov__step {
  border: 1px solid #e5e7eb;
  border-radius: 5px;
  padding: .35rem .6rem;
  background: #f9fafb;
  white-space: nowrap;
}
.ov__step b { display: block; font-size: .87rem; color: #111827; }
.ov__step span { font-size: .72rem; color: #9ca3af; font-family: ui-monospace, SFMono-Regular, Menlo, monospace; }
.ov__step--end { background: #fff; }
.ov__arrow { color: #9ca3af; }

/* 표 공통 — 개발 일정 페이지와 같은 패턴 */
.tbl__scroll { overflow-x: auto; padding-bottom: .3rem; }
.tbl { width: 100%; border-collapse: collapse; font-size: .87rem; min-width: 44rem; }
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
.tbl__key { white-space: nowrap; font-weight: 600; color: #111827; }
.tbl__out td:first-child { white-space: nowrap; }

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
.tag--keep { background: #f3f4f6; color: #4b5563; }
.tag--rev { background: #fef3c7; color: #92400e; }

.ov__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }
</style>

<div class="ov">

<div class="ov__head">
  <p class="ov__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 1. 사업 개요</p>
  <h1>사업 개요</h1>
  <p>채용 전 과정을 한 시스템으로 &mdash; 반복은 자동화하고 최종 합불은 사람이 확정한다
     &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="ov__stat">
  <div class="ov__tile"><span class="ov__k">시스템명</span>
    <span class="ov__v">Arda<small>Eval-ATS</small></span></div>
  <div class="ov__tile"><span class="ov__k">개발 기간</span>
    <span class="ov__v">69일<small>08. 20. ~ 10. 27.</small></span></div>
  <div class="ov__tile"><span class="ov__k">개발 인원</span>
    <span class="ov__v">4명<small>팀 seuk &middot; 5도메인</small></span></div>
  <div class="ov__tile"><span class="ov__k">필수 기능</span>
    <span class="ov__v">27/27<small>09. 03. 달성 후 유지</small></span></div>
  <div class="ov__tile"><span class="ov__k">API 라우트</span>
    <span class="ov__v">107<small>DB 테이블 28</small></span></div>
  <div class="ov__tile"><span class="ov__k">결정 기록</span>
    <span class="ov__v">ADR 36<small>편</small></span></div>
</div>

<div class="ov__sec">

  <h2><span class="ov__num">1.</span> 추진 배경 및 필요성</h2>
  <p class="ov__note">
    기능을 정하기 전에 <b>&ldquo;인사팀이 왜 이걸 쓰는가&rdquo;</b>에 먼저 답하려고 조사했다.
    이 절의 수치는 2026. 08. 27. 작성한 시장 조사 문서
    (<code>docs/04_planning/01-시장조사-방향성.md</code>)에서 가져왔다 &mdash;
    시간 통계의 원출처는 candidate.fyi 2026 Recruiting Coordination Statistics 와 Stratus HR,
    국내 근거는 나인하이어 &middot; zuzu 분석과 ZDNet 기사다.
    이 문서는 초안 상태로 남아 있으므로, 아래 수치는 조사된 <b>현행</b> 채용 실무의 값이고
    Arda 도입 뒤의 단축 실측치가 아니다.
  </p>

  <p class="ov__p">
    채용 실무는 엑셀 &middot; 메일함 &middot; 채용 플랫폼 세 곳에 흩어져 돌아간다.
    지원자가 늘고, 담당자가 2인 이상이 되고, 개인정보 규정이 겹치는 순간 이 구조가 무너진다.
    무너지는 지점은 기능 부족이 아니라 <b>기록이 남지 않는 것</b>이다 &mdash;
    &ldquo;누가 언제 어느 단계로 옮겼는가&rdquo;, &ldquo;면접관 세 명의 평가가 어디 있는가&rdquo;에
    엑셀은 답하지 못한다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>확인된 문제</th><th>내용 &middot; 근거</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__key">3중 관리 붕괴</td>
        <td>엑셀 + 메일함 + 채용 플랫폼. 지원자 증가 &middot; 담당자 2인 이상 &middot;
            개인정보 규정이 겹치는 순간 엑셀이 무너진다</td>
      </tr>
      <tr>
        <td class="tbl__key">행정이 시간을 먹는다</td>
        <td>코디네이터 업무의 <b>46%가 일정 조율 등 행정</b>.
            면접 1건 수동 조율 평균 <b>243분</b> &middot; 이력서 1장 30~90초 &middot;
            지원자 1명 연락 5~15분</td>
      </tr>
      <tr>
        <td class="tbl__key">협업이 안 된다</td>
        <td>단계 이동 주체 &middot; 시점 &middot; 사유와 면접관별 평가가 어디에도 남지 않는다</td>
      </tr>
      <tr>
        <td class="tbl__key">응답 지연</td>
        <td>통보가 늦으면 후보가 이탈하고 회사 평판으로 돌아온다</td>
      </tr>
      <tr>
        <td class="tbl__key">컴플라이언스</td>
        <td>채용절차법 &middot; 개인정보보호법상 서류 보관 &middot; 파기 의무를
            엑셀로는 관리할 수 없다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="ov__p" style="margin-top:1.2rem;">
    수치가 말하는 것은 하나다 &mdash; 채용의 비용은 판단이 아니라 <b>판단 주변의 반복</b>에 쌓인다.
    이력서를 읽고 판단하는 시간보다, 일정을 맞추고 메일을 쓰고 기록을 옮기는 시간이 길다.
    문제가 실재한다는 외부 증거도 있다. 정부가 중소기업의 ATS 도입에
    <b>연간 이용료의 80%(최대 40만원)</b>를 지원하는 사업을 운영 중이다 &mdash;
    국가가 돈을 대는 종류의 문제라는 뜻이다.
  </p>

  <p class="ov__p">
    그런데 여기에 AI 를 얹는 것 자체가 새로운 장벽이 된다. 채용담당자 <b>71%가 ATS 를 쓰고
    79%가 채용의 일부를 자동화</b>하고 있지만, EU AI Act 는 채용을 <b>고위험</b>으로 분류하고
    국내에는 채용절차법이 있다. 2018년 Amazon 이 과거 채용 데이터로 학습시킨 채용 AI 가
    여성 지원자를 감점해 폐기된 사례가 이 위험의 전형이다.
    2026년 구매 담당자의 실제 질문은 &ldquo;AI 되나요&rdquo;가 아니라
    <b>&ldquo;AI 켜도 사고 안 나나요&rdquo;</b>다.
  </p>

  <p class="ov__p">
    그래서 이 프로젝트의 방향을 AI 기능을 늘리는 쪽이 아니라,
    <b>AI 를 안심하고 켤 수 있게 하는 장치를 먼저 짜는 쪽</b>으로 잡았다.
    사람이 확정하고, 기록이 남고, 비용이 보이고, 근거를 인용한다 &mdash;
    이 넷이 다음 절의 개발 목적이 된다.
  </p>

</div>

<div class="ov__sec">

  <h2><span class="ov__num">2.</span> 개발 목적</h2>

  <div class="ov__quote">
    <p>반복 업무는 에이전트가 대신하고, 판단의 근거는 사람에게 보여주는 ATS.</p>
    <p>비싼 것(기록 &middot; 정리 &middot; 취합 &middot; 발송)을 자동화하고,
       위험한 것(합불 판단)은 사람에게 남긴다.</p>
  </div>

  <p class="ov__p">
    채용 과정의 반복 업무를 자동화하고 흩어진 지원자 정보를 하나의 플랫폼으로 통합해,
    채용 담당자가 <b>&lsquo;지원자라는 사람&rsquo;에 집중</b>할 수 있게 하는 것이 목적이다.
    담당자가 공고를 올리고 지원자가 외부 공개 링크로 지원서 &middot; 이력서를 제출하면,
    아르(AI)가 자격요건 &middot; 우대사항 &middot; 인재상 3축으로 채점해 서류 단계를 자동 판정하고,
    면접 이후 단계는 담당자 &middot; 면접관이 칸반 보드에서 심사 &middot; 평가한다.
    단계가 바뀌면 지원자에게 메일이 자동 발송되고, 모든 이동에 이력과 평가 기록이 남는다.
    <b>최종 합불만은 항상 사람이 확정한다</b>(ADR-0003 &rarr; 0034).
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>목적</th><th>무엇으로 달성하는가</th><th>왜 그렇게 했는가</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__key">반복 제거</td>
        <td>서류 1차 심사 &middot; 단계 전환 &middot; 안내 메일 &middot; 면접 일정 조율을 자동화.
            자연어 한 문장이 검색 &rarr; 조회 &rarr; 단계 변경으로 분해돼 순차 실행된다</td>
        <td>채용의 시간은 판단이 아니라 판단 주변에서 샌다 &mdash; 1절의 46% &middot; 243분</td>
      </tr>
      <tr>
        <td class="tbl__key">근거 노출</td>
        <td>3축 점수 &middot; 강점/우려 &middot; 확인 질문, 답변&harr;서류 대조 결과를
            화면에 남긴다. 에이전트 응답은 도구 결과 &middot; 이력서 원문만 인용한다</td>
        <td>&ldquo;왜 이 판정인가&rdquo;에 답하지 못하면 자동화는 신뢰를 얻지 못한다</td>
      </tr>
      <tr>
        <td class="tbl__key">사람 확정 보장</td>
        <td>쓰기 도구(단계 변경 &middot; 면접관 배정 &middot; 메일 발송)는 확인 카드로 반환돼
            사람이 승인해야 실행된다. 역행은 항상 허용하고, 자동 탈락 메일은
            마감 뒤 담당자가 일괄 발행한다</td>
        <td>되돌릴 수 있어야 AI 를 켤 수 있다 &mdash; 번복 여지를 구조로 남긴다</td>
      </tr>
      <tr>
        <td class="tbl__key">비용을 보이게</td>
        <td>호출마다 모델명 &middot; 토큰 &middot; 원가를 로깅하고, 프롬프트 18개를 코드로
            버전 관리한다. 인사 &middot; 능력 &middot; 기본 FAQ 는 규칙 라우터가 LLM 없이 처리</td>
        <td>&ldquo;AI 켜면 얼마 나오나&rdquo;는 실제 도입을 막는 질문이다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="ov__p" style="margin-top:1.2rem;">
    적용 원칙은 하나로 줄인다 &mdash; <b>버튼으로 되는 일에는 AI 를 쓰지 않는다.</b>
    비정형 문서 이해, 자연어 요청의 작업 분해처럼 버튼으로 안 되는 일에만 쓴다.
    표정(ViT + MediaPipe) &middot; 음성 신호는 담당자 화면에 수치로 보이되
    점수 &middot; 합불 판정의 재료로는 쓰지 않는다(ADR-0029).
    AI 요약 문장도 측정 수치의 재서술까지만 허용하고, 수치에 없는 숫자나 사람을 단정하는 단어가
    나오면 문장을 버리고 고정 틀로 대체한다.
  </p>

  <p class="ov__p">
    시스템명 <b>Arda</b> 는 톨킨의 퀘냐로 &lsquo;영역(Realm)&rsquo;, 모든 종족이 살아가는 터전을 뜻한다.
    후보였던 Argus(감시자) &middot; Themis(정의의 여신)를 뺀 이유는
    <b>판정하는 존재라서 원칙과 충돌한다</b>는 것이었다.
    Arda 는 판단하는 주체가 아니라 판단이 일어나는 장소다(ADR-0014) &mdash;
    도구는 자리를 마련하고, 판단은 그 안의 사람이 한다.
  </p>

</div>

<div class="ov__sec">

  <h2><span class="ov__num">3.</span> 개발 범위</h2>
  <p class="ov__note">
    범위는 경계가 있을 때 의미가 있다. 아래는 만든 것과 함께
    <b>만들지 않기로 하고 근거를 문서에 남긴 것</b>을 같이 적는다.
    뺀 것도 되살린 것도 전부 ADR 로 기록했고, 개정할 때는 원문을 지우지 않고 절을 덧붙인다.
    현재 상태는 해커톤 제출 프리즈(2026. 09. 20.) 이후 심사 기간(09. 20. ~ 10. 17.)이며,
    10. 27. AWS 잔여 리소스 정리와 인계로 종료한다.
  </p>

  <h3 class="ov__sub">3-1. 범위의 축 &mdash; 채용 단계 모델</h3>

  <div class="ov__flow">
    <span class="ov__step"><b>지원 접수</b><span>applied</span></span>
    <span class="ov__arrow">&rarr;</span>
    <span class="ov__step"><b>서류 검토</b><span>screening</span></span>
    <span class="ov__arrow">&rarr;</span>
    <span class="ov__step"><b>면접</b><span>interview</span></span>
    <span class="ov__arrow">&rarr;</span>
    <span class="ov__step ov__step--end"><b>최종 합격</b><span>accepted</span></span>
    <span class="ov__arrow">/</span>
    <span class="ov__step ov__step--end"><b>불합격</b><span>rejected</span></span>
  </div>

  <p class="ov__p">
    단계는 다섯, 규칙은 여섯이다. 단계는 DB enum 이 아니라 코드 상수 + 체크 제약으로 두고,
    전환 규칙은 서비스 레이어가 강제한다. 마감 &middot; 만료는 크론이 아니라 조회 시점에 판정한다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>규칙</th><th>내용 &middot; 이유</th></tr>
    </thead>
    <tbody>
      <tr><td class="tbl__key">전진은 한 칸씩</td>
          <td>단계를 건너뛰는 전진은 허용하지 않는다</td></tr>
      <tr><td class="tbl__key">역행은 항상 허용</td>
          <td>사람이 AI 판정을 되돌리는 것이 유일한 안전장치다</td></tr>
      <tr><td class="tbl__key">불합격은 어느 단계에서든</td>
          <td>단, 사유가 없으면 <code>422</code> &mdash; 사유 없는 이력은 나중에 아무도 설명하지 못한다</td></tr>
      <tr><td class="tbl__key">서류는 AI 자동 판정</td>
          <td>3축 100점 채점 &middot; 임계 기본 60 &middot; 자료 부족은 서류 탈락.
              사람이 한 번 손대면 그 지원자는 이후 자동 판정에서 빠진다 &mdash;
              <b>수동이 항상 이긴다</b>(ADR-0034)</td></tr>
      <tr><td class="tbl__key">일괄 변경은 전부 아니면 전무</td>
          <td>200명 중 30명만 바뀌면 담당자가 무엇이 됐는지 알 수 없다 &rarr; 전체 롤백(<code>409</code>)</td></tr>
      <tr><td class="tbl__key">사용자는 지우지 않는다</td>
          <td>비활성화만 &mdash; <code>changed_by</code> &middot; <code>evaluator_id</code> 로 박힌 이력을
              물리 삭제가 부순다</td></tr>
    </tbody>
  </table>
  </div>

  <h3 class="ov__sub">3-2. 포함 범위</h3>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>영역</th><th>내용</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__key">채용 프로세스 자동화</td>
        <td>칸반 보드 단계 관리 &middot; 단계 변경 시 자동 메일(n8n 웹훅 + SMTP,
            실패 시 API 가 5분마다 최대 3회 재발송) &middot; 단계 이력 기록 &middot;
            공고 마감 &middot; 다시 열기</td>
      </tr>
      <tr>
        <td class="tbl__key">자동 서류 심사</td>
        <td>요약 &rarr; 평가 &rarr; 추천 3단 체인으로 자격요건 &middot; 우대사항 &middot; 인재상
            3축 100점 채점, 임계 기준 자동 이동, 자료 부족 자동 탈락,
            사람 개입 시 자동 판정 제외(ADR-0034)</td>
      </tr>
      <tr>
        <td class="tbl__key">AI 이력서 분석</td>
        <td>PDF / DOCX / HWPX 텍스트 추출 &middot; 학력 &middot; 경력 &middot; 기술스택 구조화
            (AI 가 채운 값에는 「AI 추정」 표식) &middot;
            RAG 시맨틱 검색(ko-sroberta + pgvector, 키워드 폴백 병행)</td>
      </tr>
      <tr>
        <td class="tbl__key">도구 호출 에이전트 &lsquo;아르&rsquo;</td>
        <td>자연어로 지원자 검색 &middot; 조회 &middot; 단계 변경 &middot; 면접관 배정 &middot;
            일정 제안 &middot; 메일 초안/발송 &middot; 이력서 드롭 접수 &mdash;
            <b>도구 12종</b>, 쓰기는 확인 카드, 빈출 요청은 규칙 라우터</td>
      </tr>
      <tr>
        <td class="tbl__key">지원자 통합 관리</td>
        <td>지원자 CRUD &middot; 검색 &middot; 필터(더미 10만 건 기준 튜닝) &middot;
            면접관 배정 &middot; 평가 &middot; 종합평가 화면 &middot; 공고별 현황</td>
      </tr>
      <tr>
        <td class="tbl__key">공개 지원 &middot; 지원자 포털</td>
        <td>로그인 없는 외부 공개 링크 접수 &middot; presigned URL 로 브라우저에서 S3 직접 업로드
            &middot; 지원자 로그인(이메일 + 생년월일, ADR-0033) &middot;
            전형 현황 &middot; 일정 &middot; 설문 &middot; AI 면접을 한 화면에서 &middot; FAQ 챗봇</td>
      </tr>
      <tr>
        <td class="tbl__key">AI 면접 &middot; 실시간 분석</td>
        <td>이력서 &middot; 자소서 기반 맞춤 질문 &middot; 음성 답변 STT &middot;
            답변&harr;서류 대조 &middot; 담당자 1:1 WebRTC 실시간 화면 &middot;
            표정 &middot; 음성 참고 지표(점수 미반영) &middot; 종료 시 수치 요약</td>
      </tr>
      <tr>
        <td class="tbl__key">인적성(사전 성향) 설문</td>
        <td>10문항 5점 척도 &middot; 카테고리 통계는 코드가 계산하고
            AI 는 관찰 문장으로 재서술만 한다 &middot; 미응답 불이익 없음(ADR-0027)</td>
      </tr>
      <tr>
        <td class="tbl__key">제출물 무결성 원장</td>
        <td>이력서 &middot; 자소서의 SHA-256 을 추가 전용 원장에 해시 사슬로 쌓고,
            DB 트리거가 수정 &middot; 삭제 &middot; TRUNCATE 를 거부한다.
            사슬 머리는 Ethereum Sepolia 에 앵커하고 서명 개인키는 서버 밖에 둔다(ADR-0028)</td>
      </tr>
      <tr>
        <td class="tbl__key">인증 &middot; 권한</td>
        <td>담당자 JWT 12시간 &middot; 비활성 계정은 발급된 토큰도 401 &middot;
            권한 등급 <code>admin</code> / <code>member</code> 2종(ADR-0017) &middot;
            n8n &middot; 판정 워커는 서비스 토큰(<code>/internal</code>)</td>
      </tr>
      <tr>
        <td class="tbl__key">운영</td>
        <td>자동 CD(main 머지 &rarr; 2분 폴링 &middot; 컨테이너 안에서 alembic 이행) &middot;
            CI 5잡 &middot; CloudWatch / SNS 경보 &middot; 매일 S3 백업 &middot;
            컨테이너 로그 상한 &middot; 외부 헬스체크</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="ov__note" style="margin:1.1rem 0 0;">
    <b>규모</b> &mdash; API 라우트 107 &middot; DB 테이블 28(ERD v2.8) &middot;
    alembic 리비전 26 &middot; 웹 화면 25 &middot; 앱 화면 23 &middot;
    pytest 1,165건 통과 &middot; 앱 위젯 테스트 30파일 &middot; AI 프롬프트 18 &middot;
    ADR 36편 &middot; 커밋 1,095.
    기획 필수 27기능은 2026. 09. 03. 에 <b>27/27 구현</b>을 달성해 유지 중이고
    <span class="tag tag--done">달성</span>, 위 표의 자동 서류 심사 이하 항목은
    기획서 밖에서 ADR 로 편입해 배포까지 끝낸 확장분이다.
  </p>

  <h3 class="ov__sub">3-3. 범위 밖 &mdash; 하지 않는 것</h3>
  <p class="ov__note">
    &ldquo;못 만들어서 안 한 것&rdquo;과 &ldquo;안 만드는 게 맞다고 판단한 것&rdquo;은 다르다.
    아래는 후자다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl__out">
    <thead>
      <tr><th>하지 않는 것</th><th>이유</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__key">Kubernetes</td>
        <td>&ldquo;한 달 안에 굴렸다고 말할 수 없는 것은 넣지 않는다&rdquo;(ADR-0001).
            EC2 1대 + Docker Compose 로 간다 <span class="tag tag--keep">유지</span></td>
      </tr>
      <tr>
        <td class="tbl__key">AI 최종 합불 확정</td>
        <td>서류 단계 이동까지만 AI 가 한다. 최종 합격 &middot; 불합격은 사람만 확정한다
            (ADR-0003 &rarr; 0034). 화면 문법도 앰버 점선 = AI 제안 /
            실선 = 사람 확정으로 구분한다</td>
      </tr>
      <tr>
        <td class="tbl__key">표정 &middot; 음성으로 점수 매기기</td>
        <td>표정 &middot; 음성 신호는 담당자 참고 지표까지만이고 점수 재료가 아니다(ADR-0029).
            인적성도 성격 유형 판정 &middot; 점수화 &middot; 합불 의견을 만들지 않는다(ADR-0027)</td>
      </tr>
      <tr>
        <td class="tbl__key">면접관 성향 모방 모델</td>
        <td>검토했으나 채택하지 않았다 &mdash; 면접관의 편향까지 복제하고(2018 Amazon 폐기 사례),
            사람 검토 없는 자동 합불은 EU AI Act 고위험이며, 면접관 1인의 연간 표본과
            &lsquo;합격 이유&rsquo; 정답 라벨이 둘 다 없다.
            같은 문제의식은 성향을 복제하지 않고 <b>드러내는</b> 방향으로 정리했다</td>
      </tr>
      <tr>
        <td class="tbl__key">3인 이상 다자 화상면접</td>
        <td>제외 근거였던 견적(시그널링 + TURN + <b>SFU</b>)은 3인 이상이 전제였다.
            둘이면 SFU 없이 두 끝점이 직접 붙으므로 <b>1:1 만 도입</b>했고,
            집단 면접은 시연 뒤 ADR 로 다룬다</td>
      </tr>
      <tr>
        <td class="tbl__key">speech-to-speech</td>
        <td>음성은 STT 로 받아 기존 텍스트 에이전트에 넣는다(ADR-0004)</td>
      </tr>
      <tr>
        <td class="tbl__key">지원자 SNS 크롤링</td>
        <td>채용절차법 &middot; 개인정보보호법 &middot; 약관 위반
            <span class="tag tag--keep">유지</span></td>
      </tr>
      <tr>
        <td class="tbl__key">실시간 공동 편집</td>
        <td>제외(ADR-0005). 담당자 메모는 행 추가 방식으로 대체
            <span class="tag tag--keep">유지</span></td>
      </tr>
      <tr>
        <td class="tbl__key">외부 채용사이트 연동</td>
        <td>기획 단계에서 제외했다. 대신 회사 쪽에서 지원자를 밀어 넣는 통합 API 를
            ADR-0037 로 따로 열었다 &mdash; 코어가 받는 경로는 API push 하나다</td>
      </tr>
      <tr>
        <td class="tbl__key">구형 HWP</td>
        <td>텍스트 추출은 PDF &middot; DOCX &middot; HWPX 만 지원한다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <h3 class="ov__sub">3-4. 범위를 개정한 것</h3>
  <p class="ov__note">
    오너가 개정 ADR 을 쓰면 잘랐던 기능도 되살아난다. 원문은 지우지 않고 절을 덧붙였다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl tbl__out">
    <thead>
      <tr><th>항목</th><th>원 결정</th><th>현재</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__key">표정 분석</td>
        <td>제외 &mdash; 직무성과 예측 기여 0.25% 미만 &middot; 차별 위험 &middot;
            HireVue 2021 폐기(ADR-0002)</td>
        <td><span class="tag tag--rev">개정</span> 도입하되 담당자 참고 지표까지(ADR-0029).
            원 근거는 문서에 그대로 남겼다</td>
      </tr>
      <tr>
        <td class="tbl__key">AI 판정 범위</td>
        <td>AI 는 추천까지만(ADR-0003)</td>
        <td><span class="tag tag--rev">개정</span> 서류 단계는 AI 자동 판정,
            최종 합불만 사람(ADR-0034). 안전장치 셋 &mdash; 이력 &middot; 일괄 메일 &middot;
            수동 우선</td>
      </tr>
      <tr>
        <td class="tbl__key">실시간 화상면접</td>
        <td>제외 &mdash; 견적 4주는 3인 이상 전제</td>
        <td><span class="tag tag--rev">개정</span> 1:1 만 도입, 다자는 제외 유지</td>
      </tr>
      <tr>
        <td class="tbl__key">메일 경로</td>
        <td>SQS 큐 + 메일 워커 + SES</td>
        <td><span class="tag tag--rev">개정</span> n8n 웹훅 + SMTP 로 전환하고 SQS &middot; SES 폐기
            (ADR-0031 &middot; 0036). 메일 &middot; 큐 &middot; 스토리지는 환경변수 스위치로
            공급자를 바꿀 수 있다</td>
      </tr>
      <tr>
        <td class="tbl__key">온프레미스 자체 서빙</td>
        <td>계획 &mdash; sLLM 과 STT 를 온프레미스로 돌려 개인정보를 외부로 내보내지 않는다
            (ADR-0024)</td>
        <td><span class="tag tag--rev">개정</span> 학원 PC 3대로 실제 구축해 운영한 뒤
            <b>폐쇄</b>했다(09. 18.). 심사 &middot; 운영 서빙은 클라우드(AWS) + Claude 로 확정.
            Qwen 어댑터는 비용 절감 R&amp;D 자산으로 보존한다</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="ov__sec">

  <h2><span class="ov__num">4.</span> 기대 효과</h2>
  <p class="ov__note">
    효과는 실측치가 있는 것과 없는 것을 갈라서 쓴다.
    오른쪽 열이 비어 보이지 않게 하려고 숫자를 지어내지 않았다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>구분</th><th>기대 효과</th><th>근거 &middot; 실측</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="tbl__key">업무 효율</td>
        <td>서류 1차 심사 &middot; 단계 전환 &middot; 알림이 자동으로 돌아
            담당자는 면접과 최종 판단에 집중한다</td>
        <td>접수 즉시 3단 체인이 점수를 내고, 임계(기본 60) 이상은
            <code>applied &rarr; screening &rarr; interview</code>,
            미만은 <code>applied &rarr; rejected</code> 로 시스템이 옮긴다(ADR-0034) &mdash;
            서류 단계에 사람이 옮길 카드가 쌓이지 않는다.
            자동을 끄려면 공고를 <code>screening_mode='manual'</code> 로 둔다(점수만 매기고 멈춘다)
            &middot; 검색은 10만 건 기준 <b>111ms &rarr; 7.8ms</b></td>
      </tr>
      <tr>
        <td class="tbl__key">판단 품질</td>
        <td>판정 근거가 화면에 남아 &ldquo;왜 이 판정인가&rdquo;를 설명할 수 있다</td>
        <td>3축 100점 채점(요건 60 &middot; 우대 10 &middot; 인재상 30).
            fit-check 지원자 <b>24명 실측</b>으로 가중치를 요건 50&rarr;60 &middot;
            우대 20&rarr;10 으로 개정하고, 요건 &ge;70 이면 문화 하한 50 규칙을 넣어
            요건 우수자가 문구 하나로 탈락하지 않게 했다</td>
      </tr>
      <tr>
        <td class="tbl__key">정보 통합</td>
        <td>지원자 정보 &middot; 이력서 &middot; 평가 &middot; 면접 분석 &middot; 이력을
            단일 시스템에서 조회한다</td>
        <td>웹 25화면 + 앱 23화면이 같은 FastAPI API 를 쓴다 &middot;
            지원서를 축으로 한 테이블 28개</td>
      </tr>
      <tr>
        <td class="tbl__key">투명성 &middot; 무결성</td>
        <td>모든 단계 이동과 평가에 이력이 남고, 제출물 위변조를 외부에서 검증할 수 있다</td>
        <td>SHA-256 해시 사슬 + DB 트리거가 수정 &middot; 삭제 거부 + 사슬 머리를
            Sepolia 에 앵커 &middot; 불합격은 사유 없으면 <code>422</code> &middot;
            일괄 변경은 부분 성공 없이 전체 롤백(<code>409</code>)</td>
      </tr>
      <tr>
        <td class="tbl__key">비용 통제</td>
        <td>호출마다 원가가 보이고, 모델 교체를 감이 아니라 같은 자로 잰 근거로 결정한다</td>
        <td>아르 호출당 실측 <b>$0.0075</b> &middot; 인사 &middot; 능력 &middot; 기본 FAQ 는
            규칙 라우터가 LLM 없이 <b>$0</b> &middot; 동일 채점기(judge.py) 동일 23건으로
            Qwen 학습 전 26.1% &rarr; v9 73.9%, Claude Haiku 4.5 는 69.6%</td>
      </tr>
      <tr>
        <td class="tbl__key">접근성</td>
        <td>시간 &middot; 장소 제약 없이 지원하고 자기 전형을 확인한다</td>
        <td>로그인 없는 공개 지원 링크 &middot; 이메일 + 생년월일 로그인으로 24시간 포털
            &middot; 모바일 대응 웹 + Flutter Android 앱</td>
      </tr>
    </tbody>
  </table>
  </div>

  <h3 class="ov__sub">한계 &mdash; 아직 안 된 것</h3>

  <p class="ov__p">
    프리즈(2026. 09. 20.) 시점에 남은 것이 있다.
    <b>면접관 자동 배정이 0명으로 떨어지는 결함</b>이 남아 있고,
    받아쓰기 정확도는 재현 테스트(12/12 정확 전사)와 달리 실제 음성에서 흔들린다.
    면접 방 상태가 프로세스 메모리에 있어 API 워커를 1개로 묶어 두고 있다 &mdash;
    Redis 이관은 계획 상태다.
  </p>

  <p class="ov__p">
    비교 수치에도 단서가 붙는다. 모델 비교에 쓴 채점기는 Qwen gold 기준이라
    <b>절대 점수가 아니라 상대 궤적만 유효</b>하다고 보고서에 명시했다.
    그리고 화면과 데모의 지원자 &middot; 회사는 전부 가상 데이터다 &mdash;
    위 효과는 설계와 실측 벤치마크로 뒷받침한 것이지,
    <b>실제 채용 데이터로 검증한 성과가 아니다.</b>
  </p>

</div>

<a class="ov__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
