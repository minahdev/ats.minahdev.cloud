---
layout: default
title: 팀 구성
permalink: /team/
---

{% include role-style.html %}

<style>
/* 도메인 카드 5종 */
.dom { display: grid; grid-template-columns: repeat(auto-fit, minmax(15.5rem, 1fr)); gap: .75rem; }
.dom__card {
  border: 1px solid #e5e7eb;
  border-radius: 6px;
  padding: .95rem 1rem;
  display: flex;
  flex-direction: column;
}
.dom__top { display: flex; align-items: baseline; gap: .5rem; margin-bottom: .5rem; flex-wrap: wrap; }
.dom__name { font-size: 1rem; font-weight: 700; color: #111827; }
.dom__area { font-size: .78rem; color: #6b7280; }
.dom__dir {
  font-size: .74rem;
  color: #9ca3af;
  margin: 0 0 .55rem;
  font-family: ui-monospace, SFMono-Regular, Menlo, monospace;
  word-break: break-all;
}
.dom__mission { margin: 0 0 .8rem; font-size: .85rem; line-height: 1.7; color: #4b5563; word-break: keep-all; flex: 1; }
.dom__more { font-size: .82rem; font-weight: 600; }

/* 의존 구조 */
.dep { border: 1px solid #e5e7eb; border-radius: 6px; overflow: hidden; }
.dep__layer { padding: .8rem 1rem; border-bottom: 1px solid #f3f4f6; }
.dep__layer:last-child { border-bottom: 0; }
.dep__k {
  display: block;
  font-size: .72rem;
  color: #9ca3af;
  letter-spacing: .03em;
  margin-bottom: .4rem;
}
.dep__v { margin: 0; font-size: .87rem; line-height: 1.75; color: #374151; word-break: keep-all; }
.dep__layer--base { background: #f9fafb; }

/* 운영 규칙 카드 */
.ops { display: grid; grid-template-columns: repeat(auto-fit, minmax(13rem, 1fr)); gap: .75rem; }
.ops__item { border: 1px solid #e5e7eb; border-radius: 6px; padding: .85rem .9rem; }
.ops__item h3 { margin: 0 0 .3rem; font-size: .92rem; color: #111827; word-break: keep-all; }
.ops__when { display: block; font-size: .75rem; color: #2a7ae2; font-weight: 600; margin-bottom: .4rem; }
.ops__item p { margin: 0; font-size: .84rem; color: #6b7280; line-height: 1.7; word-break: keep-all; }
</style>

<div class="role">

<div class="role__head">
  <p class="role__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 2. 팀 구성 및 역할</p>
  <h1>팀 구성 및 역할</h1>
  <p>seuk &middot; 5명 &middot; 도메인 오너제 &mdash; 사람마다 도메인 하나를 소유한다
     &middot; 최종 갱신 2026. 08. 28.</p>
</div>

<div class="role__stat">
  <div class="stat"><span class="stat__k">개발 인원</span>
    <span class="stat__v">5<small>명</small></span></div>
  <div class="stat"><span class="stat__k">도메인</span>
    <span class="stat__v">5<small>1인 1도메인</small></span></div>
  <div class="stat"><span class="stat__k">운영 방식</span>
    <span class="stat__v">오너제<small>2026. 08. 24. 전환</small></span></div>
  <div class="stat"><span class="stat__k">초기 버전</span>
    <span class="stat__v">09. 04.<small>금</small></span></div>
  <div class="stat"><span class="stat__k">1차 완성</span>
    <span class="stat__v">09. 30.<small>수</small></span></div>
</div>

<div class="role__sec">

  <h2><span class="role__num">1.</span> 개발 인원 소개</h2>
  <p class="role__note">
    사람마다 도메인 하나를 소유한다. <b>자기 도메인의 로드맵이 자기 작업의 기준</b>이고,
    범위 &middot; 마일스톤 &middot; 작업 큐 &middot; 완료 기준이 전부 거기에 있다.
    소유 폴더 밖은 자기 것이 아니다.
  </p>

  <div class="dom">

    <div class="dom__card">
      <div class="dom__top">
        <span class="dom__name">이재우</span>
        <span class="who who-a">재우 A</span>
        <span class="dom__area">인프라 &middot; 총괄 (팀장)</span>
      </div>
      <p class="dom__dir">infra/ &middot; .github/ &middot; docker-compose &middot; AWS</p>
      <p class="dom__mission">
        전원이 딛는 바닥. 의존이 없는 대신 <b>전원의 선행 조건</b>이 된다.
      </p>
      <a class="dom__more" href="{{ '/role-infra/' | relative_url }}">역할 상세 &rarr;</a>
    </div>

    <div class="dom__card">
      <div class="dom__top">
        <span class="dom__name">이우정</span>
        <span class="who who-b">우정 B</span>
        <span class="dom__area">백엔드</span>
      </div>
      <p class="dom__dir">backend/ (agent 제외)</p>
      <p class="dom__mission">
        화면 &middot; 앱 &middot; 에이전트가 딛고 서는 <b>모든 API와 데이터.</b>
      </p>
      <a class="dom__more" href="{{ '/role-backend/' | relative_url }}">역할 상세 &rarr;</a>
    </div>

    <div class="dom__card">
      <div class="dom__top">
        <span class="dom__name">박소연</span>
        <span class="who who-d">소연 D</span>
        <span class="dom__area">프론트엔드</span>
      </div>
      <p class="dom__dir">frontend/</p>
      <p class="dom__mission">
        목업을 실제 React 제품으로 &mdash; <b>칸반 드래그가 프로젝트의 얼굴</b>이다.
      </p>
      <a class="dom__more" href="{{ '/role-frontend/' | relative_url }}">역할 상세 &rarr;</a>
    </div>

    <div class="dom__card">
      <div class="dom__top">
        <span class="dom__name">진수택</span>
        <span class="who who-e">수택 E</span>
        <span class="dom__area">에이전트</span>
      </div>
      <p class="dom__dir">backend/app/agent/</p>
      <p class="dom__mission">
        버튼으로 안 되는 작업을 에이전트로 &mdash; <b>확정은 항상 사람</b>이다.
      </p>
      <a class="dom__more" href="{{ '/role-agent/' | relative_url }}">역할 상세 &rarr;</a>
    </div>

    <div class="dom__card">
      <div class="dom__top">
        <span class="dom__name">김민아</span>
        <span class="who who-c">민아 C</span>
        <span class="dom__area">앱 (모바일)</span>
      </div>
      <p class="dom__dir">mobile/</p>
      <p class="dom__mission">
        같은 API의 두 번째 클라이언트. <b>순수 소비자라 실패해도 남이 안 죽는다.</b>
      </p>
      <a class="dom__more" href="{{ '/role-app/' | relative_url }}">역할 상세 &rarr;</a>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">2.</span> 역할 분담</h2>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr>
        <th>담당</th>
        <th>도메인</th>
        <th>담당 업무</th>
        <th>기술 스택</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><span class="who who-a">재우 A</span><br><b>이재우</b><br>
            <span class="stat__k">팀장</span></td>
        <td>인프라 &middot; 총괄</td>
        <td>AWS &middot; 배포 &middot; CI/CD &middot; GitHub 설정 &middot; 스키마 관리.
            총괄로서 인터페이스 리뷰 &middot; 통합 &middot; 발표</td>
        <td>Docker, GitHub Actions, EC2, S3, SES, SQS</td>
      </tr>
      <tr>
        <td><span class="who who-b">우정 B</span><br><b>이우정</b></td>
        <td>백엔드</td>
        <td>인증 &middot; 권한, 공고 &middot; 지원자 &middot; 평가 API, 단계 전환,
            검색 &middot; 인덱스 튜닝, 파일 &middot; 메일 코드</td>
        <td>FastAPI, PostgreSQL</td>
      </tr>
      <tr>
        <td><span class="who who-d">소연 D</span><br><b>박소연</b></td>
        <td>프론트엔드</td>
        <td>React 뼈대 &middot; 공통 컴포넌트, 전 화면 구현과 API 연동,
            칸반 드래그 &middot; 낙관적 업데이트, 반응형</td>
        <td>React, Vite, TypeScript, Vercel</td>
      </tr>
      <tr>
        <td><span class="who who-e">수택 E</span><br><b>진수택</b></td>
        <td>에이전트</td>
        <td>이력서 구조화 추출 &middot; 요약, 도구 호출 에이전트,
            에이전트 API와 UI 스펙, (여유) 음성 입력 &middot; RAG</td>
        <td>Claude API (Python SDK)</td>
      </tr>
      <tr>
        <td><span class="who who-c">민아 C</span><br><b>김민아</b></td>
        <td>앱 (모바일)</td>
        <td>모바일 네이티브 앱 &mdash; 로그인, 공고 &middot; 지원자 조회,
            단계 변경, 평가 작성, 이력서 열람</td>
        <td>Flutter, Dart, Android</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">3.</span> 의존 구조</h2>
  <p class="role__note">
    아래로 갈수록 남이 기다리는 쪽이다. <b>이 순서가 곧 일정의 임계경로</b>이고,
    각 도메인의 리스크 대응도 여기서 나온다.
  </p>

  <div class="dep">

    <div class="dep__layer dep__layer--base">
      <span class="dep__k">바닥 &mdash; 의존 없음</span>
      <p class="dep__v">
        <span class="who who-a">재우 A</span> <b>인프라</b> &mdash; 아무에게도 의존하지 않는다.
        그래서 <b>전부의 선행 조건</b>이 된다. 여기가 밀리면 나머지 넷이 대기한다.
      </p>
    </div>

    <div class="dep__layer">
      <span class="dep__k">중간 &mdash; 인프라에 의존, 셋에 제공</span>
      <p class="dep__v">
        <span class="who who-b">우정 B</span> <b>백엔드</b> &mdash; 인프라의 접속 정보와 AWS
        리소스를 받고, 클라이언트 3종에 API를 제공한다. 여기가 늦으면
        <b>나머지 전부가 목데이터에 갇힌다.</b>
      </p>
    </div>

    <div class="dep__layer">
      <span class="dep__k">소비 &mdash; 백엔드에 의존</span>
      <p class="dep__v">
        <span class="who who-d">소연 D</span> <b>프론트엔드</b> &mdash; 초반 두 마일스톤을
        목데이터로 진행해 백엔드를 기다리지 않는다. 대신 <b>목데이터 필드명을 ERD와 동일하게</b>
        맞춰 연동이 필드 교체만으로 끝나게 했다.<br>
        <span class="who who-c">민아 C</span> <b>앱</b> &mdash; 소비만 하고 제공은 없다.
        격리 수준이 가장 높아 <b>앱이 실패해도 다른 파트가 멈추지 않는다.</b>
      </p>
    </div>

    <div class="dep__layer">
      <span class="dep__k">양방향 &mdash; 백엔드와 서로 주고받음</span>
      <p class="dep__v">
        <span class="who who-e">수택 E</span> <b>에이전트</b> &mdash; 백엔드 API를 도구로
        호출하는 동시에, 지원서 접수 흐름이 부를 요약 생성 함수를 백엔드에 제공한다.
        <b>함수 시그니처는 두 오너 간 인터페이스 PR로 합의</b>한다.
      </p>
    </div>

  </div>

  <p class="role__note" style="margin-top:1.1rem; margin-bottom:0;">
    에이전트와 앱은 초기 버전(09. 04.) 범위 밖이다. 두 트랙 모두 <b>코어 기능이 항상 우선</b>이고,
    코어 데모는 두 트랙 없이도 완결된다. 그래서 전환기(&sim;09. 04.) 동안 두 담당자는 자기 트랙과
    병행해 백엔드 큐를 나눠 맡았다 &mdash; <b>앱 담당자의 경우 자기 트랙의 선행 조건인 지원자 API를
    본인 손으로 푸는 구조</b>였다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">4.</span> 협업 방식</h2>
  <p class="role__note">
    2026. 08. 24. <b>작업 풀 + 팀장 지시서 발행</b> 체계에서 <b>도메인 오너제</b>로 전환했다.
    리뷰 병목이 팀장 한 명에게 몰리는 구조를 없애는 것이 목적이었다.
  </p>

  <div class="ops">

    <div class="ops__item">
      <h3>자기 큐를 스스로 소화한다</h3>
      <span class="ops__when">오너</span>
      <p>위에서부터 순서대로. 선행이 안 풀렸으면 건너뛰고 다음 것. 큐가 비면 오너가 로드맵을
         갱신해 채운다 &mdash; 단 마일스톤 범위 안에서. <b>범위 자체를 바꾸는 건 팀장 합의.</b></p>
    </div>

    <div class="ops__item">
      <h3>자기 도메인 PR은 자기가 머지</h3>
      <span class="ops__when">오너 &middot; 수시</span>
      <p>남의 폴더나 공용 파일이 안 섞였고, PR 본문에 검증 결과가 있고, CI가 초록이면
         스스로 머지한다. <b>CI 빨간불 = 머지 불가</b>가 오너제의 안전망이다.</p>
    </div>

    <div class="ops__item">
      <h3>남의 도메인은 고치지 않는다</h3>
      <span class="ops__when">전원</span>
      <p>다른 도메인에서 문제를 발견하면 직접 고치지 말고 <b>이슈로 남긴다.</b>
         소유자가 아닌 디렉토리를 임의로 리팩터링하지 않는다.</p>
    </div>

    <div class="ops__item">
      <h3>팀장 검수 사이클</h3>
      <span class="ops__when">매주 금요일 최소 1회</span>
      <p>스키마 &middot; API 문서 &middot; 공용 문서 &middot; 도메인 경계를 넘는 PR은 팀장 승인이
         필요하다. <b>금요일 검수에 걸리도록 목요일까지 올린다.</b> 다른 도메인이 대기 중인
         급한 PR은 수시 요청.</p>
    </div>

    <div class="ops__item">
      <h3>공용 파일은 아무도 직접 안 고친다</h3>
      <span class="ops__when">전원</span>
      <p>목업 원본 &middot; ERD &middot; API 문서 &middot; 공용 모델 파일이 해당한다.
         팀 채널을 거쳐 팀장이 반영한다. <b>스키마 확정 후 변경은 전원 합의로만.</b></p>
    </div>

    <div class="ops__item">
      <h3>30분 룰</h3>
      <span class="ops__when">전원</span>
      <p>30분 넘게 막히면 혼자 붙들지 말고 팀 채널에 묻는다. 1인 1도메인 구조에서
         혼자 오래 막히는 것이 가장 큰 지연 요인이기 때문이다.</p>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">5.</span> 발표 시 각자 말할 것</h2>
  <p class="role__note">
    상세는 각 역할 상세 페이지의 발표 포인트 절. 전원 공통으로 자기 도메인의 문서화와
    발표 자료 본인 파트를 맡는다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>담당</th><th>도메인</th><th>대표 주제 1개</th></tr>
    </thead>
    <tbody>
      <tr>
        <td><span class="who who-a">재우 A</span> <b>이재우</b></td>
        <td>인프라 &middot; 총괄</td>
        <td>배포 파이프라인 &middot; 권한 모델 + <b>리뷰 병목을 구조로 푼 과정</b></td>
      </tr>
      <tr>
        <td><span class="who who-b">우정 B</span> <b>이우정</b></td>
        <td>백엔드</td>
        <td>상태 전환 규칙을 DB와 코드 중 어디서 강제했는가 + <b>인덱스 튜닝 전후 수치</b></td>
      </tr>
      <tr>
        <td><span class="who who-d">소연 D</span> <b>박소연</b></td>
        <td>프론트엔드</td>
        <td>드래그 실패 시 <b>낙관적 업데이트를 어떻게 롤백했는가</b></td>
      </tr>
      <tr>
        <td><span class="who who-e">수택 E</span> <b>진수택</b></td>
        <td>에이전트</td>
        <td>도구 호출 에이전트 &mdash; <b>왜 쓰기 도구에만 확인 단계를 강제했는가</b></td>
      </tr>
      <tr>
        <td><span class="who who-c">민아 C</span> <b>김민아</b></td>
        <td>앱</td>
        <td>같은 API로 웹 &middot; 앱 두 클라이언트 &mdash;
            <b>클라이언트 추가에 서버 변경이 몇 줄이었는가</b></td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<a class="role__back" href="{{ '/toc/' | relative_url }}">&larr; 목차</a>

</div>
