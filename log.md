---
layout: default
title: 개발 로그
permalink: /log/
---

<style>
.log { max-width: 46rem; margin: 2.5rem auto 4rem; }
.log__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.log__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; }
.log__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }
.log__entry { margin-bottom: 2.5rem; }
.log__date {
  display: flex;
  gap: .75rem;
  align-items: baseline;
  margin: 0 0 .9rem;
  padding-bottom: .5rem;
  border-bottom: 1px solid #e5e7eb;
}
.log__day {
  font-size: 1.1rem;
  font-weight: 700;
  color: #111827;
  font-variant-numeric: tabular-nums;
}
.log__week { font-size: .8rem; color: #9ca3af; }
.log__entry ul { list-style: none; margin: 0; padding: 0 0 0 2.1rem; }
.log__entry li { padding: .3rem 0; color: #374151; font-size: .95rem; word-break: keep-all; }
.log__entry li::before { content: "—"; color: #d1d5db; margin-right: .6rem; }
.log__tag {
  display: inline-block;
  margin-left: .5rem;
  padding: .05rem .4rem;
  border-radius: 3px;
  background: #f3f4f6;
  color: #6b7280;
  font-size: .72rem;
  font-weight: 600;
  letter-spacing: .02em;
  vertical-align: .05em;
}
.log__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }
</style>

<div class="log">

<div class="log__head">
  <h1>개발 로그</h1>
  <p>AI 기반 채용 프로세스 자동화 및 지원자 통합 관리 플랫폼 &middot; 작업 기록</p>
</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 08. 21.</span>
    <span class="log__week">1주차 &middot; 개발 2일차</span>
  </div>

  <ul>
    <li>Jekyll + minima 기반 보고서 사이트 스캐폴드 구성<span class="log__tag">인프라</span></li>
    <li>GitHub Pages 배포 파이프라인 연결 — <code>main</code> push 시 자동 빌드<span class="log__tag">인프라</span></li>
    <li>프로젝트 페이지 경로에 맞춰 <code>baseurl</code> 설정<span class="log__tag">인프라</span></li>
    <li>보고서 표지 및 목차(11장) 작성<span class="log__tag">문서</span></li>
    <li>리포지터리명을 <code>ats.minahdev.cloud</code>로 변경하고 참조 경로 일괄 정리<span class="log__tag">인프라</span></li>
    <li>표지를 라벨 / 값 2단 그리드로 재구성, 팀명 <code>seuk</code> 반영<span class="log__tag">문서</span></li>
    <li>로컬 미리보기 환경 구축 — Ruby 3.2.3 / Jekyll 3.10.0<span class="log__tag">환경</span></li>
    <li>Tailscale Funnel로 외부 기기 미리보기 경로 확보<span class="log__tag">환경</span></li>
  </ul>

</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 08. 20.</span>
    <span class="log__week">1주차 &middot; 개발 1일차</span>
  </div>

  <ul>
    <li>프로젝트 착수, 개발 범위 및 목차 구조 확정<span class="log__tag">기획</span></li>
    <li>팀 구성 및 역할 분담 논의<span class="log__tag">기획</span></li>
  </ul>

</div>

<a class="log__back" href="{{ '/' | relative_url }}">&larr; 표지로</a>

</div>
