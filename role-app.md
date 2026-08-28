---
layout: default
title: 앱 (모바일)
permalink: /role-app/
---

{% include role-style.html %}

<div class="role">

<div class="role__head">
  <p class="role__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo;
     팀 구성 및 역할 &rsaquo; 앱 (모바일)</p>
  <h1>앱 (모바일) &middot; 담당 김민아</h1>
  <p>담당자 &middot; 면접관용 모바일 네이티브 앱 &mdash; 웹과 같은 API를 쓰는 두 번째 클라이언트
     &middot; 최종 갱신 2026. 08. 28.</p>
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

  <div class="scope">

    <div class="scope__box scope__box--in">
      <h3>포함</h3>
      <ul>
        <li>로그인 (JWT)</li>
        <li>공고 리스트</li>
        <li>지원자 리스트 &mdash; 단계 탭 필터 + 압축 퍼널 바</li>
        <li>지원자 상세 &mdash; 지원 정보 &middot; 단계 이력 타임라인 &middot; 평가 목록</li>
        <li><b>단계 변경 버튼</b> (드래그 대신)</li>
        <li>평가 작성</li>
        <li>이력서 열람 (presigned URL)</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>제외</h3>
      <ul>
        <li>지원 폼 &mdash; 지원자용 외부 링크는 웹 전용</li>
        <li>칸반 &mdash; 모바일 금지 원칙</li>
        <li>앱 내 푸시 알림 &mdash; 여유 시 별도 합의</li>
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
      <tr class="is-now">
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
            남은 것은 팀 Android 기기 전원 APK 설치 확인과 목데이터 화면 착수</td>
        <td>Android 실기기 구동 확인 &mdash; 정적 분석 무경고, 테스트 통과.
            <span class="tag tag--miss">기기 전원 설치 확인 미완</span></td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W3</b><span>09. 07. ~ 11.</span></td>
        <td>M1 정적 화면</td>
        <td>목데이터로 지원자 리스트 &middot; 상세 &middot; 로그인 화면</td>
        <td>모바일 목업과 나란히 놓고 같은 제품으로 보인다. 목데이터 필드명이 ERD와 일치한다.</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W4</b><span>09. 14. ~ 18.</span></td>
        <td>M2 API 연동</td>
        <td>JWT 로그인 &middot; 공고 &middot; 지원자 실데이터 &middot; <b>단계 변경</b> &middot;
            평가 작성 &middot; 로딩 &middot; 빈 상태 &middot; 오류 3종</td>
        <td>앱에서 단계를 바꾸면 <b>웹 칸반에 반영된다</b>(같은 API 증명).
            면접관 계정은 배정된 지원자만 보인다.</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W5</b><span>09. 21. ~ 25.</span></td>
        <td>M3 마감 &middot; 데모</td>
        <td>이력서 열람 &middot; 극단값 점검(긴 이름 &middot; 태그 다수 &middot; 자소서 5천 자)
            &middot; 오프라인 안내 &middot; 데모 시나리오</td>
        <td>팀 Android 기기 전원에서 APK로 구동. 데모 시나리오(출근길 서류 검토 &rarr; 단계 변경
            &rarr; 메일 자동 발송 수신)가 끊김 없이 돈다.</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>버퍼</b><span>09. 28. ~ 30.</span></td>
        <td>동결</td>
        <td>데모 동결 &middot; (여유 시) 내부 테스트 트랙 배포</td>
        <td><b>09. 30. 1차 완성</b></td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">6.</span> 작업 큐</h2>
  <p class="role__note">
    위에서부터 순서대로 소화한다. 선행이 풀리지 않았으면 건너뛰고 다음 것을 잡는다.
    전환기 1&ndash;3번은 <b>앱 자신의 선행 조건(지원자 API)을 본인 손으로 푸는 구조</b>였다 &mdash;
    순서를 지킨 덕분에 대기 시간이 없었다.
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
      <tr>
        <td>6</td><td>지원자 리스트 &middot; 상세 &middot; 로그인 (목데이터)</td><td>5번</td>
        <td><span class="tag tag--now">다음 작업</span></td>
      </tr>
      <tr>
        <td>7</td><td>JWT 로그인 연동</td><td>백엔드 인증</td>
        <td><span class="tag tag--wait">대기</span></td>
      </tr>
      <tr>
        <td>8</td><td>리스트 &middot; 상세 &middot; 단계 변경 &middot; 평가 연동</td>
        <td>백엔드 M1 &middot; M2</td>
        <td><span class="tag tag--wait">대기</span></td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">7.</span> 진행 중 해소한 쟁점</h2>
  <p class="role__note">
    막힌 지점을 혼자 우회하지 않고 팀 규칙에 따라 확인받아 처리한 항목이다.
  </p>

  <div class="items">

    <div class="item">
      <p class="item__t">수정 금지 파일에 필요한 관계 정의가 없었다 <span class="tag tag--done">해소 08. 25.</span></p>
      <p class="item__d">
        지원자 상세 API 작업에 모델 간 관계 정의가 필요했는데 공용 모델 파일에 하나도 없었다.
        해당 파일은 <b>공용 파일이라 임의 수정이 금지</b>돼 있어, 직접 고치지 않고 팀 채널에
        확인을 요청했다. 팀장이 자식 관계 4종을 추가해 해결한 뒤 원래 지시대로 진행했다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">지시 내용과 API 문서가 어긋났다 <span class="tag tag--done">해소 08. 25.</span></p>
      <p class="item__d">
        지시서에는 "인증 &middot; 권한 코드를 넣지 않는다(아직 없으므로)"고 돼 있었으나, 그 사이
        인증이 들어오면서 전제가 사라진 상태였다. API 문서가 이 엔드포인트를 담당자 이상 권한으로
        규정하고 있어 <b>API 문서를 기준으로 삼기로</b> 확인받고 권한 검사를 적용했다.
        기록용 필드도 <code>TODO</code>로 남기지 않고 실제 담당자로 채웠다.
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
            위험은 언어 &middot; 프레임워크 자체다. <b>하루 안에 안 풀리면 팀 채널에 올린다.</b></td>
      </tr>
      <tr>
        <td><b>개인 기기 &middot; 개발 환경 편차</b></td>
        <td>팀 Android 기기 전원에 APK 설치를 먼저 확인하고, 안 되는 기기는 데모 대상에서 뺀다.
            즉시 반영 수단이 없으므로 <b>배포 확인을 주 1회로 정기화</b>한다.</td>
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
      <b>같은 API로 웹 &middot; 앱 두 클라이언트를 붙였다</b> &mdash; 클라이언트 추가가 서버 변경
      없이 끝났는가, 아니면 무엇이 부족해 무엇을 바꿨는가. 인터페이스 설계의 품질을 수치로 말할 수
      있는 지점이다.
    </li>
    <li>
      <b>모바일에서 칸반을 버리고 리스트 + 단계 변경 버튼으로 갔다</b> &mdash; 화면 크기가 아니라
      오조작 비용을 근거로 한 UX 재설계다.
    </li>
    <li>
      <b>스택을 Flutter로 확정한 근거</b> &mdash; 데모 범위를 Android로 좁히면서 무엇을 얻고
      무엇을 포기했는지(iOS 실기기 &middot; 웹 코드 재사용 &middot; 즉시 배포)까지 말할 수 있어야 한다.
    </li>
  </ul>

</div>

<a class="role__back" href="{{ '/toc/' | relative_url }}">&larr; 목차</a>

</div>
