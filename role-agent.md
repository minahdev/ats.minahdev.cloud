---
layout: default
title: 에이전트
permalink: /role-agent/
---

{% include role-style.html %}

<div class="role">

<div class="role__head">
  <p class="role__crumb"><a href="{{ '/team/' | relative_url }}">팀 구성 및 역할</a> &rsaquo;
     에이전트</p>
  <h1>에이전트 &middot; 담당 진수택</h1>
  <p>버튼으로 안 되는 작업을 에이전트로 &mdash; 최종 확정은 항상 사람
     &middot; 최종 갱신 2026. 08. 28.</p>
</div>

<div class="role__stat">
  <div class="stat"><span class="stat__k">담당</span>
    <span class="stat__v">진수택 <span class="who who-e">수택 E</span></span></div>
  <div class="stat"><span class="stat__k">소유 폴더</span>
    <span class="stat__v"><code>app/agent/</code></span></div>
  <div class="stat"><span class="stat__k">스택</span>
    <span class="stat__v">Claude API<small>Python SDK</small></span></div>
  <div class="stat"><span class="stat__k">기능</span>
    <span class="stat__v">3<small>축</small></span></div>
  <div class="stat"><span class="stat__k">확정 주체</span>
    <span class="stat__v">사람<small>영구 원칙</small></span></div>
</div>

<div class="role__sec">

  <h2><span class="role__num">1.</span> 미션</h2>

  <p class="role__p">
    버튼으로 안 되는 작업을 에이전트로 처리한다. 세 축이다 &mdash;
    <b>① 이력서 비정형 &rarr; 정형 추출 ② 도구 호출 에이전트 ③ RAG 질의응답(보조).</b>
  </p>
  <p class="role__p">
    셋 모두에서 <b>최종 확정은 항상 사람</b>이다. AI가 만든 모든 것은 화면에서 점선 상태로
    시작하고, 사람의 명시적 액션을 거쳐야만 실선이 된다. 이것은 구현 편의가 아니라
    <b>채용이라는 도메인에서 되돌릴 수 없는 판단을 자동화하지 않겠다는 결정</b>이다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">2.</span> 범위</h2>

  <div class="scope">

    <div class="scope__box scope__box--in">
      <h3>포함</h3>
      <ul>
        <li><b>이력서 구조화 추출</b> &mdash; PDF &middot; DOCX &middot; HWP 텍스트 추출(텍스트 PDF만,
            스캔본 제외 &middot; HWP 실패 시 수동 폴백) &rarr; 경력 &middot; 기술 &middot; 학력
            구조화 필드 + 담당자용 요약문</li>
        <li>접수 시 1회 생성 &middot; 저장. <b>재생성은 명시적 버튼으로만</b></li>
        <li><b>도구 호출 에이전트</b> &mdash; 자연어 한 문장 &rarr; 검색 &middot; 조회(읽기) /
            단계 변경 &middot; 메일 초안(쓰기) 순차 호출</li>
        <li>에이전트 API 라우터와 그 UI 스펙 (UI 구현은 프론트와 협업)</li>
        <li>(여유) 음성 입력 &mdash; STT &rarr; 엔티티 해석 레이어 &rarr; 기존 텍스트 에이전트</li>
        <li>(여유) RAG 질의응답 &mdash; ①②의 보조</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>제외</h3>
      <ul>
        <li><b>최종 합불 자동 확정 &mdash; 영구 제외</b></li>
        <li>음성 대 음성 응답 &middot; TTS</li>
        <li>표정 분석 &middot; SNS 크롤링 &middot; 실시간 화상면접</li>
      </ul>
    </div>

  </div>

  <p class="role__note" style="margin-top:1.1rem; margin-bottom:0;">
    <b>쓰기 도구는 반드시 확인 단계를 거친다.</b> "김도현을 불합격으로 옮길까요?"를 사람이 승인해야
    실행된다. 메일도 초안까지만 만들고 발송은 사람이 확정한다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">3.</span> 확정된 설계 결정</h2>
  <p class="role__note">
    착수 전에 결정이 필요했던 3건. 모두 2026. 08. 25.에 확정됐다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>결정</th><th>확정 내용</th></tr>
    </thead>
    <tbody>
      <tr>
        <td><b>에이전트 UI 위치</b></td>
        <td>혼합안 &mdash; 단축키 콘솔을 기본으로 두고, 확인 카드는 콘솔 안에, 요약은 지원자 상세
            패널의 별도 블록에 둔다. 시안 3안을 만들 계획이었으나 결정이 먼저 나와 시안 작업이
            불필요해졌다.</td>
      </tr>
      <tr>
        <td><b>모델 &middot; 비용</b></td>
        <td>도구 호출은 <code>claude-opus-5</code>, 요약은 <code>claude-haiku-4-5</code>.
            도구 호출 정확도가 데모 품질을 좌우하므로 그쪽에만 상위 모델을 쓴다.
            사용 모델명은 레코드에 기록해 발표 때 근거로 제시한다.</td>
      </tr>
      <tr>
        <td><b>음성 입력 위치</b></td>
        <td>콘솔 전용 마이크. UI 위치 결정에 묶어 함께 확정했다.</td>
      </tr>
    </tbody>
  </table>
  </div>

  <div class="items" style="margin-top:1.1rem;">
    <div class="item">
      <p class="item__t">비용 가드 &mdash; 더미 10만 건에 LLM 호출 금지</p>
      <p class="item__d">
        요약 1건이 약 $0.03이다. 성능 검증용 더미 10만 건에 그대로 호출을 걸면
        <b>$3,000짜리 사고</b>가 된다. 더미의 요약 필드는 비워두거나 문장 은행에서 채운다.
        여기에 더해 호출마다 토큰 사용량을 로깅하고, API 키는 환경변수로만 두어 코드와 로그에
        남기지 않는다.
      </p>
    </div>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">4.</span> 인터페이스 계약</h2>

  <p class="role__p">
    <b>의존</b> &mdash; 도구가 호출할 대상인 백엔드 코어 API(검색 &middot; 지원자 조회 &middot;
    단계 변경 &middot; 평가)와 이력서 원문 접근 경로.
    <b>제공</b> &mdash; 지원서 접수 흐름이 호출할 요약 생성 함수, 그리고 에이전트 API.
  </p>
  <p class="role__p">
    <b>에이전트 도구는 기존 REST를 서비스 레이어로 재사용한다 &mdash; 권한 검사를 우회하는 별도
    경로를 만들지 않는다.</b> 에이전트가 뒷문이 되면 역할 기반 접근 제어 전체가 무의미해지기
    때문이다.
  </p>

</div>

<div class="role__sec">

  <h2><span class="role__num">5.</span> 주간 계획</h2>
  <p class="role__note">
    에이전트는 초기 버전(09. 04.) 범위 밖이다. 그 시점까지의 기여는 전환기 백엔드 분담과
    UI &middot; 모델 결정이다.
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
        <td>M1&ndash;M4 조기 완료</td>
        <td>목업 &middot; 추출 PoC &middot; 에이전트 본체 &middot; 설계 결정 4건 확정 &middot;
            확정안 목업 재작업 착수 &middot; 프론트 지원</td>
        <td><span class="tag tag--done">달성</span>
            <b>M1부터 M4까지 코드가 W1 안에 끝났다.</b> 목업 착수</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W2</b><span>08. 31. ~ 09. 04.</span></td>
        <td>목업 &middot; 테스트 &middot; 데모</td>
        <td>확정안 목업 완성(확인 카드 &middot; 동명이인 &middot; 마이크) &rarr; 프론트 전달 &middot;
            테스트 정식 배치 &middot; 전 구간 데모 시나리오 실행</td>
        <td>목업 전달 완료, 테스트가 CI에서 통과, 4단계 시나리오 성공</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W3</b><span>09. 07. ~ 11.</span></td>
        <td>프롬프트 튜닝 &middot; 폴리시</td>
        <td>실호출 기반 프롬프트 개선 &middot; 엣지 케이스 처리 &middot; 토큰 비용 실측 갱신</td>
        <td>프롬프트 2차 버전, 비용 실측치 기록</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W4</b><span>09. 14. ~ 18.</span></td>
        <td>(여유) 음성 입력</td>
        <td>STT + 엔티티 해석 레이어 &mdash; 이름 유사도 매칭 &middot; 기술 용어 음차 정규화 &middot;
            한글 수사 &rarr; 숫자</td>
        <td>음성 &rarr; 에이전트 연결 데모</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>W5</b><span>09. 21. ~ 25.</span></td>
        <td>데모 동결 &middot; 발표</td>
        <td>데모 시나리오 최종 확인 &middot; 발표 스토리 정리</td>
        <td>&mdash;</td>
      </tr>
      <tr>
        <td class="tbl__wk"><b>버퍼</b><span>09. 28. ~ 30.</span></td>
        <td>동결</td>
        <td>남은 이슈 처리 &middot; (여유) RAG 질의응답</td>
        <td><b>09. 30. 1차 완성.</b> 음성이 들어가면 파괴적 명령은 음성에서도 확인 단계를 거친다</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">6.</span> 품질 기준</h2>
  <p class="role__note">전 마일스톤 공통으로 적용한다.</p>

  <div class="items">

    <div class="item">
      <p class="item__t">환각 가드 &mdash; 응답은 도구 결과만 인용한다</p>
      <p class="item__d">
        존재하지 않는 지원자나 수치를 만들어내면 그 시점에서 <b>실패로 취급하고 프롬프트를
        수정한다.</b> 그럴듯한 답변을 성공으로 세지 않는다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">확정은 사람 &mdash; 점선에서 실선으로</p>
      <p class="item__d">
        AI가 만든 모든 것은 점선 상태로 시작하고, 사람의 명시적 액션으로만 실선이 된다.
        화면에서 "AI 제안"과 "사람 확정"이 색과 선으로 구분되어 보이게 설계했다.
      </p>
    </div>

    <div class="item">
      <p class="item__t">재현성 &mdash; 프롬프트는 코드다</p>
      <p class="item__d">
        프롬프트를 소스 트리 안에서 버전 관리하고, 호출마다 모델명과 토큰 사용량을 로깅한다.
        "그때는 됐는데"를 없애기 위한 조건이다.
      </p>
    </div>

  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">7.</span> 리스크 및 대응</h2>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>리스크</th><th>대응</th></tr>
    </thead>
    <tbody>
      <tr>
        <td><b>코어 API가 늦으면 도구를 붙일 데가 없다</b></td>
        <td>M1을 API와 무관한 작업(추출 PoC &middot; UI 시안 &middot; 프롬프트 설계)으로 구성했고,
            전환기에 <b>본인이 평가 API를 직접 만들어 선행을 스스로 풀었다.</b></td>
      </tr>
      <tr>
        <td><b>HWP 추출 불안정</b></td>
        <td>처음부터 <b>"실패 시 수동 입력 폴백"을 설계에 포함</b>했다. 나중에 대응하는 예외가 아니라
            정상 경로의 일부다.</td>
      </tr>
      <tr>
        <td><b>비용 폭주</b></td>
        <td>비용 가드 3종 &mdash; 더미 데이터 호출 금지 &middot; 토큰 사용량 로깅 &middot;
            키의 환경변수 격리.</td>
      </tr>
    </tbody>
  </table>
  </div>

</div>

<div class="role__sec">

  <h2><span class="role__num">8.</span> 발표 포인트</h2>

  <ul class="talk">
    <li><b>도구 호출 에이전트 설계</b> &mdash; 한 문장이 검색 &rarr; 필터 &rarr; 상태 변경 &rarr;
        문서 생성으로 분해되는 과정, 그리고 <b>왜 쓰기 도구에만 확인 단계를 강제했는가.</b></li>
    <li><b>음성 인식 오류가 도구 호출로 전파되는 것을 어떻게 막았는가</b> &mdash; 엔티티 해석 레이어.
        (음성 기능을 넣는 경우)</li>
    <li><b>왜 "버튼으로 되는 일"에 에이전트를 쓰지 않았는가</b> &mdash; AI를 추천까지만 쓰기로 한
        원칙을 본인 언어로.</li>
  </ul>

</div>

<a class="role__back" href="{{ '/team/' | relative_url }}">&larr; 팀 구성 및 역할</a>

</div>
