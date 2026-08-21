---
layout: default
title: 미결 항목
permalink: /todo/
---

<style>
.todo { max-width: 46rem; margin: 2.5rem auto 4rem; }
.todo__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.todo__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; }
.todo__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }
.todo__item {
  padding: 1.15rem 0;
  border-bottom: 1px solid #e5e7eb;
}
.todo__item:last-of-type { border-bottom: 0; }
.todo__title {
  display: flex;
  gap: .6rem;
  align-items: baseline;
  flex-wrap: wrap;
  margin: 0 0 .45rem;
  font-size: 1rem;
  font-weight: 600;
  color: #111827;
  word-break: keep-all;
}
.todo__desc {
  margin: 0;
  padding-left: .05rem;
  color: #6b7280;
  font-size: .9rem;
  line-height: 1.65;
  word-break: keep-all;
}
.todo__status {
  padding: .1rem .45rem;
  border-radius: 3px;
  font-size: .72rem;
  font-weight: 600;
  letter-spacing: .02em;
  white-space: nowrap;
}
.is-waiting { background: #fef3c7; color: #92400e; }
.is-planned { background: #e0e7ff; color: #3730a3; }
.is-open    { background: #f3f4f6; color: #4b5563; }
.todo__back { display: inline-block; margin-top: 2rem; font-size: .9rem; }
</style>

<div class="todo">

<div class="todo__head">
  <h1>미결 항목</h1>
  <p>결정이 필요하거나 아직 착수하지 않은 항목 &middot; 최종 갱신 2026. 08. 21.</p>
</div>

<div class="todo__item">
  <p class="todo__title">보고서 본문 11장 작성<span class="todo__status is-planned">진행 예정</span></p>
  <p class="todo__desc">
    현재 표지와 목차만 작성된 상태다. 각 장은 <code>_posts/</code>가 아니라 루트의
    <code>.md</code> 페이지로 만들고 <code>permalink</code>를 지정한다.
  </p>
</div>

<div class="todo__item">
  <p class="todo__title">커스텀 도메인 <code>ats.minahdev.cloud</code> 연결<span class="todo__status is-waiting">결정 대기</span></p>
  <p class="todo__desc">
    DNS 레코드가 아직 없다. DNS가 GitHub Pages를 가리키기 전에 <code>CNAME</code> 파일을
    추가하면 사이트가 접속 불가가 되므로, DNS 확인 후에 추가해야 한다.
    이때 <code>baseurl</code>을 <code>""</code>로, <code>url</code>을
    <code>https://ats.minahdev.cloud</code>로 함께 바꿔야 한다 — 하나만 바꾸면
    CSS와 내부 링크가 모두 깨진다.
  </p>
</div>

<div class="todo__item">
  <p class="todo__title">푸터 연락처 공개 범위<span class="todo__status is-waiting">결정 대기</span></p>
  <p class="todo__desc">
    깃허브 핸들은 푸터에 노출했다. 이메일은 공개 사이트에 노출되면 크롤러가 수집할 수
    있어 보류 중이다.
  </p>
</div>

<div class="todo__item">
  <p class="todo__title">개발 일정 상세화<span class="todo__status is-open">미착수</span></p>
  <p class="todo__desc">
    전체 기간(2026. 08. 20. ~ 10. 27., 총 69일)은 확정됐으나 주차별 진행 계획과
    마일스톤은 아직 정리되지 않았다. 목차 10장에 해당한다.
  </p>
</div>

<a class="todo__back" href="{{ '/' | relative_url }}">&larr; 표지로</a>

</div>
