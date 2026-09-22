---
layout: default
title: 프론트엔드
permalink: /role-frontend/
---

{% include role-style.html %}

<div class="role">

<div class="role__head">
  <p class="role__crumb"><a href="{{ '/team/' | relative_url }}">팀 구성 및 역할</a> &rsaquo;
     프론트엔드</p>
  <h1>프론트엔드 &middot; 담당 김민아</h1>
  <p>목업 8장을 실제 React 제품으로 &mdash; 칸반 드래그가 이 프로젝트의 얼굴
     &middot; 2026. 09. 04. 인계(앱과 겸임) &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="role__stat">
  <div class="stat"><span class="stat__k">담당</span>
    <span class="stat__v">김민아 <span class="who who-c">민아 C</span></span></div>
  <div class="stat"><span class="stat__k">소유 폴더</span>
    <span class="stat__v"><code>frontend/</code></span></div>
  <div class="stat"><span class="stat__k">스택</span>
    <span class="stat__v">React<small>Vite &middot; TypeScript</small></span></div>
  <div class="stat"><span class="stat__k">배포</span>
    <span class="stat__v">Vercel</span></div>
  <div class="stat"><span class="stat__k">화면</span>
    <span class="stat__v">8<small>장</small></span></div>
</div>

<div class="role__sec">

  <h2><span class="role__num">1.</span> 미션</h2>

  <p class="role__p">
    목업 8장을 실제 React 제품으로 만든다. 이 프로젝트의 진행 원칙이 <b>"UI가 정적 화면이 곧
    스펙이다"</b>인데, 그 UI를 최종 제품까지 끌고 가는 역할이다.
  </p>
  <p class="role__p">
    칸반 드래그와 낙관적 업데이트가 이 프로젝트의 얼굴이다 &mdash; 시연에서 가장 먼저 보이고,
    가장 자주 만지는 부분이다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">2.</span> 범위</h2>

  <div class="scope">

    <div class="scope__box scope__box--in">
      <h3>포함</h3>
      <ul>
        <li>React 앱 뼈대 &mdash; Vite &middot; TypeScript &middot; 라우팅 &middot; 토큰 CSS 변수 이식
            &middot; 공통 컴포넌트(사이드바 &middot; 테이블 &middot; 뱃지 &middot; 버튼 &middot; 인풋
            &middot; 토스트)</li>
        <li>목업 잔여 1장 &mdash; 공고 목록 화면</li>
        <li>전 화면의 페이지 컴포넌트화 + API 연동</li>
        <li>칸반 뷰 &middot; 드래그 단계 이동 &middot; <b>낙관적 업데이트와 롤백</b></li>
        <li>일괄 단계 변경 &middot; 업로드 진행률 &middot; 반응형(768px 모바일 웹)</li>
        <li>에이전트 UI 구현 협업</li>
        <li>Vercel 빌드 설정 (프로젝트 연결은 인프라)</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>제외</h3>
      <ul>
        <li>목업 색 리터럴 정리 &mdash; 총괄 담당. <b>그 전까지 토큰 블록 복사 규칙 유지</b></li>
        <li>대시보드 화면 &mdash; 보류. 3주차 이후 여유가 있으면</li>
        <li>모바일 네이티브 앱 &mdash; 앱 도메인. <b>여기서는 반응형 웹까지만</b></li>
      </ul>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">3.</span> 인터페이스 계약</h2>

  <p class="role__p">
    <b>의존</b> &mdash; 백엔드 API. 다만 <b>M1과 M2는 목데이터로 진행하므로 백엔드를 기다리지
    않는다.</b> 대신 <b>목데이터 필드명을 ERD와 동일하게</b> 맞춰, 실제 연동이 필드 교체만으로
    끝나도록 설계했다.
  </p>
  <p class="role__p">
    <b>제공</b> &mdash; 공통 컴포넌트와 디자인 토큰. 에이전트 UI가 프론트 화면 안에 들어오므로,
    에이전트 담당자가 올리는 프론트 파일 PR은 이 도메인 오너의 승인을 거친다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">4.</span> 주간 계획</h2>

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
        <td>M1 뼈대</td>
        <td>공고 목록 목업 인수 완성 &middot; React 뼈대(라우팅 &middot; 토큰 이식 &middot; 공통 컴포넌트)
            &middot; 로그인과 공고 목록 페이지(목데이터)</td>
        <td>목업 8장 전부 존재. 개발 서버에서 로그인 &rarr; 공고 목록 이동.
            <b>토큰이 CSS 변수 파일 하나로 모인다</b></td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W2</b><span>08. 31. ~ 09. 04.</span></td>
        <td>M2 전 화면 정적 <span class="tag tag--gate">초기 버전</span></td>
        <td>지원자 통합검색 &middot; 공고의 지원자(테이블 + 상세 패널) &middot; 평가 현황 &middot;
            설정 &middot; 지원 폼(공개 라우트) &middot; <b>Vercel 프리뷰 배포</b> &middot;
            지원 폼만 실 API 연동</td>
        <td>전 화면이 목데이터로 동작하고 <b>Vercel URL로 접근 가능</b>. 목업과 나란히 놓고 구분 안 됨.
            각 화면 로딩 &middot; 빈 상태 &middot; 오류 3종</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W3</b><span>09. 07. ~ 11.</span></td>
        <td>M3 API 연동</td>
        <td>JWT 로그인 플로우 &middot; 목록 &middot; 상세 &middot; 평가 &middot; 검색 &middot; 단계 필터
            &middot; 지원 제출과 업로드 진행률</td>
        <td><b>목데이터 import 0개.</b> 검색과 필터가 실제 10만 건을 친다.
            업로드 진행률이 S3 직행 전송을 표시한다</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W4</b><span>09. 14. ~ 18.</span></td>
        <td>M4 칸반</td>
        <td>칸반 뷰 토글 &middot; 드래그 단계 이동(낙관적 업데이트, <b>실패 롤백 + 토스트</b>) &middot;
            일괄 변경 &middot; 에이전트 UI 구현 협업</td>
        <td>드래그 실패 시 카드가 원위치로 롤백되고 토스트가 뜬다
            &mdash; <b>네트워크 차단으로 시연 가능</b></td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W5</b><span>09. 21. ~ 25.</span></td>
        <td>배포 &middot; 마감</td>
        <td>Vercel 배포 &middot; 극단값 &middot; 반응형 &middot; 접근성 마감</td>
        <td>프로덕션 URL에서 전 시나리오 동작</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>버퍼</b><span>09. 28. ~ 30.</span></td>
        <td>동결</td>
        <td>폴리시 &middot; 잔여 버그</td>
        <td><b>09. 30. 1차 완성</b></td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">5.</span> 작업 원칙</h2>

  <div class="items">

    <div class="item">
      <p class="item__t">화면 하나 = PR 하나</p>
      <p class="item__d">
        React로 이식할 때도 목업을 만들 때의 조각 루프를 유지한다. 화면 단위로 쪼개 올리고,
        <b>목업에 없는 요소나 토큰에 없는 값이 필요하면 멈추고 총괄에게 묻는다.</b>
        임의로 만들어 넣지 않는 것이 규칙이다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">지시서 없는 항목은 오너가 직접 쪼갠다</p>
      <p class="item__d">
        작업 큐 9건 중 지시서가 있는 것은 목업 1건뿐이고 나머지는 오너가 직접 설계한다.
        도메인 오너제에서 지시서 작성 여부는 오너 판단이다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">에이전트 UI 위치는 이미 확정됐다</p>
      <p class="item__d">
        시안 3안을 만들 계획이었으나 결정이 먼저 나면서 <b>시안 작업이 통째로 불필요해졌다.</b>
        확정안은 단축키 콘솔 + 콘솔 내 확인 카드이고, 남은 것은 W4의 구현 협업뿐이다.
      </p>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">6.</span> 리스크 및 대응</h2>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>리스크</th><th>대응</th></tr>
    </thead>
    <tbody>
      <tr>
        <td><b>목업 &rarr; React 이식에서 룩이 미묘하게 틀어짐</b></td>
        <td>완료 기준을 <b>"나란히 놓고 구분 안 됨"</b>으로 고정하고, PR마다 스크린샷 비교를 붙인다.</td>
      </tr>
      <tr>
        <td><b>칸반 낙관적 업데이트가 마지막 주에 몰림</b></td>
        <td>M4를 W3 후반에 시작할 수 있도록 M3에서 상세 패널까지 끝내둔다.</td>
      </tr>
      <tr>
        <td><b>두 번 일하게 되는 순서</b></td>
        <td>색 리터럴 정리(총괄) 전에 공통 CSS 파일을 만들면 정리 후 다시 손대야 한다.
            <b>정리 머지 후에 토큰을 파일화한다.</b></td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">7.</span> 발표 포인트</h2>

  <ul class="talk">
    <li><b>드래그 실패 시 낙관적 업데이트를 어떻게 롤백했는가</b> &mdash; 먼저 그려놓고 서버가 거절하면
        되돌리는 구조를, 실패를 일부러 주입해 시연까지 한다.</li>
    <li><b>정적 목업 8장을 컴포넌트로 이식한 전략</b> &mdash; 공통 조각을 어떻게 추출했고,
        토큰이 왜 전부 CSS 변수여야 했는가.</li>
  </ul>

</div>

<a class="role__back" href="{{ '/team/' | relative_url }}">&larr; 팀 구성 및 역할</a>

</div>
