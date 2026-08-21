---
layout: default
title: 표지
---

<style>
.cover {
  max-width: 40rem;
  margin: 3.5rem auto 4.5rem;
}
.cover__kicker {
  text-align: center;
  font-size: .95rem;
  color: #6b7280;
  margin: 0 0 1.5rem;
}
.cover__title {
  text-align: center;
  font-size: clamp(1.45rem, 4vw, 2rem);
  line-height: 1.5;
  font-weight: 700;
  letter-spacing: -.01em;
  margin: 0 0 2.5rem;
  word-break: keep-all;
}
.cover__rule {
  width: 3rem;
  height: 2px;
  background: #374151;
  border: 0;
  margin: 0 auto 3rem;
}
.cover__meta {
  margin: 0 0 3.5rem;
  padding-left: .25rem;
}
.cover__label {
  font-size: .8rem;
  letter-spacing: .05em;
  color: #9ca3af;
  margin: 0 0 .35rem;
}
.cover__value {
  font-size: 1.05rem;
  font-weight: 600;
  color: #1f2937;
  margin: 0 0 1.6rem;
  word-break: keep-all;
}
.cover__value:last-child { margin-bottom: 0; }
.cover__sub {
  font-weight: 400;
  color: #9ca3af;
  font-size: .92rem;
}
.cover__value a {
  font-weight: 400;
  word-break: break-all;
}
.cover__next {
  text-align: center;
}
.cover__next a {
  font-size: 1rem;
  font-weight: 500;
}
</style>

<div class="cover">

  <p class="cover__kicker">개발 보고서</p>

  <h1 class="cover__title">AI 기반 채용 프로세스 자동화 및<br>지원자 통합 관리 플랫폼</h1>

  <hr class="cover__rule">

  <div class="cover__meta">

    <p class="cover__label">개발 기간</p>
    <p class="cover__value">2026년 8월 20일 ~ 2026년 10월 27일 <span class="cover__sub">(10주)</span></p>

    <p class="cover__label">팀명 : minahdev</p>
    <p class="cover__value">음머 · suvisdev · friendship · 또요니 · 밍뚜 <span class="cover__sub">(5명)</span></p>

    <p class="cover__label">깃허브 주소</p>
    <p class="cover__value"><a href="https://github.com/minahdev/demo.minahdev.cloud">https://github.com/minahdev/demo.minahdev.cloud</a></p>

    <p class="cover__label">데모 사이트</p>
    <p class="cover__value"><a href="https://ats.minahdev.cloud">https://ats.minahdev.cloud</a></p>

  </div>

  <p class="cover__next"><a href="{{ '/toc/' | relative_url }}">목차 &rarr;</a></p>

</div>
