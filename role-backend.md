---
layout: default
title: 백엔드
permalink: /role-backend/
---

{% include role-style.html %}

<div class="role">

<div class="role__head">
  <p class="role__crumb"><a href="{{ '/team/' | relative_url }}">팀 구성 및 역할</a> &rsaquo;
     백엔드</p>
  <h1>백엔드 &middot; 담당 이우정</h1>
  <p>화면 &middot; 앱 &middot; 에이전트가 딛고 서는 모든 API와 데이터
     &middot; 최종 갱신 2026. 08. 28.</p>
</div>

<div class="role__stat">
  <div class="stat"><span class="stat__k">담당</span>
    <span class="stat__v">이우정 <span class="who who-b">우정 B</span></span></div>
  <div class="stat"><span class="stat__k">소유 폴더</span>
    <span class="stat__v"><code>backend/</code><small>agent 제외</small></span></div>
  <div class="stat"><span class="stat__k">스택</span>
    <span class="stat__v">FastAPI<small>PostgreSQL</small></span></div>
  <div class="stat"><span class="stat__k">소비자</span>
    <span class="stat__v">3종<small>웹 &middot; 앱 &middot; 에이전트</small></span></div>
  <div class="stat"><span class="stat__k">작업 큐</span>
    <span class="stat__v">22<small>건</small></span></div>
</div>

<div class="role__sec">

  <h2><span class="role__num">1.</span> 미션</h2>

  <p class="role__p">
    화면 &middot; 앱 &middot; 에이전트가 딛고 서는 <b>모든 API와 데이터</b>를 만든다. 클라이언트 3종이
    같은 FastAPI 서버 하나를 바라보는 구조이므로, <b>이 도메인이 늦으면 나머지 전부가 목데이터에
    갇힌다.</b>
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">2.</span> 범위</h2>

  <div class="scope">

    <div class="scope__box scope__box--in">
      <h3>포함</h3>
      <ul>
        <li>인증 &middot; 권한 &mdash; JWT, 역할 3종, 면접관 배정 조회 제한</li>
        <li>도메인 API &mdash; 공고 &middot; 지원서 &middot; 지원자 관리(단계 전환 포함) &middot;
            평가 &middot; 메모</li>
        <li>검색 &middot; 필터 &middot; 정렬 &middot; 페이지네이션 + 인덱스 튜닝</li>
        <li>파일(S3 presigned) &middot; 메일(SES + SQS 워커) &mdash; <b>코드만</b></li>
        <li>더미 데이터 10만 건 &middot; 구조화 로깅 &middot; 에러 코드 표준 &middot; API 테스트</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>제외</h3>
      <ul>
        <li>스키마 변경 &mdash; ERD 확정 후 전원 합의로만. <b>인덱스 추가도 스키마 변경이다</b> &mdash;
            측정과 제안까지가 이 도메인, 반영은 총괄</li>
        <li>버킷 &middot; 큐 &middot; SES 도메인 등 AWS 리소스 준비 &mdash; 인프라 소관</li>
        <li><code>backend/app/agent/</code> &mdash; 에이전트 도메인</li>
        <li>Docker Compose &middot; CI/CD &mdash; 인프라 도메인</li>
      </ul>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">3.</span> 인터페이스 계약</h2>

  <p class="role__p">
    <b>제공</b> &mdash; API 문서에 정의된 REST 전부. 상세는 Swagger가 진실이다.
    <b>엔드포인트를 추가하거나 바꾸면 API 문서 갱신을 같은 PR에 포함하고, 그 PR은 총괄 승인을
    받는다.</b> 소비자는 프론트엔드 &middot; 앱 &middot; 에이전트 3종이다.
  </p>
  <p class="role__p">
    <b>의존</b> &mdash; 인프라(접속 문자열 &middot; AWS 자격 &middot; S3 버킷 &middot; SQS 큐 &middot;
    SES 발신 도메인), 스키마 확정, 그리고 에이전트가 제공하는 요약 생성 함수. 지원서 접수 흐름이
    그 함수를 호출하므로 <b>시그니처는 두 오너 간 인터페이스 PR로 합의</b>한다.
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
        <td>선행 해소</td>
        <td>앱 뼈대 &middot; ERD 확정 &middot; 인증 &middot; 공고 &middot; 지원서 제출 &middot;
            지원자 목록 &middot; 상세 &middot; 평가 &middot; 검색</td>
        <td><span class="tag tag--done">달성</span> <b>W2 예정이던 코어 API 물량을 W1 안에 소화했다.</b></td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W2</b><span>08. 31. ~ 09. 04.</span></td>
        <td>M1 코어 API <span class="tag tag--gate">초기 버전</span></td>
        <td>인증 &middot; 공고 &middot; 지원서 제출 &middot; 지원자 목록 &middot; 상세 &middot;
            평가 &middot; 검색</td>
        <td>배포 URL의 Swagger에서 전부 호출 가능.
            <b>수직 슬라이스</b> &mdash; 공개 지원 폼 제출 &rarr; DB 저장 &rarr; 조회까지 관통</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W3</b><span>09. 07. ~ 11.</span></td>
        <td>M2 전환 &middot; 파일 &middot; 메일</td>
        <td>단계 전환과 이력 &middot; 담당자 직접 등록 &middot; 메모 &middot; presigned 업로드 &middot;
            다운로드 &middot; 파일 검증 &middot; 메일 큐 &middot; 접수 확인 메일</td>
        <td>단계 변경 &rarr; 이력 기록 + 메일 실수신. 실패 재시도 로그. 업로드 &rarr; 다운로드 왕복</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W4</b><span>09. 14. ~ 18.</span></td>
        <td>M3 성능</td>
        <td>더미 10만 건 &middot; 정렬 &middot; 커서 페이지네이션 &middot; 인덱스 튜닝(전후 측정)
            &middot; 마감일 &middot; 공개 링크 &middot; 불합격 사유 &middot; 일괄 변경 &middot; 로깅</td>
        <td>성능 문서에 주요 쿼리 4종의 <b>전후 수치</b>가 남는다</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W5</b><span>09. 21. ~ 25.</span></td>
        <td>M4 품질 &middot; 통합</td>
        <td>API 테스트 &middot; 통합 버그픽스 &middot; 에이전트 도구용 엔드포인트 보강</td>
        <td>테스트가 30초 내 전부 통과하고 CI에서 돈다. QA 시나리오 백엔드 항목 전부 통과</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>버퍼</b><span>09. 28. ~ 30.</span></td>
        <td>동결</td>
        <td>코드 프리즈 &middot; 잔여 버그</td>
        <td><b>09. 30. 1차 완성</b></td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">5.</span> 진행 현황</h2>
  <p class="role__note">
    2026. 08. 26. 기준. 작업 큐 22건 중 <b>20건 완료</b>, 1건 승인 대기.
    M1 코어 &middot; M2 메일 &middot; M3 성능 &middot; 마감일까지 일정을 크게 앞질렀다.
    남은 API 테스트 1건은 전환기 분담으로 에이전트 담당자 몫이다.
  </p>

  <div class="items">

    <div class="item">
      <p class="item__t">검색 총계 병목 &mdash; 111 ms &rarr; 7.8 ms</p>
      <p class="item__d">
        성능 문서가 "인덱스로는 못 푼다"고 측정만 남겨둔 전체 건수 집계 병목을 옵션으로 분리해
        처리했다. 10만 건에서 이름 검색이 <b>111 ms에서 7.8 ms</b>로 줄었다. 기본값을 켜둔 채로
        분리해 기존 호출은 그대로 동작한다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">풀리지 않는 병목 둘은 측정만 남겼다</p>
      <p class="item__d">
        ① 매칭이 적은 검색어는 "50개 채우면 중단"이 안 통해 끝까지 훑는다(102 ms).
        ② 점수 정렬은 정렬 키가 집계값이라 10만 그룹을 다 만들어야 순서가 정해진다(170 ms).
        둘 다 인덱스로 풀리지 않고 스키마 쪽 문제라, <b>고치는 대신 근거와 함께 기록만 남겼다.</b>
      </p>
    </div>

    <div class="item">
      <p class="item__t">마감된 공고는 404가 아니라 410 Gone</p>
      <p class="item__d">
        스케줄러를 만들지 않고 <b>조회 시점 판정</b>으로 처리했다. 마감을 404로 주면 지원자가
        "링크가 틀렸나" 하고 헤맨다. 반대로 아직 공개한 적 없는 초안은 404가 맞다.
        검증 중 410이 에러 코드 표에 없어 내부 오류로 나가던 것을 함께 고쳤다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">메일 발행을 커밋 뒤로 옮겼다</p>
      <p class="item__d">
        기존 발송 함수는 <b>커밋 전에</b> 큐로 발행해서, 롤백이 정상 경로인 일괄 변경에서는
        되돌린 건의 메시지가 큐에 남았다. 행 기록과 발행을 분리해 커밋 뒤에 발행하도록 바꿨고,
        단건 경로도 같은 순서로 정리해 기존 경합을 없앴다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">조회 API 13개를 계약과 전수 대조했다</p>
      <p class="item__d">
        초안 공고가 무인증으로 노출되는 문제를 고치면서 <b>조회 엔드포인트 13개를 토큰 없이 전부
        호출해</b> API 문서와 대조했다. 어긋난 것은 둘뿐이었고 지금은 전부 맞는다.
        <b>"문서에 안 적혀 있다"와 "문서의 전역 규칙이 이미 덮는다"는 다르다</b> &mdash; 표만 보지 않고
        머리말을 먼저 보는 것으로 판단 기준을 바꿨다.
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
        <td><b>1인 절대량</b><br><span class="stat__k">큐 22건</span></td>
        <td>완충 셋을 뒀다. ① 전환기 분담 6건을 에이전트 &middot; 앱 담당자가 나눠 맡는다
            ② 공고 API 실측 판정 &mdash; 예상보다 오래 걸리면 권장 항목부터 다음 주로 강등
            ③ 권장 항목은 필수 항목보다 항상 뒤.</td>
      </tr>
      <tr>
        <td><b>AWS 리드타임</b></td>
        <td>SES 샌드박스 해제가 늦으면 메일 항목이 선다. 인프라가 첫날 신청을 걸고, 막히면
            <b>콘솔 출력 발송자로 폴백</b>해 워커 로직만 먼저 검증한다.</td>
      </tr>
      <tr>
        <td><b>ERD 확정 지연</b></td>
        <td>목업 머지가 선행이다. 인프라 M1의 확정 앞당김 결정에 묶여 있다.</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">7.</span> 발표 포인트</h2>

  <ul class="talk">
    <li><b>상태 전환 규칙을 DB 제약과 서비스 레이어 중 어디서 왜 강제했는가</b> &mdash; 정의되지 않은
        전이를 어디서 막을지의 선택과 그 대가.</li>
    <li><b>느린 쿼리를 어떻게 찾았고 인덱스로 몇 ms에서 몇 ms로 줄였는가</b> &mdash; 성능 문서의 실제
        숫자로. <b>고치지 못한 병목을 근거와 함께 남긴 것</b>까지 포함해서.</li>
    <li><b>파일 업로드가 왜 API 서버를 거치면 안 되는가</b> &mdash; presigned URL로 S3에 직행시킨 이유.</li>
  </ul>

</div>

<a class="role__back" href="{{ '/team/' | relative_url }}">&larr; 팀 구성 및 역할</a>

</div>
