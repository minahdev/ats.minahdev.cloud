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
        <li>업로드 진행률 &middot; 반응형(768px 모바일 웹)</li>
        <li>일괄 단계 변경 &mdash; 09. 10.에 공고별 지원자 화면의 체크박스와 하단 일괄 바를
            걷어내 <b>지금은 부르는 화면이 없다</b>. 단계 변경은 지원자 상세에서 한 명씩
            한다는 결정에 따른 것이고, 프론트 호출부(<code>stages.bulk</code>)와 서버
            엔드포인트(<code>/applications/bulk-stage</code>)는 그대로 남아 있어 되살리려면
            화면만 다시 붙이면 된다</li>
        <li>에이전트 UI 구현 협업</li>
        <li>대시보드 &mdash; 보류였다가 범위로 들어왔다. <code>/</code>가 <code>/dashboard</code>로
            가는 기본 화면이다</li>
        <li>ADR로 편입된 확장 화면 &mdash; 아르 챗 콘솔 &middot; AI 면접(<code>/interview-ai/:token</code>
            &middot; 실시간 <code>/interview-live/:token</code>) &middot; 지원자 본인 포털(<code>/my</code>)
            &middot; 인적성 설문(<code>/aptitude/:token</code>) &middot; 면접 시간 조율
            (<code>/schedule/:token</code>) &middot; 지원자 종합 평가(<code>/summary</code>
            &middot; <code>/summary/:applicationId</code>)</li>
        <li><b>지원자 셸</b> (09. 15.) &mdash; <code>/my/*</code> 한 라우트가 탭 넷(현황 &middot;
            인적성 검사 &middot; 면접 시간 &middot; AI 면접)을 <b>살려 둔 채</b> 품는다.
            메일 링크 착지점은 그대로 살아 있고, 셸의 탭은 그 착지점과 <b>같은 컴포넌트</b>를
            연다 &mdash; 화면을 두 벌 만들지 않는다</li>
        <li><b>지원자 비밀번호</b> (09. 16.) &mdash; 로그인 화면의 두 갈래(생년월일 8자리 &middot;
            비밀번호)와 메일 링크 착지점 <code>/set-password/:token</code>. 처음 정하기 &middot;
            재설정 &middot; 재발급이 모두 이 한 경로이고, <b>경로를 서버가 조립하므로</b>
            바꾸려면 백엔드와 같이 바꿔야 한다</li>
        <li><b>담당자 쪽 면접 화면</b> &mdash; 실시간 면접방(<code>/interview-room/:sessionId</code>)과
            AI 면접 판정 보기(<code>/interview-watch/:sessionId</code>). 로그인은 필요하지만
            <b>셸 밖</b>이다 &mdash; 사이드바가 있으면 지원자 얼굴이 그만큼 작아지고, 면접 중에
            다른 데로 새는 길이 화면에 남는다</li>
        <li>Vercel 빌드 설정 (프로젝트 연결은 인프라)</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>제외</h3>
      <ul>
        <li>목업 색 리터럴 정리 &mdash; 인프라&middot;총괄 담당. <b>정리는 끝났고</b> React 앱 토큰은
            <code>tokens.css</code> 한 파일에 모여 있다</li>
        <li>모바일 네이티브 앱 &mdash; 앱 도메인. <b>여기서는 반응형 웹까지만</b></li>
        <li>"평가 현황"(평가 대기 큐) &mdash; W2에 만들었으나 <b>09. 15.에 지웠다</b>.
            평가 큐와 지원자 상세의 평가 입력이 같은 API를 불러 어느 쪽이 진짜인지 갈렸고,
            평가는 그 사람을 보면서 하는 일이라 상세 쪽을 남겼다. 앱도 같은 날 같은 판단으로
            지웠다</li>
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
    W4 뒤로도 이어졌다 &mdash; 지원자 셸(탭 넷) 09. 15. &middot; 지원자 비밀번호 로그인과
    설정 화면 09. 16. &middot; 칸반 재설계와 "서류 탈락 / 면접 탈락" 09. 17. &middot;
    로그아웃 자리 개정 09. 18.
  </p>
  <p class="role__note">
    <b>실제로 한 일의 절반 이상은 새 화면이 아니라 고친 것이다.</b> 09. 04. 인계 이후
    <code>frontend/</code>를 건드린 본인 커밋 64건 가운데 <code>feat</code>가 29건이고
    나머지 35건이 <code>fix</code>(28) &middot; <code>refactor</code>(4) &middot;
    <code>chore</code>(3)다. 새 기능이 아니라 <b>이미 있던 화면이 사실과 다르게 말하거나
    같은 일을 두 자리에서 하던 것</b>을 고친 몫이고, 무엇이 반복됐는지는 7절에 묶어 두었다.
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

  <h2><span class="role__num">7.</span> 진행 중 해소한 쟁점</h2>

  <p class="role__note">
    09. 04. 인계 이후의 커밋 64건에서 <b>같은 종류의 문제가 반복해서 나왔다.</b> 아래는 그
    갈래를 묶은 것이고, 커밋을 나열한 것이 아니다. 해시는 저장소
    <code>Seuk-Team/Arda</code> 기준이며 수치는 전부 그 커밋에서 실측한 값이다.
  </p>

  <div class="items">

    <div class="item">
      <p class="item__t">인수한 코드에 다크 팔레트를 얹는 일 <span class="tag tag--done">해소 09. 04.</span></p>
      <p class="item__d">
        인계 첫 작업이 라이트 "새싹" 팔레트를 딥 네트워크 다크로 뒤집는 것이었다.
        <b>09. 04. 이전 프론트는 다른 사람이 짠 코드다</b> &mdash; 이전 오너와 뼈대 담당자가
        남긴 CSS 모듈 26개를 전부 열어야 하는 일로 보였는데, 실제로 <b>하드코딩 색이
        <code>tokens.css</code> 밖에 10개뿐</b>이어서 <code>:root</code> 한 블록 교체로 대부분
        따라왔다(<code>8c8d075</code>). 이식 단계에서 토큰을 한 파일로 모아 둔 것이 여기서
        값을 냈다.
      </p>
      <p class="item__d">
        그래도 한 커밋에 다 담지 않았다. <b>색 결정과 이름 변경을 섞으면 되돌리기 어렵다</b> &mdash;
        값만 먼저 옮기고 <code>--sprout</code>/<code>--leaf</code> &rarr; <code>--accent</code> 계열
        rename 은 다음 커밋으로 뺐다(<code>1d96160</code> &middot; 22개 파일 156곳). 긴 이름부터
        치환해 <code>--leaf</code>가 <code>--leaf-strong</code>을 갉아먹지 않게 했고, rename 으로
        생긴 자기 참조(<code>--accent: var(--accent)</code>)는 CSS가 순환을 계산 시점에 무효로
        처리해 값이 통째로 사라지므로 별칭 블록을 걷었다.
      </p>
      <p class="item__d">
        재질은 따로 붙였다(<code>3c0f0bf</code> &middot; <code>3fd8e88</code>). 유리
        (<code>backdrop-filter</code>)는 큰 껍데기와 싱글턴 29개에만 걸고 <code>rows.map()</code>
        안에서 데이터 수만큼 늘어나는 것(지원자 카드 &middot; 채팅 말풍선)은 제외했다 &mdash; blur는
        요소마다 별도 합성 패스라 개수에 비례해 비싸진다. 숫자 mono는 37곳에 넣고 <b>8곳을
        되돌렸다</b>: "tabular-nums = mono" 규칙이 너무 넓어 한글 섞인 칩까지 잡았고,
        공백 &middot; 괄호 &middot; 가운뎃점을 mono가 그려 "09.04 (금) 14:00" 칩이 18px 부풀었다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">개발 서버에서는 보이지 않던 버그 <span class="tag tag--done">해소 09. 04.</span></p>
      <p class="item__d">
        로그인 노드망을 옮기며 배포 번들을 뜯어 보니 표준 <code>backdrop-filter</code> 선언이
        <b>0개</b>, <code>-webkit-</code> 접두사만 29개였다. 손으로 쓴 접두사를 Lightning CSS가
        중복으로 보고 <b>표준 선언을 지운</b> 것이다 &mdash; 접두사를 모르는 브라우저에서는 유리가
        통째로 사라진다. 개발 서버는 미니파이를 안 해 드러나지 않았고, 대상은 이 커밋의 로그인
        카드만이 아니라 <b>앞 커밋의 유리 전부</b>였다. 접두사 29개를 걷어 도구에 맡기고 번들에
        표준 29 + 접두사 29로 짝을 맞췄다(<code>70ef0ec</code>).
      </p>
      <p class="item__d">
        여기서 확인 방식이 바뀌었다. 로그인 &middot; 공개 폼은 개발 모드에서 아예 볼 수 없다 &mdash;
        <code>DEV_USER</code>가 자동 로그인해 라우트로 못 간다. 그래서 그 화면은
        <b>프로덕션 빌드를 4173에 띄워</b> 잰다(<code>61eaf78</code>). 목 데이터
        (<code>70ef0ec</code>)와 <code>?preview</code> 표본(<code>8748866</code>)이 배포 번들에
        남지 않는 것도 같은 방법으로 실증했다 &mdash; <code>import.meta.env.DEV</code> 안에 두어
        빌드에서 죽은 코드로 제거된다.
      </p>
      <p class="item__d">
        같은 주에 <b>있는 줄 알았는데 안 되는 기능</b> 하나를 지웠다. 대시보드 캘린더 축소판의
        확대 전환(<code>MorphNav</code>)이 09. 01.에 호출부만 빠진 채 남아 구현 278줄과
        앵커 &middot; CSS 42줄이 살아 있었다(지운 줄 합계 368). 사흘간 아무도 아쉬워하지 않았으므로 되살리지 않고
        지우고, 그 전환을 여전히 요구하던 05-design 문서를 <b>같은 커밋에서</b> 코드에
        맞췄다(<code>8cbe5e3</code>) &mdash; 문서가 요구하는데 코드가 안 하는 상태를 남기면
        다음 사람이 "빠뜨린 것"으로 읽고 다시 만든다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">화면이 사실과 다른 것을 말하고 있었다 <span class="tag tag--done">해소 09. 10. ~ 18.</span></p>
      <p class="item__d">
        가장 자주 나온 갈래다. 기능이 없는 것이 아니라 <b>있는데 화면이 거짓을 적어 둔</b> 경우다.
      </p>
      <p class="item__d">
        <b>단계 변경 메일.</b> 확인 줄에 "합격 안내 메일을 이어서 보낼 수 있습니다"라고 적혀
        있었다. 아직 안 나갔으니 원하면 보내라는 뜻으로 읽히는데, 서버는 단계를 옮길 때 메일을
        <b>이미 보낸다</b> &mdash; <code>backend/app/stages.py</code>의 <code>NOTIFY_STAGES</code>가
        면접 &middot; 합격 &middot; 불합격 셋이고, <code>change_stage</code>가 단계 &middot;
        이력 &middot; 메일 행을 한 트랜잭션에 묶는다. 담당자가 그 문구를 믿고 연락처의
        [메일 보내기]를 한 번 더 누르면 <b>지원자에게 합격 안내가 두 번 간다.</b> 문구를
        "함께 나갑니다"로 바꾸고, 메일이 나가는데 안내가 아예 없던 면접 단계를 채우고, 상수
        이름도 <code>MAIL_AFTER</code> &rarr; <code>MAIL_ON_CHANGE</code>로 고쳤다
        (<code>f76e720</code>).
      </p>
      <p class="item__d">
        <b>지원자 "내 정보"의 비밀번호 칸.</b> 09. 16.에 지원자 비밀번호 로그인이 나갔는데 이
        칸만 "지금은 생년월일 8자리로 로그인합니다 &middot; 비밀번호를 정하는 기능은 준비
        중입니다"로 남아 있었다 &mdash; <b>이미 비밀번호로 들어온 사람이 자기 화면에서 그 문장을
        본다</b>(<code>011ae49</code>). 앱과 같은 말로 바꾸고, 여기에 폼을 새로 열지는 않았다:
        설정과 재설정이 메일 링크 한 경로이고 두 벌을 들면 한쪽만 고치는 날이 온다. 눌리지 않는
        버튼도 없앴다 &mdash; 비활성 버튼은 그 자체로 "고장인가 아직인가"를 묻게 만드는데, 누를
        것이 없으면 그 질문이 안 생긴다(안 쓰이게 된 CSS 25줄도 같이 지웠다).
      </p>
      <p class="item__d">
        <b>불합격 지원자의 진행 바.</b> <code>rejected</code>는 진행 단계 배열 밖이라
        <code>indexOf</code>가 -1이고, 그래서 <b>지나온 칸이 하나도 안 밝았다</b> &mdash; 다섯 갈래
        모두 "불합격" 한 마디에 밝은 칸 0이었다. 떨어진 지점까지 밝히고 그 자리에 "서류 탈락 /
        면접 탈락"을 붙였다(<code>e033c6d</code>). 뜻이 분명한 둘만 이름을 붙이고
        <code>applied &rarr; rejected</code>는 <b>"접수 탈락"이라고 쓰지 않는다</b> &mdash; 접수는
        성공한 것이라 말이 뒤집힌다. 되돌렸다 다시 떨어뜨린 경우를 위해 이력을 뒤에서 찾고,
        상세 응답이 <code>stage_history</code>를 이미 주므로 서버를 더 부르지 않았다.
      </p>
      <p class="item__d">
        <b>제출물 무결성 배지.</b> 네 판정 가운데 <code>none</code>을 <code>ok</code>와 같은
        초록으로 칠하지 않았다 &mdash; <code>none</code>은 "깨끗하다"가 아니라 <b>"증명할 근거가
        아예 없다"</b>이고, 초록으로 칠하면 보증하지 않는 것을 보증하는 것처럼 보인다.
        "확인을 못 했다"(<code>unreadable</code>)도 "바뀌었다"(<code>mismatch</code>)와 갈랐다.
        화면 문구도 "위조 방지"가 아니라 <b>"위조 검출"</b>이다 &mdash; DB를 고치는 것은 막을 수
        없고, 달라지는 것은 고친 사실이 드러난다는 점이다(<code>992247d</code>).
      </p>
    </div>

    <div class="item">
      <p class="item__t">같은 일을 하는 자리가 둘이면 어느 쪽이 진짜인지 갈린다 <span class="tag tag--done">해소 09. 10. ~ 18.</span></p>
      <p class="item__d">
        <b>단계 변경 진입점이 셋이었다</b> &mdash; 상단 진행 바 &middot; 메일 섹션의 합격/불합격
        &middot; 하단 고정 바. 상태만 바꾸고 메일을 빠뜨리는 사고가 실제로 났다. 상세 패널
        재설계에서 헤더의 [단계 변경] 하나로 줄이고, 진행 바는 <code>role="img"</code>로
        <b>읽는 것</b>으로 두었다 &mdash; 패널에서 제일 큰 요소가 늘 눌리면 스크롤하다 빗나간
        손가락에 메일까지 나가는 동작이 걸린다(<code>a8ae24a</code>).
      </p>
      <p class="item__d">
        <b>로그인 폼이 둘이었다.</b> <code>/login</code>의 지원자 칸으로 들어왔는데 로그아웃하면
        <code>/my</code> 안의 <b>다른 폼</b>이 떴다 &mdash; 생김새도 문구도 달랐다("지원 현황 조회 /
        조회하기" vs "내 지원 현황 / 로그인"). <code>/my</code>의 자체 폼을 걷고 토큰이 없으면
        <code>/login?as=applicant</code>로 보낸다 &mdash; 들어온 문과 나가는 문이 같아진다.
        <b>담당자가 이미 로그인돼 있어도 이 주소는 튕기지 않는다</b>: 전에는 대시보드로 보내
        담당자가 로그인해 둔 브라우저에서 지원자가 자기 현황을 볼 길이 아예 없었다
        (<code>feacf7f</code>).
      </p>
      <p class="item__d">
        <b>"평가 현황" 화면을 지웠다.</b> 평가 큐와 지원자 상세의 평가 입력이 같은 API를 불렀고,
        평가는 그 사람을 보면서 하는 일이라 상세 쪽을 남겼다. 대시보드의 "내 배정"은 숫자의 일이
        큐로 보내는 것이었으므로 갈 데 없는 숫자만 남아 통째로 뺐고, 덤으로
        <code>assignments.mine()</code>을 부르는 곳이 사라져 <b>대시보드가 여는 요청이 하나
        줄었다.</b> 지원자 상세가 계속 쓰는 타입과 엔드포인트는 남기고 백엔드는 건드리지 않았다
        &mdash; 옛 북마크는 catch-all을 타고 떨어지는 것까지 실측했다(<code>fb187a4</code>).
      </p>
      <p class="item__d">
        <b>로그아웃이 담당자 웹만 한 단계 안쪽에 있었다.</b> 지원자 웹과 앱은 계정 메뉴 한 자리에
        두는데 담당자 웹만 "내 계정" 화면 안에 있어, 나가려는 사람이 여기서만 두 단계를 더
        눌렀다. 09. 05.에 "프로필은 자주 눌리는 자리라 되돌릴 수 없는 항목을 두면 오조작이
        난다"로 정한 것을 <b>오너 판단으로 개정했다</b> &mdash; 전제가 틀렸다. <b>로그아웃은
        되돌릴 수 없는 일이 아니다</b>(되돌리는 비용이 다시 로그인 한 번이다). 같은 저장소 안에서
        앱은 이미 "되돌릴 수 있는 일이라 삭제와 같은 무게를 주지 않는다"고 판단하고 있었으니,
        한 서비스가 같은 동작을 두 가지로 판단하고 있었던 셈이다. 오조작은 <b>자리로 던다</b>
        &mdash; 구분선 아래 맨 끝. 옮긴 것이지 더한 것이 아니므로 "내 계정"에서는 빼고 안 쓰게 된
        CSS 41줄과 죽은 <code>import</code>도 같이 지웠다(<code>756f5e5</code>).
      </p>
      <p class="item__d">
        같은 규칙을 화면 구조에도 적용했다. 셸의 탭은 메일 링크 착지점과 <b>같은 컴포넌트</b>를
        열고(<code>aa3f14a</code>), 어느 링크를 열지 정하는 규칙은 <code>myApplicant.ts</code>
        한 곳에 모아 앱과 글자 하나까지 맞췄다 &mdash; 셸이 여는 세션과 현황이 그리는 줄이 달라
        <b>한 화면이 두 말을 하던</b> 사고가 앱에서 먼저 났기 때문이다(<code>9c6666a</code>).
      </p>
    </div>

    <div class="item">
      <p class="item__t">지원자 웹을 앱과 같은 셸로 다시 짜고, 그때 깨진 것을 되짚었다 <span class="tag tag--done">해소 09. 15.</span></p>
      <p class="item__d">
        <code>/my</code>는 한 장이었다. 인적성을 보려면 <code>/aptitude/&lt;토큰&gt;</code>이라는
        <b>셸 밖 화면</b>으로 나갔고 거기에는 <code>/my</code>로 돌아오는 링크가 한 개도 없었다
        &mdash; 브라우저 뒤로 가기가 유일한 길이었다. 앱은 같은 전형을 하단 탭 다섯으로 돌고
        있었으므로, <b>같은 사람이 같은 제품을 두 모양으로 썼다.</b> 앱
        <code>ApplicantShell</code>의 자리를 웹에 만들었다(<code>9c6666a</code>):
        <code>/applicant/me</code>를 한 번 부르고 탭에 나눠 주는 셸 &middot; 담당자 사이드바와
        같은 규격(216px &middot; 항목 48px) &middot; 탭마다 할 일 개수 배지 &middot; 지원이 둘
        이상일 때만 뜨는 "보고 있는 지원" 고르기. 어느 지원을 보는지는 상태가 아니라 주소
        (<code>?app=</code>)가 들고 있다 &mdash; 상태로 두면 탭을 옮길 때마다 처음 것으로 돌아간다.
      </p>
      <p class="item__d">
        그리고 <b>셸을 라우트로 짠 탓에 탭을 누를 때마다 앞 화면이 통째로 사라졌다</b> &mdash;
        사이드바를 넣으면서 스스로 만든 회귀다. 인적성 3문항을 답하고 현황에 들렀다 오면
        <b>3/10 &rarr; 0/10</b>이 됐고(10문항짜리라 중간에 한 번 눌러 보는 것이 드문 일이 아니다),
        AI 면접 중에 다른 탭을 누르면 소켓과 카메라만 닫히고 <code>/finish</code>는 안 불려
        세션이 <code>in_progress</code>로 남아 <b>담당자 화면에 "아직 보는 중"으로 영영
        걸렸다</b>(<code>88d43b0</code>). 고친 방법은 앱과 같다: 탭마다 파던 라우트를
        <code>/my/*</code> 하나로 합치고, 연 탭은 DOM에 남기고 안 보이는 것만 감춘다
        (<code>.pane[hidden]</code> &mdash; 앱 <code>IndexedStack</code>의 <code>_opened</code>와
        같은 구조). <b>안 연 탭은 만들지 않는다</b> &mdash; 처음부터 넷을 만들면 화면을 켜는 순간
        네 화면이 각자 자기 링크를 부른다. 스크롤도 본문 자리가 아니라 판마다 내 탭이 자기
        자리를 기억한다.
      </p>
      <p class="item__d">
        같은 주에 셸을 세 번 훑어 여섯을 더 찾아 네 커밋으로 고쳤다. 일정 채팅 입력줄이
        1000&times;800에서
        <b>뷰포트 밖</b>(아래끝 858px)에 있었다 &mdash; 채팅이 자기 높이를 직접 재고 있었고
        (<code>100dvh - 64px</code>) 사이드바가 가로로 눕는 폭에서는 그 띠 90px이 빠져 있었다.
        셸이 높이를 쥐게 바꿨다(<code>129ae72</code>). 셸이 <code>/applicant/me</code>를 한 번만
        받아 인적성을 내고 현황으로 오면 "아직 안 하셨습니다"와 배지가 그대로 남았다 &mdash; 탭을
        옮길 때마다 다시 받되 <b>두 번째부터는 실패해도 보던 것을 뺏지 않는다</b>(잠깐의
        네트워크 끊김으로 로그인 화면에 튕기면 하던 일이 날아간다). 그 밖에
        <code>/my/garbage</code>가 탭 없이 열려 활성 탭이 0개이던 것과 지운 사이드바
        <code>z-index</code>를 되살린 것(<code>eeae0d4</code>), 시안에 없던 880px 상한을 넣어
        1900px에서 왼쪽에 몰려 보이던 것을 되돌린 것(<code>9f1c50f</code>), 로딩 칸이 CSS 모듈을
        나누며 스타일을 못 찾던 것(<code>d3d6e77</code>)이 있다.
      </p>
      <p class="item__d">
        마지막 하나는 프로덕션 실측에서 나왔다. 서버 세션이 이미 <code>in_progress</code>면
        화면은 실시간 화면을 그리는데 <b>훅은 시작 버튼으로만 켜져서</b>, 카메라도 소켓도 안 열린
        채 "준비 중"만 뜬 <b>죽은 화면</b>이 됐다(<code>video</code>는 있는데
        <code>srcObject</code>가 null). 새로고침과 창 닫기가 <code>/finish</code>를 안 부르므로
        이 상태가 흔하고, 사이드바가 생기며 드나들 길이 늘어 더 자주 걸리게 됐다. 시작 전까지는
        준비 화면으로 두고 문구와 버튼만 "면접이 아직 열려 있습니다 / 이어서 하기"로 바꿨다 &mdash;
        <b>자동으로 켜지 않는다</b>(옛 웹은 링크 클릭만으로 카메라가 켜져 지원자가 무엇이
        시작되는지 모른 채 권한 팝업을 마주쳤다)(<code>ad04a87</code>).
      </p>
    </div>

    <div class="item">
      <p class="item__t">유리를 깔면 <code>z-index</code>가 통하지 않는 자리가 생긴다 <span class="tag tag--done">해소 09. 07. ~ 15.</span></p>
      <p class="item__d">
        다크 테마가 셸 크롬을 <code>backdrop-filter</code>로 바꾼 뒤 <b>같은 원인의 겹침 사고가
        다섯 번</b> 났다. <code>backdrop-filter</code>는 쌓임 맥락을 만든다 &mdash; 그것을 잊으면
        안쪽 값을 아무리 올려도 밖으로 나가지 못한다.
      </p>
      <p class="item__d">
        계정 메뉴가 본문 카드 뒤로 깔렸다. 제목 띠가 맥락을 만드는데 자신에게
        <code>z-index</code>가 없어 맥락이 <code>auto(0)</code>였고, <b>안쪽
        <code>z-index</code>를 아무리 올려도 맥락 밖으로 못 나간다</b> &mdash; 띠 전체를
        <code>--z-sticky</code>로 올렸다(<code>e66b656</code>). 사이드바 접기 손잡이는 경계 밖으로
        절반 삐져나오는 구조인데 사이드바에 <code>z-index</code>가 없어 그 절반이 제목 띠에
        덮였다 &mdash; 셸 크롬이 본문 띠보다 위여야 하므로 사이드바를 올렸다
        (<code>d47d16e</code>). 상세 패널의 고정 헤더가 비친 것은 배경이 없던 게 아니라
        반투명이었기 때문이고, <b>부모의 <code>backdrop-filter</code>는 자기 밑으로 스크롤해 오는
        자식에게는 안 먹힌다</b>(<code>a8ae24a</code>). 지원자 셸에서는 지운
        <code>z-index</code>를 되살렸다 &mdash; 그때도 목록이 본문 위로 잘 떨어지고 있었지만
        맥락 덕에 <b>우연히 맞는 것</b>이었다(<code>eeae0d4</code>).
      </p>
      <p class="item__d">
        아르 도크도 같은 값에 걸렸다 &mdash; 위 수정으로 사이드바가 <code>--z-dropdown</code>이 되면서
        도크(<code>--z-sticky</code>)가 그 뒤에 깔려 안 보였다. 같은 값을 쓰는 패널 &middot;
        시트를 덮지 않게 <b>사이드바 위에만</b> 올렸다. 그러다 <b>정의되지 않은 토큰</b>도 하나
        찾았다. <code>--bottomnav-h</code>를
        Layout 두 곳에서 쓰기만 하고 어디에도 정의한 적이 없었다. <code>var()</code>가 무효면
        그것을 쓴 <code>calc()</code>도 통째로 무효라 (1) 도크 <code>bottom</code>이 죽어
        모바일에서 화면 맨 위로 날아가고 (2) <code>main</code> 아래 여백이 0이 되어 본문이 하단
        내비에 가려 있었다. 토큰을 60px로 정의하고 하단 내비가 박아 둔 값도 그 토큰을 보게 했다
        (<code>09c36b0</code>).
      </p>
    </div>

    <div class="item">
      <p class="item__t">색과 폭은 눈이 아니라 자로 정했다 <span class="tag tag--done">해소 09. 07. ~ 17.</span></p>
      <p class="item__d">
        <b>단계 램프가 다 회색으로 보인다</b>는 지적을 재 보니 인접 &Delta;E(OKLab&times;100)가
        <b>9.6</b>이었다 &mdash; 정상 시야 구분 기준이 15이므로 취향이 아니라 실제로 안 보이는
        값이었다. 색상과 채도는 05-design &sect;1이 "판단 전 3단은 무채"로 못박아 손댈 수 없어
        밝기만 벌려 <b>15.9</b>로 올리고, 그러면서 잃을 뻔한 두 거리(막대 바탕 16.9 &middot;
        합격 18.4)를 확인했다. 부끄러운 것 하나를 커밋에 적어 남겼다 &mdash; 시안 단계에서
        검증기가 이미 이것을 FAIL로 잡았는데 순서 램프라 밝기가 단조 증가면 된다고 넘겼다.
        <b>검증기가 맞았다</b>(<code>c3e3450</code>).
      </p>
      <p class="item__d">
        <b>상세 패널 폭 620px은 재지 않고 정한 값</b>이었다. 실제로 재니 탭 4개 + 배지 3개(최악)가
        341px이면 충분해 한참 과했다. 폭별로 표를 만들어 500px로 내렸다 &mdash; 480 밑으로는 긴
        값(학교명 &middot; 공고 제목)이 3~4줄로 늘고, 500이면 1280px 화면에서 목록에 564px이
        남아 최소선 560을 넘는다. <b>덮지 않고 나란히 볼 수 있는 가장 좁은 폭</b>이다. 덮기
        경계도 560 + 500 + 216 = 1276에 맞춰 1275px로 따라 내렸다(<code>1ca5baa</code>).
        같은 화면에서 단계를 고를 때 <b>칸이 밀리는 것</b>도 수치로 잡았다 &mdash; 불합격 버튼이
        같은 줄에서 자리를 뺏어 칸이 74 &rarr; 65px로 줄고 면접 칸이 20px 밀렸다. 뒤쪽 버튼
        자리를 가장 넓은 상태로 미리 잡아 이동과 폭변화를 모두 0으로 만들었다
        (<code>fc952ab</code>).
      </p>
      <p class="item__d">
        칸반 재설계에서는 카드가 <b>다 똑같이 생긴 것</b>이 문제였다. 목록 API가 주는 값이
        이름 &middot; 경력 &middot; 지원일 &middot; 평점 넷뿐이라 "무엇을 더 적나"가 아니라
        "어떻게 구별되게 하나"로 풀었고, 상세가 쓰는 이니셜 원을 카드에도 두되 <b>색을 이름이
        정하게</b> 했다. 해시 나머지를 그대로 쓰면 한글 이름이 쏠린다 &mdash; 더미 14명으로
        <b>9 &middot; 5 &middot; 0 &middot; 0</b>이라 넉 장 중 둘은 아예 안 쓰였고, 다섯 비트를
        밀면 <b>3 &middot; 2 &middot; 4 &middot; 5</b>다(<code>pages/Kanban.tsx</code>).
        카드의 단계 셀렉트는 <code>appearance: none</code>이 있어야 브라우저가 제 상자를 그리지
        않고, 높이 32px는 그대로 둔다(숨겼다 꺼내면 카드가 커지며 아래가 덜컥 밀린다).
        종료를 진행 밖으로 가르려고 보드를 격자에서 flex로 바꿨다 &mdash;
        <code>minmax(220px,1fr)</code>에서는 구분선까지 220px짜리 칸이 되고, flex에서는
        <code>flex: none</code>이 있어야 선이 0으로 안 줄어든다. <b>둘 다 실측으로
        잡았다</b>(<code>a5c6061</code>).
      </p>
    </div>

    <div class="item">
      <p class="item__t">이미 오는 값을 다시 세지 않고, effect로 되돌리지 않는다 <span class="tag tag--done">해소 09. 07. ~ 10.</span></p>
      <p class="item__d">
        대시보드를 현황판으로 다시 짜면서 호출이 <b>26회에서 3회</b>로 줄었다. 필요한 값이
        <code>postings</code> 응답의 <code>stage_counts</code> 안에 이미 있는데
        <code>countByStage</code>를 15번 따로 돌리고 있었다 &mdash; 새 엔드포인트가 아니라 안 쓰던
        값을 쓴 것이다(<code>c61117f</code>). 지원자 목록의 단계 칩 숫자도 같은 서버 집계값을
        쓴다: <b>현재 쪽의 행을 세지 않는다</b> &mdash; 페이지를 넘기면 숫자가 바뀐다. 정렬도 서버가
        <code>sort</code> &middot; <code>order</code>를 이미 받는데 프론트 래퍼가 노출을 안 하고
        있었을 뿐이고, <b>경력 순은 넣지 않았다</b> &mdash; 서버 정렬 키가 둘뿐이라 클라이언트에서
        섞으면 현재 쪽 10건만 뒤집혀 거짓말이 된다(<code>a91c64d</code>). 평가자별 점수와
        지원자의 인적성 &middot; 면접 시간도 백엔드가 처음부터 내려주고 있었고 프론트 타입에만
        빠져 있었다(<code>103567e</code> &middot; <code>8748866</code>).
      </p>
      <p class="item__d">
        반대로 <b>부르지 않기로</b> 정한 것도 있다. 무결성 API는 볼 때마다 S3에서 원본을 다시
        읽으므로 목록에서 부르면 사람 수만큼 S3를 읽는다 &mdash; 상세에서만 부르고 그 이유를
        <code>api/endpoints.ts</code> 주석에 남겼다(<code>992247d</code>).
      </p>
      <p class="item__d">
        렌더도 같은 방식으로 줄였다. 같은 린트 지적(<code>set-state-in-effect</code>)을 세 번
        만났고 세 번 다 <code>useEffect</code>를 고치지 않고 <b>없앴다</b>. 무결성 배지는 지원자가
        바뀔 때 effect 안에서 상태를 비우고 있었는데 실제로도 <b>앞 지원자의 결과가 한 프레임
        남았다</b> &mdash; 부모가 <code>key={applicationId}</code>로 리마운트하게 바꿨다
        (<code>5b58a2e</code>). 고르던 단계도 <code>key</code> 리마운트가 곧 초기화였고
        (<code>c9cd176</code>), 공고 제목은 지원자가 바뀌면 부모가 통째로 언마운트되므로 비우는
        한 줄이 애초에 필요 없었다(<code>c88d5f1</code>). 경고 수는 5 &rarr; 4로 재설계 전
        수준으로 돌아왔다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">웹과 앱이 서로의 값을 베낀다 <span class="tag tag--done">해소 09. 11. ~ 16.</span></p>
      <p class="item__d">
        두 클라이언트를 한 사람이 들고 있으므로, 값이 갈리는 것을 문서가 아니라 <b>실측값으로</b>
        막았다. 로그인 화면의 담당자/지원자 두 칸 세그먼트는 앱 <code>_RoleTabs</code>의 값을
        그대로 옮겼다 &mdash; 바깥 3px 안쪽 &middot; 칸 높이 38px &middot; 글자 14px w600
        &middot; 칸 사이 간격 0 &middot; 켜진 칸은 테두리 없이 <code>rgba(34,211,238,.13)</code>
        배경만. 힌트 문구까지 앱과 같게 맞추고 프로덕션 빌드에서 앱 토큰과 전부 일치하는지
        확인했다. 이 작업의 출발은 <b>웹에 지원자 로그인과 현황 화면이 이미 다 있는데 거기로 가는
        링크가 코드 전체에 0개</b>였다는 것이다 &mdash; 주소를 직접 치지 않으면 아무도 못
        들어갔다(<code>61eaf78</code>).
      </p>
      <p class="item__d">
        비밀번호 로그인에서는 <b>화면이 서버보다 먼저 막는다</b>. bcrypt가 72바이트를 넘는 입력을
        말없이 자르고 그 뒤는 무엇을 치든 같은 비밀번호가 되는데, 한글은 글자당 3바이트라 24자쯤이
        한계다. 서버도 422로 막지만 제출 뒤에 알면 처음부터 다시 쳐야 하므로 한 곳에서 먼저
        잡는다 &mdash; 실측으로 한글 24자(72바이트) 통과 &middot; 25자(75바이트) 거절까지 경계를
        확인했다. <b>감추기로 한 것은 화면도 드러내지 않는다</b>: 만료된 링크와 이미 쓴 링크가
        같은 410 같은 문구이고, 설정 링크 요청은 지원 이력이 있든 없든 같은 화면이다 &mdash;
        갈라 말하면 "이 사람이 여기 지원했나"를 떠보는 도구가 된다(ADR-0033).
        앱에는 설정 화면을 만들지 않았다 &mdash; 매니페스트에 딥링크가 없어 메일 링크는 브라우저로
        열린다(<code>5a19334</code> &middot; 백엔드 PR #268).
      </p>
      <p class="item__d">
        마지막은 두 클라이언트가 <b>한 판정을 만들기 위해 역할을 바꾼</b> 건이다. 앱이 얼굴
        프레임을 한 장도 안 보내고 있었다 &mdash; 실기기 실측으로 면접 내내
        <code>frames.recv</code>가 4806에서 1도 안 움직이고 <code>live.no_face</code>만 +82였다.
        영상이 WebRTC로 갈리면서 JPEG 경로가 개발용 화면에만 남은 것이고, 서버가 WebRTC에서
        얼굴을 뽑으려면 SFU가 필요해 09. 30. 전에는 못 한다. 그래서 <b>이미 그 영상을 받아 그리고
        있는 담당자 방</b>이 보내게 했다 &mdash; 가는 곳만 토큰 없는 자리에서
        <code>/ai/ws/interview/{token}?role=recruiter</code>로 바꿨다. 앱이 소리를, 담당자가
        얼굴을 <b>같은 토큰으로</b> 보내야 서버가 둘을 한 판정으로 묶는다(전에는 소켓마다 세션이
        새로 생겨 앱은 얼굴 없음, 담당자는 소리 짧음으로 양쪽 다 판정이 안 났다). 판정이 오는
        길도 바뀌어 훅 셋을 이어야 했다 &mdash; 안 이으면 판정 패널이 "지원자가 말하기 시작하면
        여기에 나타납니다"에서 영영 안 바뀐다. 도중에 <code>aiWsUrl</code>이 쿼리를 경로에 이어
        붙여 <code>?</code>가 <code>%3F</code>로 이스케이프돼 토큰이
        <code>ORjRSr4K%3Frole=recruiter</code>가 되던 것도 잡았다 &mdash; <b>접속 자체가 실패할
        값</b>이었다(<code>5a25971</code> &middot; 백엔드 PR #273).
      </p>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">8.</span> 발표 포인트</h2>

  <ul class="talk">
    <li><b>같은 FastAPI에 웹과 앱을 붙였고, 두 클라이언트가 한 판정을 만들었다</b> &mdash;
        앱이 WebRTC로 갈리며 얼굴 프레임을 한 장도 안 보내던 것(<code>frames.recv</code> 4806
        고정 &middot; <code>no_face</code> +82)을, SFU 없이 <b>이미 그 영상을 그리고 있는 담당자
        웹</b>이 같은 면접 토큰으로 보내게 바꿨다. 서버가 소리와 얼굴을 한 세션으로 묶는 지점까지
        말할 수 있다(<code>5a25971</code> &middot; 백엔드 PR #273).</li>
    <li><b>드래그 실패 시 낙관적 업데이트를 어떻게 롤백했는가</b> &mdash; 먼저 그려놓고 서버가 거절하면
        되돌리는 구조를, 실패를 일부러 주입해 시연까지 한다.</li>
    <li><b>지원자 웹을 앱과 같은 셸로 다시 짜며 스스로 만든 회귀를 찾아 고쳤다</b> &mdash;
        탭을 옮기면 인적성 답이 3/10에서 0/10이 되고, AI 면접이 <code>/finish</code> 없이 끊겨
        담당자 화면에 "아직 보는 중"으로 걸렸다. 라우트 교체를 버리고 앱
        <code>IndexedStack</code>과 같은 keep-alive(<code>.pane[hidden]</code>)로 갔다 &mdash;
        <b>같은 제품을 두 모양으로 쓰게 두지 않는다</b>가 판단 기준이었다(<code>88d43b0</code>).</li>
    <li><b>화면 문구가 사고의 원인이 되는 경우</b> &mdash; 단계 변경 확인 줄이 "메일을 이어서 보낼 수
        있습니다"라고 적혀 있었는데 서버는 단계를 옮길 때 이미 보내고 있었다. 담당자가 그 문구를
        믿으면 지원자에게 합격 안내가 두 번 간다. 코드가 아니라 문구를 고친 버그다
        (<code>f76e720</code>).</li>
    <li><b>색과 폭은 눈이 아니라 자로 정했다</b> &mdash; 단계 램프 인접 &Delta;E 9.6 &rarr; 15.9
        (시안 단계 검증기의 FAIL을 넘긴 것이 틀렸다는 것까지 기록에 남겼다), 상세 패널
        620 &rarr; 500px(560 + 500 + 216 = 1276이라 1275px에서 덮기로 넘어간다)
        (<code>c3e3450</code> &middot; <code>1ca5baa</code>).</li>
    <li><b>개발 서버에서는 안 나던 프로덕션 전용 버그</b> &mdash; 손으로 쓴 접두사를 Lightning CSS가
        중복으로 보고 표준 <code>backdrop-filter</code>를 지워, 배포 번들에 표준 0 &middot;
        접두사 29였다. 개발 모드가 자동 로그인하는 화면은 프로덕션 빌드를 직접 띄워 재는 쪽으로
        확인 방식을 바꿨다(<code>70ef0ec</code>).</li>
    <li><b>오너가 자기 결정을 개정하는 운영이 실제로 어떻게 도는가</b> &mdash; 09. 05.에 "로그아웃은
        되돌릴 수 없으니 한 단계 안쪽"으로 정한 것을 09. 18.에 뒤집었다. 전제가 틀렸고(되돌리는
        비용이 다시 로그인 한 번), 같은 저장소 안에서 앱은 이미 반대로 판단하고 있었다. 승인
        대기 없이 커밋 본문에 근거를 남기고 개정한다(<code>756f5e5</code>).</li>
    <li><b>정적 목업 8장을 컴포넌트로 이식한 전략</b> &mdash; 공통 조각을 어떻게 추출했고,
        토큰이 왜 전부 CSS 변수여야 했는가. 값을 낸 지점이 인계 직후다 &mdash; 다크 팔레트 전환이
        하드코딩 색 10개와 <code>:root</code> 한 블록 교체로 끝났다(<code>8c8d075</code>).</li>
  </ul>

</div>

<a class="role__back" href="{{ '/team/' | relative_url }}">&larr; 팀 구성 및 역할</a>

</div>
