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
  <p>결정이 필요하거나 아직 착수하지 않은 항목 &middot; 최종 갱신 2026. 08. 28.</p>
</div>

<div class="todo__item">
  <p class="todo__title">보고서 본문 잔여 장 작성<span class="todo__status is-planned">진행 예정</span></p>
  <p class="todo__desc">
    12장 중 <b>2장(팀 구성 및 역할)</b>과 <b>10장(개발 일정 및 추진 체계)</b>은 작성됐다.
    나머지 10개 장이 남았다. 각 장은 <code>_posts/</code>가 아니라 루트의 <code>.md</code>
    페이지로 만들고 <code>permalink</code>를 지정한다.
  </p>
</div>

<div class="todo__item">
  <p class="todo__title">커스텀 도메인 <code>ats.minahdev.cloud</code> 연결<span class="todo__status is-waiting">결정 대기</span></p>
  <p class="todo__desc">
    <b>이 보고서 사이트의 도메인이다</b> — 데모 사이트(<code>arda.seuk.cloud</code>)와는 다르다.
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
  <p class="todo__title">10. 01. 이후 2차 구간 계획<span class="todo__status is-open">미착수</span></p>
  <p class="todo__desc">
    주차별 계획은 <b>1차 완성(09. 30.)까지만</b> 수립돼 있다. 전체 개발 기간은 10. 27.까지이므로
    10. 01. ~ 10. 27. 구간의 목표와 산출물이 비어 있다. 1차 완성 판정 결과를 보고 수립한다.
  </p>
</div>

<div class="todo__item">
  <p class="todo__title">개발 로그 공백 (08. 22. ~ 28.)<span class="todo__status is-open">미착수</span></p>
  <p class="todo__desc">
    <code>/log/</code>의 마지막 기록이 08. 21.이다. 그 사이 도메인 오너제 전환, ERD 확정,
    코어 API, 앱 스택 확정과 뼈대 등 실제 진행이 있었으므로 주차 단위로 메워야 한다.
    스프린트 체계를 접으면서 <code>/sprint-1/</code> 일자별 페이지를 삭제했으므로,
    <b>08. 20. ~ 21.의 기록도 이 로그로 옮겨야 한다.</b>
  </p>
</div>

<a class="todo__back" href="{{ '/' | relative_url }}">&larr; 표지로</a>

</div>
