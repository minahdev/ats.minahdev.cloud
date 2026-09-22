---
layout: default
title: 인프라 · 총괄
permalink: /role-infra/
---

{% include role-style.html %}

<div class="role">

<div class="role__head">
  <p class="role__crumb"><a href="{{ '/team/' | relative_url }}">팀 구성 및 역할</a> &rsaquo;
     인프라 &middot; 총괄</p>
  <h1>인프라 &middot; 총괄 &middot; 담당 진수택</h1>
  <p>전원이 딛는 바닥 &mdash; AWS &middot; 자동 CD &middot; CI와 스키마 이행 &middot; 통합
     &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="role__stat">
  <div class="stat"><span class="stat__k">담당</span>
    <span class="stat__v">진수택 <span class="who who-e">수택 E</span></span></div>
  <div class="stat"><span class="stat__k">겸임</span>
    <span class="stat__v">팀장<small>09. 04. 승계</small></span></div>
  <div class="stat"><span class="stat__k">소유 폴더</span>
    <span class="stat__v"><code>infra/</code> <code>.github/</code></span></div>
  <div class="stat"><span class="stat__k">스택</span>
    <span class="stat__v">AWS<small>Docker &middot; Actions</small></span></div>
  <div class="stat"><span class="stat__k">의존</span>
    <span class="stat__v">없음<small>전부의 선행</small></span></div>
</div>

<div class="role__sec">

  <h2><span class="role__num">1.</span> 미션</h2>

  <p class="role__p">
    전원이 딛는 바닥이다. AWS &middot; 배포 &middot; CI/CD를 책임지고, 총괄로서 스키마 &middot; 아키텍처
    &middot; 인터페이스 리뷰 &middot; 통합 &middot; 발표를 잡는다.
  </p>
  <p class="role__p">
    이 도메인은 <b>다른 어떤 도메인에도 의존하지 않는다.</b> 그래서 반대로 <b>전부의 선행 조건</b>이
    된다 &mdash; 여기가 지연되면 그것이 곧 나머지 네 도메인의 대기다. 이 도메인의 큐 우선순위가
    사실상 팀 전체의 임계경로다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">2.</span> 범위</h2>

  <div class="scope">

    <div class="scope__box scope__box--in">
      <h3>도메인 업무</h3>
      <ul>
        <li>AWS &mdash; 계정 &middot; IAM 최소 권한 &middot; S3 버킷 &middot; SES 발신 도메인(샌드박스 해제)
            &middot; SQS 큐 &middot; EC2 배포</li>
        <li>로컬 실행 환경 &mdash; Docker Compose (API &middot; DB &middot; 워커)</li>
        <li>CI/CD &mdash; GitHub Actions (테스트 &middot; 프론트 빌드 &rarr; EC2 배포)</li>
        <li>GitHub 설정 &mdash; 브랜치 보호 &middot; 코드 소유자 &middot; 리포 권한</li>
        <li>Vercel 프로젝트 연결 (빌드 설정은 프론트와 협업)</li>
        <li>공용 문서 &middot; 스키마 관리 &mdash; 확정과 변경 절차 집행</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>총괄 업무 (도메인 밖 상시)</h3>
      <ul>
        <li>인터페이스 PR 리뷰 &middot; 머지 &mdash; 기본 금요일 주 1회 일괄</li>
        <li>다른 도메인이 <b>대기 중인 선행 PR은 수시 처리</b> &mdash; 밀리면 받는 쪽이 일주일을 논다</li>
        <li>주간 계획서 &mdash; 주 마감 게이트 &middot; 충돌 방지</li>
        <li>도메인 간 조정 &middot; 통합 리허설 &middot; 발표 총괄</li>
      </ul>
    </div>

  </div>

  <p class="role__note" style="margin-top:1.1rem; margin-bottom:0;">
    사람별 작업 큐는 총괄이 쥐지 않는다. 도메인 오너제로 전환하면서 각 로드맵으로 이관했고,
    주간 계획서에는 <b>주 마감 게이트와 도메인 간 충돌만</b> 남겼다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">3.</span> 인터페이스 계약</h2>

  <p class="role__p">
    <b>제공</b> &mdash; 데이터베이스 접속 문자열과 AWS 자격 &middot; 리소스명은 전부
    <code>.env</code>(git 제외)와 <code>.env.example</code>(키 이름만)로 전달한다.
    리소스가 준비되면 <b><code>.env.example</code> 갱신 PR이 곧 공지</b>다 &mdash; 별도 안내 없이도
    받는 쪽이 무엇이 생겼는지 알 수 있게 했다.
  </p>
  <p class="role__p">
    <b>의존</b> &mdash; 없음.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">4.</span> 주간 계획</h2>
  <p class="role__note">
    초기 버전 게이트(09. 04.)의 정의에 <b>배포</b>가 들어가므로, 게이트 판정의 집행자가 이 도메인이다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr>
        <th>주차</th>
        <th>마일스톤</th>
        <th>내용</th>
        <th>완료 기준</th>
      </tr>
    </thead>
    <tbody>
      <tr class="is-now">
        <td class="tbl__wk"><b>W1</b><span>08. 24. ~ 28.</span></td>
        <td>M1 선행조건 풀기</td>
        <td>AWS 계정 &middot; S3 &middot; SES 발신 도메인 신청 &middot; 앱 뼈대 머지 &middot; 목업 머지
            &rarr; <b>ERD 확정</b> &middot; 스키마 합의 2건 결정 &middot; Docker Compose &middot;
            브랜치 보호와 코드 소유자 갱신</td>
        <td>ERD 문서 상단이 "확정 vX.X &middot; 날짜". <code>docker compose up</code> 한 줄로 기동.
            백엔드 큐의 선행이 전부 해소됨</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W2</b><span>08. 31. ~ 09. 04.</span></td>
        <td>M2 실배포 1차 <span class="tag tag--gate">초기 버전</span></td>
        <td>IAM 최소 권한 정리 &middot; SQS 큐 생성 &middot; SES 샌드박스 해제 확인 &middot;
            EC2에 API와 워커 수동 배포 &middot; Vercel 연결 &middot; 환경변수 체계 확정 &middot;
            <b>09. 04. 초기 버전 게이트 판정</b></td>
        <td>외부 URL에서 <code>/health</code> 200. 프론트 프리뷰가 실 API를 바라본다.
            초기 버전 정의 4항목 전부 충족 판정</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W3</b><span>09. 07. ~ 11.</span></td>
        <td>M3 CI/CD</td>
        <td>PR마다 테스트 + 프론트 빌드 &middot; main 머지 시 EC2 배포 자동화 &middot;
            헬스체크와 로그 확인 경로</td>
        <td>push &rarr; 테스트 &rarr; 배포가 사람 손 없이 돈다.
            <b>CI 빨간불 = 머지 불가</b>가 오너제의 안전망으로 작동 시작</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W4</b><span>09. 14. ~ 18.</span></td>
        <td>중간 통합 점검</td>
        <td>QA 시나리오로 전 도메인 가로지르는 1차 통합 점검 &middot; 막힌 도메인 식별과 조정
            &middot; 모니터링 &middot; 로그 경로 정리</td>
        <td>중간 점검 결과가 주간 계획서에 기록되고 W5 계획에 반영됨</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W5</b><span>09. 21. ~ 25.</span></td>
        <td>M4 통합 &middot; 리허설</td>
        <td>QA 시나리오 전 항목 통합 리허설 &middot; 데모 환경 동결 &middot; 발표용 역할표 최종 확정</td>
        <td>데모 시나리오가 프로덕션 URL과 실기기에서 끊김 없이 돈다. 리허설 2회</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>버퍼</b><span>09. 28. ~ 30.</span></td>
        <td>1차 완성 판정</td>
        <td>잔여 버그 뒷처리 &middot; 발표 자료 총괄 착수</td>
        <td><b>09. 30. 1차 완성 선언</b> &mdash; 필수 기능 전부 프로덕션에서 동작</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">5.</span> 리스크 및 대응</h2>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>리스크</th><th>대응</th></tr>
    </thead>
    <tbody>
      <tr>
        <td><b>팀장 병목의 재생산</b></td>
        <td>도메인 오너제의 목적 자체가 이것을 없애는 것이다. 금요일 사이클에 인터페이스 PR이 몰리면
            의존 작업이 최대 1주 대기한다. 팀원은 <b>목요일까지</b> 올리고, 다른 도메인을 대기시키는
            PR은 수시 검수를 요청한다. 그래도 밀리면 그 주 계획서에 원인을 적는다.</td>
      </tr>
      <tr>
        <td><b>SES 샌드박스 해제 지연</b></td>
        <td>신청을 W1 첫날에 걸고, 해제 전에는 검증된 수신자(팀원 메일)로만 발송을 테스트한다.</td>
      </tr>
      <tr>
        <td><b>ERD 확정이 늦으면 전 도메인 대기</b></td>
        <td>목업 머지 직후 즉시 확정한다. 확정 시점을 앞당기는 결정을 W1에 내려 유지 중이다.</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">6.</span> 발표 포인트</h2>

  <ul class="talk">
    <li><b>배포 파이프라인을 어떻게 설계했는가</b> &mdash; Docker &rarr; EC2 &rarr; Actions 자동화까지의
        단계와 각 단계에서 무엇을 사람 손에서 뗐는가.</li>
    <li><b>권한 모델</b> &mdash; 클라우드의 IAM 최소 권한과 애플리케이션의 역할 3종을 어떤 기준으로
        나눴는가.</li>
    <li><b>5인 팀의 리뷰 병목을 구조로 풀었다</b> &mdash; 작업 풀 + 팀장 지시서 체계에서 도메인
        오너제로 전환한 과정. <b>조직 설계도 아키텍처다.</b></li>
  </ul>

</div>

<a class="role__back" href="{{ '/team/' | relative_url }}">&larr; 팀 구성 및 역할</a>

</div>
