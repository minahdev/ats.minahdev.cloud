---
layout: default
title: 개발 일정
permalink: /schedule/
---

<style>
.sch { max-width: 64rem; margin: 2.5rem auto 4rem; }
.sch__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.sch__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; }
.sch__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

.sch__sec { margin-bottom: 3.25rem; }
.sch__sec > h2 {
  font-size: 1.05rem;
  color: #2a7ae2;
  margin: 0 0 1.1rem;
  padding-bottom: .5rem;
  border-bottom: 1px solid #e5e7eb;
  display: flex;
  gap: .5rem;
  align-items: baseline;
  word-break: keep-all;
}
.sch__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.sch__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }
.sch__note code { font-size: .82rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 담당자 색 — 사이트 전체에서 사람마다 고정이다 */
.who {
  display: inline-block;
  padding: .06rem .4rem;
  border-radius: 3px;
  font-size: .72rem;
  font-weight: 700;
  letter-spacing: .02em;
  white-space: nowrap;
}
.who-a { background: #e0e7ff; color: #3730a3; }
.who-b { background: #d1fae5; color: #065f46; }
.who-c { background: #fce7f3; color: #9d174d; }
.who-d { background: #fef3c7; color: #92400e; }
.who-e { background: #e0f2fe; color: #075985; }
.who-all { background: #f3f4f6; color: #4b5563; }

/* 게이트 2개 */
.gate { display: grid; grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr)); gap: .75rem; margin-bottom: 1.5rem; }
.gate__box { border: 1px solid #e5e7eb; border-left: 3px solid #2a7ae2; border-radius: 6px; padding: .9rem 1.1rem; }
.gate__box--second { border-left-color: #dc2626; }
.gate__when { display: block; font-size: .74rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .2rem; }
.gate__name { font-size: 1.05rem; font-weight: 700; color: #111827; margin: 0 0 .5rem; }
.gate__box ul { margin: 0; padding-left: 1.05rem; }
.gate__box li { font-size: .84rem; line-height: 1.7; color: #4b5563; word-break: keep-all; }

/* 표 공통 */
.tbl__scroll { overflow-x: auto; padding-bottom: .3rem; }
.tbl { width: 100%; border-collapse: collapse; font-size: .87rem; }
.tbl th {
  background: #f9fafb;
  text-align: left;
  padding: .6rem .7rem;
  font-size: .74rem;
  color: #6b7280;
  letter-spacing: .03em;
  border-bottom: 1px solid #e5e7eb;
  white-space: nowrap;
}
.tbl td {
  padding: .6rem .7rem;
  border-bottom: 1px solid #f3f4f6;
  vertical-align: top;
  color: #374151;
  line-height: 1.65;
  word-break: keep-all;
}
.tbl code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 주차 매트릭스 */
.matrix { min-width: 58rem; }
.matrix th.wk { text-align: center; font-variant-numeric: tabular-nums; }
.matrix th.wk span { display: block; font-weight: 400; color: #9ca3af; font-size: .7rem; margin-top: .12rem; }
.matrix th.wk--gate { background: #eff6ff; color: #1e40af; }
.matrix td.dom { white-space: nowrap; background: #fafafa; }
.matrix td { font-size: .82rem; }
.matrix td.c--gate { background: #f8fbff; }
.matrix .done { color: #9ca3af; }

.tag {
  display: inline-block;
  padding: .04rem .38rem;
  border-radius: 3px;
  font-size: .7rem;
  font-weight: 700;
  letter-spacing: .02em;
  white-space: nowrap;
  vertical-align: .05em;
}
.tag--done { background: #d1fae5; color: #065f46; }
.tag--gate { background: #fee2e2; color: #991b1b; }

/* 칸반 보드 */
.kanban__scroll { overflow-x: auto; padding-bottom: .5rem; }
.kanban {
  display: grid;
  grid-template-columns: repeat(5, minmax(12rem, 1fr));
  gap: .75rem;
  min-width: 60rem;
}
.col { background: #f9fafb; border: 1px solid #e5e7eb; border-radius: 6px; padding: .7rem .6rem; }
.col__head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: .4rem;
  margin: 0 0 .7rem;
  padding: 0 .15rem .5rem;
  border-bottom: 1px solid #e5e7eb;
  font-size: .82rem;
  font-weight: 700;
  color: #374151;
}
.col__count {
  background: #e5e7eb;
  color: #4b5563;
  border-radius: 10px;
  padding: .02rem .42rem;
  font-size: .72rem;
  font-variant-numeric: tabular-nums;
}
.col--now { background: #eff6ff; border-color: #bfdbfe; }
.col--now .col__head { border-bottom-color: #bfdbfe; }
.col--now .col__count { background: #bfdbfe; color: #1e40af; }
.col--done { background: #f0fdf4; border-color: #bbf7d0; }
.col--done .col__head { border-bottom-color: #bbf7d0; }
.col--done .col__count { background: #bbf7d0; color: #166534; }
.card {
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 5px;
  padding: .55rem .6rem;
  margin-bottom: .5rem;
  font-size: .81rem;
  line-height: 1.5;
  color: #1f2937;
  word-break: keep-all;
}
.card:last-child { margin-bottom: 0; }
.card--more { background: transparent; border-style: dashed; color: #9ca3af; text-align: center; }
.card__meta { display: flex; gap: .35rem; align-items: center; margin-top: .4rem; flex-wrap: wrap; }
.card__wk { font-size: .7rem; color: #9ca3af; font-weight: 600; }

/* 역할 요약 */
.roles { min-width: 44rem; }
.roles td:first-child { white-space: nowrap; }
.roles__name { font-weight: 600; color: #111827; }
.roles__stack { color: #6b7280; font-size: .8rem; }

/* 운영 리듬 */
.cere { display: grid; grid-template-columns: repeat(auto-fit, minmax(13rem, 1fr)); gap: .75rem; }
.cere__item { border: 1px solid #e5e7eb; border-radius: 6px; padding: .85rem .9rem; }
.cere__item h3 { margin: 0 0 .3rem; font-size: .92rem; color: #111827; word-break: keep-all; }
.cere__when { display: block; font-size: .75rem; color: #2a7ae2; font-weight: 600; margin-bottom: .4rem; }
.cere__item p { margin: 0; font-size: .84rem; color: #6b7280; line-height: 1.65; word-break: keep-all; }

.sch__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }
</style>

<div class="sch">

<div class="sch__head">
  <h1>개발 일정 및 추진 체계</h1>
  <p>AI 기반 채용 프로세스 자동화 및 지원자 통합 관리 플랫폼 &middot;
     도메인 오너제 / 주 단위 자율 진행 &middot; 담당은 09. 04. 재배치 기준
     &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="sch__sec">

  <h2><span class="sch__num">1.</span> 진행 체계</h2>
  <p class="sch__note">
    착수는 2026. 08. 20.이고, 도메인별 주차 진행은 08. 24.(W1)부터 센다.
    전체를 스프린트로 끊지 않고 <b>게이트 2개</b>를 세운 뒤, 그 사이를 각 도메인이 자기 로드맵의
    주간 계획대로 진행한다. 완료 기준은 도메인마다 다르므로 각 역할 상세 페이지에 있다.
  </p>

  <div class="gate">

    <div class="gate__box">
      <span class="gate__when">1차 게이트</span>
      <p class="gate__name">초기 버전 &mdash; 09. 04. (금)</p>
      <ul>
        <li>프론트: 전 화면이 목데이터로 동작하고 <b>Vercel URL로 접근 가능</b></li>
        <li>백엔드: 코어 API가 <b>배포 URL의 Swagger에서 동작</b></li>
        <li><b>수직 슬라이스 1개</b> &mdash; 공개 지원 폼 제출 &rarr; DB 저장 &rarr;
            담당자 확인까지 실데이터로 관통</li>
        <li>에이전트 &middot; 앱은 미포함 &mdash; 산출은 설계 결정까지</li>
      </ul>
    </div>

    <div class="gate__box gate__box--second">
      <span class="gate__when">2차 게이트</span>
      <p class="gate__name">1차 완성 &mdash; 09. 30. (수)</p>
      <ul>
        <li>필수 27개 기능 전부 <b>프로덕션에서 동작</b></li>
        <li>정식 트랙 2종(에이전트 &middot; 앱)도 데모 가능 상태</li>
        <li>QA 시나리오 전 항목 통합 리허설 2회 완료</li>
        <li>09. 28. ~ 30.은 전 도메인 공통 버퍼 &mdash; 코드 프리즈와 잔여 버그</li>
      </ul>
    </div>

  </div>

  <p class="sch__note" style="margin-bottom:0;">
    <b>주차 구분</b> &mdash; W1 08. 24.~28. &middot; W2 08. 31.~09. 04. &middot; W3 09. 07.~11. &middot;
    W4 09. 14.~18. &middot; W5 09. 21.~25. &middot; 통합 버퍼 09. 28.~30.
    <br>10. 01. 이후 최종 마감(10. 27.)까지의 2차 구간은 1차 완성 결과를 보고 수립한다.
  </p>

</div>

<div class="sch__sec">

  <h2><span class="sch__num">2.</span> 주차별 진행 계획</h2>
  <p class="sch__note">
    가로는 주차, 세로는 도메인이다. 회색은 이미 완료된 항목.
    <b>에이전트와 앱은 초기 버전 범위 밖</b>이라, 그 시점까지는 자기 트랙과 병행해
    백엔드 큐를 나눠 맡았다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl matrix">
    <thead>
      <tr>
        <th>도메인</th>
        <th class="wk">W1 <span>08. 24.~28.</span></th>
        <th class="wk wk--gate">W2 <span>~09. 04. 초기 버전</span></th>
        <th class="wk">W3 <span>09. 07.~11.</span></th>
        <th class="wk">W4 <span>09. 14.~18.</span></th>
        <th class="wk">W5 <span>09. 21.~25.</span></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="dom"><span class="who who-e">수택 E</span><br>인프라 &middot; 총괄</td>
        <td class="done">AWS 신청 &middot; <b>ERD 확정</b> &middot; Compose</td>
        <td class="c--gate">실배포 1차 &middot; <b>게이트 판정</b></td>
        <td>CI/CD 자동화</td>
        <td>중간 통합 점검</td>
        <td>통합 리허설 &middot; 환경 동결</td>
      </tr>
      <tr>
        <td class="dom"><span class="who who-b">우정 B</span><br>백엔드</td>
        <td class="done">인증 &middot; 코어 API <span class="tag tag--done">조기 달성</span></td>
        <td class="c--gate">코어 API 배포 확인</td>
        <td>전환 로직 &middot; 파일 &middot; 메일</td>
        <td>성능 &mdash; 10만 건 &middot; 인덱스</td>
        <td>테스트 &middot; 통합</td>
      </tr>
      <tr>
        <td class="dom"><span class="who who-c">민아 C</span><br>프론트엔드</td>
        <td>React 뼈대 &middot; 토큰 이식</td>
        <td class="c--gate"><b>전 화면 정적 + Vercel</b></td>
        <td>API 연동</td>
        <td>칸반 &middot; 낙관적 업데이트</td>
        <td>배포 &middot; 마감</td>
      </tr>
      <tr>
        <td class="dom"><span class="who who-d">소연 D</span><br>에이전트</td>
        <td class="done">추출 &middot; 에이전트 본체 <span class="tag tag--done">조기 달성</span></td>
        <td class="c--gate">목업 전달 &middot; 테스트 배치</td>
        <td>프롬프트 튜닝</td>
        <td>(여유) 음성 입력</td>
        <td>데모 동결</td>
      </tr>
      <tr>
        <td class="dom"><span class="who who-c">민아 C</span><br>앱 (모바일)</td>
        <td class="done">백엔드 분담 &middot; <b>Flutter 뼈대</b> <span class="tag tag--done">앞당김</span></td>
        <td class="c--gate">기기 설치 확인 &middot; 목데이터 착수</td>
        <td>정적 화면</td>
        <td>API 연동 &middot; 단계 변경</td>
        <td>마감 &middot; 데모</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="sch__note" style="margin-top:1.1rem; margin-bottom:0;">
    W1에 <b>세 도메인이 계획을 앞질렀다.</b> 백엔드는 W2 물량인 코어 API를 W1 안에 소화했고,
    에이전트는 M1&ndash;M4 코드를 끝냈으며, 앱은 W2 예정이던 뼈대를 08. 26.에 완료했다.
    앞당겨진 만큼이 뒤쪽 주차의 버퍼가 된다.
  </p>

</div>

<div class="sch__sec">

  <h2><span class="sch__num">3.</span> 칸반 보드</h2>
  <p class="sch__note">
    카드 배치는 2026. 08. 28. 기준이고, <b>담당 칩은 09. 04. 재배치 이후 오너</b>로 표시했다.
    카드는 왼쪽에서 오른쪽으로만 이동한다.
    도메인 오너제에서는 각자 자기 큐를 위에서부터 소화하므로,
    <b>진행 중 컬럼은 도메인당 1건</b>을 넘지 않는 것을 원칙으로 한다.
    완료 컬럼은 주요 항목만 표시했다.
  </p>

  <div class="kanban__scroll">
  <div class="kanban">

    <div class="col">
      <p class="col__head">백로그 <span class="col__count">10</span></p>

      <div class="card">CI/CD 파이프라인 자동화
        <span class="card__meta"><span class="who who-e">수택 E</span><span class="card__wk">W3</span></span></div>
      <div class="card">중간 통합 점검 · 통합 리허설
        <span class="card__meta"><span class="who who-e">수택 E</span><span class="card__wk">W4–5</span></span></div>
      <div class="card">불합격 사유 · 일괄 단계 변경
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__wk">W3</span></span></div>
      <div class="card">화면 API 연동 (목데이터 제거)
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W3</span></span></div>
      <div class="card">칸반 드래그 · 낙관적 업데이트 롤백
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W4</span></span></div>
      <div class="card">프롬프트 튜닝 · 비용 실측
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__wk">W3</span></span></div>
      <div class="card">(여유) 음성 입력 · 엔티티 해석
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__wk">W4</span></span></div>
      <div class="card">JWT 로그인 연동
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W4</span></span></div>
      <div class="card">단계 변경 · 평가 연동
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W4</span></span></div>
      <div class="card">이력서 열람 · 데모 시나리오
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W5</span></span></div>
    </div>

    <div class="col col--now">
      <p class="col__head">이번 주 (W2) <span class="col__count">5</span></p>

      <div class="card">실배포 1차 · 초기 버전 게이트 판정
        <span class="card__meta"><span class="who who-e">수택 E</span><span class="card__wk">W2</span></span></div>
      <div class="card">전 화면 정적 + Vercel 프리뷰
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W2</span></span></div>
      <div class="card">주요 API 테스트 코드
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__wk">W2</span></span></div>
      <div class="card">지원자 리스트 · 상세 · 로그인 (목데이터)
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W2</span></span></div>
      <div class="card">팀 Android 기기 전원 APK 설치 확인
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W2</span></span></div>
    </div>

    <div class="col">
      <p class="col__head">진행 중 <span class="col__count">4</span></p>

      <div class="card">SES 샌드박스 해제 · IAM 최소 권한
        <span class="card__meta"><span class="who who-e">수택 E</span><span class="card__wk">W1–2</span></span></div>
      <div class="card">React 뼈대 · 공통 컴포넌트
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W1</span></span></div>
      <div class="card">공고 목록 화면 목업 (인수)
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W1</span></span></div>
      <div class="card">확정안 기준 에이전트 목업 재작업
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__wk">W1–2</span></span></div>
    </div>

    <div class="col">
      <p class="col__head">리뷰 / 승인 대기 <span class="col__count">1</span></p>

      <div class="card">불합격 사유 + 일괄 단계 변경 — 팀장 승인 대기
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__wk">W1</span></span></div>
    </div>

    <div class="col col--done">
      <p class="col__head">완료 <span class="col__count">27</span></p>

      <div class="card">ERD 확정 · Docker Compose · 브랜치 보호
        <span class="card__meta"><span class="who who-e">수택 E</span><span class="card__wk">W1</span></span></div>
      <div class="card">인증 · 역할 3종 · 접근 제어
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__wk">W1</span></span></div>
      <div class="card">검색 · 인덱스 튜닝 (111ms → 7.8ms)
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__wk">W1</span></span></div>
      <div class="card">메일 큐 워커 · 재시도 · 확인 메일
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__wk">W1</span></span></div>
      <div class="card">S3 presigned 업로드 · 더미 10만 건
        <span class="card__meta"><span class="who who-b">우정 B</span><span class="card__wk">W1</span></span></div>
      <div class="card">이력서 추출 PoC · 도구 호출 에이전트
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__wk">W1</span></span></div>
      <div class="card">에이전트 UI 위치 · 모델 · 비용 확정
        <span class="card__meta"><span class="who who-d">소연 D</span><span class="card__wk">W1</span></span></div>
      <div class="card">앱 스택 Flutter 확정 · 뼈대 · 토큰 이식
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W1</span></span></div>
      <div class="card">공고 · 지원자 API · 담당자 직접 등록
        <span class="card__meta"><span class="who who-c">민아 C</span><span class="card__wk">W1</span></span></div>
      <div class="card card--more">그 외 백엔드 큐 항목 등 18건</div>
    </div>

  </div>
  </div>

</div>

<div class="sch__sec">

  <h2><span class="sch__num">4.</span> 조직 구성 및 역할 분담</h2>
  <p class="sch__note">
    사람마다 도메인 하나를 소유한다. 소유 폴더 밖은 자기 것이 아니고,
    자기 도메인의 로드맵이 자기 작업의 기준이다.
    각자의 범위 &middot; 마일스톤 &middot; 리스크는
    <a href="{{ '/team/' | relative_url }}">팀 구성 및 역할</a> 페이지와 역할 상세에 있다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl roles">
    <thead>
      <tr>
        <th>담당</th>
        <th>도메인</th>
        <th>소유 폴더</th>
        <th>담당 업무</th>
        <th>기술 스택</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><span class="who who-e">수택 E</span><br><span class="roles__name">진수택</span><br>
            <span class="roles__stack">팀장</span></td>
        <td><a href="{{ '/role-infra/' | relative_url }}">인프라 &middot; 총괄</a></td>
        <td><code>infra/</code> <code>.github/</code> AWS</td>
        <td>AWS · 자동 CD · CI · GitHub 설정 · alembic 이행 · 통합 · 발표 총괄</td>
        <td class="roles__stack">Docker, GitHub Actions, EC2, S3, alembic</td>
      </tr>
      <tr>
        <td><span class="who who-b">우정 B</span><br><span class="roles__name">이우정</span></td>
        <td><a href="{{ '/role-backend/' | relative_url }}">백엔드</a></td>
        <td><code>backend/</code></td>
        <td>인증 · 권한, 공고 · 지원자 · 평가 API, 단계 전환, 검색 · 인덱스 튜닝, 파일 · 메일 코드</td>
        <td class="roles__stack">FastAPI, PostgreSQL</td>
      </tr>
      <tr>
        <td><span class="who who-c">민아 C</span><br><span class="roles__name">김민아</span></td>
        <td><a href="{{ '/role-frontend/' | relative_url }}">프론트엔드</a></td>
        <td><code>frontend/</code></td>
        <td>React 뼈대 · 공통 컴포넌트, 전 화면 구현과 연동, 칸반 드래그 · 낙관적 업데이트, 반응형</td>
        <td class="roles__stack">React, Vite, TypeScript, Vercel</td>
      </tr>
      <tr>
        <td><span class="who who-d">소연 D</span><br><span class="roles__name">박소연</span></td>
        <td><a href="{{ '/role-agent/' | relative_url }}">에이전트</a></td>
        <td><code>backend/app/agent/</code></td>
        <td>이력서 구조화 추출 · 요약, 도구 호출 에이전트, 에이전트 API와 UI 스펙, RAG 시맨틱 검색</td>
        <td class="roles__stack">Claude API (Python SDK)</td>
      </tr>
      <tr>
        <td><span class="who who-c">민아 C</span><br><span class="roles__name">김민아</span></td>
        <td><a href="{{ '/role-app/' | relative_url }}">앱 (모바일)</a></td>
        <td><code>mobile/</code></td>
        <td>모바일 네이티브 앱 — 로그인, 공고 · 지원자 조회, 단계 변경, 평가 작성, 이력서 열람</td>
        <td class="roles__stack">Flutter, Dart, Android</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="sch__sec">

  <h2><span class="sch__num">5.</span> 운영 리듬</h2>
  <p class="sch__note">
    2026. 08. 24. <b>작업 풀 + 팀장 지시서 발행</b> 체계에서 <b>도메인 오너제</b>로 전환했다.
    리뷰가 팀장 한 명에게 몰려 다른 사람의 작업이 최대 일주일씩 대기하던 구조를 없애는 것이
    목적이었다.
  </p>

  <div class="cere">

    <div class="cere__item">
      <h3>주간 계획</h3>
      <span class="cere__when">주 시작 · 오너 각자</span>
      <p>지난주 점검 → 이번 주 계획 → 자기 로드맵 갱신을 스스로 한다.
         다른 도메인에 걸리는 변경만 공용 주간 계획서에 적어 팀장과 맞춘다.</p>
    </div>

    <div class="cere__item">
      <h3>도메인 내부 PR</h3>
      <span class="cere__when">수시 · 셀프 머지</span>
      <p>남의 폴더나 공용 파일이 안 섞였고, PR 본문에 검증 결과가 있고, CI가 초록이면
         오너가 스스로 머지한다. 팀장 검수 사이클과 무관하게 돈다.</p>
    </div>

    <div class="cere__item">
      <h3>팀장 검수 · 머지</h3>
      <span class="cere__when">매주 금요일 최소 1회</span>
      <p>스키마 · API 문서 · 공용 문서 · 도메인 경계를 넘는 PR이 대상이다.
         금요일 검수에 걸리도록 <b>목요일까지</b> 올린다. 다른 도메인이 대기 중인 PR은 수시 요청.</p>
    </div>

    <div class="cere__item">
      <h3>게이트 판정</h3>
      <span class="cere__when">09. 04. · 09. 30.</span>
      <p>초기 버전과 1차 완성을 정의된 항목 충족 여부로 판정한다.
         판정 집행은 배포를 쥔 인프라 도메인이 맡는다.</p>
    </div>

    <div class="cere__item">
      <h3>30분 룰</h3>
      <span class="cere__when">상시</span>
      <p>30분 넘게 막히면 혼자 붙들지 말고 팀 채널에 묻는다. 1인 1도메인 구조에서는
         혼자 오래 막히는 것이 가장 큰 지연 요인이다.</p>
    </div>

    <div class="cere__item">
      <h3>통합 리허설</h3>
      <span class="cere__when">W5 · 2회</span>
      <p>QA 시나리오 전 항목을 프로덕션 URL과 실기기에서 돌린다.
         이후 데모 환경을 동결하고 버퍼 기간에는 잔여 버그만 처리한다.</p>
    </div>

  </div>

</div>

<a class="sch__back" href="{{ '/toc/' | relative_url }}">&larr; 목차</a>

</div>
