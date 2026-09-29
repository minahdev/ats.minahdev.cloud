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
     &middot; 2026. 09. 04. 인계(앱과 겸임) &middot; 최종 갱신 2026. 09. 29.</p>
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
    <span class="stat__v">25<small>장</small></span></div>
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
  <p class="role__p">
    출발은 목업 8장이었지만 <b>지금 웹은 화면 25장</b>이다. 계획에 없던 확장 기능이 뒤에 ADR로
    편입되면서 늘었다 &mdash; 아르 챗 콘솔 &middot; AI 면접(실시간 화면 포함) &middot;
    지원자 본인 포털 &middot; 인적성 설문 &middot; 지원자 종합 요약.
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
        <li>대시보드 &mdash; 보류였다가 범위로 들어왔다. <code>/</code>가 <code>/dashboard</code>로
            가는 기본 화면이다</li>
        <li>ADR로 편입된 확장 화면 &mdash; 아르 챗 콘솔 &middot; AI 면접(<code>/interview-ai/:token</code>
            &middot; 실시간 <code>/interview-live/:token</code>) &middot; 지원자 본인 포털(<code>/my</code>)
            &middot; 인적성 설문(<code>/aptitude/:token</code>) &middot; 지원자 종합 평가
            (<code>/summary</code>)</li>
        <li>Vercel 빌드 설정 (프로젝트 연결은 인프라)</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>제외</h3>
      <ul>
        <li>목업 색 리터럴 정리 &mdash; 인프라&middot;총괄 담당. <b>정리는 끝났고</b> React 앱 토큰은
            <code>tokens.css</code> 한 파일에 모여 있다</li>
        <li>모바일 네이티브 앱 &mdash; 앱 도메인. <b>여기서는 반응형 웹까지만</b></li>
      </ul>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">3.</span> 인터페이스 계약</h2>

  <p class="role__p">
    <b>의존</b> &mdash; 백엔드 API. 다만 <b>M1과 M2는 목데이터로 진행해 백엔드를 기다리지
    않았다.</b> 대신 <b>목데이터 필드명을 ERD와 동일하게</b> 맞춰, 실제 연동이 필드 교체만으로
    끝나도록 설계했다 &mdash; 실제 연동은 M3에서 끝났다.
  </p>
  <p class="role__p">
    <b>제공</b> &mdash; 공통 컴포넌트와 디자인 토큰. 에이전트 UI가 프론트 화면 안에 들어오므로,
    에이전트 담당자가 프론트 파일을 고치면 <b>커밋 메시지에 명시하고 팀 채널에 사후 한 줄</b>을
    남긴다. 승인 게이트는 2026. 08. 28. 에 없어졌고, 리뷰는 필요할 때 이 도메인 오너에게
    요청하는 선택 사항이다.
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
      <tr>
        <td class="tbl__wk"><b>W1</b><span>08. 24. ~ 28.</span></td>
        <td>M1 뼈대</td>
        <td>공고 목록 목업 인수 완성 &middot; React 뼈대(라우팅 &middot; 토큰 이식 &middot; 공통 컴포넌트)
            &middot; 로그인과 공고 목록 페이지(목데이터)</td>
        <td><span class="tag tag--done">달성</span> 목업 8장 전부 존재. 개발 서버에서 로그인 &rarr;
            공고 목록 이동. <b>토큰은 08. 26. 에 <code>tokens.css</code> 한 파일로 모았다</b></td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W2</b><span>08. 31. ~ 09. 04.</span></td>
        <td>M2 전 화면 정적 <span class="tag tag--gate">초기 버전</span></td>
        <td>지원자 통합검색 &middot; 공고의 지원자(테이블 + 상세 패널) &middot; 평가 현황 &middot;
            설정 &middot; 지원 폼(공개 라우트) &middot; <b>Vercel 프리뷰 배포</b> &middot;
            지원 폼만 실 API 연동</td>
        <td><span class="tag tag--done">달성</span> 전 화면이 목데이터로 동작하고
            <b>Vercel URL로 접근 가능</b>. 목업과 나란히 놓고 구분 안 됨.
            각 화면 로딩 &middot; 빈 상태 &middot; 오류 3종. 초기 버전 게이트의 마지막 결손이던
            공개 지원 폼(<code>/apply/:token</code>)은 08. 31. 에 붙었다</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W3</b><span>09. 07. ~ 11.</span></td>
        <td>M3 API 연동</td>
        <td>JWT 로그인 플로우 &middot; 목록 &middot; 상세 &middot; 평가 &middot; 검색 &middot; 단계 필터
            &middot; 지원 제출과 업로드 진행률</td>
        <td><span class="tag tag--done">달성</span> 화면은 전부 실 API를 쓴다 &mdash; 목데이터는
            개발용 폴백(<code>api/mock.ts</code>)으로만 남아 배포 번들에서 빠진다. 검색과 필터가
            실제 10만 건을 치고, 업로드 진행률이 S3 직행 전송을 표시한다.
            <b>W3 물량은 08. 31. 에 이미 끝나 있었다</b></td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W4</b><span>09. 14. ~ 18.</span></td>
        <td>M4 칸반</td>
        <td>칸반 뷰 토글 &middot; 드래그 단계 이동(낙관적 업데이트, <b>실패 롤백 + 토스트</b>) &middot;
            일괄 변경 <span class="tag tag--miss">화면 미연결</span> &middot;
            에이전트 UI 구현 협업</td>
        <td><span class="tag tag--done">달성</span> 드래그 실패 시 카드가 원위치로 롤백되고 토스트가 뜬다
            &mdash; <b>네트워크 차단으로 시연 가능</b>. 칸반 자체는 08. 28. 에 먼저 붙었고,
            이 주에는 <b>칸반을 다시 그렸다</b>(이니셜 &middot; 조용한 옮기기 &middot; 종료 분리).
            에이전트 협업 몫은 아르 챗의 이력서 첨부와 선택형 답변이었다.
            일괄 단계 변경은 API 호출부(<code>stages.bulk</code>)까지만 있고 이를 부르는 화면이 아직 없다</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W5</b><span>09. 21. ~ 25.</span></td>
        <td>배포 &middot; 마감</td>
        <td>Vercel 배포 &middot; 극단값 &middot; 반응형 &middot; 접근성 마감</td>
        <td><span class="tag tag--now">이번 주</span> 프로덕션 URL은 <b>main 머지마다 Vercel이
            자동 배포</b>한다 &mdash; 자동 배포 연결은 08. 27. 에 이미 끝났다.
            768px 이하 모바일 웹 셸(하단 탭바)도 09. 02. 에 붙었다. 이번 주는
            극단값 &middot; 반응형 &middot; 접근성 마감을 훑는다</td>
      </tr>
      <tr class="is-now">
        <td class="tbl__wk"><b>버퍼</b><span>09. 28. ~ 30.</span></td>
        <td>동결</td>
        <td>폴리시 &middot; 잔여 버그</td>
        <td><b>09. 30. 1차 완성</b></td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="role__note">
    이 표에 없는 화면이 W2 뒤부터 계속 들어왔다 &mdash; 아르 챗 콘솔 08. 31. &middot;
    인적성 설문 09. 02. &middot; AI 면접과 지원자 본인 포털 09. 08. &middot;
    지원자 종합 평가 09. 14. 순이다. 전부 ADR로 편입된 뒤 붙은 것이라 원래 주간 계획에는 칸이 없다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">5.</span> 작업 원칙</h2>

  <div class="items">

    <div class="item">
      <p class="item__t">화면 하나 = PR 하나</p>
      <p class="item__d">
        React로 이식할 때도 목업을 만들 때의 조각 루프를 유지한다. 화면 단위로 쪼개 올리고,
        <b>목업에 없는 요소나 토큰에 없는 값이 필요하면 디자인 규칙 문서를 먼저 고쳐 토큰을
        추가하고 같은 커밋에서 반영한다.</b> 값을 임의로 박아 넣지 않는 것이 규칙이고,
        확정 토큰을 바꾸는 판단도 2026. 09. 04. 부터 도메인 오너 몫이다 &mdash; 승인을 기다리지 않는다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">지시서 없는 항목은 오너가 직접 쪼갠다</p>
      <p class="item__d">
        작업 큐 11건 중 지시서가 있는 것은 목업 1건뿐이고 나머지는 오너가 직접 설계한다.
        도메인 오너제에서 지시서 작성 여부는 오너 판단이다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">에이전트 UI 위치는 이미 확정됐다</p>
      <p class="item__d">
        시안 3안을 만들 계획이었으나 결정이 먼저 나면서 <b>시안 작업이 통째로 불필요해졌다.</b>
        확정안은 단축키 콘솔 + 콘솔 내 확인 카드였고, 구현 협업까지 끝나 지금은
        <code>Ctrl+K</code>(맥 &#8984;K)로 열리는 콘솔과 그 안의 확인 카드로 돌아간다.
        콘솔이 붙은 것은 W4가 아니라 <b>계획보다 이른 08. 31.</b> 이고, 09. 07. 에 우하단 도크로
        자리를 옮겼다.
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
        <td>M4를 W3 후반에 시작할 수 있도록 M3에서 상세 패널까지 끝내뒀다.
            <span class="tag tag--done">해소</span> API 연동과 칸반 물량이 08. 31. 에 먼저 끝나
            마지막 주로 밀리지 않았다.</td>
      </tr>
      <tr>
        <td><b>두 번 일하게 되는 순서</b></td>
        <td>색 리터럴 정리(인프라&middot;총괄) 전에 공통 CSS 파일을 만들면 정리 후 다시 손대야 한다.
            <span class="tag tag--done">해소</span> 토큰은 <code>tokens.css</code> 한 파일로 모였고,
            09. 04. 딥 네트워크 다크 전환도 그 파일의 <code>:root</code> 한 블록 교체로 끝났다.</td>
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
