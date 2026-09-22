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
  <p>결정이 필요하거나 아직 착수하지 않은 항목 &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="todo__item">
  <p class="todo__title">보고서 본문 재검토<span class="todo__status is-planned">진행 예정</span></p>
  <p class="todo__desc">
    09. 22. 에 12개 장의 초안이 모두 채워졌다. 다만 본문은 <b>팀 문서
    (<a href="https://ats.suvisdev.cloud/">ats.suvisdev.cloud</a>)와 저장소 문서를 근거로
    작성한 것</b>이라, 본인이 직접 수행한 앱 &middot; 프론트엔드 파트의 서술이 상대적으로 얇다.
    발표 전에 그 두 도메인의 1인칭 근거(실제 겪은 문제 &middot; 선택 &middot; 수치)를 보강해야 한다.
  </p>
</div>

<div class="todo__item">
  <p class="todo__title">개발 방법론 표기 통일<span class="todo__status is-waiting">결정 대기</span></p>
  <p class="todo__desc">
    팀 문서 사이트는 <b>애자일 스크럼 &middot; 2주 1스프린트 &middot; 총 5스프린트</b>로 적고,
    이 보고서와 저장소 문서(<code>06-weekly.md</code>)는 <b>스프린트를 접고 게이트 2개 +
    주 단위 자율 진행</b>으로 적는다. 발표에서 두 서술이 충돌하므로 팀 차원에서
    어느 쪽으로 말할지 정해야 한다 &mdash; 도메인 밖 사안이라 팀장(진수택)과 합의 대상이다.
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
  <p class="todo__title">개발 로그 세부 보강<span class="todo__status is-planned">진행 예정</span></p>
  <p class="todo__desc">
    09. 22. 에 08. 22. ~ 09. 22. 한 달치 공백을 주차 단위로 메웠다. 다만 팀 전체 관점의
    기록이라, <b>본인이 직접 커밋한 앱 &middot; 프론트엔드 작업</b>은 주차 요약에 묻혀 있다.
    발표에서 자기 몫을 말하려면 그 부분을 날짜 단위로 더 쪼개는 편이 낫다.
  </p>
</div>

<a class="todo__back" href="{{ '/' | relative_url }}">&larr; 표지로</a>

</div>
