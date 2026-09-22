---
layout: default
title: 요구사항 분석
permalink: /requirements/
---

<style>
.req { max-width: 64rem; margin: 2.5rem auto 4rem; }

.req__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 1.6rem; }
.req__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.req__crumb a { color: #9ca3af; }
.req__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; word-break: keep-all; }
.req__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

.req__stat {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(8.5rem, 1fr));
  gap: .6rem;
  margin-bottom: 2.75rem;
}
.req__stat .stat { border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .85rem; }
.req__stat .stat__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.req__stat .stat__v { font-size: 1.05rem; font-weight: 700; color: #111827; word-break: keep-all; }
.req__stat .stat__v small { font-size: .78rem; font-weight: 400; color: #9ca3af; margin-left: .15rem; }

.req__sec { margin-bottom: 3.25rem; }
.req__sec > h2 {
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
.req__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.req__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }
.req__p { margin: 0 0 1rem; color: #374151; font-size: .92rem; line-height: 1.8; word-break: keep-all; }
.req__p:last-child { margin-bottom: 0; }
.req__p code, .req__note code { font-size: .84rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

.req__sub {
  font-size: .9rem;
  color: #111827;
  margin: 2rem 0 .8rem;
  padding-bottom: .35rem;
  border-bottom: 1px solid #f3f4f6;
  word-break: keep-all;
}
.req__sub:first-child { margin-top: 0; }

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
.tag--drop { background: #fee2e2; color: #991b1b; }

/* 요구 ID 열 */
.req__id { white-space: nowrap; font-variant-numeric: tabular-nums; font-weight: 700; color: #111827; }
.req__fnum { white-space: nowrap; font-variant-numeric: tabular-nums; font-weight: 700; color: #2a7ae2; }
.req__grp { white-space: nowrap; background: #fafafa; font-weight: 600; color: #111827; }

/* 문제점 카드 */
.pain { display: grid; grid-template-columns: repeat(auto-fit, minmax(15.5rem, 1fr)); gap: .75rem; }
.pain__card { border: 1px solid #e5e7eb; border-left: 3px solid #dc2626; border-radius: 6px; padding: .9rem 1rem; }
.pain__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.pain__name { font-size: .95rem; font-weight: 700; color: #111827; margin: 0 0 .45rem; word-break: keep-all; }
.pain__card p { margin: 0 0 .5rem; font-size: .84rem; line-height: 1.7; color: #4b5563; word-break: keep-all; }
.pain__card p:last-child { margin-bottom: 0; }
.pain__ans { font-size: .8rem; color: #2a7ae2; font-weight: 600; }

/* 비기능 4축 */
.nfr { border: 1px solid #e5e7eb; border-radius: 6px; overflow: hidden; margin-bottom: 1.2rem; }
.nfr__head {
  display: flex;
  align-items: baseline;
  gap: .55rem;
  flex-wrap: wrap;
  padding: .7rem 1rem;
  background: #f9fafb;
  border-bottom: 1px solid #e5e7eb;
}
.nfr__axis { font-size: .95rem; font-weight: 700; color: #111827; }
.nfr__one { font-size: .8rem; color: #6b7280; word-break: keep-all; }
.nfr__body { padding: .9rem 1rem; }
.nfr__body ul { margin: 0; padding-left: 1.05rem; }
.nfr__body li { font-size: .855rem; line-height: 1.75; color: #374151; word-break: keep-all; margin-bottom: .3rem; }
.nfr__body li:last-child { margin-bottom: 0; }

/* 시나리오 */
.sc { border: 1px solid #e5e7eb; border-radius: 6px; padding: .95rem 1.1rem; margin-bottom: .8rem; }
.sc__top { display: flex; align-items: baseline; gap: .55rem; flex-wrap: wrap; margin-bottom: .6rem; }
.sc__code { font-size: .74rem; font-weight: 700; color: #2a7ae2; font-variant-numeric: tabular-nums; }
.sc__name { font-size: .95rem; font-weight: 700; color: #111827; word-break: keep-all; }
.sc__who { font-size: .76rem; color: #9ca3af; }
.sc__row { display: flex; gap: .7rem; margin-bottom: .4rem; }
.sc__row:last-child { margin-bottom: 0; }
.sc__k {
  flex: 0 0 3.4rem;
  font-size: .74rem;
  color: #9ca3af;
  letter-spacing: .03em;
  padding-top: .12rem;
}
.sc__v { margin: 0; font-size: .86rem; line-height: 1.75; color: #374151; word-break: keep-all; }

.req__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }
</style>

<div class="req">

<div class="req__head">
  <p class="req__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 3. 요구사항 분석</p>
  <h1>요구사항 분석</h1>
  <p>엑셀·메일함으로 굴러가던 채용을 하나의 파이프라인으로 &mdash;
     필수 27기능과 그 검수 기준 &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="req__stat">
  <div class="stat"><span class="stat__k">전체 기능 목록</span>
    <span class="stat__v">80<small>개</small></span></div>
  <div class="stat"><span class="stat__k">필수</span>
    <span class="stat__v">27<small>개 · 27/27 구현</small></span></div>
  <div class="stat"><span class="stat__k">권장 / 여유</span>
    <span class="stat__v">30 / 23<small>개</small></span></div>
  <div class="stat"><span class="stat__k">개발 범위 요구 ID</span>
    <span class="stat__v">SFR 9<small> + SEC 2 + PER 2 + QUA 3</small></span></div>
  <div class="stat"><span class="stat__k">QA 시나리오</span>
    <span class="stat__v">27<small>+ 실패 7</small></span></div>
</div>

<div class="req__sec">

  <h2><span class="req__num">1.</span> 기존 채용 프로세스의 문제점</h2>
  <p class="req__note">
    요구사항을 기능 목록에서 시작하지 않고 <b>"인사팀이 왜 이걸 사는가"</b>에서 시작했다
    (<code>docs/04_planning/01-시장조사-방향성.md</code>, 2026. 08. 27.).
    그 답이 없으면 기능을 아무리 쌓아도 우선순위를 정할 근거가 없기 때문이다.
    조사에서 확인된 pain 은 다섯 가지이고, 각각을 그것을 받아내는 기능 영역에 대응시켰다.
  </p>

  <div class="pain">

    <div class="pain__card">
      <span class="pain__k">PAIN 1</span>
      <p class="pain__name">엑셀 + 메일함 + 채용플랫폼 3중 관리</p>
      <p>지원자가 늘고, 담당자가 2인 이상이 되고, 개인정보 규정이 겹치는
         <b>세 조건이 동시에 걸리는 순간 엑셀이 무너진다.</b>
         지원자 정보가 세 곳에 흩어져 어느 것이 최신인지 알 수 없게 된다.</p>
      <p class="pain__ans">&rarr; 단일 파이프라인 (B &middot; C &middot; D)</p>
    </div>

    <div class="pain__card">
      <span class="pain__k">PAIN 2</span>
      <p class="pain__name">행정 업무가 시간을 잡아먹는다</p>
      <p>채용 코디네이터 업무의 <b>46%가 일정 조율 등 행정</b>이다.
         면접 1건을 수동으로 조율하는 데 평균 <b>243분</b>,
         이력서 1장을 훑는 데 30~90초, 지원자 1명에게 연락하는 데 5~15분이 든다.</p>
      <p class="pain__ans">&rarr; 자동 메일 (G1) &middot; 자동 서류 심사 &middot; 일정 자동화</p>
    </div>

    <div class="pain__card">
      <span class="pain__k">PAIN 3</span>
      <p class="pain__name">협업이 안 된다</p>
      <p>"누가 언제 어느 단계로 옮겼나", "면접관 3명의 평가가 어디 있나"
         &mdash; 엑셀에는 이 두 질문의 답이 없다.
         <b>기록이 없으니 나중에 아무도 설명할 수 없다.</b></p>
      <p class="pain__ans">&rarr; 단계 이력 (D5) &middot; 평가 (E1 &middot; E2)</p>
    </div>

    <div class="pain__card">
      <span class="pain__k">PAIN 4</span>
      <p class="pain__name">응답 지연 = 후보 이탈 = 회사 평판</p>
      <p>단계가 바뀌었는데 지원자가 모르면 기다리다 이탈하고,
         무응답은 그대로 회사 평판이 된다. 사람이 한 통씩 보내는 구조에서는
         지원자가 늘수록 지연도 같이 는다.</p>
      <p class="pain__ans">&rarr; 단계 변경 자동 메일 (G1 &middot; G2 &middot; G3)</p>
    </div>

    <div class="pain__card">
      <span class="pain__k">PAIN 5</span>
      <p class="pain__name">컴플라이언스</p>
      <p>채용절차법 &middot; 개인정보보호법상 서류 보관 &middot; 파기 의무가 있고,
         EU AI Act 는 채용을 <b>고위험</b>으로 분류하고, 사람 검토 없는 자동 합불을 문제 삼는다.
         엑셀로는 이 의무를 이행했다는 것을 증명할 수 없다.</p>
      <p class="pain__ans">&rarr; 접근 제어 (A3) &middot; 이력 &middot; 사람 확정 원칙</p>
    </div>

  </div>

  <p class="req__p" style="margin-top:1.3rem;">
    pain 이 실재한다는 가장 강한 증거는 <b>정부가 중소기업 ATS 도입에
    연간 이용료의 80%(최대 40만 원)를 지원하는 사업을 운영 중</b>이라는 사실이다.
    국가가 돈을 대는 문제라는 뜻이다. 시장 조사에 따르면 채용담당자의 71%가 이미 ATS 를 쓰고 있고,
    79%가 채용의 일부를 자동화하고 있다. 즉 <b>"ATS 가 필요한가"는 이미 끝난 질문</b>이고,
    남은 질문은 "AI 를 켜도 사고가 안 나는가"다.
  </p>

  <p class="req__p">
    그래서 이 프로젝트의 요구사항은 기능 개수가 아니라 한 문장의 정체성에서 파생됐다 &mdash;
    <b>반복 업무는 에이전트가 대신하고, 판단의 근거는 사람에게 보여주는 ATS.</b>
    비싼 것(기록 &middot; 정리 &middot; 취합 &middot; 발송)은 자동화하고,
    위험한 것(합불 판단)은 사람에게 남긴다.
    이 원칙이 아래 기능 요구사항 전체를 관통하고,
    "최종 합불은 사람이 확정한다"(ADR-0003 &rarr; 0034)는 제약으로 박혀 있다.
  </p>

</div>

<div class="req__sec">

  <h2><span class="req__num">2.</span> 기능 요구사항</h2>

  <p class="req__sub">2-1. 개발 범위 &mdash; 요구 ID 9건</p>
  <p class="req__note">
    사업 단위의 개발 범위다. 각 항목에 <b>검수 기준을 수치로 붙였다</b> &mdash;
    "구현했다"가 아니라 "무엇을 보면 됐다고 할 수 있는가"를 먼저 정하지 않으면
    완료 판정이 사람마다 달라지기 때문이다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>요구 ID</th><th>기능</th><th>검수 기준</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="req__id">SFR-001</td>
        <td>이력서 파싱 &mdash; PDF/DOCX 업로드 시 이름 &middot; 학력 &middot; 경력 &middot; 기술스택 자동 추출</td>
        <td>주요 필드 추출 정확도 90% 이상</td>
      </tr>
      <tr>
        <td class="req__id">SFR-002</td>
        <td>칸반 보드 &mdash; 지원자 카드를 드래그하여 채용 단계 전환</td>
        <td>상태 전환 시 DB 반영 200ms 이내</td>
      </tr>
      <tr>
        <td class="req__id">SFR-003</td>
        <td>Tool-Calling Agent &mdash; 자연어 명령으로 지원자 검색 &middot; 조회 &middot; 단계 변경 &middot;
            면접관 배정 &middot; 일정 제안 &middot; 메일 초안/발송 &middot; 이력서 드롭 접수</td>
        <td>도구 <b>12종</b> · 쓰기 도구는 확인 카드 필수 · 회귀 하네스 40시나리오 ·
            동일 채점기 23건 기준 Claude 69.6% / 자체학습 v9 73.9% (2026-09-17)</td>
      </tr>
      <tr>
        <td class="req__id">SFR-004</td>
        <td>RAG 질의응답 &middot; 시맨틱 검색 &mdash; 이력서 &middot; 자소서 &middot; 공고 기반 의미 검색
            (ko-sroberta + pgvector, ADR-0021)</td>
        <td>키워드 폴백 병행 · <code>search_mode</code> 로 벡터 가동 여부를 응답에 노출</td>
      </tr>
      <tr>
        <td class="req__id">SFR-005</td>
        <td>지원자 관리 &mdash; 지원자 CRUD, 검색 &middot; 필터링, 채용 단계별 목록 조회</td>
        <td>전체 CRUD 정상 동작, 커서 페이지네이션 · <b>10만 건 111ms &rarr; 7.8ms</b></td>
      </tr>
      <tr>
        <td class="req__id">SFR-006</td>
        <td>이메일 알림 &mdash; 채용 단계 변경 시 자동 이메일 발송 (n8n 웹훅 + SMTP, ADR-0030)</td>
        <td>n8n 장애 시 API 가 5분마다 재발송(최대 3회) · SES &middot; SQS 는 폐기(ADR-0031 &middot; 0036)</td>
      </tr>
      <tr>
        <td class="req__id">SFR-007</td>
        <td>자동 서류 심사 &mdash; 3축(자격요건 &middot; 우대사항 &middot; 인재상) 100점 채점 &rarr;
            임계 기준 자동 단계 이동 (ADR-0034)</td>
        <td>자료 부족 자동 탈락 · 사람 개입 시 자동 판정 제외 ·
            fit-check <b>24명</b> 정확성 분석으로 가중치 개정</td>
      </tr>
      <tr>
        <td class="req__id">SFR-008</td>
        <td>AI 면접 &middot; 실시간 분석 &mdash; 맞춤 질문 &middot; 음성 STT &middot; 답변&harr;서류 대조 &middot;
            1:1 WebRTC &middot; 표정/음성 참고 지표 (ADR-0029 &middot; 0032 &middot; 0038)</td>
        <td>참고 지표는 점수 &middot; 합불에 미반영 · 실시간 STT 는 서버 내 로컬 전사</td>
      </tr>
      <tr>
        <td class="req__id">SFR-009</td>
        <td>제출물 무결성 원장 &mdash; SHA-256 해시 사슬 &middot; DB 트리거 수정/삭제 거부 &middot;
            Sepolia 앵커 (ADR-0028)</td>
        <td>트리거 상태 변경은 감사 로그 · 서명 키는 서버 밖</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="req__sub">2-2. 필수 27기능</p>
  <p class="req__note">
    전체 기능 목록은 <b>80개</b>이고, 이를 <b>● 필수 27 / ○ 권장 30 / △ 여유 23</b>으로 나눴다.
    필수 27은 기획 시점(2026. 08. 24.)에 판단한 <b>4주의 현실적 상한</b>이다 &mdash;
    "다 하고 싶다"가 아니라 "이것만 되면 제품이라 부를 수 있다"의 선이고,
    게이트 판정과 QA 시나리오가 이 27개를 그대로 쓴다.
    아래가 그 전체 목록이다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>영역</th><th>번호</th><th>기능</th><th>비고</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="req__grp" rowspan="3">A. 인증 &middot; 권한</td>
        <td class="req__fnum">A1</td>
        <td>회원가입 / 로그인 (JWT)</td>
        <td>토큰 12시간 · 비활성 계정은 발급된 토큰도 401</td>
      </tr>
      <tr>
        <td class="req__fnum">A2</td>
        <td>역할 구분 &mdash; <b>관리자 / 멤버</b></td>
        <td><span class="tag tag--rev">개정</span> 원안은 관리자/채용담당자/면접관 3종,
            2026. 08. 31. ADR-0017 로 2종화</td>
      </tr>
      <tr>
        <td class="req__fnum">A3</td>
        <td>역할별 <b>조작</b> 제어</td>
        <td><span class="tag tag--rev">개정</span> 원안의 "면접관은 배정된 지원자만 조회" 폐지 —
            조회는 로그인 전체 허용, 제한은 조작에만(ADR-0017)</td>
      </tr>

      <tr>
        <td class="req__grp" rowspan="3">B. 채용 공고</td>
        <td class="req__fnum">B1</td>
        <td>공고 생성 / 수정 / 삭제</td>
        <td>&mdash;</td>
      </tr>
      <tr>
        <td class="req__fnum">B2</td>
        <td>공고 상태 &mdash; 임시저장 / 진행중 / 마감</td>
        <td>진행중 공고만 공개 지원 링크가 활성화된다</td>
      </tr>
      <tr>
        <td class="req__fnum">B3</td>
        <td>공고별 지원자 수 집계</td>
        <td>&mdash;</td>
      </tr>

      <tr>
        <td class="req__grp" rowspan="3">C. 지원 (지원자용)</td>
        <td class="req__fnum">C1</td>
        <td>지원서 제출 폼 (로그인 없이)</td>
        <td>공개 링크 <code>/public/postings/{id}</code></td>
      </tr>
      <tr>
        <td class="req__fnum">C2</td>
        <td>이력서 파일 업로드</td>
        <td>presigned URL 로 브라우저 &rarr; S3 직접 업로드</td>
      </tr>
      <tr>
        <td class="req__fnum">C3</td>
        <td>개인정보 수집 동의</td>
        <td>미체크 시 제출 거부</td>
      </tr>

      <tr>
        <td class="req__grp" rowspan="6">D. 지원자 관리</td>
        <td class="req__fnum">D1</td>
        <td>지원자 목록 (테이블 뷰)</td>
        <td>이름 &middot; 단계 &middot; 경력 &middot; 스펙 &middot; 평점 &middot; 지원일</td>
      </tr>
      <tr>
        <td class="req__fnum">D2</td>
        <td>칸반 보드 (단계별 컬럼)</td>
        <td>접수 / 서류 / 면접 / 최종 합격 / 불합격 5컬럼</td>
      </tr>
      <tr>
        <td class="req__fnum">D3</td>
        <td>드래그로 단계 이동</td>
        <td>실패 시 원위치 복귀 + 토스트 (낙관적 업데이트 롤백)</td>
      </tr>
      <tr>
        <td class="req__fnum">D4</td>
        <td>지원자 상세 페이지</td>
        <td>&mdash;</td>
      </tr>
      <tr>
        <td class="req__fnum">D5</td>
        <td>단계 변경 이력 기록 (누가 / 언제 / 어디서 어디로)</td>
        <td><code>changed_by=NULL</code> 은 시스템 자동 판정</td>
      </tr>
      <tr>
        <td class="req__fnum">D6</td>
        <td>담당자가 지원자 직접 등록</td>
        <td>&mdash;</td>
      </tr>

      <tr>
        <td class="req__grp" rowspan="2">E. 평가</td>
        <td class="req__fnum">E1</td>
        <td>평가 코멘트 작성 (점수 + 텍스트)</td>
        <td>멤버는 <b>배정된 건만</b> 작성 가능 (미배정 403)</td>
      </tr>
      <tr>
        <td class="req__fnum">E2</td>
        <td>평가 목록 조회, 평균 점수 계산</td>
        <td>&mdash;</td>
      </tr>

      <tr>
        <td class="req__grp" rowspan="2">F. 파일</td>
        <td class="req__fnum">F1</td>
        <td>이력서 업로드 &rarr; S3 저장</td>
        <td>API 서버를 경유하지 않는다</td>
      </tr>
      <tr>
        <td class="req__fnum">F2</td>
        <td>presigned URL 다운로드</td>
        <td>&mdash;</td>
      </tr>

      <tr>
        <td class="req__grp" rowspan="3">G. 알림 &middot; 메일</td>
        <td class="req__fnum">G1</td>
        <td>단계 변경 시 지원자에게 메일 발송</td>
        <td>&mdash;</td>
      </tr>
      <tr>
        <td class="req__fnum">G2</td>
        <td>메일 발송 비동기 처리</td>
        <td><span class="tag tag--rev">개정</span> 원안 SQS + 워커 &rarr;
            n8n 웹훅 + SMTP (ADR-0030 &middot; 0036). 화면 응답이 메일을 기다리지 않는다는 요구는 동일</td>
      </tr>
      <tr>
        <td class="req__fnum">G3</td>
        <td>발송 실패 시 재시도</td>
        <td>API 가 5분마다 재발송, 최대 3회 초과는 <code>failed</code></td>
      </tr>

      <tr>
        <td class="req__grp" rowspan="2">H. 검색 &middot; 필터</td>
        <td class="req__fnum">H1</td>
        <td>이름 / 이메일 검색</td>
        <td>더미 10만 건 기준 인덱스 튜닝 대상</td>
      </tr>
      <tr>
        <td class="req__fnum">H2</td>
        <td>단계별 필터</td>
        <td>&mdash;</td>
      </tr>

      <tr>
        <td class="req__grp" rowspan="3">J. 시스템 &middot; 운영</td>
        <td class="req__fnum">J1</td>
        <td>Docker 컨테이너 구성</td>
        <td><code>docker compose up</code> 으로 API &middot; DB 기동, <code>/health</code> 응답</td>
      </tr>
      <tr>
        <td class="req__fnum">J2</td>
        <td>AWS 배포</td>
        <td>공개 URL 접속 + 헬스체크 정상</td>
      </tr>
      <tr>
        <td class="req__fnum">J3</td>
        <td>API 문서 (Swagger)</td>
        <td><code>/docs</code> 에서 전체 엔드포인트 조회 &middot; Try it out</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="req__note" style="margin-top:1.1rem;">
    <b>영역 I(통계) 에는 필수가 하나도 없다.</b> 통계 5개는 전부 권장 &middot; 여유로 밀었다 &mdash;
    I1 &middot; I2 가 권장, I3 &middot; I4 &middot; I5 가 여유이고
    "통계 대시보드는 여유가 생기면 여기부터 착수"가 기획 시점의 명시적 결정이었다.
  </p>

  <p class="req__sub">2-3. 구현 현황 (2026. 09. 22. 기준)</p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>구분</th><th>개수</th><th>현황</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="req__grp">● 필수</td>
        <td>27</td>
        <td><b>27/27 구현</b> <span class="tag tag--done">달성</span> &mdash;
            2026. 09. 03. 달성 이후 유지</td>
      </tr>
      <tr>
        <td class="req__grp">○ 권장</td>
        <td>30</td>
        <td>09. 03. 기준 22/30. 이후 ADR 편입 범위로 확장 진행</td>
      </tr>
      <tr>
        <td class="req__grp">△ 여유</td>
        <td>23</td>
        <td>09. 03. 기준 0/23. 이후 ADR 편입 범위로 확장 진행</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="req__p" style="margin-top:1.1rem;">
    필수 27이 09. 03. 에 전부 끝났기 때문에, 이후의 개발은 <b>기획서 밖의 범위를 ADR 로 정식 편입하는 방식</b>으로
    진행됐다. 그렇게 편입되어 배포까지 끝난 것은 &mdash; 도구 호출 에이전트(확인 카드 &middot; 비용 관측 &middot;
    규칙 라우터 $0), 요약&rarr;평가&rarr;추천 3단 체인과 자동 서류 심사(ADR-0034),
    RAG 시맨틱 검색(ADR-0021), 면접 일정 자동화와 FAQ 챗봇,
    AI 면접(1:1 화상 &middot; STT &middot; 표정/음성 참고 지표, ADR-0029 &middot; 0032 &middot; 0038),
    인적성 설문(ADR-0027), 지원자 로그인(ADR-0033),
    제출물 무결성 원장과 Sepolia 앵커(ADR-0028), 헥사고날 재편(ADR-0035), 심사위원 데모 계정이다.
  </p>

  <p class="req__sub">2-4. 명시적으로 제외한 요구사항</p>
  <p class="req__note">
    <b>"안 한 것"에도 문서를 남겼다.</b> 못 만들어서 뺀 것과 안 만드는 게 맞다고 판단해서 뺀 것은
    완전히 다른 결정이고, 후자는 근거를 남기지 않으면 증명할 방법이 없기 때문이다.
    아래 열 건 중 일곱은 ADR 이고, 실시간 화상면접 &middot; SNS 크롤링 &middot; 면접관 모방 모델
    셋은 ADR 번호 없이 기획 문서(<code>docs/04_planning/</code>)에 근거가 남아 있다.
    개정할 때도 원문을 지우지 않고 절을 덧붙인다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>항목</th><th>원 결정과 근거</th><th>현재</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="req__grp">Kubernetes</td>
        <td>제외 &mdash; "한 달 안에 실제로 굴렸다고 말할 수 없는 것은 넣지 않는다" (ADR-0001)</td>
        <td><span class="tag tag--drop">제외 유지</span> EC2 1대 + Docker Compose</td>
      </tr>
      <tr>
        <td class="req__grp">표정 분석</td>
        <td>제외 &mdash; 직무성과 예측 기여 0.25% 미만, 차별 위험,
            HireVue 가 2021. 03. 폐기 (ADR-0002)</td>
        <td><span class="tag tag--rev">개정 도입</span> ADR-0029 &mdash;
            담당자 참고 지표까지만, 점수 재료 아님. 원 근거는 문서에 그대로 남김</td>
      </tr>
      <tr>
        <td class="req__grp">AI 자동 합불 판정</td>
        <td>AI 는 추천까지만 (ADR-0003)</td>
        <td><span class="tag tag--rev">개정</span> ADR-0034 &mdash; 서류 단계는 AI 자동 판정,
            <b>최종 합불만 사람</b>. 안전장치 셋(이력 &middot; 일괄 메일 &middot; 수동 우선)</td>
      </tr>
      <tr>
        <td class="req__grp">실시간 화상면접</td>
        <td>제외 &mdash; 견적(시그널링 + TURN + SFU 4주)은 3인 이상이 전제였다</td>
        <td><span class="tag tag--rev">1:1 만 도입</span> 둘이면 SFU 없이 P2P.
            3인 이상 다자 화상면접은 그대로 제외이고,
            <b>집단 면접(지원자 여러 명 + 면접관 1명)은 시연 뒤 ADR 로 다시 본다</b></td>
      </tr>
      <tr>
        <td class="req__grp">음성 감정 분석 ·<br>인적성 성격 판정</td>
        <td>재서술 &middot; 전사까지만 (ADR-0026 &middot; 0027)</td>
        <td>음성 신호는 참고 지표로 표시(점수 미반영) · <b>성격 판정 금지 유지</b></td>
      </tr>
      <tr>
        <td class="req__grp">지원자 SNS 크롤링</td>
        <td>제외 &mdash; 채용절차법 제4조의3 &middot; 개인정보보호법 제15조 위반,
            플랫폼 약관 위반도 별도로 발생</td>
        <td><span class="tag tag--drop">제외 유지</span></td>
      </tr>
      <tr>
        <td class="req__grp">실시간 공동 편집</td>
        <td>제외 (ADR-0005) &mdash; 메모는 행 추가 방식으로 대체</td>
        <td><span class="tag tag--drop">제외 유지</span></td>
      </tr>
      <tr>
        <td class="req__grp">면접관 모방 모델</td>
        <td>제외 &mdash; 면접관 성향 학습은 그 사람의 편향까지 복제한다.
            Amazon 이 2018년 같은 구조로 만든 채용 AI 를 폐기한 사례가 있고,
            면접관 1명의 연간 면접 수로는 표본도 안 된다
            (<code>docs/04_planning/01-시장조사-방향성.md</code> §5)</td>
        <td><span class="tag tag--drop">제외</span> 대신 성향을 <b>드러내는</b> 캘리브레이션
            (기능 목록 I5) 방향으로 뒤집음</td>
      </tr>
      <tr>
        <td class="req__grp">SQS 워커 &middot; SES</td>
        <td>초기 메일 경로</td>
        <td><span class="tag tag--drop">폐기</span> ADR-0031 &middot; 0036 &mdash;
            n8n + SMTP 로 전환, 스위치 3개로 공급자 교체 가능</td>
      </tr>
      <tr>
        <td class="req__grp">온프레미스 자체 서빙</td>
        <td>계획 (ADR-0024)</td>
        <td><span class="tag tag--drop">구축 후 폐쇄</span> 로컬 sLLM 의 도구 오호출 &middot;
            예시 베끼기 &middot; JSON 깨짐이 심사 직전 누적. Qwen 어댑터는 R&amp;D 자산으로 보존</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="req__sec">

  <h2><span class="req__num">3.</span> 비기능 요구사항</h2>
  <p class="req__note">
    성능 &middot; 보안 &middot; 가용성 &middot; 확장성 네 축이다.
    <b>축마다 검수 기준을 수치나 동작으로 정의했고, 실측값이 있으면 실측값을 적었다</b> &mdash;
    "빠르다" &middot; "안전하다"는 판정할 수 없는 문장이기 때문이다.
    가용성 항목은 대부분 설계가 아니라 <b>실제 사고가 남긴 장치</b>다.
  </p>

  <p class="req__sub">3-1. 성능 (PER)</p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>요구 ID</th><th>항목</th><th>검수 기준 · 실측 (2026. 09. 22.)</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="req__id">PER-001</td>
        <td>지원자 검색 &middot; 필터</td>
        <td>더미 <b>10만 건</b> 기준 인덱스 튜닝 실측 <b>111ms &rarr; 7.8ms</b></td>
      </tr>
      <tr>
        <td class="req__id">PER-002</td>
        <td>실시간 면접 STT</td>
        <td>오디오 청크 <b>1.5초 예산</b> 안에 전사 (GPU 실측 275ms / 3초 음성 · API 경로)</td>
      </tr>
      <tr>
        <td class="req__id">SFR-002</td>
        <td>칸반 단계 전환</td>
        <td>상태 전환 시 DB 반영 <b>200ms 이내</b></td>
      </tr>
      <tr>
        <td class="req__id">G2</td>
        <td>메일 발송 비동기</td>
        <td>단계 변경 API 가 메일 발송 완료를 기다리지 않고 즉시 응답</td>
      </tr>
    </tbody>
  </table>
  </div>

  <div class="nfr" style="margin-top:1.2rem;">
    <div class="nfr__head">
      <span class="nfr__axis">성능</span>
      <span class="nfr__one">부하를 만들어 놓고 재는 것이 요구사항이다</span>
    </div>
    <div class="nfr__body">
      <ul>
        <li>성능 요구는 <b>더미 지원자 10만 건을 먼저 만들고(J7) 그 위에서 측정</b>하는 것을 전제로 했다.
            데이터가 수십 건일 때는 인덱스가 있으나 없으나 같은 속도가 나오므로 요구사항이 성립하지 않는다.</li>
        <li>목록 조회는 offset 이 아니라 <b>커서 페이지네이션</b>을 요구한다 &mdash;
            뒤 페이지로 갈수록 느려지는 구조를 애초에 만들지 않기 위함이다.</li>
        <li>AI 원가도 성능 지표로 관측한다 &mdash; 호출마다 모델명 &middot; 토큰을 로깅하고,
            실측 <b>아르 호출당 $0.0075</b>, 인사 &middot; 능력 &middot; 기본 FAQ 는
            규칙 라우터가 LLM 없이 <b>$0</b> 로 처리한다. 대량 더미 데이터에는 AI 호출을 금지한다.</li>
        <li>실시간 면접의 성능 요구는 CPU 에서 충족되지 않았다 &mdash;
            t3.large(2 vCPU)에서 44초 발화가 180초를 넘겼고, 8명 동시 부하에서 STT 대기가
            15초 &rarr; 42초로 늘었다. GPU 이관과 API 경로 전환(ADR-0038)으로 대기줄 0을 만들었다.</li>
      </ul>
    </div>
  </div>

  <p class="req__sub">3-2. 보안 &middot; 개인정보 (SEC)</p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>요구 ID</th><th>항목</th><th>검수 기준</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="req__id">SEC-001</td>
        <td>인증 &middot; 인가 &mdash; JWT 기반 인증, CORS 설정, 개인정보 암호화</td>
        <td>미인증 요청 401/403 차단, 개인정보 AES-256 암호화</td>
      </tr>
      <tr>
        <td class="req__id">SEC-002</td>
        <td>데이터 보안 &mdash; 이력서 파일 S3 암호화 저장, 접근 권한 IAM 기반 제어</td>
        <td>S3 SSE 활성화, IAM 정책 적용</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="req__note" style="margin-top:1rem;">
    <b>권한 모델 (RBAC)</b> &mdash; 등급은 둘뿐이고(ADR-0017), 위계가 아니라 <b>조작 권한의 유무</b>다.
    조회는 로그인만 하면 전부 허용된다 &mdash; 옛 "면접관은 배정된 지원서만" 규칙은 폐지됐다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>등급</th><th>권한 범위</th></tr>
    </thead>
    <tbody>
      <tr><td class="req__grp">admin</td>
          <td>면접관 배정 &middot; 해제 / 계정 생성 / 메일 템플릿 / 타인 가용 시간 &mdash; 이 넷이 admin 전용</td></tr>
      <tr><td class="req__grp">member</td>
          <td>그 외 전부 &mdash; 단 <b>평가 작성은 배정된 건만</b></td></tr>
      <tr><td class="req__grp">지원자</td>
          <td>링크 안 일회성 토큰 또는 이메일 + 생년월일 8자리 로그인(ADR-0033) &mdash; 담당자 화면과 분리</td></tr>
      <tr><td class="req__grp">시스템 &middot; n8n</td>
          <td>서비스 토큰(<code>/internal/*</code>) &mdash; 없으면 아예 호출하지 않는다</td></tr>
    </tbody>
  </table>
  </div>

  <div class="nfr" style="margin-top:1.2rem;">
    <div class="nfr__head">
      <span class="nfr__axis">보안 &middot; 개인정보</span>
      <span class="nfr__one">적용된 통제</span>
    </div>
    <div class="nfr__body">
      <ul>
        <li><b>JWT 12시간</b> · 비활성 계정은 <b>이미 발급된 토큰도 401</b> &mdash;
            퇴사자 토큰이 만료까지 살아 있는 구멍을 막기 위함이다.</li>
        <li><code>APP_ENV=production</code> 에서 <b>공개 회원가입 차단</b> · 기본 시크릿 사용 불가.
            오타나 미설정도 production 으로 잠기게 했다 &mdash; 안전한 쪽이 기본값이어야 한다.</li>
        <li>심사 데모 계정은 비밀번호 &middot; 역할 변경이 403 &mdash; 공유 계정을 서로 잠그지 못하게.</li>
        <li>이력서 파일은 presigned URL 로 브라우저에서 S3 로 직접 올라간다 &mdash;
            <b>파일이 API 서버를 거치지 않아 서버 부담과 유출 접점이 함께 줄어든다.</b></li>
        <li>시크릿은 서버 <code>.env</code> 에만 두고 <code>.env.example</code> 에는 키 이름만 남긴다.
            IAM 은 콘솔용 &middot; 서버 전용 유저로 분리하고 서버 유저는 최소 권한이다(ADR-0025).</li>
        <li><b>AI 프롬프트에 연락처 &middot; 주민번호를 넣지 않는다.</b>
            음성 경로는 <code>STT_BACKEND</code> 로 명시한다 &mdash;
            <code>openai</code> 면 외부 API 전송, <code>faster_whisper</code> 면 서버 내 로컬 전사(ADR-0038).</li>
        <li>사용자는 물리 삭제하지 않고 <b>비활성화만</b> 한다 &mdash;
            <code>changed_by</code> &middot; <code>evaluator_id</code> 로 박힌 이력을 삭제가 부수기 때문이다.</li>
        <li>제출물 무결성 &mdash; 이력서 &middot; 자소서의 SHA-256 을 추가 전용 원장에 해시 사슬로 쌓고,
            <b>DB 트리거가 UPDATE &middot; DELETE &middot; TRUNCATE 를 거부</b>한다.
            사슬 머리는 매일 Sepolia 에 앵커하고 <b>서명 개인키는 서버에 두지 않는다</b>(ADR-0028).</li>
      </ul>
    </div>
  </div>

  <p class="req__sub">3-3. 가용성</p>

  <div class="nfr">
    <div class="nfr__head">
      <span class="nfr__axis">가용성</span>
      <span class="nfr__one">대부분 설계가 아니라 사고가 남긴 장치다</span>
    </div>
    <div class="nfr__body">
      <ul>
        <li><b>메일 단일 장애점 제거</b> &mdash; n8n 이 웹훅을 받고 죽어 메일이 <code>queued</code> 로 남은 사고 이후,
            API 가 스스로 <b>5분마다 밀린 메일을 SMTP 로 재발송</b>한다(최대 3회, 초과는 <code>failed</code>).
            경로가 하나뿐일 때 n8n 이 멈추면 합불 통보가 통째로 멎었다.</li>
        <li><b>백업</b> &mdash; 매일 04:00 KST DB <code>pg_dump</code> &rarr; gzip 검증 &rarr; S3(최소 권한 PutObject),
            30일 자동 만료.</li>
        <li><b>경보 &middot; 외부 감시</b> &mdash; CloudWatch 사용자 지정 지표(디스크 &middot; 백업 나이 &middot; API 헬스)를
            SNS 메일로 받고, GitHub Actions 가 <b>15분마다 외부에서 헬스체크</b>해 실패 시 이슈를 자동으로 열고 닫는다.</li>
        <li><b>디스크 고갈 재발 방지</b> &mdash; 컨테이너 로그 상한 <b>20MB &times; 3</b>,
            배포 때 이미지 &middot; 캐시 prune, EBS 29 &rarr; 50GB. 디스크가 차서 배포가 멎은 사고의 후속이다.</li>
        <li><b>자동 복구</b> &mdash; EC2 시스템 상태 검사 실패 시 자동 복구 알람,
            컨테이너 <code>restart: unless-stopped</code>.</li>
        <li><b>부분 실패 허용</b> &mdash; pgvector 확장을 못 켜면 API 전체가 죽는 대신
            경고만 남기고 시맨틱 검색만 꺼진 채 기동한다.
            확장 하나 때문에 API 가 재시작 루프에 빠져 <code>/health</code> 가 502 였던 사고의 후속이다.</li>
        <li><b>멈춤을 실패로</b> &mdash; Docker 가 죽어 pytest 가 24분간 조용히 멈춘 뒤
            <code>pytest-timeout</code> 60초를 넣었다. 침묵은 성공도 실패도 아니라서 가장 늦게 발견된다.</li>
        <li><b>배포 안전망</b> &mdash; main 직접 push 는 브랜치 보호가 차단하고,
            CI 5잡이 전부 초록이어야 머지한다. main 머지 2분 뒤 자동 배포되므로
            <b>CI 빨간불 = 머지 불가</b>가 유일한 게이트다.</li>
      </ul>
    </div>
  </div>

  <p class="req__sub">3-4. 확장성</p>

  <div class="nfr">
    <div class="nfr__head">
      <span class="nfr__axis">확장성</span>
      <span class="nfr__one">바꿔 끼울 수 있게 만드는 것이 요구사항이다</span>
    </div>
    <div class="nfr__body">
      <ul>
        <li><b>클라이언트 추가가 서버 변경을 부르지 않는다</b> &mdash;
            React 웹 &middot; Flutter 앱이 같은 FastAPI API 를 쓰는 계약 중심 설계다.
            ERD &middot; API 문서를 코드와 <b>같은 커밋</b>에서 갱신하는 규칙이 이 계약을 지킨다.</li>
        <li><b>공급자 교체 가능</b> &mdash; 메일 &middot; 큐 &middot; 스토리지 &middot; STT &middot; 모델을
            환경변수 스위치로 바꾼다 &mdash;
            <code>MAIL_DISPATCH</code> &middot; <code>QUEUE_BACKEND</code> &middot;
            <code>S3_ENDPOINT_URL</code> &middot; <code>STT_BACKEND</code> &middot;
            <code>AGENT_*_BACKEND</code>. AWS 의존을 8종에서 <b>3종(EC2 &middot; S3 &middot; IAM)</b>으로 줄인 것도
            "AWS 를 떠나도 돌게" 하기 위함이다(ADR-0031 &middot; 0036).</li>
        <li><b>구조 확장</b> &mdash; 헥사고날 부분 적용 &mdash;
            Bounded Context 4개(hiring &middot; talent &middot; application &middot; interview) +
            포트/어댑터(ADR-0035). <code>models.py</code> 를 71개 파일이 직접 참조하던 상태를 해소한 것이 목적이다.
            Full DDD 는 하지 않는다.</li>
        <li><b>스키마 확장</b> &mdash; 이행은 alembic 리비전 <b>26개</b>로 관리하고,
            CI 가 모델 &harr; 이행 결과를 비교해 이행 누락을 잡는다(2026. 09. 17.).
            <code>git pull</code> 로는 DB 가 따라오지 않으므로
            <code>uv run alembic upgrade head</code> 한 줄로 전원이 따라올 수 있는 것이 규칙이다.</li>
        <li><b>현재 확인된 확장 제약</b> &mdash; 실시간 면접의 방 상태가 프로세스 메모리에 있어
            <b>API 워커를 1개로 묶어 둔 상태</b>다. Redis 이관으로 이 제약을 푸는 것이 프리즈 뒤 계획으로 남아 있다.
            집단 면접(지원자 여러 명 + 면접관 1명)도 ADR 단계다.</li>
      </ul>
    </div>
  </div>

  <p class="req__sub">3-5. 품질 &middot; 문서화 (QUA)</p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>요구 ID</th><th>항목</th><th>검수 기준 · 현황 (2026. 09. 22.)</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="req__id">QUA-001</td>
        <td>테스트 &mdash; 자동화</td>
        <td>CI 에서 push &middot; PR 마다 백엔드 pytest(실제 PostgreSQL + pgvector, alembic 이행 후) ·
            프론트 oxlint + tsc + build · 앱 <code>flutter test</code> · AI 서버 pytest 가
            <b>전부 초록이어야 머지</b>. 백엔드 <b>pytest 1,165건 통과</b></td>
      </tr>
      <tr>
        <td class="req__id">QUA-002</td>
        <td>문서화 &mdash; API</td>
        <td>FastAPI Swagger <code>/docs</code> 에서 전체 API 명세(<b>107 라우트</b>) 조회 가능</td>
      </tr>
      <tr>
        <td class="req__id">QUA-003</td>
        <td>문서화 &mdash; 스키마</td>
        <td>모델 &harr; alembic 이행 결과를 CI 가 비교해 이행 누락을 잡는다.
            ERD <b>테이블 28개</b>(v2.8)가 전원의 계약이다</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="req__sec">

  <h2><span class="req__num">4.</span> 사용자 시나리오</h2>
  <p class="req__note">
    필수 27기능을 <b>전제 &rarr; 절차 &rarr; 기대 결과</b> 형식의 시나리오 27건으로 풀어
    <code>docs/00_overview/qa-scenarios.md</code> 에 정리했고, 여기에 실패 케이스 7건을 더했다.
    시나리오는 <b>게이트 판정과 통합 리허설의 체크리스트</b>로 쓰인다 &mdash;
    "구현했다"는 주장 대신 "이 절차를 밟으면 이것이 보인다"로 완료를 판정하기 위함이다.
    아래는 행위자별 대표 시나리오 넷이다.
  </p>

  <div class="sc">
    <div class="sc__top">
      <span class="sc__code">C1 &middot; C2 &middot; C3 &middot; F1</span>
      <span class="sc__name">지원자가 로그인 없이 지원서를 낸다</span>
      <span class="sc__who">행위자 &mdash; 지원자 (외부, 비로그인)</span>
    </div>
    <div class="sc__row"><span class="sc__k">전제</span>
      <p class="sc__v">진행중 상태인 공고의 공개 지원 링크(<code>/public/postings/{id}</code>)를 브라우저에 열었다.
         로그인하지 않은 상태이고, PDF 이력서(5MB 이하)를 준비했다.</p></div>
    <div class="sc__row"><span class="sc__k">절차</span>
      <p class="sc__v">공고 정보를 확인하고 이름 &middot; 연락처 &middot; 이메일 &middot; 최종학력을 입력한다.
         이력서 첨부 영역에 파일을 끌어 놓는다. 개인정보 수집 동의를 체크하고 "지원서 보내기"를 누른다.</p></div>
    <div class="sc__row"><span class="sc__k">기대</span>
      <p class="sc__v">파일은 presigned URL 로 <b>브라우저에서 S3 로 직접</b> 올라가고(API 서버 미경유)
         진행률과 파일명 &middot; 용량이 표시된다. 제출 완료 화면이 뜨고,
         담당자가 해당 공고의 지원자 목록을 열면 방금 낸 지원자가 <b>"지원 접수" 단계</b>로 나타난다.
         동의를 체크하지 않으면 제출 자체가 되지 않는다.</p></div>
  </div>

  <div class="sc">
    <div class="sc__top">
      <span class="sc__code">D2 &middot; D3 &middot; D5 &middot; G1</span>
      <span class="sc__name">담당자가 칸반에서 카드를 끌어 단계를 옮긴다</span>
      <span class="sc__who">행위자 &mdash; 채용담당자</span>
    </div>
    <div class="sc__row"><span class="sc__k">전제</span>
      <p class="sc__v">지원자 목록 화면에서 보기 방식을 "칸반"으로 전환했다.
         접수 / 서류 / 면접 / 최종 합격 / 불합격 다섯 컬럼이 가로로 나열되고,
         각 지원자가 현재 단계 컬럼에 카드로 있다. 지원자의 이메일이 등록되어 있다.</p></div>
    <div class="sc__row"><span class="sc__k">절차</span>
      <p class="sc__v">"서류 검토" 컬럼의 카드를 "면접" 컬럼으로 끌어 놓는다.
         이어서 해당 지원자의 상세 화면에서 단계 이력을 확인한다.</p></div>
    <div class="sc__row"><span class="sc__k">기대</span>
      <p class="sc__v">카드가 옮겨지고 변경 이력이 <b>누가 / 언제 / 어디서 어디로</b> 형태로 시간순 기록된다.
         지원자에게 안내 메일이 발송되고 발송 기록이 남는다.
         실패하면 카드가 <b>원래 위치로 돌아가고</b> 토스트 알림이 뜬다 &mdash; 낙관적 업데이트의 롤백이다.
         전진은 한 칸씩만 가능하고, 역행은 항상 허용된다 &mdash;
         <b>사람이 AI 판정을 되돌리는 안전장치</b>이기 때문이다.
         불합격으로 옮길 때 사유가 없으면 422 다.</p></div>
  </div>

  <div class="sc">
    <div class="sc__top">
      <span class="sc__code">E1 &middot; E2 &middot; A3-2</span>
      <span class="sc__name">면접관이 배정된 지원자에게 평가를 남긴다</span>
      <span class="sc__who">행위자 &mdash; member 등급 사용자</span>
    </div>
    <div class="sc__row"><span class="sc__k">전제</span>
      <p class="sc__v">member 계정으로 로그인했다. 본인에게 배정된 지원자가 2명,
         배정되지 않은 지원자가 10명 있다.</p></div>
    <div class="sc__row"><span class="sc__k">절차</span>
      <p class="sc__v">지원자 목록 &middot; 평가 현황 &middot; 검색 화면을 확인하고,
         배정되지 않은 지원자의 상세도 연다. 배정된 지원자와 배정되지 않은 지원자
         각각에서 점수(1~5)와 코멘트 입력을 시도한다.</p></div>
    <div class="sc__row"><span class="sc__k">기대</span>
      <p class="sc__v"><b>조회는 12명 전원이 열린다</b> &mdash; 배정되지 않은 지원자의 상세 &middot; 이력 &middot;
         평가 &middot; 메모 &middot; 이력서도 정상 열람된다(ADR-0017 로 조회 제한 폐지).
         평가 작성은 배정된 건만 저장되고, 배정되지 않은 건은 <b>403</b> 과
         "본인에게 배정된 지원자만 평가할 수 있습니다" 안내가 나온다.
         점수를 고르지 않으면 등록 버튼이 비활성이다.
         면접관 2명이 4점 &middot; 5점을 남기면 상세에 두 건과 <b>평균 4.5</b>가 표시된다.
         로그아웃 상태에서 같은 URL 을 열면 401 이다.</p></div>
  </div>

  <div class="sc">
    <div class="sc__top">
      <span class="sc__code">A2 &middot; A3-3</span>
      <span class="sc__name">관리자만 할 수 있는 조작을 확인한다</span>
      <span class="sc__who">행위자 &mdash; admin / member</span>
    </div>
    <div class="sc__row"><span class="sc__k">전제</span>
      <p class="sc__v">admin 계정과 member 계정이 각각 있다.</p></div>
    <div class="sc__row"><span class="sc__k">절차</span>
      <p class="sc__v">member 계정으로 ① 면접관 배정 &middot; 해제 ② 남의 가용 시간 등록 &middot; 삭제
         를 시도한다. 같은 조작을 admin 계정으로 다시 한다.
         admin 계정에서는 설정 &rarr; 사용자 관리로 한 사용자의 역할을 멤버에서 관리자로 바꾼다.</p></div>
    <div class="sc__row"><span class="sc__k">기대</span>
      <p class="sc__v">member 는 둘 다 <b>403</b>, admin 은 성공한다.
         단 <b>본인 가용 시간은 member 도 등록 &middot; 삭제할 수 있다</b> &mdash;
         자기 일정은 자기 것이기 때문이다. 역할은 <b>관리자 / 멤버 2종</b>뿐이고
         변경한 역할이 목록에 반영된다.</p></div>
  </div>

  <p class="req__sub">4-1. 실패 케이스 7건</p>
  <p class="req__note">
    정상 흐름만 확인하면 <b>거절해야 할 것을 거절하는지</b>는 알 수 없다.
    실패 케이스는 기대 결과를 "에러가 난다"가 아니라 <b>안내 문구</b>까지, 정해진 것은
    <b>상태 코드</b>까지 적었다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>번호</th><th>상황</th><th>기대 결과</th></tr>
    </thead>
    <tbody>
      <tr><td class="req__fnum">F-1</td>
          <td>같은 공고에 같은 이메일로 중복 지원</td>
          <td>"이미 지원한 공고입니다" 안내 후 제출 거부(<b>409</b>). 기존 지원 기록은 변경되지 않는다</td></tr>
      <tr><td class="req__fnum">F-2</td>
          <td><code>.exe</code> 등 허용되지 않는 파일 형식 업로드</td>
          <td>업로드 거부 + 허용 형식(pdf &middot; docx &middot; hwp) 안내를 함께 표시</td></tr>
      <tr><td class="req__fnum">F-3</td>
          <td>50MB PDF 등 용량 초과 파일 업로드</td>
          <td>업로드가 <b>시작되지 않고</b> 최대 허용 용량을 함께 안내</td></tr>
      <tr><td class="req__fnum">F-4</td>
          <td>미배정 지원자 상세 URL 직접 입력</td>
          <td><span class="tag tag--rev">폐지</span> ADR-0017 로 조회 제한이 없어져
              <b>이 케이스는 더 이상 유효하지 않다.</b> 대체 확인 항목은 A3-2(평가 작성 403)</td></tr>
      <tr><td class="req__fnum">F-5</td>
          <td>마감된 공고에 지원 시도</td>
          <td>"마감된 공고입니다" 안내 후 제출 불가. 폼 자체가 비활성이거나 접수 불가 화면</td></tr>
      <tr><td class="req__fnum">F-6</td>
          <td>잘못된 비밀번호로 로그인</td>
          <td>"이메일 또는 비밀번호가 올바르지 않습니다" &mdash;
              <b>어느 항목이 틀렸는지 구분하지 않는다</b>(계정 존재 여부 노출 방지)</td></tr>
      <tr><td class="req__fnum">F-7</td>
          <td>필수 항목(이름)을 비우고 지원서 제출</td>
          <td>누락 항목을 지목한 안내 표시 후 제출 차단</td></tr>
    </tbody>
  </table>
  </div>

  <p class="req__sub">4-2. 시나리오 문서와 현재 구현의 차이</p>
  <p class="req__p">
    QA 시나리오 문서는 <b>2026. 08. 24. 작성된 초안</b>이고, 화면이 없던 시점이라
    확정되지 않은 UI 디테일에 "(화면 확정 후 갱신)" 표식이 붙어 있다.
    그 뒤 결정이 개정되면서 <b>시나리오 자체가 낡은 항목이 셋</b> 있다 &mdash;
    이것을 지우지 않고 남겨 두는 이유는, 무엇이 왜 바뀌었는지가 요구사항 이력이기 때문이다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>항목</th><th>초안 (08. 24.)</th><th>현재</th></tr>
    </thead>
    <tbody>
      <tr><td class="req__fnum">A2</td>
          <td>역할 3종 &mdash; 관리자 / 채용담당자 / 면접관</td>
          <td>2종 &mdash; admin / member (ADR-0017, 08. 31.)</td></tr>
      <tr><td class="req__fnum">A3 &middot; F-4</td>
          <td>면접관은 배정된 지원자만 조회</td>
          <td>조회 제한 폐지 &mdash; 제한은 <b>조작</b>에만. 확인 항목이 A3-1 &middot; A3-2 &middot; A3-3 으로 쪼개졌다</td></tr>
      <tr><td class="req__fnum">G2</td>
          <td>SQS 큐에 메시지가 들어가고 워커가 처리</td>
          <td>n8n 웹훅 + SMTP (ADR-0030 &middot; 0036). <b>"화면 응답이 메일을 기다리지 않는다"는 요구 자체는 동일</b>하고,
              그것을 만족시키는 수단만 바뀌었다</td></tr>
    </tbody>
  </table>
  </div>

  <p class="req__p" style="margin-top:1.2rem;">
    시나리오와 실제 배포본이 어긋나지 않는지는 사람 눈이 아니라 스크립트로 대조한다 &mdash;
    <code>check_public_contract.py</code> 가 배포본 OpenAPI 와 main 의 경로 &middot; 스키마 &middot; 인증을 비교하고,
    08. 31. 실측에서 <b>35/35 &middot; 62/62 일치</b>를 확인했다.
  </p>

</div>

<a class="req__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
