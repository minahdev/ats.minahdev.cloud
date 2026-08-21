---
layout: default
title: 목차
permalink: /toc/
---

<style>
.toc { max-width: 46rem; margin: 2.5rem auto 4rem; }
.toc__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.toc__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; }
.toc__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }
.toc__ch { margin-bottom: 2.25rem; }
.toc__ch > h2 {
  font-size: 1.05rem;
  color: #2a7ae2;
  margin: 0 0 .75rem;
  padding-bottom: .5rem;
  border-bottom: 1px solid #e5e7eb;
  display: flex;
  gap: .5rem;
  align-items: baseline;
  word-break: keep-all;
}
.toc__num { font-variant-numeric: tabular-nums; font-weight: 700; }
/* 항목 번호는 CSS 카운터로 매긴다. 장마다 1)부터 다시 시작한다. */
.toc__ch ul {
  list-style: none;
  margin: 0;
  padding: 0 0 0 1.1rem;
  counter-reset: toc-item;
}
.toc__ch li {
  counter-increment: toc-item;
  display: flex;
  gap: .8rem;
  padding: .32rem 0;
  color: #374151;
  font-size: .95rem;
  word-break: keep-all;
}
.toc__ch li::before {
  content: counter(toc-item) ")";
  flex: 0 0 1.4rem;
  text-align: right;
  color: #9ca3af;
  font-variant-numeric: tabular-nums;
}
.toc__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }
</style>

<div class="toc">

<div class="toc__head">
  <h1>목차</h1>
  <p>AI 기반 채용 프로세스 자동화 및 지원자 통합 관리 플랫폼 &middot; 개발 보고서</p>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">1.</span> 사업 개요</h2>
  <ul>
    <li>추진 배경 및 필요성</li>
    <li>개발 목적</li>
    <li>개발 범위</li>
    <li>기대 효과</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">2.</span> 팀 구성 및 역할</h2>
  <ul>
    <li>개발 인원 소개</li>
    <li>역할 분담</li>
    <li>협업 방식 및 일정 관리</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">3.</span> 요구사항 분석</h2>
  <ul>
    <li>기존 채용 프로세스의 문제점</li>
    <li>기능 요구사항</li>
    <li>비기능 요구사항</li>
    <li>사용자 시나리오</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">4.</span> 시스템 설계</h2>
  <ul>
    <li>시스템 아키텍처</li>
    <li>데이터베이스 설계 (ERD)</li>
    <li>API 설계</li>
    <li>화면 설계 (UI/UX)</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">5.</span> 기술 스택 및 개발 환경</h2>
  <ul>
    <li>기술 스택 선정 및 근거</li>
    <li>개발 환경 구성</li>
    <li>형상 관리 및 브랜치 전략</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">6.</span> 주요 기능 개발</h2>
  <ul>
    <li>채용 공고 등록 및 관리</li>
    <li>지원자 통합 관리</li>
    <li>이력서 파싱 및 자동 스크리닝</li>
    <li>지원자–공고 매칭 추천</li>
    <li>면접 일정 관리 및 알림</li>
    <li>채용 현황 대시보드 및 통계</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">7.</span> AI 모델 적용</h2>
  <ul>
    <li>모델 선정 및 비교</li>
    <li>프롬프트 및 파이프라인 설계</li>
    <li>정확도 평가 및 개선</li>
    <li>편향성 검토</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">8.</span> 테스트</h2>
  <ul>
    <li>테스트 계획</li>
    <li>단위 및 통합 테스트</li>
    <li>사용자 인수 테스트</li>
    <li>결함 추적 및 조치</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">9.</span> 배포 및 운영</h2>
  <ul>
    <li>배포 구성</li>
    <li>CI/CD 파이프라인</li>
    <li>모니터링 및 로그 관리</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">10.</span>
    <a href="{{ '/schedule/' | relative_url }}">개발 일정 및 추진 체계</a></h2>
  <ul>
    <li>스프린트 계획 (2주 &times; 5회, 2026.08.20 – 2026.10.27)</li>
    <li>칸반 보드</li>
    <li>조직 구성 및 역할 분담</li>
    <li>스크럼 운영</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">11.</span> 결론 및 향후 과제</h2>
  <ul>
    <li>개발 성과</li>
    <li>한계점</li>
    <li>향후 개선 방향</li>
  </ul>
</div>

<div class="toc__ch">
  <h2><span class="toc__num">12.</span> 부록</h2>
  <ul>
    <li>용어 정의</li>
    <li>관련 서식</li>
    <li>참고 자료</li>
  </ul>
</div>

<a class="toc__back" href="{{ '/' | relative_url }}">&larr; 표지</a>

</div>
