---
layout: default
title: 앱 (모바일)
permalink: /role-app/
---

{% include role-style.html %}

<div class="role">

<div class="role__head">
  <p class="role__crumb"><a href="{{ '/team/' | relative_url }}">팀 구성 및 역할</a> &rsaquo;
     앱 (모바일)</p>
  <h1>앱 (모바일) &middot; 담당 김민아</h1>
  <p>담당자 &middot; 면접관용 모바일 네이티브 앱 &mdash; 웹과 같은 API를 쓰는 두 번째 클라이언트.
     2026. 09. 08.부터 지원자 갈래까지 한 앱에 들어 있다 &middot; 최종 갱신 2026. 09. 29.</p>
</div>

<div class="role__stat">
  <div class="stat"><span class="stat__k">담당</span>
    <span class="stat__v">김민아 <span class="who who-c">민아 C</span></span></div>
  <div class="stat"><span class="stat__k">소유 폴더</span>
    <span class="stat__v"><code>mobile/</code></span></div>
  <div class="stat"><span class="stat__k">스택</span>
    <span class="stat__v">Flutter<small>Dart</small></span></div>
  <div class="stat"><span class="stat__k">대상 플랫폼</span>
    <span class="stat__v">Android<small>전용</small></span></div>
  <div class="stat"><span class="stat__k">화면</span>
    <span class="stat__v">23<small>장</small></span></div>
  <div class="stat"><span class="stat__k">위젯 테스트</span>
    <span class="stat__v">373<small>개 &middot; 30파일</small></span></div>
  <div class="stat"><span class="stat__k">앱 커밋</span>
    <span class="stat__v">60<small>건 / 78</small></span></div>
  <div class="stat"><span class="stat__k">1차 완성</span>
    <span class="stat__v">09. 30.<small>수</small></span></div>
</div>

<div class="role__sec">

  <h2><span class="role__num">1.</span> 미션</h2>

  <p class="role__p">
    담당자와 면접관이 이동 중에 지원자를 확인하고, 전형 단계를 바꾸고, 평가를 남기는
    <b>모바일 네이티브 앱</b>을 만든다. 웹 클라이언트와 <b>동일한 API</b>를 사용하는 두 번째
    클라이언트로서, "API를 제대로 설계하면 클라이언트가 몇 개든 붙는다"를 실제로 증명하는
    트랙이다.
  </p>
  <p class="role__p">
    앱은 API를 <b>소비만 하고 제공하지 않는다.</b> 다른 파트에 대한 의존은 백엔드 API 전부이지만,
    반대로 앱이 실패해도 다른 파트가 멈추지 않는다 &mdash; 시스템에서 격리 수준이 가장 높은 트랙이다.
  </p>
  <p class="role__p">
    2026. 09. 08.부터 <b>한 앱을 담당자와 지원자가 같이 쓴다.</b> 지원자 화면은 탭 셸 밖에 따로
    두어 담당자 UI를 한 조각도 보여 주지 않고, 지원자는 지원할 때 쓴 이메일로 <b>담당자와 별개인
    지원자 전용 토큰</b>을 받는다. 지원 현황 &middot; AI 면접 &middot; 실시간 면접 &middot;
    인적성 검사 &middot; 면접 시간 조율이 그 갈래에 들어 있다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">2.</span> 기술 스택 및 선정 근거</h2>
  <p class="role__note">
    2026. 08. 26. Flutter로 확정. 실개발과 시연은 Android 전용이며, iOS는 코드 호환만 유지한다.
  </p>

  <div class="items">

    <div class="item">
      <p class="item__t">Flutter (Dart) &mdash; 자체 렌더링 엔진</p>
      <p class="item__d">
        화면이 OS와 무관하게 동일하게 그려지고, 위젯 카탈로그가 넓어 서드파티 의존이 적다.
        개발 환경은 Flutter 3.44.8 / Dart 3.12.2이며 Android Studio와 Android SDK를 함께 쓴다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">디자인 토큰은 수동 이식</p>
      <p class="item__d">
        웹의 <code>tokens.css</code>가 원본이고, CSS 값을 Dart <code>ThemeData</code>로 옮긴다.
        임의의 색을 새로 정하지 않으며, 완료 기준에 모바일 목업 대조를 포함해 웹과 룩이
        어긋나는 것을 막는다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">폰트는 CDN이 아니라 앱에 번들</p>
      <p class="item__d">
        웹은 Google Fonts CDN을 쓰지만 앱은 <code>assets/fonts/</code>에 직접 담았다.
        발표장 네트워크 상태에 시연이 좌우되지 않게 하기 위함이다. 굵기는 디자인 문서가 실제로
        지정한 400 &middot; 600 두 종만 담아 5.4MB로 줄였고, SIL OFL 1.1 라이선스 사본 배포
        요구를 지키려고 <code>OFL.txt</code>를 <code>LicenseRegistry</code>에 등록했다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">앱 ID <code>cloud.seuk.arda</code></p>
      <p class="item__d">
        스토어에 올리면 영구 고정되는 값이라 코드가 쌓이기 전에 확정했다. 조직명 기반 후보도
        있었으나, <b>실제로 소유한 도메인이 있으면 그것이 규칙상 맞는 근거</b>라 팀 도메인
        <code>seuk.cloud</code>를 거꾸로 쓴 값을 택했다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">iOS는 "지원"이라고 말하지 않는다</p>
      <p class="item__d">
        Mac이 없어 iOS 빌드 검증이 불가능하다. 따라서 iOS 지원 플러그인만 쓰고 플랫폼 분기를
        남기지 않는 <b>코드 호환까지만</b> 유지하며, 검증하지 못한 것을 지원한다고 주장하지 않는다.
      </p>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">3.</span> 개발 범위</h2>
  <p class="role__note">
    처음 범위는 로그인 &middot; 공고 리스트 &middot; 지원자 리스트 &middot; 지원자 상세 &middot;
    단계 변경 &middot; 평가 작성 &middot; 이력서 열람 7개였다.
    2026. 09. 01.에 웹이 사이드바 6개로 커지면서 앱도 그 화면 지도를 따라갔고,
    09. 08.부터 지원자 갈래가 더 붙어 <b>지금은 화면 23장</b>이다.
  </p>

  <div class="scope">

    <div class="scope__box scope__box--in">
      <h3>포함</h3>
      <ul>
        <li>로그인 (JWT) &mdash; 토큰은 보안 저장소에 둔다</li>
        <li>하단 탭바 5칸 &mdash; 공고 &middot; 지원자 &middot; 홈 &middot; 캘린더 &middot; 더보기</li>
        <li>대시보드(홈) &mdash; 폰은 위에서부터 읽으므로 급한 순으로 다시 세웠다</li>
        <li>공고 리스트 + <b>공고 등록 &middot; 수정 &middot; 삭제</b> &mdash; 웹은 마감 &middot;
            다시 열기만 있어, 공고를 만들고 고치고 지우는 곳은 앱뿐이다</li>
        <li>지원자 리스트 &mdash; 단계 탭 필터 + 압축 퍼널 바</li>
        <li>전 공고 통합 검색 &mdash; 테이블 대신 카드형 + [더 보기]</li>
        <li>지원자 상세 &mdash; 지원 정보 &middot; 아르의 요약 &middot; 메일 이력 &middot; 메모.
            단계 이력 타임라인 &middot; 평가 목록은 별도 화면</li>
        <li><b>단계 변경 버튼</b> (드래그 대신, 확인 시트 한 번)</li>
        <li>평가 작성 &mdash; 중복은 앱이 막고, 내가 쓴 것은 고친다</li>
        <li>이력서 열람 (presigned URL)</li>
        <li>캘린더 &mdash; 월 그리드 없이 주간 스트립 + 그날 목록</li>
        <li>메일 발송 &mdash; 프리셋 &rarr; 프리필 &rarr; 확인 3단계. 치환은 서버가 한다</li>
        <li>더보기 &middot; 설정 &mdash; 내 계정 탭(이름 &middot; 비밀번호)만 잠금이 풀렸다</li>
        <li><b>아르</b>(에이전트) &mdash; 전체 화면 시트. 쓰기는 앰버 점선 확인 카드를
            사람이 눌러야 돈다</li>
        <li><b>지원자 갈래</b> (09. 08.) &mdash; 지원자 로그인(비밀번호 &middot; 안 정한 계정만
            생년월일, 09. 16.) &middot; 지원 현황 &middot; AI 면접 &middot; 실시간 면접(WebRTC)
            &middot; 인적성 검사 &middot; 면접 시간 조율 &middot; 내 정보</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>제외</h3>
      <ul>
        <li>지원 폼 &mdash; 지원자용 외부 링크는 웹 전용</li>
        <li>칸반 &mdash; 모바일 금지 원칙</li>
        <li>평가 현황(평가 대기 큐) &mdash; 09. 01.에 만들었으나 09. 15.에 웹과 맞춰 지웠다.
            평가는 지원자 상세에서 남긴다 &mdash; 같은 일을 하는 자리가 둘이면 어느 쪽이
            진짜인지 갈린다</li>
        <li>앱 내 푸시 알림 &mdash; 여유 시 별도 합의</li>
        <li>팀 기기 전원 APK 배포 &mdash; 09. 02.에 계획에서 뺐다.
            APK는 필요할 때 뽑아 전달하면 된다</li>
        <li>스토어 배포 &mdash; 데모는 Android APK 직접 전달</li>
        <li>iOS 실기기 시연 &mdash; Mac 부재로 빌드 불가</li>
      </ul>
    </div>

  </div>

  <p class="role__note" style="margin-top:1.1rem; margin-bottom:0;">
    모바일에서 칸반을 버린 것은 화면 크기 때문만이 아니다. 좁은 화면의 드래그 앤 드롭은 오조작이
    잦고, 오조작이 곧 지원자의 전형 단계 변경으로 이어진다. 터치 목표는 44px 이상으로 두고
    <b>명시적인 단계 변경 버튼</b>으로 대체했다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">4.</span> 인터페이스 계약</h2>

  <p class="role__p">
    <b>의존</b> &mdash; 백엔드 API 전부. 인증 기능이 API 연동 마일스톤의 선행 조건이다.
    <b>제공</b> &mdash; 없음.
  </p>
  <p class="role__p">
    원칙은 <b>앱 때문에 API를 바꾸지 않는 것</b>이다. 부족한 것이 발견되면 앱에서 우회하지 않고
    백엔드 담당자와 인터페이스 변경으로 합의한다. 클라이언트를 하나 더 붙였을 때 서버가
    몇 줄 바뀌었는지 &mdash; 혹은 바뀌지 않았는지 &mdash; 자체가 이 트랙의 결과물이다.
  </p>

  <p class="role__note">
    그래서 결과를 수치로 적는다. 앱이 부르는 서버 경로는
    <code>mobile/lib/api/endpoints.dart</code> 한 파일에 모여 있고 지금 <b>36개</b>다.
    문자열을 화면에 흩지 않은 것이 이 표를 셀 수 있게 만든 이유이기도 하다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr>
        <th>앱이 부르는 경로 36개의 출처</th>
        <th class="tbl__num">건</th>
        <th>근거</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><b>앱이 오기 전에 이미 열려 있던 것</b><br>
            <span class="stat__k">담당자 갈래 전부 + 지원자 공개 경로(면접 5 &middot; 인적성 2
            &middot; 일정 3)</span></td>
        <td class="tbl__num"><b>33</b></td>
        <td>큐 7 &middot; 8 (09. 02. ~ 03.)에서 <b>당시 화면 17개를 전부 서버에 붙이는 동안 앱
            때문에 생긴 백엔드 커밋은 0건</b>이다(화면 수는 큐 8 완료 시점 트리
            <code>8be4aa3</code> 기준). 그 이틀의 백엔드 커밋은 AI 면접
            (<code>2edf624</code> &middot; <code>c3087ec</code> &middot; <code>6f3ce65</code>)
            &middot; 인적성(<code>d1d34ba</code>) &middot; 에이전트(<code>ea964da</code> &middot;
            <code>4c5559b</code>) &middot; 시맨틱 검색(<code>833ad7e</code>)이고,
            앱이 부른 경로를 고친 것은 하나도 없다. 09. 08. 지원자 탭을 붙일 때도
            <b>탭 넷이 부르는 API 가 이미 다 열려 있었다</b> &mdash; 커밋이 절 제목을
            「네 탭 다 진짜 API 가 있다 (백엔드 변경 없음)」으로 달고 있다
            (<code>5c25066</code>)</td>
      </tr>
      <tr>
        <td><b>앱이 있어서 생긴 것</b><br>
            <span class="stat__k"><code>POST /public/applicant/login</code> &middot;
            <code>GET /applicant/me</code></span></td>
        <td class="tbl__num"><b>2</b></td>
        <td>ADR-0033 이 문제 진술을 "지원자가 <b>앱에서</b> 자기 지원 현황을 본다"로 적고 있다.
            백엔드 오너가 썼고(<code>0ac3de9</code> &middot; 확장 <code>e4e146b</code> &middot;
            alembic 리비전 <code>0012</code> 로 <code>birth_date</code> 추가),
            앱은 저장소 메서드가 501 을 던지는 <b>껍데기 상태로 화면을 먼저 만들어 두고</b>
            기다렸다(<code>a74fca5</code>). 서버가 오자 <b>그 메서드 하나만</b> 진짜 호출로
            바꿨다 &mdash; 화면 &middot; 저장 &middot; 이동은 그대로다(<code>17ce2c6</code>)</td>
      </tr>
      <tr>
        <td><b>결정 개정으로 생긴 것</b><br>
            <span class="stat__k"><code>POST /public/applicant/password-setup-request</code></span></td>
        <td class="tbl__num"><b>1</b></td>
        <td>ADR-0033 개정(비밀번호 로그인)을 백엔드 오너가 확정하고
            (<code>92d2378</code>, PR #268, 09. 16.), 같은 날 웹(<code>f9bb9d4</code>)과
            앱(<code>cfe4764</code>)이 나란히 붙었다. 한 클라이언트만 따라가면 <b>웹에서
            비밀번호를 정한 사람이 앱에서 잠긴다</b></td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="role__p" style="margin-top:1.1rem;">
    <b>부족한 것을 앱에서 우회하지 않았다.</b> 연동 중에 계약 공백 넷이 드러났다 &mdash;
    평가자 이름(<code>EvaluationOut</code> 은 <code>evaluator_id</code> 뿐) &middot;
    단계 이력의 변경자 &middot; 이력의 메일 발송 여부(필드 자체가 없다) &middot;
    목록 API 의 학력 &middot; 기술. 전용 엔드포인트도 대개 같은 스키마라 더 불러도 소용이 없었다
    &mdash; <b>메모만 예외</b>여서, 전용 경로가 <code>author_name</code> 을 주는 그 한 자리는
    요청을 하나 더 쓰기로 했다(&ldquo;이서연 &middot; 08.21&rdquo;과 &ldquo;알 수 없음 &middot;
    08.21&rdquo;은 쓸모가 다르다). 나머지는 <b>id 를 화면에 띄우거나 값을 지어내지 않고 그 자리를
    접었다</b>(<code>1624352</code> &middot; <code>0448264</code>). 반대로 실제로 서버를 고쳐야 했던 한 건은
    백엔드에 넘겼다: 만료 판정이 토큰을 열 때만 돌아 기한이 지난 인적성이
    <code>/applicant/me</code> 목록에 그대로 실리던 것이다. 09. 15. 실기기 보고가
    <code>e281b15</code>(09. 16.)로 닫혔고, 그 커밋은 <b>앱이 제안한 규칙(만료 시각만 보고
    거르기)을 거절했다</b> &mdash; 그대로 쓰면 끝난 면접이 화면에서 사라지는 09. 09. 문제가
    되돌아온다는 이유다. 인터페이스 합의가 실제로 양방향으로 돌아간 자리다.
  </p>
  <p class="role__p">
    <b>흐름이 한 번 거꾸로 갔다.</b> 지원자 갈래는 앱이 먼저 만들었고(09. 08.,
    <code>applicant_shell.dart</code>), 웹은 그때까지 <code>/my</code> 한 장이라 인적성을 보려면
    셸 밖 토큰 주소로 나가야 했다. 09. 15. 에 웹에 같은 구조를 옮겼다 &mdash;
    <code>/applicant/me</code> 를 한 번 부르고 탭에 나눠 주는 셸, 그리고 앱과 글자 하나까지 맞춘
    <code>pickLink</code> 규칙(<code>9c6666a</code>). <b>서버는 이때도 바뀌지 않았다.</b>
    나중에 만든 클라이언트의 설계가 먼저 있던 클라이언트로 옮겨 간 것이라, 계약이 얇게 잘 서 있으면
    <b>클라이언트를 늘리는 비용만 싼 것이 아니라 한쪽에서 배운 것을 다른 쪽에 그대로 옮길 수
    있다</b>는 이야기가 된다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">5.</span> 주간 계획</h2>
  <p class="role__note">
    앱은 초기 버전(09. 04.) 범위 밖이다. 그 시점까지의 기여는 전환기 백엔드 분담과 스택 결정이며,
    앱 트랙 자체는 1차 완성(09. 30.)을 기준으로 진행한다.
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
      <tr>
        <td class="tbl__wk"><b>W1</b><span>08. 24. ~ 28.</span></td>
        <td>전환기 + 뼈대 선행</td>
        <td>공고 CRUD &middot; 지원자 API &middot; 담당자 직접 등록 &middot; 스택 확정 &middot;
            Flutter 뼈대</td>
        <td><span class="tag tag--done">완료</span> 전환기 백엔드 분담 3건과 스택 결정 완료.
            <b>W2 예정이던 앱 뼈대를 08. 26.에 앞당겨 끝냈다.</b></td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W2</b><span>08. 31. ~ 09. 04.</span></td>
        <td>M1 뼈대</td>
        <td>당초 계획(프로젝트 생성 &middot; 토큰 이식 &middot; 내비게이션)은 W1에 완료.
            남은 것은 목데이터 화면 착수</td>
        <td><span class="tag tag--done">완료</span> Android 실기기 구동 확인 &mdash; 정적 분석
            무경고, 테스트 통과. 09. 01. 릴리스 APK를 뽑아 전달했다(서명은 debug 키 &mdash;
            스토어 배포가 아니라 직접 설치다). 기기 전원 설치 확인은
            <b>09. 02.에 계획에서 뺐다.</b></td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W3</b><span>09. 07. ~ 11.</span></td>
        <td>M1 정적 화면</td>
        <td>목데이터로 지원자 리스트 &middot; 상세 &middot; 로그인 화면 &middot;
            <b>(09. 01. 앞당김)</b> 하단 탭바 + 대시보드 &middot; 캘린더 &middot; 통합 검색
            &middot; 더보기 &middot; 평가 현황 &middot; 설정</td>
        <td><span class="tag tag--done">완료</span> 09. 01. 모바일 목업 &middot; 시안과 나란히 놓고
            같은 제품으로 보이고, 목데이터 필드명이 ERD와 일치한다. 정적 분석 무경고 &middot;
            테스트 175개 통과 &middot; 실기기 확인.
            <b>W4 예정이던 로딩 &middot; 빈 &middot; 오류 3종도 여기서 선행했다.</b></td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W4</b><span>09. 14. ~ 18.</span></td>
        <td>M2 API 연동</td>
        <td>JWT 로그인 &middot; 공고 &middot; 지원자 실데이터 &middot; <b>단계 변경</b> &middot;
            평가 작성 &middot; 메일 발송 &middot; 아르 (3종은 W3에서 선행)</td>
        <td><span class="tag tag--done">완료</span> JWT 로그인 09. 02. &middot; 단계 변경 저장
            09. 02. &middot; 나머지 연동 09. 03. 앱에서 단계를 바꾸면
            <b>웹 칸반에 반영된다</b>(같은 API 증명). 당초 완료 기준이던 "면접관 계정은 배정된
            지원자만 보인다"는 <b>ADR-0017(08. 31.)로 폐지됐다</b> &mdash; 로그인하면 전부
            조회하고 역할은 <code>admin</code> &middot; <code>member</code> 2종이라,
            앱은 역할별 화면 분기를 만들지 않는다. 남은 제한은 <code>member</code>의
            평가 작성(배정된 건만)뿐이고, <code>admin</code>은 그마저 없다.</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W5</b><span>09. 21. ~ 25.</span></td>
        <td>M3 마감 &middot; 데모</td>
        <td>극단값 점검(긴 이름 &middot; 태그 다수 &middot; 자소서 5천 자) &middot; 오프라인 안내
            &middot; 데모 시나리오 &mdash; <b>이력서 열람은 09. 03.에 끝냈다</b></td>
        <td><b>데모에 쓸 기기</b>에서 APK로 구동. 데모 시나리오(출근길 서류 검토 &rarr; 단계 변경
            &rarr; 메일 자동 발송 수신)가 끊김 없이 돈다.</td>
      </tr>
      <tr class="is-now">
        <td class="tbl__wk"><b>버퍼</b><span>09. 28. ~ 30.</span></td>
        <td>동결</td>
        <td>데모 동결 &middot; (여유 시) 내부 테스트 트랙 배포</td>
        <td><b>09. 30. 1차 완성</b></td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="role__note" style="margin-top:1.1rem; margin-bottom:0;">
    <b>M1&ndash;M3은 계획보다 앞서 끝났다</b> &mdash; 뼈대 08. 26. &middot; 정적 화면 09. 01.
    &middot; API 연동 09. 03. 그래서 09. 07. 이후의 실제 작업은 주간 계획에 없던 확장과
    재설계다: 다크 팔레트 이식과 대시보드 현황판(09. 07.) &middot; 지원자 갈래와
    AI 면접(09. 08. ~ 09.) &middot; 인적성 검사와 면접 시간 조율 탭(09. 08.) &middot;
    실시간 면접 WebRTC(09. 09. ~ 10.) &middot; 그 탭 넷과 지원자 홈의 재설계 + 비밀번호
    로그인(09. 15. ~ 16.) &middot; 캘린더와 담당자 홈 재설계(09. 16.).
    확장은 ADR로 편입해 같은 방식으로 이어 갔다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">6.</span> 작업 큐</h2>
  <p class="role__note">
    위에서부터 순서대로 소화한다. 선행이 풀리지 않았으면 건너뛰고 다음 것을 잡는다.
    전환기 1&ndash;3번은 <b>앱 자신의 선행 조건(지원자 API)을 본인 손으로 푸는 구조</b>였다 &mdash;
    순서를 지킨 덕분에 대기 시간이 없었다. 8번까지가 원래 큐이고, 9번 이후는 계획에 없던
    확장이다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr>
        <th>#</th>
        <th>작업</th>
        <th>선행</th>
        <th>상태</th>
      </tr>
    </thead>
    <tbody>
      <tr class="is-done">
        <td>1</td><td>(전환기) 공고 CRUD API</td><td>ERD 확정</td>
        <td><span class="tag tag--done">완료</span> 08. 25.</td>
      </tr>
      <tr class="is-done">
        <td>2</td><td>(전환기) 지원자 목록 &middot; 상세 API</td><td>1번</td>
        <td><span class="tag tag--done">완료</span> 08. 25.</td>
      </tr>
      <tr class="is-done">
        <td>3</td><td>(전환기) 담당자 직접 등록</td><td>2번</td>
        <td><span class="tag tag--done">완료</span> 08. 25.</td>
      </tr>
      <tr class="is-done">
        <td>4</td><td>앱 스택 확정 (아키텍처 결정 기록)</td><td>&mdash;</td>
        <td><span class="tag tag--done">완료</span> 08. 26.</td>
      </tr>
      <tr class="is-done">
        <td>5</td><td>Flutter 프로젝트 생성 + 토큰 이식 + 내비게이션 뼈대</td><td>4번</td>
        <td><span class="tag tag--done">완료</span> 08. 26.</td>
      </tr>
      <tr class="is-done">
        <td>6</td>
        <td>지원자 리스트 &middot; 상세 &middot; 로그인 &middot; 공고 리스트 (목데이터)
            + 모바일 시안 반영</td>
        <td>5번</td>
        <td><span class="tag tag--done">완료</span> 08. 28.</td>
      </tr>
      <tr class="is-done">
        <td>6.5</td>
        <td>앱 UI 초안 반영 &mdash; 하단 탭바 &middot; 대시보드 &middot; 캘린더 &middot;
            통합 검색 &middot; 더보기 &middot; 평가 현황 &middot; 설정 + 로딩 &middot; 빈 &middot;
            오류 3종</td>
        <td>6번</td>
        <td><span class="tag tag--done">완료</span> 09. 01.</td>
      </tr>
      <tr class="is-done">
        <td>7</td><td>JWT 로그인 연동 &mdash; 앱에 처음으로 네트워크가 생겼다</td><td>백엔드 인증</td>
        <td><span class="tag tag--done">완료</span> 09. 02.</td>
      </tr>
      <tr class="is-done">
        <td>8</td>
        <td>리스트 &middot; 상세 &middot; 단계 변경 &middot; 평가 &middot; 메일 &middot;
            공고 등록/수정 &middot; 이력서 열기 &middot; 캘린더 &middot; 아르 연동 &mdash;
            <b>목데이터로 남은 화면이 없다</b></td>
        <td>백엔드 M1 &middot; M2</td>
        <td><span class="tag tag--done">완료</span> 09. 03.</td>
      </tr>
      <tr class="is-done">
        <td>9</td>
        <td>지원자 갈래 &mdash; 지원자 로그인 &middot; 지원 현황 &middot; AI 면접 (ADR-0033)</td>
        <td>8번</td>
        <td><span class="tag tag--done">완료</span> 09. 08. ~ 09.</td>
      </tr>
      <tr class="is-done">
        <td>10</td>
        <td>실시간 면접(WebRTC) 지원자 자리 &mdash; 담당자 웹과 1:1로 얼굴을 마주 본다.
            이 화면(<code>interview_live_screen.dart</code>)은 <b>면접 트랙이
            <code>mobile/</code> 에 직접 넣은 것</b>이다 <span class="who who-e">수택 E</span>
            &mdash; 앱 오너 몫은 셸에 앉히는 것과 자원 해제였다(<code>36bb7c5</code>)</td>
        <td>9번</td>
        <td><span class="tag tag--done">완료</span> 09. 09. ~ 10.</td>
      </tr>
      <tr class="is-done">
        <td>11</td>
        <td>지원자 갈래 재설계 &mdash; 인적성을 <b>한 번에 한 문항</b>으로
            (<code>e5bdf81</code>) &middot; 면접 시간 확정 판(<code>8d3b439</code>) &middot;
            더보기를 「내 정보」로(<code>e0d169e</code> &middot; <code>0d037f0</code>) &middot;
            지원자 홈(<code>05e7295</code> &middot; <code>8150e25</code>) &middot;
            비밀번호 로그인 (ADR-0033 개정, <code>cfe4764</code>).
            <b>탭 자체는 9번에서 이미 서버에 붙어 있었고</b>, 여기서 바뀐 것은 흐름과 위계다</td>
        <td>9번</td>
        <td><span class="tag tag--done">완료</span> 09. 15. ~ 16.</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="role__note" style="margin-top:1.1rem; margin-bottom:0;">
    <code>mobile/</code> 를 건드린 커밋은 78건이고 그중 <b>60건이 앱 오너 것</b>이다. 남은 18건
    중 17건은 실시간 면접 &middot; 마이크 &middot; 얼굴 프레임처럼 <b>AI 면접 트랙이 앱 폴더에 직접
    넣은 것</b>이다 &mdash; <span class="who who-b">우정 B</span> 9건,
    <span class="who who-e">수택 E</span> 8건. 도메인 밖 편집을 커밋에 명시하고 사후 공지하는
    현재 규칙대로 들어왔다. 남은 한 건은 코드가 아니다 &mdash; <code>mobile/README.md</code> 에
    「토큰에 없는 값은 승인을 받고 추가한다」로 남아 있던 옛 문장을 <b>「같은 커밋에서 05-design
    갱신 + 사후 공지」로 고친 문서 정리</b>(<code>c37e4f1</code>, 09. 02.)다. 규칙이 바뀐 것을
    앱 폴더의 문서까지 따라오게 한 자리다.
    9 &middot; 10번이 그 경계에 걸쳐 있다: 지원자 갈래와 AI 면접 화면의
    껍데기 &middot; 탭 배치 &middot; 카메라 생명주기는 앱 오너가, 소켓 &middot; STT &middot;
    WebRTC 파이프라인은 면접 트랙이 넣었다. <b>앱이 순수 소비자여서 생긴 일</b>이다 &mdash;
    앱은 다른 도메인에 아무것도 제공하지 않지만, 다른 도메인이 지원자 화면을 필요로 할 때는
    이 폴더로 들어온다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">7.</span> 진행 중 해소한 쟁점</h2>
  <p class="role__note">
    앱 커밋 60건을 나열하지 않고 <b>문제의 종류</b>로 묶었다 &mdash; 같은 부류가 두 번 이상 나온
    것은 한 항목에 모았다. 절반은 <b>실기기(SM-S928N / Android 16)에 올려 보고서야</b>
    드러난 것이다: <code>flutter analyze</code> 무결 &middot; 위젯 테스트 전부 통과인데도 폰에서
    보면 틀린 것들이다.
  </p>

  <div class="items">

    <div class="item">
      <p class="item__t">지원자 갈래를 한 앱 안에 냈다 &mdash; 셸을 둘로 갈라서
        <span class="tag tag--done">해소 09. 08.</span></p>
      <p class="item__d">
        앱은 로그인해야 아무것도 볼 수 없는데 <b>지원자에게는 계정이 없었다.</b> 길이 셋이었다
        &mdash; ① 앱을 하나 더 만든다 ② 한 셸에 역할 분기를 둔다 ③ 셸을 둘로 두고 탭 밖에서
        갈라 보낸다. <b>③을 골랐다.</b> <code>applicant_shell.dart</code> 는 담당자 셸과 겹치는
        것이 하나도 없다 &mdash; 탭도, 상단 제목도, 부르는 API 도 다르다. 역할 분기를 한 셸에
        두면 담당자 UI 가 한 조각이라도 새어 나갈 자리가 생긴다.
        토큰 저장 키까지 갈랐다(<code>arda.applicant_token</code> &harr;
        <code>arda.access_token</code>): 같은 키면 서로 덮어써 한쪽이 <b>조용히 로그아웃</b>되고,
        서버가 <code>typ</code> 로 갈라 보므로 섞이면 401 만 남아 원인을 못 찾는다.
        <b>섞일 자리를 코드에서 없앴다</b> &mdash; 클라이언트 조립이 갈려 있어
        (<code>applicantClient()</code> &harr; <code>authedClient()</code>) 각자 자기 저장소만
        읽는다. 09. 08. 당시에는 지원자 경로가 전부 주소에 토큰을 싣는 방식이라 Authorization
        헤더가 아예 없었고, 서버 로그인이 생긴 뒤에는 <b>지원자 전용 토큰</b>(2시간 &middot;
        리프레시 없음)만 Bearer 로 붙는다. 담당자 신분이 지원자 요청에 실릴 길은 여전히 없다.
        결과: <b>요청 하나</b>(<code>GET /applicant/me</code>)가 지원자 탭 다섯을 채운다. 셸이
        한 번 받아 탭에 나눠 주고 홈은 서버를 아예 안 부르며, 나머지 탭은 열 때 자기 링크만
        부른다. 런치 화면은 셋으로 갈린다 &mdash; 담당자 토큰이 먼저다(12시간짜리라 살아 있으면
        방금 로그인한 것이다).
        근거: <code>9a5c658</code> &middot; <code>5c25066</code> &middot; <code>17ce2c6</code>
      </p>
    </div>

    <div class="item">
      <p class="item__t">지원자 인증 방식이 여드레 사이에 세 번 바뀌었다 &mdash; 그때마다 화면을 먼저 세웠다
        <span class="tag tag--done">해소 09. 16.</span></p>
      <p class="item__d">
        ① <b>링크 붙여넣기</b>(09. 08. <code>9a5c658</code>) &mdash; 서버 공개 경로가 전부 토큰
        방식이라 메일로 받은 링크를 앱에 넣게 했다. 43자 &middot; 22자 토큰을 손으로 치게 하지
        않으려고 붙여넣기 칸이었다.
        ② <b>이메일 + 생년월일 8자리</b>(<code>a74fca5</code>) &mdash; 링크를 설치할 때 주는
        것으로 바꾸면서 방식을 바꿨는데 <b>서버에 아직 없었다.</b> 화면만 먼저 만들고 저장소
        메서드가 501 을 던지게 뒀다. 이때 백엔드에 전한 것이 <b>이 방식의 약점</b>이다 &mdash;
        지원자 나이대가 좁아 경우의 수가 만 단위이고, <code>portal.py</code> 가 링크 방식을
        고른 이유가 바로 그것이라고 주석에 적혀 있었다. 시도 횟수 제한이 같이 와야 한다고
        적었고, ADR-0033 이 그 넷(5회 15분 잠금 &middot; 사유를 나누지 않는 401 &middot;
        <code>typ</code> 분리 &middot; 조회 인자 없음)을 결정에 담았다.
        ③ <b>비밀번호</b>(09. 16. <code>cfe4764</code> &mdash; 백엔드 개정은
        <code>92d2378</code> &middot; PR #268) &mdash; 개정 사유는 ADR 이 스스로
        적어 둔 약점과, 지원 폼에서 생년월일이 <b>선택</b>이라 그 칸을 비운 사람은 영영 못
        들어오는 구멍이었다. 폼을 필수로 고쳐서는 닫히지 않는다 &mdash; 안 낸 사람은 지원 자체가
        막히고 그건 더 나쁘다.
        ③에서 앱이 웹보다 늦으면 <b>웹에서 비밀번호를 정한 사람이 앱에서 잠긴다.</b> 생년월일로
        401 이 나는데 서버가 실패 사유를 일부러 안 나누므로 화면이 이유를 알려 줄 수 없다.
        백엔드 문서 두 곳 어디에도 앱 얘기가 없어 <b>서로 모르고 지나갈 뻔한 자리</b>였다.
        대응은 「비밀번호로 로그인」과 「설정 링크 받기」를 <b>늘 보이게</b> 둔 것이다 &mdash;
        길이 늘 열려 있어야 스스로 찾고, 늘 보이므로 계정 상태가 새어 나가지 않는다. 설정 링크
        요청은 <b>성공 &middot; 실패가 같은 화면</b>이고(서버가 지원 이력과 무관하게 202 를 주는
        것과 같은 이유다), 로그인 실패에 「비밀번호를 정하셨네요」를 쓰지 않는다. 테스트 5개 중
        하나가 <b>「설정 링크 요청이 실패해도 같은 문구다」</b> &mdash; 이 원칙이 코드에서 깨지면
        그것이 먼저 운다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">서버가 없는 동안 개발용 문 둘을 열었고, 서버가 온 날 지웠다
        <span class="tag tag--done">해소 09. 08.</span></p>
      <p class="item__d">
        지원자 로그인이 서버에 없어 <b>다 만든 지원자 화면에 들어갈 길이 하나도 없었다.</b>
        둘을 열었다 &mdash; 서버를 캔 데이터로 <b>대신하는</b> 데모 모드
        (<code>APPLICANT_DEMO</code>, <code>631fd9b</code>)와, 담당자가 웹에서 만든 링크를 붙여넣어
        <b>진짜 서버로</b> 들어가는 '링크로 입장'(<code>APPLICANT_LINK</code>,
        <code>a64cd94</code>). 뒤엣것은 백엔드 담당자가 자기 서버에 붙여 볼 때 쓰는 문이라
        카메라도 동의 &middot; 시작 &middot; 답변 &middot; 종료도 서버에 남는 기록도 전부 진짜다.
        <b>새는 것을 막는 장치를 같이 넣었다</b> &mdash; 목데이터가 조용히 진짜인 척한 사고가
        이미 있었기 때문이다(아래 항목). 기본값 false &middot; 데모는 화면 모서리에 '데모' 리본.
        처음에는 <code>kDebugMode</code> 로 묶었는데, <b>나눠 줄 APK 는 릴리스라야 했다</b>
        (디버그 186MB / 릴리스 54MB) &mdash; 릴리스에서 상수가 false 로 접혀 팀원이 받아 봐야
        지원자 화면에 못 들어갔다. <b>쓸 수 없는 안전장치는 안전장치가 아니라서</b> 묶음을 풀고,
        남은 셋(기본값 false &middot; 데모 리본 &middot; 링크 입장은 애초에 진짜 서버)으로
        갔다(<code>a1bf4c2</code>).
        <b>로그인이 서버에 생긴 날 둘 다 지웠다</b>(<code>17ce2c6</code>) &mdash; 지금 저장소에
        두 플래그는 한 글자도 없다. 같은 부류로 평문 HTTP 허용이 있다: Android 9 부터
        <code>http://</code> 가 막혀 로컬 백엔드에 못 붙고 앱에는 "연결하지 못했습니다" 로만
        보이는데, <b>디버그 매니페스트에만</b> 넣고 릴리스는 https 전용으로 뒀다
        (<code>a828e2e</code>).
      </p>
    </div>

    <div class="item">
      <p class="item__t">탭을 살려 두는 셸에서 카메라를 놓지 못했다 &mdash; 같은 원인으로 두 번
        <span class="tag tag--done">해소 09. 16.</span></p>
      <p class="item__d">
        지원자 셸은 <code>IndexedStack</code> 으로 탭을 살려 둔다(인적성 답 &middot; AI 면접이
        탭을 옮길 때마다 날아가지 않게 한 선택이다). 그래서 <b>이 화면들은 앱이 살아 있는 한
        dispose 되지 않는다</b> &mdash; 놓는 코드를 <code>dispose()</code> 에만 두면 영영 안 돈다.
        <b>① 09. 08.</b> 다른 탭을 보는 내내 카메라가 잡혀 있었고, 그 사이 다른 앱이 카메라를
        가져가면(기본 카메라 앱을 열었다 닫으면) 돌아왔을 때 검은 화면이 남았다.
        <b>탭 전환은 앱 생명주기 신호가 오지 않는다</b> &mdash; 셸이 보이는 탭을 알려 주고 화면이
        그때 열고 닫게 했다(<code>5c25066</code>).
        <b>② 09. 16.</b> 「면접 종료」를 누르고 완료 문구가 떠도 카메라 표시등이 계속 켜져 있었고
        앱을 죽여야 꺼졌다. 눈에 안 보이는 쪽이 더 나빴다 &mdash; 판정 소켓도 안 닫혀
        <b>서버가 끝난 세션을 계속 판정했다.</b> 실기기로 면접을 끝낸 뒤에도
        <code>/ai/health</code> 의 <code>live.scored</code> 와 <code>no_face</code> 가 10초에
        하나씩 나란히 오르는 것으로 확인했다(09. 16. 실측). <b>끝나는 길이 셋</b>인데
        (종료 버튼 / 서버가 보내는 <code>InterviewDone</code> &mdash; 질문을 다 답하면 이 길이라
        더 흔하다 / 조회가 done &middot; expired 를 받음) 어느 것도 안 놓고 있었다. 셋 다
        <code>_releaseCall()</code> 을 부르고 두 번 불러도 안전하게 뒀다. 종료 버튼은
        <b>서버가 끝을 확인한 뒤에</b> 놓는다 &mdash; 먼저 놓으면 종료가 실패했을 때 카메라만
        꺼지고 면접은 살아 있는 자리가 된다.
        <b>테스트를 못 붙였다는 사실을 커밋에 그대로 적었다.</b> 이 화면은
        <code>MicService</code> 와 소켓을 하드코딩해 만들어(주입구가 WebRTC 하나뿐) 위젯
        테스트가 플랫폼 채널에 걸려 죽는다 &mdash; <b>이 화면에 테스트가 한 줄도 없는 것이 이
        버그가 살아남은 까닭이다.</b> 주입구를 내는 것은 별도 작업으로 남겼다.
        근거: <code>5c25066</code> &middot; <code>36bb7c5</code> &middot;
        <code>interview_live_screen.dart:457</code>
      </p>
    </div>

    <div class="item">
      <p class="item__t">빈 상태를 예외로 두고 만든 화면들을 기본으로 다시 그렸다
        <span class="tag tag--done">해소 09. 16.</span></p>
      <p class="item__d">
        실기기에서 캘린더를 보니 <b>화면의 60%가 빈 공간</b>이었다. 이번 주가 0건이라 「면접 없음」
        상자 하나 뒤로 아무것도 없었다. <b>면접이 없는 날은 예외가 아니라 기본에 가깝다</b>
        &mdash; 면접은 한 주에 몇 건이고 나머지 날은 원래 비어 있는데, 화면은 "있다"를 기본으로
        놓고 만들어져 <b>정작 흔한 경우에 무너졌다.</b>
        캘린더(<code>4c6dc5e</code>): 0 을 숫자로 찍지 않고 작은 점으로 자리만 남긴다(빼 버리면
        칸 높이가 날마다 달라진다) &middot; 선택 표시를 밝은 채움에서 워시 + 테두리로 한 톤
        낮췄다(고른 날이 0건일 때가 많아 「여기 뭔가 있다」로 잘못 읽혔다) &middot; 일요일 적갈을
        뺐다(적갈은 불합격 &middot; 실패에만 쓴다. 종이 달력의 관습을 빌려 와 예외로 뒀던
        자리인데, 그 관습 때문에 오히려 「이 날 뭔가 잘못됐다」로 읽힐 여지가 컸다) &middot;
        <b>빈 자리를 「이번 주 다른 날」로 채웠다</b> &mdash; 한 주치를 이미 받아 놓고 엿새를
        버리고 있었으니, <b>서버 호출을 늘리지 않고 화면을 채울 수 있는 유일한 재료</b>였다.
        담당자 홈(<code>318d6ca</code>): 오늘이 0건이면 첫 카드가 제목과 「캘린더 &rarr;」만 남아
        화면이 통째로 비었다. 인사말과 「오늘 한 장」을 세우고, 오늘이 비면 이번 주 건수와 가장
        가까운 면접으로 '그럼 다음은 언제'에 답한다. 요청은 안 늘렸다 &mdash; 하루를 묻던 것을
        한 주로 넓힌 것뿐이고 캘린더가 이미 같은 단위로 부른다.
        바로 다음 커밋이 남은 반쪽을 걷었다(<code>16c76cd</code>): 히어로가 「면접이 없는
        날이에요」를 이미 말하는데 <b>그 아래 제목과 링크만 남은 빈 카드가 또 서 있었다.</b>
        같은 말을 두 번 하면서 화면만 비웠다 &mdash; 있을 때만 그린다.
        지원자 홈도 같은 부류로 정리했다(<code>8150e25</code>): 카드 한 장에 요소가 열둘이고
        전부 10~15px 라 <b>눈이 붙을 데가 없었다.</b> 밋밋해 보이던 까닭이 장식이 없어서가 아니라
        <b>위계가 없어서</b>였다 &mdash; 공고명을 15&rarr;19px 로, 네 칸 막대를 점 &middot; 선
        노선도로(지나온 역은 채운 점이라 색 없이도 갈린다), 할 일 셋을 내려앉은 패널로 묶어
        일곱으로 줄였다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">레이아웃은 문법이 아니라 배치 규칙에서 깨졌다 &mdash; 같은 원인으로 세 번
        <span class="tag tag--done">해소 09. 16.</span></p>
      <p class="item__d">
        <code>Container</code> 에 <code>alignment</code> 를 주면 <b>받은 제약의 최대 폭을
        차지한다.</b> 이것 하나로 세 번 깨졌다. 09. 01. 상세의 메일 버튼 넷이 <code>Wrap</code>
        안에서 한 줄에 하나씩 깔렸고(<code>68f5f69</code>), 09. 16. 캘린더 「다음 주 보기」와 홈
        히어로의 「캘린더」가 <b>화면 끝에서 끝까지</b> 갔다 &mdash; 빈 주를 알리는 자리와 다음
        면접을 알리는 자리가 화면에서 제일 센 요소가 됐다. 흰 판은 <b>주 동작</b>에 쓰라는
        규칙이었고 크게 만들라는 말이 아니었다.
        첫 대응(<code>Align</code> 으로 감싸기, <code>f0a38da</code>)은 <b>안 먹었다</b> &mdash;
        <code>Align</code> 이 주는 것도 느슨한 제약이라 최대는 여전히 화면 폭이다. 원인을
        <code>Align</code> 이 아니라 <code>Container</code> 로 다시 짚고
        <code>Center(widthFactor: 1)</code> 로 바꿨다 &mdash; 세로 가운데는 잡으면서 폭은
        글자만큼이다(<code>1052926</code>).
        같은 부류가 08. 28. 에도 있었다: 퍼널 막대가 색은 칠해졌는데 <b>화면에서 사라졌다.</b>
        <code>Row</code> 는 기본 정렬이 center 라 자식에게 느슨한 높이 제약(0~8)을 주고
        <code>ColoredBox</code> 는 자식이 없으면 그중 <b>가장 작은 값 0</b> 을 골라 두께가
        없어진다. <code>analyze</code> 도 테스트도 전부 통과했고 눈으로는 "가늘어서 안 보이는 것"
        과 구별되지 않아, <b>높이 8dp 와 구간 폭 비율을 숫자로 재는 테스트</b>를 넣었다
        (<code>f1f8294</code>). 이 부류에 쓴 시간이 Dart &middot; Flutter 첫 사용에서 실제로
        어려웠던 부분이다 &mdash; 언어 문법이 아니라 제약이 위에서 아래로 전파되는 방식이었다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">없는 숫자를 지어내지 않는다 &mdash; 목데이터가 진짜인 척한 자리 하나가 바꾼 규율
        <span class="tag tag--done">해소 09. 08.</span></p>
      <p class="item__d">
        더보기의 평가 현황 배지가 <b>배정이 0건이든 7건이든 영원히 '2'</b> 였다. 셸이
        <code>const MoreScreen()</code> 으로 만들어 실수가 늘 null 이고 목데이터 폴백으로
        떨어졌다 &mdash; 목 지원자 중 서류 &middot; 면접 단계이면서 평가 기록이 없는 사람이 둘이라
        나온 숫자다. 진짜 수는 대시보드가 이미 받고 있어 셸이 <code>ValueNotifier</code> 로
        흘려 주게 했고(더보기가 또 물으면 앱을 켤 때마다 왕복이 하나 는다),
        <b>못 받았으면 배지를 아예 안 그린다</b> &mdash; 없는 숫자를 지어내느니 비우는 게 낫다.
        해결하면서 <b>남은 문제도 같이 적었다</b>: 그 수는 서버의 배정 건수라 내가 이미 평가한
        건도 센다. 진짜 미착수 수를 세려면 배정마다 상세를 받아야 해서(N+1) 배지 하나에는
        무겁다는 판단까지 커밋에 남겼다(<code>9581fae</code>).
        <b>이 배지는 지금 화면에 없다</b> &mdash; 09. 15. 에 웹과 맞춰 평가 현황 자체를 걷으면서
        더보기의 그 항목과 배지가 같이 나갔고, 대시보드의 「내 리뷰 대기」 카드까지 없어져
        <code>GET /interviewers/{me}/applications</code> 요청 하나가 줄었다(<code>6016c4f</code>).
        <b>남은 것은 규율이다</b> &mdash; 자리는 없어졌지만 "못 받았으면 안 그린다"는 그 뒤 화면에
        그대로 쓰였다.
        이 사고가 이후 판단의 근거가 됐다 &mdash; 데모 모드에 리본과 릴리스 차단을 붙인 이유를
        커밋이 "목데이터가 조용히 진짜인 척한 사고가 이미 있었다"로 적고 있다. 같은 규율이
        서버 계약 공백에도 적용됐다(&sect;4): 평가자 이름 &middot; 변경자 &middot; 메일 발송 여부를
        서버가 주지 않아 <b>id 를 화면에 띄우지 않고 그 자리를 접었다.</b> 「평가자 7번」은 아무
        의미가 없고, 갔는지 모르면서 "갔다"도 "안 갔다"도 쓸 수 없다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">화면 둘이 같은 것을 두고 서로 다른 말을 했다
        <span class="tag tag--done">해소 09. 15. ~ 16.</span></p>
      <p class="item__d">
        폰 실측에서 나왔다. 홈은 「제출했어요」인데 인적성 탭은 「기한이 지났습니다」였다.
        원인이 둘이다. <b>① 상태 이름이 서버와 달랐다</b> &mdash; 서버는 제출하면
        <code>status = "done"</code> 인데 앱은 <code>submitted</code> 를 알고 있었고, 파서가
        <b>모르는 값을 만료로 떨어뜨려</b>(없는 상태를 "지금 하면 된다"로 읽으면 다 풀고 나서
        거절당하니 그 판단 자체는 맞다) 제출한 사람이 만료 화면을 봤다. 홈은 원시 문자열을 직접
        비교해 맞게 나왔고 탭만 enum 을 거쳐 틀렸다 &mdash; 그래서 두 화면이 갈렸다.
        <b>② 홈과 셸이 서로 다른 세션을 골랐다</b> &mdash; 홈은 가장 오래된 것, 셸은 가장 새 것을
        집었다. 재발송으로 세션이 둘이 되면 홈이 A 의 마감을 읽고 탭은 B 를 열었다. 규칙을
        <code>pickLink</code>(<code>mobile/lib/models/applicant_me.dart:44</code>) <b>한 곳으로
        모으고</b> 홈 &middot; 셸이 같이 쓰게 했다. 인적성뿐 아니라 일정 &middot; 면접도 같은
        구조라 함께 고쳤다(<code>4d7a107</code>).
        <b>같은 규칙을 웹에도 옮겼다</b>(<code>9c6666a</code>) &mdash; 웹도 인적성은 첫 번째,
        면접은 "끝나지 않은 첫 번째" 를 집고 있어 <b>같은 사고가 기다리고 있었다.</b> 글자 하나까지
        맞췄다. 두 클라이언트를 한 사람이 들고 있어 한쪽에서 겪은 것이 다른 쪽으로 옮겨 간 자리다.
        남은 하나는 앱에서 못 고치는 것이라 백엔드에 넘겼고 <code>e281b15</code> 로 닫혔다
        (&sect;4 참조).
      </p>
    </div>

    <div class="item">
      <p class="item__t">위젯 테스트 15개가 빨간 채로 지나갔다 &mdash; 회귀 그물이 CI 밖에 있었다
        <span class="tag tag--done">해소 09. 15. ~ 17.</span></p>
      <p class="item__d">
        09. 15. 에 지원자 화면 넷(홈 &middot; 인적성 &middot; 일정 &middot; 내 정보)을 재설계하면서
        <code>applicant_shell_test.dart</code> 를 안 맞췄다. 못 본 이유가 코드가 아니었다 &mdash;
        <b>CI 에 flutter 가 없었다.</b> 워크플로가 백엔드와 프론트만 돌려 <b>PR 은 초록으로 떴고
        앱 회귀 그물은 죽어 있었다.</b>
        빨간 구간은 같은 날 안이다 &mdash; 재설계 커밋이 09. 15. 10:47, 고친 커밋이 16:15 이라
        <b>다섯 시간 반</b>이고, 그 사이 손으로 <code>flutter test</code> 를 돌리지 않으면 아무
        신호가 없었다. 이틀 뒤 CI 에 앱 잡을 붙인 팀장이 워크플로 주석에 이 일을
        「며칠 지나갔다 &mdash; 아무도 몰랐다」로 적었는데, <b>날수가 아니라 「아무도 몰랐다」가
        요점</b>이다. 그물이 없으면 빨간 시간의 길이를 재는 방법 자체가 없다.
        고칠 때 <b>통과시키려고 맞추지 않았다.</b> 재설계된 화면이 실제로 무엇을 그리는지 먼저
        뽑아 대조했고, <b>화면 버그는 하나도 없었다</b> &mdash; 전부 글자 &middot; 구조가 바뀐 대로
        단언이 낡은 것이었다. 한 번은 진짜 회귀처럼 보였다(지원이 2건인데 홈에 둘째 공고가 안
        잡혔다). <b>화면 밖이었다</b> &mdash; 지원마다 여정 카드가 한 장이라 한 화면에 안 들어간다.
        스크롤해서 보이는 것까지 확인하고 테스트에 그렇게 적었다.
        덤으로 세 군데가 튼튼해졌다: <code>FilledButton</code> 을 찾던 자리를 실제 구현
        (Material + InkWell)에 맞췄고(옛 구현에 기대 있어 언젠가 또 깨질 자리였다), 제네릭이라
        <code>byType</code> 이 못 잡던 <code>AppBottomNav&lt;T&gt;</code> 를
        <code>byWidgetPredicate</code> 로 바꿨고, <b>「안 고른 문항은 건너뛸 수 없다」를 새로 못
        박았다</b> &mdash; 「다음」이 죽어 있는 것이 흐름의 핵심인데 아무도 안 보고 있었다.
        결과 397개 전부 통과(고치기 전 15개 실패, <code>212921b</code>).
        지금 수(373)가 그때보다 적은 것은 테스트를 지운 것이 아니라 <b>화면을 지웠기</b>
        때문이다 &mdash; 같은 날 웹에 맞춰 평가 현황을 걷으면서
        <code>evaluation_queue_screen_test.dart</code> 가 화면과 함께 나갔다(<code>6016c4f</code>).
        <b>근본 원인은 도메인 밖이라 이슈로 넘겼다.</b> 팀장이 09. 17. 에 CI 에 앱 잡을 붙였고
        (Flutter 3.44.8 &middot; <code>analyze</code> + <code>test</code>,
        <code>717623d</code>), 워크플로 주석이 그 사정과 출처(Issue #254 &middot; 앱 오너 원안)를
        그대로 적고 있다. 그 전까지 앱의 유일한 그물은 로컬 <code>flutter test</code> 였다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">되돌릴 수 없는 동작에만 확인 시트를 세웠다 &mdash; 자리 셋
        <span class="tag tag--done">해소 09. 03.</span></p>
      <p class="item__d">
        웹은 버튼을 누르면 바로 실행되지만 폰은 스크롤하다 손가락이 스친다. 그렇다고 전부 시트를
        세우면 <b>경고를 안 읽게 된다</b> &mdash; 그래서 자리를 셋으로 한정했다.
        <b>단계 변경</b>(<code>cc3e041</code> &middot; <code>274a271</code>): 갈 수 있는 단계만
        띄운다 &mdash; <code>backend/app/stages.py</code> 전이 규칙의 <b>사본</b>이라 서버에서
        409 를 받을 일이 없고, 어긋나면 서버가 기준이라고 주석에 적었다. 메일 경고는 실제로 메일이
        나가는 단계에만 붙고, 불합격 사유가 비면 확정이 잠긴다. 버튼 라벨이 「확인」이 아니라
        「서류 검토으로 변경」인 것도 같은 규율이다 &mdash; 무엇이 일어나는지 버튼이 말한다.
        다이얼로그가 아니라 바텀시트인 이유는 <b>아래로 밀어 닫는 동작이 곧 취소</b>가 되기
        때문이다.
        <b>메일 발송</b>(<code>0c18136</code>): 이 앱에서 유일하게 되돌릴 수 없는 동작이다
        &mdash; 큐에 쌓이는 것이 아니라 실제로 발송된다. 시트에 <b>받는 사람 이름</b>을 적는 것이
        웹과 다른 점이고(폰은 목록에서 잘못 눌러 들어오기 쉽다), <b>주소는 안 적는다</b> &mdash;
        서버가 수신자를 고정하므로 앱이 틀릴 수가 없어 띄워도 막을 실수가 없다.
        <b>공고 삭제</b>(<code>c906dcf</code>): 저장 바 <b>바깥</b> 맨 아래다 &mdash; 같은 줄에
        두면 손가락이 스치고, 스크롤 끝이라는 위치가 "여기서 끝"이라는 뜻도 된다. 지원자 수는
        앱이 세지 않는다: 서버가 지원서 딸린 공고를 409 로 막고 그 문구에 걸린 건수와 다음에 할
        일이 다 들어 있다. 화면이 든 인원은 받아 온 시점의 값이라 <b>세는 쪽을 서버 하나로</b> 뒀다.
        검증도 같은 원칙으로 했다 &mdash; 메일 [발송]과 비밀번호 입력은 <b>기기 소유자가 직접
        눌렀고</b>, 값을 바꾸는 공고 저장은 팀 공용 데이터라 실기기에서 하지 않았다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">평가 중복을 앱이 막았다 &mdash; 웹과 달라지지만 데이터는 웹이 원하는 모양이 된다
        <span class="tag tag--done">해소 09. 03.</span></p>
      <p class="item__d">
        DB 에 (지원, 평가자) 유니크 제약이 없고 서버도 확인하지 않는다. 웹은 그냥 POST 해서
        저장할 때마다 평가가 한 줄씩 쌓이고 <b>평균과 「n명이 평가함」이 둘 다 틀어진다.</b>
        점수를 매기는 화면에서 숫자가 틀리는 것은 그냥 버그다.
        그래서 내가 쓴 것이 있으면 새로 만들지 않고 <code>PATCH /evaluations/{id}</code> 로
        고친다. 서버에 「내 것만 고칠 수 있다」는 검사가 <b>이미 있는데 웹이 안 쓰고
        있었다</b> &mdash; 앱이 먼저 썼다. 내 것 찾기는 로그인한 사람의 id 와 평가자 id 비교라
        <b>추가 요청이 없다</b>. 로그인 정보가 없으면 늘 새로 쓰기다 &mdash; 남의 평가를 내 것으로
        열면 안 된다.
        실기기에서 4점 저장 &rarr; 2점 수정 뒤 <b>「1명이 평가했습니다」가 유지되는 것</b>을 눈으로
        확인했다 &mdash; 웹 방식이었으면 2명 / 평균 3.0 이 됐을 자리다.
        근거: <code>355175f</code>
      </p>
    </div>

    <div class="item">
      <p class="item__t">실기기가 아니면 안 나오는 것 세 부류
        <span class="tag tag--done">해소 09. 02. ~ 03.</span></p>
      <p class="item__d">
        <b>① 릴리스에서만 없는 것.</b> <code>AndroidManifest</code> 에 INTERNET 권한이 없었다
        &mdash; debug &middot; profile 은 Flutter 가 자동으로 넣지만 릴리스는 아니라, <b>팀에
        배포한 APK 에서만 모든 요청이 조용히 실패했을 자리</b>다. Android 11+ 는
        <code>&lt;queries&gt;</code> 선언이 없으면 다른 앱을 아예 못 봐서 이력서가 "열 앱이 없다"로
        끝난다.
        <b>② 문서에 없던 것.</b> API 경로에 <code>/api/v1</code> 접두어가 필요했다. 02-api.md 표가
        접두어를 생략하고 있어 <code>/auth/login</code> 으로 불렀다가 404 를 맞았다. 실서버
        <code>openapi.json</code> 으로 확인하고 접두어를 <code>ApiConfig</code> 한 곳에만 뒀다
        &mdash; 이후 경로가 36개까지 붙었다. 저장소가 만든 클라이언트에 토큰이 안 붙어 로그인
        직후에도 401 이 나던 것도 같은 부류라, 조립을 <code>authedClient()</code> 한 곳에 모았다.
        <b>③ 첫 실행에서만 걸리는 것.</b> 지원자 로그인을 누르면 스피너가 영영 돌았다. 저장된
        것이 없으면 읽기가 <b>수정 불가 목록</b>을 주는데 거기에 <code>removeWhere</code> 를 불러
        <code>UnsupportedError</code> 가 났고, <code>Error</code> 라서 <code>on ApiError</code> 에도
        안 걸려 아무도 안 받은 채 future 가 죽었다 &mdash; <b>첫 실행에서는 반드시 걸리는
        길</b>이었다. 테스트가 못 잡은 이유는 가짜 저장소가 늘 growable 목록을 써 <b>진짜와
        갈렸기</b> 때문이다. 플랫폼 채널이 없는 테스트 환경이 같은 경로를 만든다는 것을 이용해
        회귀 테스트를 넣었고, 지원자 로그인에 catch-all 을 붙였다 &mdash; 예상 못 한 실패에도
        버튼이 풀려야 사용자가 할 수 있는 일이 남는다.
        근거: <code>6b8aa33</code> &middot; <code>1624352</code> &middot; <code>2e100be</code>
        &middot; <code>631fd9b</code>
      </p>
    </div>

  </div>

  <p class="role__note" style="margin-top:1.4rem;">
    아래 셋은 08월 말 일이고, 그때는 공용 파일 수정과 판단 변경에 사전 확인이 필요했다 &mdash;
    <b>2026. 08. 28.에 리뷰 &middot; 사전 확인 게이트가 폐지되면서</b> 지금은 같은 일을 오너가
    직접 고치고 사후에 한 줄 공지한다. 위 열두 항목에 확인을 기다린 자리가 하나도 없는 것이
    그 차이다.
  </p>

  <div class="items">

    <div class="item">
      <p class="item__t">수정 금지 파일에 필요한 관계 정의가 없었다 <span class="tag tag--done">해소 08. 25.</span></p>
      <p class="item__d">
        지원자 상세 API 작업에 모델 간 관계 정의가 필요했는데 공용 모델 파일에 하나도 없었다.
        해당 파일은 당시 <b>공용 파일이라 임의 수정이 금지</b>돼 있어, 직접 고치지 않고 팀 채널에
        확인을 요청했다. 팀장이 자식 관계 4종을 추가해 해결한 뒤 원래 지시대로 진행했다.
        <b>지금이라면 직접 고친다</b> &mdash; 공용 파일도 오너가 손대고, 코드와 같은 커밋에서
        문서를 갱신한 뒤 팀 채널에 사후 한 줄을 남기는 것이 현재 규칙이다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">지시 내용과 API 문서가 어긋났다 <span class="tag tag--done">해소 08. 25.</span></p>
      <p class="item__d">
        지시서에는 "인증 &middot; 권한 코드를 넣지 않는다(아직 없으므로)"고 돼 있었으나, 그 사이
        인증이 들어오면서 전제가 사라진 상태였다. API 문서가 이 엔드포인트를 담당자 이상 권한으로
        규정하고 있어 <b>API 문서를 기준으로 삼기로</b> 확인받고 권한 검사를 적용했다.
        기록용 필드도 <code>TODO</code>로 남기지 않고 실제 담당자로 채웠다.
        이후 <b>ADR-0017(08. 31.)로 그 권한 등급 자체가 없어져</b> 지금은 로그인한 사람이면
        누구나 호출한다 &mdash; 기록용 필드를 실제 담당자로 채운 것만 그대로 남았다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">스택 결정의 전제가 바뀌었다 <span class="tag tag--done">해소 08. 26.</span></p>
      <p class="item__d">
        08. 25.에는 같은 판단 기준(학습 비용이 아니라 <b>데모 배포 경로</b>)이 다른 후보를 가리켰다.
        08. 26. 팀이 데모 범위에서 iOS 기기를 제외하기로 하면서 전제가 바뀌었고, 그에 따라
        Flutter로 확정했다. <b>기술 비교가 아니라 범위가 바뀐 결정</b>이라는 점을 기록에 남겼다.
      </p>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">8.</span> 리스크 및 대응</h2>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr>
        <th>리스크</th>
        <th>대응</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><b>iOS 빌드 검증 불가</b><br><span class="stat__k">Mac 없음</span></td>
        <td>호환을 코드 규율로만 관리한다 &mdash; iOS 지원 플러그인만 사용, 플랫폼 분기 금지,
            정적 분석 무경고 유지. <b>"iOS도 된다"고 말하지 않는다.</b></td>
      </tr>
      <tr>
        <td><b>Dart &middot; Flutter 첫 사용</b><br><span class="stat__k">팀 내 경험자 0명</span></td>
        <td>막히면 전부 혼자 풀어야 한다. SDK &middot; 실기기 구동은 08. 26.에 통과했으므로 남은
            위험은 언어 &middot; 프레임워크 자체다. <b>하루 안에 안 풀리면 팀 채널에 올린다.</b>
            <b>실제로 시간을 먹은 것은 문법이 아니라 제약 전파였다</b> &mdash; <code>Row</code> 가
            자식에게 느슨한 높이를 줘 막대 두께가 0 이 된 것, <code>Container.alignment</code> 가
            최대 폭을 차지해 버튼이 화면을 가로지른 것(세 번), <code>IndexedStack</code> 이 탭을
            살려 둬 <code>dispose()</code> 가 영영 안 돈 것(두 번). 셋 다 <b>정적 분석과 테스트가
            통과한 채로 틀렸고 실기기에서만 보였다</b>. 팀 채널에 올린 건은 없다</td>
      </tr>
      <tr>
        <td><b>앱 회귀 그물이 CI 밖이었다</b><br><span class="stat__k">09. 15. 실제로 터졌다</span></td>
        <td>워크플로가 백엔드와 프론트만 돌려, 재설계에 안 맞춘 <b>위젯 테스트 15건이 반나절
            빨간 채로 지나갔다</b>(10:47 &rarr; 16:15) &mdash; PR 은 초록이었다.
            로컬 <code>flutter test</code> 가
            유일한 그물이었다. 도메인 밖이라 <b>고치지 않고 이슈로 올렸고</b>(Issue #254),
            09. 17. 에 CI 에 앱 잡이 붙었다(<code>717623d</code> &mdash; Flutter 3.44.8 &middot;
            <code>analyze</code> + <code>test</code>). 지금은 앱도 초록이어야 머지된다</td>
      </tr>
      <tr>
        <td><b>개인 기기 &middot; 개발 환경 편차</b></td>
        <td>데모에 쓸 Android 기기에 APK 설치를 먼저 확인하고, 안 되는 기기는 데모 대상에서 뺀다.
            <b>기기 전원 설치 확인을 마일스톤으로 두는 것은 09. 02.에 뺐다</b> &mdash; APK는
            필요할 때 뽑아 전달하면 되고, 기기마다 설치를 확인하는 것 자체가 목표일 이유가 없었다.</td>
      </tr>
      <tr>
        <td><b>웹과 룩이 어긋남</b></td>
        <td>토큰을 코드로 이식하고 임의 색 사용을 금지한다. 완료 기준에 목업 대조를 포함한다.</td>
      </tr>
      <tr>
        <td><b>백엔드 지연</b></td>
        <td>M1 전체가 API와 무관하도록 설계했다. 전환기 큐로 본인이 선행 조건을 직접 만들었다.</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">9.</span> 발표 포인트</h2>

  <ul class="talk">
    <li>
      <b>같은 API로 웹 &middot; 앱 두 클라이언트 &mdash; 수치로 답한다.</b> 앱이 부르는 서버 경로
      36개 중 <b>33개는 앱이 오기 전에 이미 열려 있던 것</b>이고, 당시 화면 17개를 전부 서버에 붙인
      이틀(09. 02. ~ 03.)에 앱 때문에 생긴 백엔드 커밋은 <b>0건</b>이다. 서버가 늘어난 것은 지원자
      갈래를 낼 때 둘(<code>/public/applicant/login</code> &middot; <code>/applicant/me</code>,
      ADR-0033)뿐이고, 그것도 앱이 우회하지 않고 백엔드 오너와 합의해서 생겼다. 남은 하나는
      비밀번호 로그인 개정으로 생긴 경로인데 웹과 앱이 같은 날 나란히 붙었다. 그리고
      <b>흐름이 한 번 거꾸로 갔다</b> &mdash; 지원자 셸 구조를 앱이 먼저 만들고 웹이 09. 15. 에
      그대로 가져갔는데(<code>9c6666a</code>) 그때도 서버는 바뀌지 않았다.
    </li>
    <li>
      <b>탭을 살려 두는 셸에서는 <code>dispose()</code> 가 안 돈다.</b> 면접이 끝나도 카메라가
      안 꺼지던 것을 <b>끝나는 길 셋</b>(종료 버튼 / 서버의 완료 통보 / 조회가 만료를 받음)에서
      다 놓게 고쳤다. 눈에 보이는 증상보다 나쁜 쪽은 판정 소켓이었다 &mdash; <b>서버가 끝난
      세션을 계속 판정했고</b> 그것을 <code>/ai/health</code> 카운터가 10초에 하나씩 오르는 것으로
      확인했다. 종료 버튼은 서버가 끝을 확인한 뒤에 놓는다 &mdash; 먼저 놓으면 카메라만 꺼지고
      면접은 살아 있는 자리가 된다(<code>36bb7c5</code>).
    </li>
    <li>
      <b>빈 상태를 예외로 두고 만든 화면은 정작 흔한 경우에 무너진다.</b> 캘린더가 실기기에서
      화면의 60%가 빈 공간이었다 &mdash; 면접 없는 날이 예외가 아니라 기본인데 "있다"를 기본으로
      그렸기 때문이다. <b>한 주치를 이미 받아 놓고 엿새를 버리고 있던 것</b>을 「이번 주 다른 날」
      로 채웠다 &mdash; 서버 호출을 늘리지 않고 화면을 채울 수 있는 유일한 재료였다
      (<code>4c6dc5e</code> &middot; <code>318d6ca</code> &middot; <code>16c76cd</code>).
    </li>
    <li>
      <b>없는 숫자를 지어내지 않는다.</b> 더보기 배지가 배정 건수와 무관하게 영원히 '2' 였던 것
      (목데이터 폴백)을 서버 값으로 바꾸면서, <b>못 받았으면 아예 안 그리는 쪽</b>으로 갔다. 같은
      규율을 서버 계약 공백에도 적용했다 &mdash; 평가자 이름 &middot; 변경자 &middot; 메일 발송
      여부를 서버가 주지 않아 <b>id 를 띄우지 않고 그 자리를 접었다.</b> 「평가자 7번」은 아무
      의미가 없고, 갔는지 모르면서 "갔다"도 "안 갔다"도 쓸 수 없다
      (<code>9581fae</code> &middot; <code>0448264</code>).
    </li>
    <li>
      <b>평가 중복을 앱이 막아 웹보다 데이터가 정확해진 자리.</b> DB 에 유니크 제약이 없고 서버도
      웹도 막지 않아 저장할 때마다 평가가 한 줄씩 쌓이면 평균과 「n명이 평가함」이 둘 다 틀어진다.
      앱은 내 것이 있으면 <code>PATCH</code> 로 고친다 &mdash; 서버에 이미 있던 「내 것만 고칠 수
      있다」 검사를 <b>앱이 먼저 썼다.</b> 4점 저장 &rarr; 2점 수정 뒤에도 「1명이 평가했습니다」가
      유지되는 것을 실기기에서 확인했다(<code>355175f</code>).
    </li>
    <li>
      <b>모바일에서 칸반을 버리고 리스트 + 단계 변경 버튼으로 갔다</b> &mdash; 화면 크기가 아니라
      오조작 비용을 근거로 한 재설계다. 대신 <b>되돌릴 수 없는 동작 셋</b>(단계 변경 &middot; 메일
      발송 &middot; 공고 삭제)에만 확인 시트를 세웠다. 전부에 세우면 경고를 안 읽게 된다.
      전이 규칙은 서버 파일의 사본이고 어긋나면 서버가 기준이라고 주석에 적어 뒀다.
    </li>
    <li>
      <b>테스트 15개가 깨져 있었는데 PR 은 초록이었다.</b> CI 에 flutter 가 없어 앱 회귀
      그물이 죽어 있었다. 고칠 때 통과시키려 맞추지 않고 <b>재설계된 화면이 실제로 무엇을 그리는지
      먼저 뽑아 대조했고</b>, 화면 버그는 하나도 없었다는 사실까지 적었다. 근본 원인은 도메인 밖이라
      이슈로 올렸고 09. 17. 에 CI 에 앱 잡이 붙었다(<code>212921b</code> &rarr;
      <code>717623d</code>).
    </li>
    <li>
      <b>스택을 Flutter로 확정한 근거</b> &mdash; 데모 범위를 Android로 좁히면서 무엇을 얻고
      무엇을 포기했는지(iOS 실기기 &middot; 웹 코드 재사용 &middot; 즉시 배포)까지 말할 수 있어야 한다.
      <b>기술 비교가 아니라 범위가 바뀐 결정</b>이라는 점이 핵심이고, 그래서 검증하지 못한 iOS 를
      "지원한다"고 말하지 않는다.
    </li>
  </ul>

</div>

<a class="role__back" href="{{ '/team/' | relative_url }}">&larr; 팀 구성 및 역할</a>

</div>
