---
layout: default
title: Sprint 1
permalink: /sprint-1/
---

<style>
.sp { max-width: 62rem; margin: 2.5rem auto 4rem; }
.sp__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 1.6rem; }
.sp__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.sp__crumb a { color: #9ca3af; }
.sp__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; }
.sp__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

.sp__stat {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(8rem, 1fr));
  gap: .6rem;
  margin-bottom: 2.5rem;
}
.stat { border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .85rem; }
.stat__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }
.stat__v { font-size: 1.05rem; font-weight: 700; color: #111827; font-variant-numeric: tabular-nums; }
.stat__v small { font-size: .78rem; font-weight: 400; color: #9ca3af; margin-left: .15rem; }

.sp__note { margin: -1.6rem 0 2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }

.daily__scroll { overflow-x: auto; }
.daily { width: 100%; border-collapse: collapse; font-size: .88rem; min-width: 50rem; }
.daily th {
  background: #f9fafb;
  text-align: left;
  padding: .65rem .8rem;
  font-size: .76rem;
  color: #6b7280;
  letter-spacing: .03em;
  border-bottom: 1px solid #e5e7eb;
  white-space: nowrap;
}
.daily td {
  padding: .6rem .8rem;
  border-bottom: 1px solid #f3f4f6;
  vertical-align: top;
  color: #374151;
  word-break: keep-all;
}
/* 날짜가 바뀌는 행에만 굵은 선을 그어 하루 단위를 구분한다 */
.daily tr.d-first td { border-top: 1px solid #e5e7eb; }
.daily tr.d-weekend td { background: #fafafa; color: #9ca3af; }
.daily__date { white-space: nowrap; font-variant-numeric: tabular-nums; }
.daily__date b { display: block; font-size: .92rem; color: #111827; font-weight: 700; }
.daily__date span { font-size: .74rem; color: #9ca3af; }
.daily tr.d-weekend .daily__date b { color: #9ca3af; font-weight: 600; }
.daily__out { color: #6b7280; font-size: .82rem; }
.daily code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

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
.who-all { background: #f3f4f6; color: #4b5563; }

.st {
  display: inline-block;
  padding: .08rem .45rem;
  border-radius: 3px;
  font-size: .72rem;
  font-weight: 600;
  white-space: nowrap;
}
.st-done    { background: #dcfce7; color: #166534; }
.st-doing   { background: #dbeafe; color: #1e40af; }
.st-todo    { background: #f3f4f6; color: #6b7280; }
.st-off     { background: transparent; color: #d1d5db; }

.sp__back { display: inline-block; margin-top: 1.5rem; font-size: .9rem; }
</style>

<div class="sp">

<div class="sp__head">
  <p class="sp__crumb"><a href="{{ '/schedule/' | relative_url }}">개발 일정</a> &rsaquo; Sprint 1</p>
  <h1>Sprint 1 · 기반 구축</h1>
  <p>2026. 08. 20. (목) ~ 09. 02. (수) &middot; 14일 &middot; 1–2주차 &middot; 일자별 업무 진행사항</p>
</div>

<div class="sp__stat">
  <div class="stat"><span class="stat__k">기간</span>
    <span class="stat__v">14<small>일</small></span></div>
  <div class="stat"><span class="stat__k">작업일</span>
    <span class="stat__v">10<small>일</small></span></div>
  <div class="stat"><span class="stat__k">경과</span>
    <span class="stat__v">2<small>/ 14일</small></span></div>
  <div class="stat"><span class="stat__k">완료</span>
    <span class="stat__v">14<small>건</small></span></div>
  <div class="stat"><span class="stat__k">진행 중</span>
    <span class="stat__v">4<small>건</small></span></div>
</div>

<p class="sp__note">
  2026. 08. 21. 기준. 08. 20. ~ 08. 21.은 실제 진행 내역이고, 08. 24. 이후는
  스프린트 백로그에서 배분한 계획이다. 주말은 작업일에서 제외한다.
</p>

<div class="daily__scroll">
<table class="daily">
  <thead>
    <tr>
      <th>날짜</th>
      <th>담당</th>
      <th>업무 내용</th>
      <th>산출물</th>
      <th>상태</th>
    </tr>
  </thead>
  <tbody>

    <tr class="d-first">
      <td class="daily__date" rowspan="6"><b>08. 20. (목)</b><span>1일차</span></td>
      <td><span class="who who-all">전원</span></td>
      <td>팀명 <code>seuk</code> 확정</td>
      <td class="daily__out">팀 명칭</td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-all">전원</span></td>
      <td>프로젝트 타이틀 확정 — “AI 기반 채용 프로세스 자동화 및 지원자 통합 관리 플랫폼”</td>
      <td class="daily__out">과제명</td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-a">재우 A</span></td>
      <td>개발 범위 및 보고서 목차 구조 확정 (12장)</td>
      <td class="daily__out">목차 초안</td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>Jekyll + minima 사이트 스캐폴드 생성</td>
      <td class="daily__out"><code>_config.yml</code>, <code>Gemfile</code>, <code>index.md</code></td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>GitHub Pages 배포 연결 — <code>main</code> 브랜치 legacy 빌드</td>
      <td class="daily__out">배포 파이프라인</td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>프로젝트 페이지 경로에 맞춰 <code>baseurl</code> 설정, <code>.gitignore</code> 정비</td>
      <td class="daily__out"><code>baseurl: /ats.minahdev.cloud</code></td>
      <td><span class="st st-done">완료</span></td>
    </tr>

    <tr class="d-first">
      <td class="daily__date" rowspan="8"><b>08. 21. (금)</b><span>2일차</span></td>
      <td><span class="who who-e">수택 E</span></td>
      <td>AWS 루트 계정 로그인 후 IAM 사용자 생성, IAM 계정으로 재로그인 —
          이후 작업은 루트 계정을 사용하지 않는다</td>
      <td class="daily__out">IAM 사용자 · 접근 권한</td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>RDS 인스턴스 생성 및 접속 엔드포인트 확보 — 애플리케이션 DB 연결의 선행 작업</td>
      <td class="daily__out">RDS 접속 URL</td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-all">전원</span></td>
      <td>보고서 표지 레이아웃 확정 — 라벨 / 값 2단 그리드, 팀원 명단 반영</td>
      <td class="daily__out">표지 페이지</td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-a">재우 A</span></td>
      <td>목차 12장 번호 체계 정리 및 부록 추가</td>
      <td class="daily__out"><code>/toc/</code></td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-a">재우 A</span></td>
      <td>스프린트 계획 수립 및 칸반 보드 작성</td>
      <td class="daily__out"><code>/schedule/</code></td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-c">민아 C</span></td>
      <td>개발 로그 · 미결 항목 페이지 구성</td>
      <td class="daily__out"><code>/log/</code>, <code>/todo/</code></td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>로컬 미리보기 환경 구축 — Ruby 3.2.3 / Jekyll 3.10.0</td>
      <td class="daily__out"><code>bundle exec jekyll serve</code></td>
      <td><span class="st st-done">완료</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>Tailscale Funnel로 외부 기기 미리보기 경로 확보</td>
      <td class="daily__out">미리보기 URL</td>
      <td><span class="st st-done">완료</span></td>
    </tr>

    <tr class="d-first d-weekend">
      <td class="daily__date"><b>08. 22. (토)</b><span>3일차</span></td>
      <td colspan="3">주말</td>
      <td><span class="st st-off">—</span></td>
    </tr>
    <tr class="d-weekend">
      <td class="daily__date"><b>08. 23. (일)</b><span>4일차</span></td>
      <td colspan="3">주말</td>
      <td><span class="st st-off">—</span></td>
    </tr>

    <tr class="d-first">
      <td class="daily__date" rowspan="4"><b>08. 24. (월)</b><span>5일차</span></td>
      <td><span class="who who-a">재우 A</span></td>
      <td>DB 스키마 1차 설계 — 공고 / 지원자 / 전형 단계 엔티티</td>
      <td class="daily__out">ERD 초안</td>
      <td><span class="st st-doing">진행 중</span></td>
    </tr>
    <tr>
      <td><span class="who who-b">우정 B</span></td>
      <td>검색 대상 컬럼 정리 및 인덱스 후보 도출</td>
      <td class="daily__out">인덱스 설계안</td>
      <td><span class="st st-doing">진행 중</span></td>
    </tr>
    <tr>
      <td><span class="who who-d">소연 D</span></td>
      <td>주요 화면 와이어프레임 — 지원자 목록 / 상세, 공고 관리</td>
      <td class="daily__out">와이어프레임</td>
      <td><span class="st st-doing">진행 중</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>Docker 개발 환경 구성 — FastAPI + PostgreSQL 컨테이너</td>
      <td class="daily__out"><code>docker-compose.yml</code></td>
      <td><span class="st st-doing">진행 중</span></td>
    </tr>

    <tr class="d-first">
      <td class="daily__date" rowspan="3"><b>08. 25. (화)</b><span>6일차</span></td>
      <td><span class="who who-a">재우 A</span></td>
      <td>ERD 팀 리뷰 및 정규화 조정</td>
      <td class="daily__out">ERD v2</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-c">민아 C</span></td>
      <td>S3 버킷 생성 및 IAM 권한 정책 구성</td>
      <td class="daily__out">버킷 · IAM 정책</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-d">소연 D</span></td>
      <td>React + TypeScript 프로젝트 초기화, 라우팅 구조 설계</td>
      <td class="daily__out">프론트 골격</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>

    <tr class="d-first">
      <td class="daily__date" rowspan="3"><b>08. 26. (수)</b><span>7일차</span></td>
      <td><span class="who who-a">재우 A</span></td>
      <td>마이그레이션 스크립트 작성 및 스키마 적용</td>
      <td class="daily__out">마이그레이션</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-b">우정 B</span></td>
      <td>더미 데이터 생성 스크립트 설계 — 10만 건 기준</td>
      <td class="daily__out">생성 스크립트</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>GitHub Actions CI 골격 — 린트 · 테스트 워크플로</td>
      <td class="daily__out"><code>ci.yml</code></td>
      <td><span class="st st-todo">예정</span></td>
    </tr>

    <tr class="d-first">
      <td class="daily__date" rowspan="3"><b>08. 27. (목)</b><span>8일차</span></td>
      <td><span class="who who-d">소연 D</span></td>
      <td>공통 컴포넌트 골격 — 테이블, 폼, 모달</td>
      <td class="daily__out">컴포넌트</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-c">민아 C</span></td>
      <td>파일 업로드 사전 검증 규칙 정의 — 확장자 · 용량 · 바이러스 검사</td>
      <td class="daily__out">업로드 정책</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-a">재우 A</span></td>
      <td>API 명세 초안 작성 — 공고 / 지원자 엔드포인트</td>
      <td class="daily__out">OpenAPI 초안</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>

    <tr class="d-first">
      <td class="daily__date" rowspan="2"><b>08. 28. (금)</b><span>9일차</span></td>
      <td><span class="who who-all">전원</span></td>
      <td>1주차 중간 점검 — 스키마 · 화면 설계 정합성 확인</td>
      <td class="daily__out">점검 기록</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>개발 환경 문서화 및 팀 배포 — 실행 절차 정리</td>
      <td class="daily__out">환경 구축 문서</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>

    <tr class="d-first d-weekend">
      <td class="daily__date"><b>08. 29. (토)</b><span>10일차</span></td>
      <td colspan="3">주말</td>
      <td><span class="st st-off">—</span></td>
    </tr>
    <tr class="d-weekend">
      <td class="daily__date"><b>08. 30. (일)</b><span>11일차</span></td>
      <td colspan="3">주말</td>
      <td><span class="st st-off">—</span></td>
    </tr>

    <tr class="d-first">
      <td class="daily__date" rowspan="3"><b>08. 31. (월)</b><span>12일차</span></td>
      <td><span class="who who-b">우정 B</span></td>
      <td>더미 데이터 10만 건 적재 및 기본 쿼리 성능 측정</td>
      <td class="daily__out">성능 기준선</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-a">재우 A</span></td>
      <td>공고 CRUD 엔드포인트 착수</td>
      <td class="daily__out">API 구현</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-e">수택 E</span></td>
      <td>CI에 테스트 단계 연결, PR 체크 활성화</td>
      <td class="daily__out">PR 체크</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>

    <tr class="d-first">
      <td class="daily__date" rowspan="2"><b>09. 01. (화)</b><span>13일차</span></td>
      <td><span class="who who-d">소연 D</span></td>
      <td>API 연동 목업 — 지원자 목록 화면 데이터 바인딩</td>
      <td class="daily__out">연동 목업</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-c">민아 C</span></td>
      <td>S3 업로드 프로토타입 검증 — presigned URL 방식</td>
      <td class="daily__out">업로드 PoC</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>

    <tr class="d-first">
      <td class="daily__date" rowspan="2"><b>09. 02. (수)</b><span>14일차</span></td>
      <td><span class="who who-all">전원</span></td>
      <td>스프린트 리뷰 — 기반 구축 결과물 시연</td>
      <td class="daily__out">리뷰 기록</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>
    <tr>
      <td><span class="who who-all">전원</span></td>
      <td>회고 및 Sprint 2 백로그 확정</td>
      <td class="daily__out">회고 · S2 백로그</td>
      <td><span class="st st-todo">예정</span></td>
    </tr>

  </tbody>
</table>
</div>

<a class="sp__back" href="{{ '/schedule/' | relative_url }}">&larr; 개발 일정</a>

</div>
