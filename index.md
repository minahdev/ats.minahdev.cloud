---
layout: default
title: 표지
---

<style>
.cover {
  max-width: 44rem;
  margin: 3.5rem auto 4.5rem;
}
.cover__kicker {
  text-align: center;
  font-size: .8rem;
  letter-spacing: .45em;
  text-indent: .45em;
  color: #9ca3af;
  margin: 0 0 2rem;
}
.cover__title {
  text-align: center;
  font-size: clamp(1.5rem, 4.4vw, 2.15rem);
  line-height: 1.45;
  font-weight: 700;
  letter-spacing: -.015em;
  color: #111827;
  margin: 0 0 1.6rem;
  word-break: keep-all;
}
.cover__subtitle {
  text-align: center;
  font-size: .82rem;
  line-height: 1.7;
  color: #9ca3af;
  margin: 0 0 2.8rem;
}
.cover__rule {
  width: 3rem;
  height: 1px;
  background: #d1d5db;
  border: 0;
  margin: 0 auto 3rem;
}
.cover__meta {
  display: grid;
  grid-template-columns: 7.5rem minmax(0, 1fr);
  column-gap: 1.75rem;
  row-gap: 1.35rem;
  max-width: 32rem;
  margin: 0 auto 3.5rem;
}
.cover__label {
  font-size: .9rem;
  font-weight: 600;
  color: #4b5563;
  margin: 0;
  word-break: keep-all;
}
.cover__value {
  font-size: .95rem;
  line-height: 1.55;
  color: #1f2937;
  margin: 0;
  word-break: keep-all;
}
.cover__sub {
  display: block;
  margin-top: .2rem;
  font-size: .8rem;
  color: #9ca3af;
}
.cover__value a { word-break: break-all; }
.cover__next {
  text-align: center;
  margin: 0;
}
.cover__next a {
  font-size: 1rem;
  font-weight: 500;
}

@media (max-width: 30rem) {
  .cover__meta {
    grid-template-columns: 1fr;
    row-gap: .35rem;
  }
  .cover__label { margin-top: 1.1rem; }
  .cover__label:first-child { margin-top: 0; }
}
</style>

<div class="cover">

  <p class="cover__kicker">개발 보고서</p>

  <h1 class="cover__title">AI 기반 채용 프로세스 자동화 및<br>지원자 통합 관리 플랫폼</h1>

  <p class="cover__subtitle">
    AI-Powered Recruitment Process Automation<br>
    and Integrated Applicant Management Platform
  </p>

  <hr class="cover__rule">

  <div class="cover__meta">

    <p class="cover__label">개발 기간</p>
    <p class="cover__value">2026년 8월 20일 (목) ~ 2026년 10월 27일 (화)
      <span class="cover__sub">총 69일 / 약 10주</span></p>

    <p class="cover__label">개발팀 : seuk</p>
    <p class="cover__value">김민아 · 박소연 · 이재우 · 이우정 · 진수택
      <span class="cover__sub">5명</span></p>

    <p class="cover__label">문서 작성일</p>
    <p class="cover__value">2026년 8월 21일</p>

    <p class="cover__label">깃허브 주소</p>
    <p class="cover__value"><a href="https://github.com/minahdev/ats.minahdev.cloud">https://github.com/minahdev/ats.minahdev.cloud</a></p>

    <p class="cover__label">데모 사이트</p>
    <p class="cover__value"><a href="https://ats.minahdev.cloud">https://ats.minahdev.cloud</a></p>

  </div>

  <p class="cover__next"><a href="{{ '/toc/' | relative_url }}">목차 &rarr;</a></p>

</div>
