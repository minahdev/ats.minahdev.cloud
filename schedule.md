---
layout: default
title: 개발 일정
permalink: /schedule/
---

<style>
.sch { max-width: 60rem; margin: 2.5rem auto 4rem; }
.sch__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.sch__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; }
.sch__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

.sch__sec { margin-bottom: 3.25rem; }
.sch__sec > h2 {
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
.sch__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.sch__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }

/* 담당자 색 — 칸반 카드와 역할표에서 같은 색을 쓴다 */
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

/* 스프린트 타임라인 */
.sprint { border: 1px solid #e5e7eb; border-radius: 6px; overflow: hidden; }
.sprint__row {
  display: grid;
  grid-template-columns: 7.5rem 9.5rem 1fr;
  gap: 1rem;
  padding: .85rem 1rem;
  border-bottom: 1px solid #f3f4f6;
  align-items: start;
}
.sprint__row:last-child { border-bottom: 0; }
.sprint__row--head {
  background: #f9fafb;
  font-size: .78rem;
  font-weight: 700;
  color: #6b7280;
  letter-spacing: .03em;
}
.sprint__id { font-weight: 700; color: #111827; font-size: .92rem; }
/* 상세 페이지가 있는 스프린트만 링크가 된다 */
.sprint__link { display: inline-flex; align-items: baseline; gap: .3rem; text-decoration: none; }
.sprint__link .sprint__id { color: #2a7ae2; }
.sprint__link:hover .sprint__id { text-decoration: underline; }
.sprint__arrow { color: #2a7ae2; font-size: .8rem; }
.sprint__detail {
  display: inline-block;
  margin-top: .3rem;
  padding: .04rem .35rem;
  border-radius: 3px;
  background: #eff6ff;
  color: #2a7ae2;
  font-size: .68rem;
  font-weight: 600;
}
.sprint__goal { font-size: .8rem; color: #6b7280; display: block; margin-top: .15rem; word-break: keep-all; }
.sprint__date { font-size: .85rem; color: #374151; font-variant-numeric: tabular-nums; }
.sprint__days { display: block; font-size: .75rem; color: #9ca3af; margin-top: .15rem; }
.sprint__out { font-size: .88rem; color: #374151; line-height: 1.75; word-break: keep-all; }

/* 칸반 보드 — 좁은 화면에서는 가로 스크롤 */
.kanban__scroll { overflow-x: auto; padding-bottom: .5rem; }
.kanban {
  display: grid;
  grid-template-columns: repeat(5, minmax(11.5rem, 1fr));
  gap: .75rem;
  min-width: 58rem;
}
.col { background: #f9fafb; border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .6rem; }
.col__head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: .4rem;
  margin: 0 0 .7rem;
  padding: 0 .15rem .5rem;
  border-bottom: 1px solid #e5e7eb;
  font-size: .82rem;
  font-weight: 700;
  color: #374151;
}
.col__count {
  background: #e5e7eb;
  color: #4b5563;
  border-radius: 10px;
  padding: .02rem .42rem;
  font-size: .72rem;
  font-variant-numeric: tabular-nums;
}
.col--done { background: #f0fdf4; border-color: #bbf7d0; }
.col--done .col__head { border-bottom-color: #bbf7d0; }
.col--done .col__count { background: #bbf7d0; color: #166534; }
.card {
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 5px;
  padding: .55rem .6rem;
  margin-bottom: .5rem;
  font-size: .82rem;
  line-height: 1.5;
  color: #1f2937;
  word-break: keep-all;
}
.card:last-child { margin-bottom: 0; }
.card__meta { display: flex; gap: .35rem; align-items: center; margin-top: .4rem; flex-wrap: wrap; }
.card__sprint { font-size: .7rem; color: #9ca3af; font-weight: 600; }

/* 역할 분담 표 */
.roles__scroll { overflow-x: auto; }
.roles { width: 100%; border-collapse: collapse; font-size: .88rem; min-width: 44rem; }
.roles th, .roles td {
  text-align: left;
  padding: .7rem .8rem;
  border-bottom: 1px solid #e5e7eb;
  vertical-align: top;
  word-break: keep-all;
}
.roles th { background: #f9fafb; font-size: .78rem; color: #6b7280; letter-spacing: .03em; }
.roles td:first-child { white-space: nowrap; }
.roles__name { font-weight: 600; color: #111827; }
.roles__stack { color: #6b7280; font-size: .82rem; }

/* 스크럼 운영 */
.cere { display: grid; grid-template-columns: repeat(auto-fit, minmax(13rem, 1fr)); gap: .75rem; }
.cere__item { border: 1px solid #e5e7eb; border-radius: 6px; padding: .85rem .9rem; }
.cere__item h3 { margin: 0 0 .3rem; font-size: .92rem; color: #111827; }
.cere__when { display: block; font-size: .75rem; color: #2a7ae2; font-weight: 600; margin-bottom: .4rem; }
.cere__item p { margin: 0; font-size: .84rem; color: #6b7280; line-height: 1.65; word-break: keep-all; }

.sch__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }

@media (max-width: 34rem) {
  .sprint__row { grid-template-columns: 1fr; gap: .35rem; }
  .sprint__row--head { display: none; }
}
</style>

<div class="sch">

<div class="sch__head">
  <h1>개발 일정</h1>
  <p>AI 기반 채용 프로세스 자동화 및 지원자 통합 관리 플랫폼 &middot;
     애자일 스크럼 / 2주 스프린트 &times; 5회 &middot; 2026. 08. 20. ~ 10. 27. (69일)</p>
</div>

<div class="sch__sec">

  <h2><span class="sch__num">1.</span> 스프린트 계획</h2>
  <p class="sch__note">
    전체 69일을 2주 단위 스프린트 5회로 나눈다. 마지막 스프린트만 13일이다.
    각 스프린트는 배포 가능한 결과물을 산출하는 것을 목표로 하며, 스프린트 종료일에
    리뷰와 회고를 진행한다.
  </p>

  <div class="sprint">

    <div class="sprint__row sprint__row--head">
      <span>스프린트</span>
      <span>기간</span>
      <span>주요 산출물</span>
    </div>

    <div class="sprint__row">
      <span><a class="sprint__link" href="{{ '/sprint-1/' | relative_url }}">
          <span class="sprint__id">Sprint 1</span>
          <span class="sprint__arrow">&rarr;</span></a>
        <span class="sprint__goal">기반 구축</span>
        <span class="sprint__detail">일자별 진행</span></span>
      <span><span class="sprint__date">08.20 ~ 09.02</span>
        <span class="sprint__days">14일 · 1–2주차</span></span>
      <span class="sprint__out">
        DB 스키마 설계 및 ERD 확정 <span class="who who-a">재우 A</span> ·
        개발 환경 / Docker 구성 <span class="who who-e">수택 E</span> ·
        화면 설계와 컴포넌트 골격 <span class="who who-d">소연 D</span> ·
        테이블 인덱스 설계 <span class="who who-b">우정 B</span> ·
        S3 버킷 및 IAM 구성 <span class="who who-c">민아 C</span>
      </span>
    </div>

    <div class="sprint__row">
      <span><span class="sprint__id">Sprint 2</span>
        <span class="sprint__goal">핵심 CRUD</span></span>
      <span><span class="sprint__date">09.03 ~ 09.16</span>
        <span class="sprint__days">14일 · 3–4주차</span></span>
      <span class="sprint__out">
        공고 / 지원자 CRUD API <span class="who who-a">재우 A</span> ·
        지원자 목록 · 공고 관리 화면 <span class="who who-d">소연 D</span> ·
        이력서 S3 업로드와 지원 폼 <span class="who who-c">민아 C</span> ·
        더미 데이터 10만 건 생성 <span class="who who-b">우정 B</span> ·
        CI 파이프라인 구축 <span class="who who-e">수택 E</span>
      </span>
    </div>

    <div class="sprint__row">
      <span><span class="sprint__id">Sprint 3</span>
        <span class="sprint__goal">검색 · 매칭</span></span>
      <span><span class="sprint__date">09.17 ~ 09.30</span>
        <span class="sprint__days">14일 · 5–6주차</span></span>
      <span class="sprint__out">
        검색 / 필터 API <span class="who who-b">우정 B</span> ·
        인덱스 튜닝 및 쿼리 최적화 <span class="who who-b">우정 B</span> ·
        지원자 상세 화면 <span class="who who-d">소연 D</span> ·
        전형 단계 전환 로직 <span class="who who-a">재우 A</span> ·
        로그인 / 권한 처리 <span class="who who-d">소연 D</span>
      </span>
    </div>

    <div class="sprint__row">
      <span><span class="sprint__id">Sprint 4</span>
        <span class="sprint__goal">자동화 · 알림</span></span>
      <span><span class="sprint__date">10.01 ~ 10.14</span>
        <span class="sprint__days">14일 · 7–8주차</span></span>
      <span class="sprint__out">
        메일 발송 큐 (SQS + SES) <span class="who who-c">민아 C</span> ·
        면접 일정 관리 및 알림 <span class="who who-c">민아 C</span> ·
        채용 현황 대시보드 <span class="who who-d">소연 D</span> ·
        API 통합 테스트 <span class="who who-e">수택 E</span> ·
        단계 전환 이벤트 연동 <span class="who who-a">재우 A</span>
      </span>
    </div>

    <div class="sprint__row">
      <span><span class="sprint__id">Sprint 5</span>
        <span class="sprint__goal">안정화 · 배포</span></span>
      <span><span class="sprint__date">10.15 ~ 10.27</span>
        <span class="sprint__days">13일 · 9–10주차</span></span>
      <span class="sprint__out">
        AWS EC2 배포 및 운영 점검 <span class="who who-e">수택 E</span> ·
        QA 및 결함 조치 <span class="who who-e">수택 E</span> ·
        모바일 대응 화면 <span class="who who-d">소연 D</span> ·
        부하 테스트 (10만 건 기준) <span class="who who-b">우정 B</span> ·
        보고서 본문 정리 <span class="who who-a">재우 A</span>
      </span>
    </div>

  </div>

</div>

<div class="sch__sec">

  <h2><span class="sch__num">2.</span> 칸반 보드</h2>
  <p class="sch__note">
    2026. 08. 21. 기준. 진행 중 컬럼의 WIP 한도는 인당 1건으로 두어, 새 작업을
    당기기 전에 진행 중인 작업을 끝내도록 한다. 카드는 왼쪽에서 오른쪽으로만 이동한다.
  </p>

  <div class="kanban__scroll">
  <div class="kanban">

    <div class="col">
      <p class="col__head">백로그 <span class="col__count">10</span></p>

      <div class="card">면접 일정 관리 및 알림
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__sprint">S4</span></span></div>
      <div class="card">메일 발송 큐 (SQS + SES)
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__sprint">S4</span></span></div>
      <div class="card">채용 현황 대시보드 및 통계
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__sprint">S4</span></span></div>
      <div class="card">전형 단계 전환 로직
        <span class="card__meta"><span class="who who-a">재우 A</span><span class="card__sprint">S3</span></span></div>
      <div class="card">검색 / 필터 API
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__sprint">S3</span></span></div>
      <div class="card">인덱스 튜닝 및 쿼리 최적화
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__sprint">S3</span></span></div>
      <div class="card">로그인 / 권한 처리
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__sprint">S3</span></span></div>
      <div class="card">모바일 대응 화면
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__sprint">S5</span></span></div>
      <div class="card">AWS EC2 배포 및 운영 점검
        <span class="card__meta"><span class="who who-e">수택 E</span><span class="card__sprint">S5</span></span></div>
      <div class="card">부하 테스트 (10만 건 기준)
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__sprint">S5</span></span></div>
    </div>

    <div class="col">
      <p class="col__head">이번 스프린트 <span class="col__count">4</span></p>

      <div class="card">공고 / 지원자 CRUD API
        <span class="card__meta"><span class="who who-a">재우 A</span><span class="card__sprint">S2</span></span></div>
      <div class="card">더미 데이터 10만 건 생성
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__sprint">S2</span></span></div>
      <div class="card">이력서 S3 업로드 · 지원 폼
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__sprint">S2</span></span></div>
      <div class="card">지원자 목록 · 공고 관리 화면
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__sprint">S2</span></span></div>
    </div>

    <div class="col">
      <p class="col__head">진행 중 <span class="col__count">4</span></p>

      <div class="card">DB 스키마 설계 · ERD 확정
        <span class="card__meta"><span class="who who-a">재우 A</span><span class="card__sprint">S1</span></span></div>
      <div class="card">테이블 인덱스 설계
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__sprint">S1</span></span></div>
      <div class="card">화면 설계 · 컴포넌트 골격
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__sprint">S1</span></span></div>
      <div class="card">Docker 개발 환경 구성
        <span class="card__meta"><span class="who who-e">수택 E</span><span class="card__sprint">S1</span></span></div>
    </div>

    <div class="col">
      <p class="col__head">리뷰 / QA <span class="col__count">1</span></p>

      <div class="card">S3 버킷 및 IAM 권한 구성
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__sprint">S1</span></span></div>
    </div>

    <div class="col col--done">
      <p class="col__head">완료 <span class="col__count">4</span></p>

      <div class="card">개발 범위 · 목차 구조 확정
        <span class="card__meta"><span class="who who-a">재우 A</span><span class="card__sprint">S1</span></span></div>
      <div class="card">팀 구성 및 역할 분담
        <span class="card__meta"><span class="who who-a">재우 A</span><span class="card__sprint">S1</span></span></div>
      <div class="card">보고서 사이트 구축 · Pages 배포
        <span class="card__meta"><span class="who who-e">수택 E</span><span class="card__sprint">S1</span></span></div>
      <div class="card">기술 스택 선정
        <span class="card__meta"><span class="who who-e">수택 E</span><span class="card__sprint">S1</span></span></div>
    </div>

  </div>
  </div>

</div>

<div class="sch__sec">

  <h2><span class="sch__num">3.</span> 조직 구성 및 역할 분담</h2>

  <div class="roles__scroll">
  <table class="roles">
    <thead>
      <tr>
        <th>담당</th>
        <th>영역</th>
        <th>담당 업무</th>
        <th>기술 스택</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><span class="who who-a">재우 A</span><br><span class="roles__name">이재우</span></td>
        <td>백엔드 · 총괄</td>
        <td>공고 / 지원자 CRUD, 단계 전환 로직, DB 스키마</td>
        <td class="roles__stack">FastAPI, PostgreSQL</td>
      </tr>
      <tr>
        <td><span class="who who-b">우정 B</span><br><span class="roles__name">이우정</span></td>
        <td>검색 · 데이터</td>
        <td>검색 / 필터 API, 인덱스 튜닝, 더미 10만 건 생성</td>
        <td class="roles__stack">PostgreSQL, SQL</td>
      </tr>
      <tr>
        <td><span class="who who-c">민아 C</span><br><span class="roles__name">김민아</span></td>
        <td>파일 · 알림</td>
        <td>이력서 S3 업로드, 지원 폼, 메일 발송 큐</td>
        <td class="roles__stack">AWS S3, SES, SQS</td>
      </tr>
      <tr>
        <td><span class="who who-d">소연 D</span><br><span class="roles__name">박소연</span></td>
        <td>프론트엔드</td>
        <td>지원자 목록 / 상세, 공고 관리, 로그인, 모바일 화면</td>
        <td class="roles__stack">React, TypeScript, Vercel</td>
      </tr>
      <tr>
        <td><span class="who who-e">수택 E</span><br><span class="roles__name">진수택</span></td>
        <td>인프라 · 품질</td>
        <td>Docker, CI/CD, AWS 배포, API 테스트, QA</td>
        <td class="roles__stack">Docker, GitHub Actions, EC2</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="sch__sec">

  <h2><span class="sch__num">4.</span> 스크럼 운영</h2>

  <div class="cere">

    <div class="cere__item">
      <h3>스프린트 계획</h3>
      <span class="cere__when">스프린트 첫날 · 60분</span>
      <p>백로그에서 이번 스프린트 분량을 당겨오고 담당자를 정한다. 당겨온 카드는
         스프린트 중 추가하지 않는 것을 원칙으로 한다.</p>
    </div>

    <div class="cere__item">
      <h3>데일리 스크럼</h3>
      <span class="cere__when">매일 · 15분</span>
      <p>어제 한 일, 오늘 할 일, 막힌 것 세 가지만 공유한다. 문제 해결은
         스크럼 이후 관련자끼리 따로 진행한다.</p>
    </div>

    <div class="cere__item">
      <h3>스프린트 리뷰</h3>
      <span class="cere__when">스프린트 마지막 날 · 40분</span>
      <p>동작하는 결과물을 시연한다. 완료 컬럼에 도달하지 못한 카드는 다음
         스프린트 백로그로 되돌린다.</p>
    </div>

    <div class="cere__item">
      <h3>회고</h3>
      <span class="cere__when">리뷰 직후 · 30분</span>
      <p>유지할 것과 바꿀 것을 정리하고, 다음 스프린트에 적용할 개선 항목을
         한 가지 이상 정한다.</p>
    </div>

  </div>

</div>

<a class="sch__back" href="{{ '/toc/' | relative_url }}">&larr; 목차</a>

</div>
