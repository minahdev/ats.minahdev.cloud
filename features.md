---
layout: default
title: 주요 기능 개발
permalink: /features/
---

<style>
.ftr { max-width: 64rem; margin: 2.5rem auto 4rem; }

.ftr__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 1.6rem; }
.ftr__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.ftr__crumb a { color: #9ca3af; }
.ftr__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; word-break: keep-all; }
.ftr__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

/* 규모 지표 타일 */
.ftr__stat {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(8.5rem, 1fr));
  gap: .6rem;
  margin-bottom: 2.25rem;
}
.ftr__tile { border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .85rem; }
.ftr__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.ftr__v { font-size: 1.05rem; font-weight: 700; color: #111827; word-break: keep-all; }
.ftr__v small { font-size: .78rem; font-weight: 400; color: #9ca3af; margin-left: .15rem; }

.ftr__lead { margin: 0 0 2.75rem; color: #374151; font-size: .92rem; line-height: 1.85; word-break: keep-all; }
.ftr__lead b { color: #111827; }

.ftr__sec { margin-bottom: 3.25rem; }
.ftr__sec > h2 {
  font-size: 1.05rem;
  color: #2a7ae2;
  margin: 0 0 1.1rem;
  padding-bottom: .5rem;
  border-bottom: 1px solid #e5e7eb;
  display: flex;
  gap: .5rem;
  align-items: baseline;
  flex-wrap: wrap;
  word-break: keep-all;
}
.ftr__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.ftr__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }
.ftr__p { margin: 0 0 1rem; color: #374151; font-size: .92rem; line-height: 1.8; word-break: keep-all; }
.ftr__p:last-child { margin-bottom: 0; }
.ftr__p code, .ftr__note code { font-size: .84rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

.ftr__h3 { margin: 1.8rem 0 .7rem; font-size: .92rem; font-weight: 700; color: #111827; word-break: keep-all; }
.ftr__h3:first-child { margin-top: 0; }

/* 사고 · 남은 것 카드 */
.ftr__box {
  border: 1px solid #e5e7eb;
  border-left: 3px solid #2a7ae2;
  border-radius: 6px;
  padding: .85rem 1rem;
  margin: 1.2rem 0 0;
}
.ftr__box--open { border-left-color: #d97706; background: #fffbeb; }
.ftr__box h4 {
  margin: 0 0 .35rem;
  font-size: .85rem;
  font-weight: 700;
  color: #111827;
  word-break: keep-all;
}
.ftr__box p { margin: 0 0 .5rem; font-size: .86rem; line-height: 1.75; color: #4b5563; word-break: keep-all; }
.ftr__box p:last-child { margin-bottom: 0; }
.ftr__box code { font-size: .8rem; background: rgba(0, 0, 0, .045); padding: .05rem .3rem; border-radius: 3px; }

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

/* 표 공통 — 개발 일정 페이지와 같은 값 */
.tbl__scroll { overflow-x: auto; padding-bottom: .3rem; }
.tbl { width: 100%; border-collapse: collapse; font-size: .87rem; min-width: 46rem; }
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
.tbl__path { white-space: nowrap; }
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
.tag--part { background: #fef3c7; color: #92400e; }
.tag--drop { background: #f3f4f6; color: #6b7280; }

.ftr__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }

@media (max-width: 34rem) {
  .ftr__stat { grid-template-columns: repeat(2, 1fr); }
}
</style>

<div class="ftr">

<div class="ftr__head">
  <p class="ftr__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 6. 주요 기능 개발</p>
  <h1>주요 기능 개발</h1>
  <p>기획 필수 27기능은 2026. 09. 03.에 27/27 구현을 달성해 유지 중이고,
     그 밖의 확장은 전부 ADR 로 편입해 배포했다 &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="ftr__stat">
  <div class="ftr__tile"><span class="ftr__k">필수 기능</span>
    <span class="ftr__v">27<small>/ 27 구현</small></span></div>
  <div class="ftr__tile"><span class="ftr__k">API 라우트</span>
    <span class="ftr__v">107<small>Swagger</small></span></div>
  <div class="ftr__tile"><span class="ftr__k">DB 테이블</span>
    <span class="ftr__v">28<small>ERD v2.8</small></span></div>
  <div class="ftr__tile"><span class="ftr__k">에이전트 도구</span>
    <span class="ftr__v">12<small>종</small></span></div>
  <div class="ftr__tile"><span class="ftr__k">화면</span>
    <span class="ftr__v">25+23<small>웹 · 앱</small></span></div>
  <div class="ftr__tile"><span class="ftr__k">백엔드 테스트</span>
    <span class="ftr__v">1,165<small>건 통과</small></span></div>
</div>

<p class="ftr__lead">
  아래 여섯 절은 목차의 소절 구성을 그대로 따른다. 실제로 만든 것은 이보다 갈래가 많아
  <b>기능 축과 소절이 1:1 이 아니다</b> &mdash; 채용 파이프라인 통합 관리는 1&middot;2절,
  이력서 이해와 자동 서류 심사는 3절, 도구 호출 에이전트 &lsquo;아르&rsquo;와 RAG 시맨틱 검색은 4절,
  면접 일정 자동화 &middot; 지원자 포털 &middot; AI 면접은 5절, 대시보드 &middot; 종합 평가 &middot;
  비용 관측은 6절에 나누어 넣었다. 웹&middot;앱 두 클라이언트와 운영&middot;모델 전략은 특정 절의 것이
  아니라 여섯 절 전체에 걸쳐 있어, 해당 기능을 설명하는 자리에서 함께 적었다.
  <b>기능마다 완료 여부를 절 제목 옆 뱃지로 표시</b>하고, 안 끝난 것은 안 끝났다고 적는다.
</p>

<div class="ftr__sec">

  <h2><span class="ftr__num">1.</span><span>채용 공고 등록 및 관리</span>
      <span class="tag tag--done">완료</span></h2>
  <p class="ftr__note">
    공고는 단순한 CRUD 가 아니라 <b>그 공고에 들어올 지원자의 심사 정책을 담는 그릇</b>이다.
    임계 점수 &middot; 자동 심사 on/off &middot; 기본 면접관 풀이 공고 행에 함께 저장된다(ADR-0034).
  </p>

  <p class="ftr__p">
    공고 CRUD(B1&ndash;B3)는 앱 오너 확정 전의 <b>전환기 백엔드 분담분</b>이라
    <span class="who who-c">민아 C</span> 가 맡았고, 지원자 목록 &middot; 상세 &middot; 단계 이력(D1&middot;D4&middot;D5)과
    담당자 직접 등록(D6)까지 한 묶음으로 2026. 08. 25.에 끝냈다(B2 #32 &middot; D1 #48 &middot; D6 #72).
    마감일 자동 마감과 공개 지원 링크(B4&middot;B6)는
    <span class="who who-b">우정 B</span> 가 08. 26.에 붙였다(PR #108 &middot; #109).
    상태는 <code>draft</code> &middot; <code>open</code> &middot; <code>closed</code> 셋이고,
    마감일을 과거 날짜로 넣으면 422 다. 공고 응답에는 <code>deadline</code> 과 계산값
    <code>d_day</code>(남은 일수, 마감일이 없으면 <code>null</code>)가 함께 실려 화면이 <code>D-12</code> 로 표시한다.
  </p>

  <p class="ftr__p">
    <b>마감과 만료는 크론이 아니라 조회 시점에 판정한다.</b> 배치가 도는 시각과 사람이 보는 시각이
    어긋나면 같은 공고가 두 화면에서 다르게 보이기 때문이다. 그래서 마감된 공고를 공개 경로로
    조회하면 그 자리에서 <b>410 Gone</b> 이 나가고, 지원서 제출도 같은 410 으로 막힌다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>기능</th><th>경로</th><th>규칙 · 근거</th></tr>
    </thead>
    <tbody>
      <tr>
        <td>공고 목록 · 생성</td>
        <td class="tbl__path"><code>GET&nbsp;/postings</code><br><code>POST&nbsp;/postings</code></td>
        <td>목록에 공고별 지원자 수를 함께 내린다 &mdash; 목록에서 상세로 들어가지 않고 적체를 본다</td>
      </tr>
      <tr>
        <td>수정 · 상태 변경 · 자동 심사 설정</td>
        <td class="tbl__path"><code>PATCH&nbsp;/postings/{id}</code></td>
        <td><code>pass_threshold</code>(0~100, 기본 60) · <code>screening_mode</code>(<code>auto</code>/<code>manual</code>) ·
            <code>interviewer_ids</code>(기본 면접관 풀, 보내면 통째로 교체). 심사 정책을 전역이 아니라
            <b>공고 단위</b>로 둔 이유는 직무마다 합격선이 다르기 때문이다 (ADR-0034)</td>
      </tr>
      <tr>
        <td>공개 지원 링크 발급 · 재발급</td>
        <td class="tbl__path"><code>POST&nbsp;/postings/{id}/public-link</code></td>
        <td>재발급하면 <b>이전 토큰이 즉시 무효</b>가 된다 &mdash; 유출된 링크를 끊는 유일한 수단이라
            무효화를 미루지 않는다 (B6)</td>
      </tr>
      <tr>
        <td>불합격 메일 일괄 발행</td>
        <td class="tbl__path"><code>POST&nbsp;/postings/{id}/send-rejections</code></td>
        <td>자동 판정은 메일을 즉시 보내지 않는다. <b>마감 전 번복 여지</b>를 남기려고 담당자가 마감 뒤
            일괄 발행한다. 이미 보낸 사람과 사람이 직접 불합격시킨 사람은 건너뛰고 <code>{queued}</code> 를 돌려준다</td>
      </tr>
      <tr>
        <td>공개 조회 (지원 폼)</td>
        <td class="tbl__path"><code>GET&nbsp;/public/postings/by-token/{token}</code></td>
        <td>로그인 없이 공고를 읽는 유일한 경로. 마감 410 · 없는 토큰이나 미공개는 404</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="ftr__p" style="margin-top:1.2rem;">
    화면 쪽에서는 09. 15.에 <b>공고 마감 &middot; 다시 열기 버튼</b>을 넣었다 &mdash; 최종 결과가 난 뒤
    담당자가 직접 닫는 동작이라 자동화하지 않고 사람의 클릭으로 남겼다. 앱에서는 공고 리스트가
    <b>첫 화면</b>이다(PR #145). 지원자 목록에서 시작하면 지금 어느 공고를 보는 중인지가 화면에
    남지 않아, 계층을 공고 &rarr; 그 공고의 지원자 &rarr; 상세로 세웠다. 공고 삭제는 되돌릴 수 없어
    수정 화면 하단에 두고 확인 시트를 한 번 더 띄운다(PR #9).
  </p>

</div>

<div class="ftr__sec">

  <h2><span class="ftr__num">2.</span><span>지원자 통합 관리</span>
      <span class="tag tag--done">완료</span></h2>
  <p class="ftr__note">
    메인 화면은 <b>지원자 칸반 보드</b>다. 카드를 끌어 단계를 옮기면 이력이 남고 메일이 나간다.
    단계 모델은 다섯, 그것을 지배하는 규칙은 여섯이다.
  </p>

  <p class="ftr__p">
    단계는 <code>applied</code> &rarr; <code>screening</code> &rarr; <code>interview</code> &rarr;
    <code>accepted</code> / <code>rejected</code> 다섯이다. 단계를 <b>DB enum 이 아니라 코드 상수 + 체크
    제약</b>으로 두고 전환 규칙은 서비스 레이어가 강제한다 &mdash; enum 을 쓰면 단계 하나를 늘리는 데
    스키마 이행이 필요해진다. 칸반 보드 UI(D2&middot;D3)와 공고별 지원자 화면 &middot; 상세 패널 &middot;
    일괄 단계 변경(D1&middot;D4&middot;D9)은 <span class="who who-d">소연 D</span> 가 만들었고,
    이후 API 클라이언트 &middot; 인증 배선과 함께 실연동을 붙이며 드래그 &middot; 토스트 안내까지
    넣었다(PR #131 &middot; #132 &middot; #134 &middot; #135 &middot; #140).
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>규칙</th><th>내용</th><th>그렇게 한 이유</th></tr>
    </thead>
    <tbody>
      <tr><td>전진은 한 칸씩</td><td>단계를 건너뛰는 전진은 허용하지 않는다</td>
          <td>건너뛴 단계의 이력과 메일이 통째로 비어 나중에 설명할 수 없다</td></tr>
      <tr><td>역행은 항상 허용</td><td>어느 단계에서든 되돌릴 수 있다</td>
          <td><b>사람이 AI 판정을 되돌리는 것이 유일한 안전장치</b>다</td></tr>
      <tr><td>불합격은 어느 단계에서든</td><td>단 <code>reason</code> 이 없으면 <b>422</b></td>
          <td>사유 없는 이력은 나중에 아무도 설명할 수 없다 (D8)</td></tr>
      <tr><td>서류 단계는 AI 가 자동 판정</td><td>사람이 한 번 손대면 그 지원자는 이후 자동 판정에서 빠진다</td>
          <td><b>수동이 항상 이긴다</b> &mdash; AI 가 사람의 결정을 덮으면 되돌릴 자리가 없다 (ADR-0034)</td></tr>
      <tr><td>일괄 변경은 전부 아니면 전무</td><td>한 번에 200명까지, 부분 실패는 전체 롤백(<b>409</b>)</td>
          <td>200명 중 30명만 바뀌면 담당자가 무엇이 됐는지 알 수 없다 (D9)</td></tr>
      <tr><td>사용자는 지우지 않는다</td><td>비활성화만 한다</td>
          <td><code>changed_by</code>·<code>evaluator_id</code> 로 박힌 이력을 물리 삭제가 부순다</td></tr>
    </tbody>
  </table>
  </div>

  <p class="ftr__h3">검색 &mdash; 10만 건에서 111ms → 7.8ms</p>
  <p class="ftr__p">
    더미 지원서 10만 건을 만들어 놓고 인덱스를 튜닝해 <b>검색 응답을 111ms 에서 7.8ms 로</b> 줄였다.
    전 공고를 가로지르는 통합 검색(<code>GET /applications</code>)은 커서 페이지네이션을 쓰고,
    <code>with_total=false</code> 를 주면 총 건수 집계를 건너뛰어 크게 빨라진다 &mdash; 커서로 넘기는
    화면은 총 건수를 쓰지 않기 때문이다(H4&middot;H5).
    <b>검색 범위는 이름 &middot; 이메일로 확정</b>했다. 자소서 본문 전문 검색은 한국어가 PostgreSQL 기본
    FTS 에서 형태소 분석이 안 되는 데다 자소서 5천 자 &times; 10만 건이면 인덱스 용량과 쓰기 비용이
    커져, <code>pg_trgm</code> GIN 인덱스 확장으로 미뤘다 &mdash; 스키마 변경이 아니라 인덱스 추가라
    미루는 비용이 없다.
  </p>

  <p class="ftr__h3">평가 &middot; 면접관 &middot; 메모</p>
  <p class="ftr__p">
    평가는 점수와 코멘트를 남기고 목록과 평균을 함께 낸다(E1&middot;E2). 권한은 두 등급뿐이라
    <b>조회는 로그인만 하면 전부 허용</b>하되, 평가 작성은 <code>member</code> 의 경우 배정된 건만
    가능하고 미배정이면 403 이다(ADR-0017). 면접관 배정은 <code>admin</code> 전용이고 중복 배정은
    멱등으로 무시한다. 배정 대상의 역할은 보지 않는다 &mdash; <b>누구나 면접관이 될 수 있다</b>는 것이
    ADR-0013 의 결론이다. 메모는 평가와 <b>별도 엔드포인트</b>다 &mdash; 점수가 없고, 지원자 한 명에
    여러 사람이 각자 행을 쌓기 때문이다.
  </p>

  <p class="ftr__h3">같은 API, 두 클라이언트</p>
  <p class="ftr__p">
    React 웹 25화면과 Flutter 앱 23화면이 <b>같은 FastAPI 를 쓴다.</b> 앱은 JWT 를
    <code>flutter_secure_storage</code>(Android Keystore)에 넣고, 조회 &middot; 단계 변경 &middot;
    평가 작성 &middot; 이력서 열람까지 웹과 같은 일을 한다. 앱의 단계 변경 시트는
    <code>backend/app/stages.py</code> 의 전이 규칙을 앱으로 옮겨 <b>갈 수 있는 단계만</b> 보여주고,
    메일 경고는 실제로 메일이 나가는 단계에만 띄우며, 불합격은 사유 없이 넘어가지 못하게 했다
    (PR #146, 앱 테스트 36 &rarr; 42개). 서버 규칙을 화면이 다시 해석하지 않고 그대로 옮긴 것이라,
    클라이언트가 하나 더 붙어도 서버가 달라지지 않는다.
  </p>

</div>

<div class="ftr__sec">

  <h2><span class="ftr__num">3.</span><span>이력서 파싱 및 자동 스크리닝</span>
      <span class="tag tag--done">완료</span></h2>
  <p class="ftr__note">
    접수 &rarr; 추출 &rarr; 3단 체인 요약 &rarr; 3축 채점 &rarr; 자동 단계 이동까지 한 줄로 이어져 있다.
    <b>최종 합불만 사람</b>이고, 서류 단계는 아르가 옮긴다(ADR-0003 &rarr; 0034).
  </p>

  <p class="ftr__h3">업로드 &mdash; 파일이 API 서버를 거치지 않는다</p>
  <p class="ftr__p">
    이력서는 presigned URL 로 <b>브라우저에서 S3 로 직접</b> 올라간다. 파일이 API 를 통과하지 않아
    서버 부담과 유출 접점이 함께 줄어든다. 업로드 시점에는 아직 지원서 행이 없으므로,
    제출 본문에 <code>files[]</code>(<code>s3_key</code>·<code>filename</code>·<code>size_bytes</code>·
    <code>content_type</code>·<code>kind</code>)를 함께 보내 그때 <code>files</code> 행을 만든다(F1 &rarr; C2).
  </p>

  <div class="ftr__box">
    <h4>사고 &mdash; 브라우저에서만 업로드가 조용히 막혔다</h4>
    <p>API 는 정상이고 서버 로그도 없는데 브라우저에서만 실패했다. 원인은 버킷 CORS 미설정이었다 &mdash;
      <b>CORS 는 브라우저만 검사</b>하므로 서버 간 PUT 은 통과해 드러나지 않았다. PUT &middot; 프론트
      출처 &middot; 헤더를 허용하고, &ldquo;프론트 주소가 늘면 여기에도&rdquo;를 문서 규칙으로 남겼다.</p>
  </div>

  <p class="ftr__h3">추출 &mdash; 실패해도 요약은 죽지 않는다</p>
  <p class="ftr__p">
    <code>app/agent/extractor.py</code> 가 S3 에서 파일을 받아 PDF &middot; DOCX &middot; HWPX 본문을
    뽑는다(구형 HWP 미지원). <b>어떤 실패도 <code>None</code> 폴백</b>이라 추출이 안 돼도 요약 자체는
    돌아간다. 로컬 처리라 LLM 비용이 들지 않고, 프롬프트 주입을 막으려 8천 자 상한을 걸었다.
    이 경로를 붙이기 전에는 요약이 지원 폼 필드만 읽어서 <b>이력서를 충실히 낸 지원자도
    &ldquo;제출물 부족&rdquo;이 나왔다</b>(PR #158).
  </p>
  <p class="ftr__p">
    폼에서 비운 학력 &middot; 경력 &middot; 기술스택은 이력서에서 추출해 채운다
    (<code>_fill_structured_fields</code>, <span class="who who-d">소연 D</span> PR #307).
    경력 연수를 확인할 수 없으면 지어내지 않고 <code>null</code> 을 돌려준다. 그리고
    AI 가 채운 값에는 <code>career_years_source="ai"</code> 표식을 남겨 화면에 <b>「AI 추정」 배지</b>로
    보인다 &mdash; 표식이 없으면 지원자 신고값과 구별되지 않아 공정성 문제가 된다.
  </p>

  <div class="ftr__box ftr__box--open">
    <h4>남은 것 &mdash; 요약을 재생성하면 「AI 추정」 표식이 사라진다</h4>
    <p>PR #311 로 후속 처리하기로 했으나 <b>머지되지 않았다.</b> 재생성을 거친 지원자는 추정값과
      신고값이 화면에서 다시 구별되지 않는다.</p>
  </div>

  <p class="ftr__h3">3단 체인과 3축 채점</p>
  <p class="ftr__p">
    요약&rarr;평가&rarr;추천을 한 번의 프롬프트가 아니라 <b>세 단계로 나눈다</b>(ADR-0022).
    1단계가 요지와 핵심 역량을 뽑고, 2단계가 자격요건 &middot; 우대사항 &middot; 인재상 3축으로
    점수와 강점/우려를 매기고, 3단계가 추천과 확인 질문을 낸다. 근거가 부족하면 지어내는 대신
    <b>&lsquo;판단 불가&rsquo;로 표시</b>하고, 어떤 모델이 만들었는지 태그로 남긴다.
    점수는 <code>applications.doc_score</code> 에 저장되고, 공고의 <code>pass_threshold</code> 이상이면
    아르가 <code>applied&rarr;screening&rarr;interview</code> 로, 미만이면 <code>rejected</code> 로 옮긴다.
    이때 이력의 <code>changed_by</code> 는 NULL(시스템 판정)이고 점수 사유가 함께 박힌다.
  </p>

  <p class="ftr__h3">가중치는 실측으로 고쳤다</p>
  <p class="ftr__p">
    fit-check 지원자 24명의 판정을 사람이 전수 검토해 <b>아슬한 세 케이스</b>를 찾아냈다 &mdash;
    요건이 우수한데 인재상 한 문구로 탈락 &middot; 1점 차이 탈락 &middot; 필수 요건을 통과했는데
    우대 부족으로 탈락. 인수인계에 적혀 있던 &ldquo;자동 불합격 3명&rdquo;도 실제로는 <b>8명</b>이었다.
    그 8명의 3축 점수를 각각 수치화한 리포트를 근거로 가중치를 고쳤다(PR #182).
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>축</th><th class="tbl__num">개정 전</th><th class="tbl__num">개정 후</th><th>이유</th></tr>
    </thead>
    <tbody>
      <tr><td>자격요건</td><td class="tbl__num">50</td><td class="tbl__num"><b>60</b></td>
          <td>직무를 할 수 있는가가 먼저다 &mdash; 강조</td></tr>
      <tr><td>우대사항</td><td class="tbl__num">20</td><td class="tbl__num"><b>10</b></td>
          <td>있으면 좋은 것이지 없다고 떨어질 것이 아니다 &mdash; 축소</td></tr>
      <tr><td>인재상</td><td class="tbl__num">30</td><td class="tbl__num">30</td>
          <td>유지. 대신 <b>요건 점수가 70 이상이면 인재상 하한 50</b> 규칙을 새로 넣어,
              요건 우수 지원자를 자소서 한 문구로 떨어뜨리지 않는다</td></tr>
    </tbody>
  </table>
  </div>

  <p class="ftr__p" style="margin-top:1.2rem;">
    아슬한 건을 위해 <code>hold</code>(보류) 상태를 두자는 안은 <b>팀장 결정으로 채택하지 않고</b>
    자동 판정을 그대로 유지했다. 개정은 자동 CD 로 배포했고, 기존 회사 프로파일 두 키는
    alembic <code>0020</code> 으로 갱신했다.
  </p>

  <p class="ftr__h3">자료가 없는 지원자</p>
  <p class="ftr__p">
    자소서가 1줄이거나 전부 미기재면 <b>분석할 것 자체가 없다.</b> 요약 결과가
    <code>insufficient=true</code> 면 <code>decide_document</code> 가
    <code>applied&rarr;screening&rarr;rejected</code> 로 옮겨 화면에 <b>「서류 탈락」</b> 라벨이 붙게 했다
    (PR #349 &middot; #351). <code>applied&rarr;rejected</code> 직행으로 두면 사유를 알 수 없는
    「불합격」으로 보이기 때문이다. 실제 역량이 있는 지원자(<code>insufficient=false</code>)는
    건드리지 않아 대량 탈락을 막았고, 대상 3명은 요약 재생성 없이 판정만 재실행해 <b>$0</b> 로 끝냈다.
  </p>

  <div class="ftr__box">
    <h4>사고 두 건 &mdash; 점수 수렴과 JSON 깨짐</h4>
    <p><b>전원 64~65점으로 수렴.</b> 온프레미스에서 요약을 재생성하니 모든 지원자가 요건 70 &middot;
      우대 40/50 &middot; 인재상 60 으로 나와 변별력을 잃었다. 원인은 프롬프트의 <b>출력 예시 숫자
      70/40/60 을 소형 모델이 그대로 베낀 것</b>이었다 &mdash; Claude 는 베끼지 않아 드러나지 않았다.
      v3 프롬프트에서 예시 숫자를 지우고 채점 구간표(85~100 / 65~84 / …)와 절차를 명시하니
      실측이 85 &middot; 85 &middot; 40 &middot; 15 로 갈렸고 Claude 의 78 &middot; 86 &middot; 44 와 같은 방향이었다.</p>
    <p><b>JSON 이 깨져 점수 NULL.</b> 56명 재생성 중 2명의 서류 점수가 비었다. 소형 모델이 문자열
      안에 이스케이프하지 않은 따옴표를 써서 파싱이 실패한 것으로, Ollama 의 format 스키마도 막지
      못했다. 파서에 문자열 내부 따옴표 복구 폴백을 넣어 <b>56/56 파싱 성공</b>.</p>
  </div>

  <p class="ftr__h3">제출물 무결성 원장</p>
  <p class="ftr__p">
    이력서 &middot; 자소서의 SHA-256 지문을 추가 전용 원장에 해시 사슬로 쌓고, <b>DB 트리거가
    UPDATE &middot; DELETE &middot; TRUNCATE 를 거부</b>한다. 사슬 머리는 매일 이더리움 Sepolia
    테스트넷에 앵커해 위&middot;변조를 외부에서 검증할 수 있게 했다(ADR-0028).
    <b>서명 개인키는 서버에 두지 않고</b> GitHub Actions 에 둔다 &mdash; 서버가 뚫려도 서명은 못 한다.
    화면에는 <span class="who who-c">민아 C</span> 가 상세 패널 첨부 아래에 무결성 배지를 붙여
    (PR #46), 앵커 게시 이후 제출물이 바뀌었는지 한눈에 보인다.
    운영 체인은 처음 Polygon Amoy 였으나 <b>무료 가스 수도꼭지 6곳이 전부 막혀</b> Sepolia 로 전환했다(PR #29).
    시연 데이터 정리를 위해 트리거를 임시 해제한 이력이 실제로 있었기 때문에, 트리거 상태 변경이
    반드시 흔적을 남기도록 감사 트리거 &middot; 이벤트 로그 &middot; 문서화 규칙 세 갈래를
    ADR-0028 §1.7 에 추가했다(PR #173). <b>원장은 잠긴 상태가 기본이고 우회는 마지막 수단</b>이다.
  </p>

</div>

<div class="ftr__sec">

  <h2><span class="ftr__num">4.</span><span>지원자&ndash;공고 매칭 추천</span>
      <span class="tag tag--done">완료</span></h2>
  <p class="ftr__note">
    매칭은 세 갈래로 구현했다 &mdash; 공고 요건으로 <b>점수를 매기는</b> 3축 채점(3절),
    의미로 <b>찾아내는</b> RAG 시맨틱 검색, 자연어 한 문장을 작업으로 <b>분해하는</b> 도구 호출
    에이전트 &lsquo;아르&rsquo;. 세 갈래 모두 추천까지이고 확정은 사람이 한다.
  </p>

  <p class="ftr__h3">RAG 시맨틱 검색 (ADR-0021)</p>
  <p class="ftr__p">
    스킬 &middot; 학력 &middot; 경력을 <code>ko-sroberta</code> 로 임베딩해 pgvector 에 768차원으로
    저장하고, &ldquo;Python 경험자&rdquo; 같은 의미 검색을 붙였다
    (<span class="who who-e">수택 E</span> PR #151). 키워드 검색을 버리지 않고 <b>폴백으로 병행</b>하며,
    응답의 <code>search_mode</code> 로 벡터가 실제로 돌았는지 화면에 노출한다 &mdash;
    확장이 꺼져 있을 때 조용히 키워드로 떨어지면 사용자가 왜 결과가 달라졌는지 알 수 없다.
    도입 직후 <b>스킬 배열의 정확 일치를 시맨틱 랭킹 최상위로 올려</b> &ldquo;Kubernetes&rdquo; 같은
    고유명사에서 의미가 비슷한 엉뚱한 지원자가 먼저 나오던 것을 원천 차단했다.
  </p>

  <div class="ftr__box">
    <h4>사고 &mdash; pgvector 확장 하나 때문에 API 전체가 안 떴다</h4>
    <p>재배포 직후 API 가 재시작 루프(<code>exit=3</code> · restarts=10)에 빠지고
      <code>/health</code> 가 502 였다. RAG 가 커넥션마다 <code>CREATE EXTENSION vector</code> 를 거는데
      운영 DB 이미지(<code>postgres:16-alpine</code>)에 확장이 없어 lifespan 이 죽은 것이다.
      <b>fix-forward</b> 로 &mdash; 확장을 못 켜면 경고만 남기고 시맨틱 검색만 꺼진 채 기동하게 바꾼 뒤,
      DB 이미지를 <code>pgvector/pgvector:pg16</code> 으로 교체했다(alpine musl &rarr; debian glibc 전환이라
      REINDEX 동반). 데이터는 무사했고, 로컬 compose 도 같은 이미지로 맞춰 재발을 막았다.</p>
  </div>

  <p class="ftr__h3">도구 호출 에이전트 &lsquo;아르&rsquo; &mdash; 도구 12종</p>
  <p class="ftr__p">
    &ldquo;김도현 찾아줘 &rarr; 면접 안내 이메일 만들어줘&rdquo; 같은 자연어를 검색 &middot; 조회 &middot;
    단계 변경 &middot; 면접관 배정 &middot; 일정 제안 &middot; 메일 초안 &middot; 이력서 드롭 접수로
    분해한다. 핵심은 실행 경계다 &mdash; <b>읽기 도구는 즉시 실행, 쓰기 도구는
    <code>pending_action</code> 으로 반환</b>되어 사람이 확인 카드를 승인해야
    <code>POST /agent/confirm</code> 으로 실행된다. 메일 발송도 이 경로를 탄다. 되돌릴 수 없는 조작에
    승인을 강제한 것이 이 기능의 설계 전부라고 해도 된다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>검증</th><th>내용</th><th>결과 · 실측</th></tr>
    </thead>
    <tbody>
      <tr><td>데모 4단계 E2E</td><td>검색 &rarr; 조회 &rarr; 단계 변경 &rarr; 이메일 초안, 로컬 서버 실호출</td>
          <td>4단계 전부 정상. 동명이인 2명 안내 · 후퇴 불가 안내 + 대안 · 초안은 <code>pending_action</code> 반환.
              비용 <b>$0.045</b></td></tr>
      <tr><td>엣지 8종</td><td>검색 0건 · 모호한 요청 · 잘못된 단계명 · 범위 밖 삭제 요청 · 멀티턴 3단계 ID 추적 ·
              특수문자(O&rsquo;Brien) 등</td>
          <td>8종 <b>전부 PASS</b>, 비용 <b>$0.083</b></td></tr>
      <tr><td>API 레벨 테스트</td><td>에이전트 4개 엔드포인트를 HTTP 로 &mdash; 기본 20 + 경계값 ·
              SQL injection · XSS · 권한 없는 접근 · 빈 입력 21</td>
          <td><b>41건</b> (PR #141). 에이전트 관련 테스트 포함 전체 185개 통과 시점 기록</td></tr>
      <tr><td>회귀 하네스</td><td>실서버 <code>/agent/chat</code> 시나리오 &mdash; 기본 10 + 변형 30</td>
          <td><b>40시나리오</b>. 모델·프롬프트를 바꿀 때마다 돌린다</td></tr>
    </tbody>
  </table>
  </div>

  <p class="ftr__p" style="margin-top:1.2rem;">
    긴 대화에서 <code>application_id</code> 를 엉뚱한 값(id=1)으로 참조하는 문제가 E2E 에서 잡혀,
    프롬프트에 규칙 두 줄을 넣었다 &mdash; <b>직전 도구 결과에서 확인된 ID 만 쓴다</b>,
    &ldquo;이 지원자&rdquo;는 최근 조회한 지원자를 가리킨다(PR #136).
    면접관을 이름으로 찾지 못하던 문제는 <code>search_users</code> 읽기 도구로 풀고, 프롬프트에
    <code>user_role</code> 을 주입해 <code>member</code> 가 admin 전용 도구(<code>assign_interviewer</code>)를
    요청하면 <b>도구를 부르기 전에 차단</b>한다(PR #153).
  </p>

  <p class="ftr__h3">무관한 질문과 비용</p>
  <p class="ftr__p">
    &ldquo;안드레 카파시가 누구야&rdquo; 같은 질문에 Claude 가 인물 설명을 <b>다 생성한 뒤 거절 문구를
    덧붙이던</b> 문제가 있었다. 거절 규칙이 &ldquo;정치 &middot; 연예 &middot; 주식&rdquo;처럼 카테고리
    열거식이라 인물 &middot; 상식 유형은 모델이 확률적으로 판단한 것이다. 판단 기준을
    <b>&ldquo;답의 근거가 우리 데이터냐&rdquo;</b>로 다시 쓰자, 외부 일반 지식은 내용 없이 한 문장으로
    거절하고 이력서 &middot; 자소서 속 인물 &middot; 프로젝트는 원문을 조회해 정상 답변한다(PR #353).
    비용 쪽은 &ldquo;안녕&rdquo;, &ldquo;뭘 할 수 있어&rdquo; 같은 정적 발화가 매번 LLM 을 타 호출당 약
    $0.02 씩 나가던 것을, 규칙 의도 라우터의 캔드 응답으로 우회했다 &mdash; 정규식을
    <code>^…$</code> 로 묶어 실제 요청이 붙으면 다시 LLM 으로 넘긴다.
    <b>실측 아르 호출당 평균 $0.0075, 인사 &middot; 능력 &middot; 사용법 같은 기본 질문은 $0</b> 다.
  </p>

  <p class="ftr__p">
    추천의 성격은 화면 문법으로도 못박았다 &mdash; <b>앰버 점선은 AI 제안, 실선은 사람 확정</b>이다.
    아르가 서류 단계를 옮겨도 <code>accepted</code> 는 사람만 만들 수 있고, 사람이 한 번 단계를
    옮기면 <code>decision_source=human</code> 이 되어 그 뒤로 자동은 손대지 않는다.
  </p>

</div>

<div class="ftr__sec">

  <h2><span class="ftr__num">5.</span><span>면접 일정 관리 및 알림</span>
      <span class="tag tag--done">완료</span> <span class="tag tag--part">잔여 결함 1건</span></h2>
  <p class="ftr__note">
    가용 시간 등록 &rarr; 후보 슬롯 제안 &rarr; 지원자 선택 &rarr; 확정 &rarr; 통보까지 전 구간이
    2026. 08. 31.에 배포 서버 E2E(가용 시간&rarr;배정&rarr;제안&rarr;공개 조회&rarr;확정&rarr;메일 렌더)로
    관통을 확인했다(ADR-0016).
  </p>

  <p class="ftr__p">
    면접관이 자기 가용 시간을 등록하면(본인 또는 admin), 배정된 면접관의 가용 시간에서 후보 슬롯이
    만들어지고 제안 메일이 큐에 들어간다. 지원자는 메일 링크의 공개 페이지에서 슬롯을 고르고,
    이미 확정 &middot; 만료 &middot; 취소된 제안이면 409 가 난다. 확정되면 통보 메일이 또 큐에 들어간다.
    <b>만료는 조회 시점에 판정</b>하고, 이미 나간 제안의 슬롯은 스냅샷이라 면접관이 가용 시간을
    지워도 영향받지 않는다 &mdash; 보낸 제안이 뒤에서 바뀌면 지원자가 본 화면과 서버가 갈린다.
    아르에는 일정 도구 4개(조회 &middot; 제안 &middot; 확정 &middot; 취소)를 붙여 자연어로도 같은 일을 한다
    (<span class="who who-e">수택 E</span> PR #150 &middot; #153 &middot; #157).
  </p>

  <p class="ftr__h3">지원자 쪽 &mdash; 24시간 접근</p>
  <p class="ftr__p">
    지원자 일정 페이지는 카드 + 정적 안내에서 <b>아르와의 대화형</b>으로 다시 만들었다(PR #157).
    PC 는 아르 캐릭터 + 일정 카드/채팅 2단, 모바일은 상단 고정 일정 카드(접기&middot;펴기) + 채팅이다.
    아르 얼굴은 3D 뷰어 스냅숏 PNG <b>12KB</b> 로 대체해 지원자 기기의 WebGL 부담을 없앴다.
    FAQ 는 <code>POST /public/schedule/{token}/faq</code> 로, 토큰 인증 &middot; stateless 1문1답이며
    <b>담당자용 아르와 완전히 별개 경로</b>다 &mdash; 지원자가 담당자 도구에 닿을 길을 아예 만들지 않았다.
    연봉 &middot; 평가 &middot; 다른 지원자 &middot; 회사 내부 절차는 답하지 않고, 프롬프트 주입을
    무시하는 것을 실호출로 확인했다. 실측 하네스 15 시나리오를 신설했고, 인사 &middot; 연봉 &middot;
    합격 가능성 &middot; 감사 인사는 규칙 응답으로 <b>$0</b> 다.
  </p>

  <p class="ftr__h3">메일 &mdash; 경로를 갈아엎고 재발송을 넣었다</p>
  <p class="ftr__p">
    문구는 <b>코드 기본값 + DB 오버라이드</b>다. 4종(<code>applied</code>·<code>interview</code>·
    <code>accepted</code>·<code>rejected</code>)만 있고, 허용하지 않은 치환 변수를 쓰면 422 로 막는다.
    발송 주체(<code>email_logs.actor_kind</code>)가 <b>From 표시 이름 &middot; 본문 서명 &middot; 회신
    주소 셋을 함께</b> 정한다 &mdash; 셋이 어긋나면 지원자가 누구에게 연락해야 할지 헷갈린다.
    발신 <b>주소</b>는 언제나 하나다. 담당자 개인 주소를 From 에 넣으면 외부 메일에서 DMARC 정렬이
    깨져 스팸함으로 가기 때문이고, 개인 연락처 역할은 Reply-To 가 맡는다.
    일괄 단계 변경에서도 <b>메일은 건별로 큐에 넣는다</b> &mdash; 지원자마다 이름과 공고가 달라
    한 통으로 묶을 수 없다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>시점</th><th>메일 경로</th><th>바꾼 이유</th></tr>
    </thead>
    <tbody>
      <tr><td>초기</td><td>API &rarr; SQS 큐 &rarr; 메일 워커 컨테이너 &rarr; SES</td>
          <td>&mdash;</td></tr>
      <tr><td>2026-09-07</td><td>n8n 컨테이너 도입 (ADR-0030 1단계)</td>
          <td>발송을 코드가 아니라 워크플로 노드로 분리하면 <b>노드 하나만 바꿔 공급자를 교체</b>할 수 있다.
              워크플로 JSON 은 저장소가 진실 &mdash; 화면에서 고쳤으면 내보내서 커밋한다</td></tr>
      <tr><td>현재</td><td>API &rarr; n8n 웹훅 &rarr; SMTP</td>
          <td>SQS &middot; SES 는 폐기(ADR-0031 &middot; 0036). AWS 사용 서비스를 8종에서 3종(EC2·S3·IAM)으로 줄였다</td></tr>
    </tbody>
  </table>
  </div>

  <div class="ftr__box" style="margin-top:1.2rem;">
    <h4>사고 &mdash; n8n 이 웹훅을 받고 죽어 메일이 <code>queued</code> 로 남았다</h4>
    <p>경로가 하나뿐이라 n8n 이 멈추면 합격 &middot; 불합격 통보가 통째로 멎는 <b>단일 장애점</b>이었다.
      API 가 스스로 <b>5분마다 밀린 메일을 SMTP 로 직접 재발송</b>하게 했다(최대 3회, 초과는
      <code>failed</code> 로 접어 사람이 확인). <span class="who who-b">우정 B</span> 09-17 작업.</p>
  </div>

  <p class="ftr__h3">면접 세션 링크</p>
  <p class="ftr__p">
    면접 세션을 만들면 지원자에게 링크 메일이 나간다(<code>notify</code> 기본 <code>true</code>).
    재발송은 새 세션이 아니라 <b>같은 세션 &middot; 같은 링크</b>를 다시 보내는 별도 경로다 &mdash;
    새 세션을 만들면 앱이 가장 먼저 만들어진 방으로 들어가 담당자와 갈린다.
    만료는 410, 이미 끝난 면접은 409 다. 그리고 링크를 만들자마자 지원자가 시작해도 422 가 나지
    않도록 <b>기본 질문 3개를 세션과 같은 커밋에</b> 먼저 넣고, 뒤에서 이력서 &middot; 자소서 기반
    맞춤 질문 최대 4개(09-12 에 10 &rarr; 4로 줄임)를 만들어 아직 시작 전이면 바꿔 넣는다.
  </p>

  <div class="ftr__box ftr__box--open">
    <h4>남은 것 &mdash; 면접관 자동 배정이 0명으로 떨어진다</h4>
    <p>프리즈(09-20) 시점에 <b>미해결</b>로 남은 결함이다. 담당은 백엔드.
      배정 자체는 수동으로 가능하므로 일정 조율 흐름 전체가 막히지는 않는다.</p>
  </div>

</div>

<div class="ftr__sec">

  <h2><span class="ftr__num">6.</span><span>채용 현황 대시보드 및 통계</span>
      <span class="tag tag--done">완료</span></h2>
  <p class="ftr__note">
    대시보드는 목록이 아니라 <b>현황판</b>이다. 2026. 09. 07.에 지원자 목록을 여기서 뺐다 &mdash;
    사람을 훑는 일은 &lsquo;지원자&rsquo; 탭이 이미 하고, 대시보드는
    &ldquo;회사가 지금 어떻게 돌아가나&rdquo;에만 답한다.
  </p>

  <p class="ftr__p">
    화면은 <b>위에서 아래로 얼마나 &rarr; 어디가 &rarr; 언제</b> 순이다. 부르는 API 는 셋뿐이고
    전부 다른 화면을 위해 이미 열려 있던 것이라 <b>백엔드 변경이 없었다.</b>
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>블록</th><th>데이터 출처</th><th>설계 판단</th></tr>
    </thead>
    <tbody>
      <tr>
        <td>전체 현황 &middot; 공고별 적체</td>
        <td class="tbl__path"><code>GET /postings</code><br>(<code>status</code>·<code>d_day</code>·<code>stage_counts</code>)</td>
        <td>막대는 <b>심사 중 3단(접수·서류·면접)만</b> 그린다. 합격·불합격은 한번 되면 영원히 쌓이는
            누적값이라 같은 자를 쓰면 시간이 갈수록 앞 세 칸이 실오라기가 된다 &mdash; 견줄 대상이 아니다.
            덤으로 두 색은 적록색약에서 ΔE 3.5 라 나란히 두면 경계가 보이지 않는다</td>
      </tr>
      <tr>
        <td>이번 주 면접</td>
        <td class="tbl__path"><code>GET /schedules?from&amp;to</code></td>
        <td>확정된 일정만 싣는다. 캘린더 화면과 같은 규칙으로 주 시작을 일요일로, 시간대를
            Asia/Seoul 로 고정했다 &mdash; 여기서만 다르면 같은 주가 두 화면에서 다르게 보인다</td>
      </tr>
      <tr>
        <td>지금 면접 중</td>
        <td class="tbl__path"><code>GET /interview-sessions/active</code></td>
        <td><code>in_progress</code> 만 낸다. 지원자 이름과 공고 제목을 같이 내려
            <b>대시보드가 한 번에 들어간다</b> &mdash; 없으면 지원자 목록&rarr;상세&rarr;세션&rarr;링크 넷을
            거쳐야 실시간 분석 화면에 닿는다. 이 블록은 <b>실패해도 화면은 뜬다</b></td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="ftr__p" style="margin-top:1.2rem;">
    표에 싣는 진행 중 공고는 <b>6개까지</b>이고 넘치면 잘라 &ldquo;외 n개&rdquo;를 단다 &mdash;
    스크롤을 만들면 현황판이 다시 목록이 된다. 09. 15.에는 &lsquo;내 배정 수&rsquo;
    (<code>GET /interviewers/{me}/applications</code>) 블록을 뺐다.
    경로 순서에도 함정이 하나 있었다 &mdash; <code>active</code> 를 <code>{id}</code> 아래에 두면
    <code>active</code> 가 id 로 읽혀 422 가 난다.
  </p>

  <p class="ftr__h3">종합 평가 &mdash; 점수를 한 화면에서</p>
  <p class="ftr__p">
    <code>GET /summary</code> 가 공고(최신순)마다
    <code>{id, title, status, applicant_count, applicants[]}</code> 를 주고, 지원자마다
    <code>doc_score</code> &middot; <code>doc_decision</code> &middot;
    <code>interview_ai_score</code>(최신 면접) &middot; <code>final_score</code> &middot;
    <code>grade</code>(S/A/B/C) &middot; <code>ai_summary</code> 와 최신 면접의 강점 &middot; 우려
    (각 최대 3개)를 싣는다. 페이지 없이 <b>전 공고를 한 번에</b> 준다 &mdash; 담당자가 여기서
    최종 합격 &middot; 불합격을 확정하므로 화면을 넘겨 가며 비교할 일이 없어야 한다.
    최종 점수는 서류&times;가중치 + 면접&times;가중치이고, 가중치 7개 &middot; 인재상 &middot;
    등급 경계는 <code>GET/PUT /settings/scoring</code> 으로 admin 이 바꾼다(가중치 합이 100 이
    아니어도 되며 합으로 나눈다). 화면 구성은 <span class="who who-c">민아 C</span> 가 대시보드 &middot;
    평가 현황을 시안대로 재구성하면서 함께 정리했다(PR #27 &middot; #28 &middot; #41 &middot; #43).
  </p>

  <p class="ftr__h3">통계는 코드가, 재서술만 AI 가</p>
  <p class="ftr__p">
    인적성(사전 성향) 설문은 10문항 5점 척도이고, <b>카테고리 통계는 코드가 계산</b>한다.
    아르는 응답을 관찰 문장으로 재서술만 하며 <b>성격 유형 판정 &middot; 점수화 &middot; 합불 의견을
    만들지 않고</b>, 미응답에 불이익도 없다(ADR-0027). 공고 단위 일괄 발송은 응답으로
    <code>{sent, skipped_already_sent, skipped_stage}</code> 를 돌려줘 <b>몇 건이 왜 빠졌는지 숫자로</b>
    남긴다.
  </p>
  <p class="ftr__p">
    면접 중 실시간 분석도 같은 원칙이다. <code>stats.overall</code> 과
    <code>stats.per_question[]</code>(판정 수 <code>n</code> · <code>truth</code> % ·
    표정 라벨별 비율 · <code>blink_per_sec</code> · <code>flags_pct</code> · 음성)을 수치로 쌓고,
    AI 가 그것을 한 문단으로 요약한다. 다만 <b>요약 문장에 <code>stats</code> 에 없는 숫자가
    나오거나 사람을 단정하는 단어가 나오면 그 문장을 버리고 고정 틀로 대체</b>하며,
    어느 쪽이었는지를 <code>summary_source</code> 로 구별한다. 표정(ViT + MediaPipe)과 음성 신호는
    <b>담당자 참고 지표일 뿐 점수 &middot; 합불 판정에 쓰지 않는다</b>(ADR-0029 &middot; 0032).
  </p>

  <p class="ftr__h3">비용도 지표다</p>
  <p class="ftr__p">
    채팅 &middot; 요약 &middot; STT 세 기능에 <b>토큰 &middot; 비용 로깅을 통일</b>했다. 응답의
    <code>model</code> 은 모델명이 아니라 <code>backend:model</code> 태그다 &mdash; 백엔드마다
    토크나이저가 달라 토큰 수를 그대로 비교할 수 없으므로 <b>어느 엔진이 낸 값인지 함께</b> 남긴다.
    로컬 백엔드는 프롬프트 캐싱 개념이 없어 캐시 토큰이 항상 0 인데, <code>backend</code> 필드가
    있어야 &lsquo;캐시 미적중&rsquo;과 &lsquo;캐시 개념 없음&rsquo;이 구분된다.
    실측은 <b>아르 호출당 평균 $0.0075</b>, 실시간 면접 세션당 약 <b>$0.05</b>(답변 10개 + 종료 시 1회),
    STT 는 분당 $0.006 으로 <b>면접당 약 $0.06</b> 이다. 대량 더미 데이터에는 AI 호출을 금지했다.
  </p>

</div>

<a class="ftr__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
