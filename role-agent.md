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
  <h1>에이전트 &middot; 담당 박소연</h1>
  <p>버튼으로 안 되는 작업을 에이전트로 &mdash; 최종 합불은 항상 사람
     &middot; 2026. 09. 04. 인계 &middot; 최종 갱신 2026. 09. 29.</p>
</div>

<div class="role__stat">
  <div class="stat"><span class="stat__k">담당</span>
    <span class="stat__v">박소연 <span class="who who-d">소연 D</span></span></div>
  <div class="stat"><span class="stat__k">소유 폴더</span>
    <span class="stat__v"><code>backend/app/agent/</code></span></div>
  <div class="stat"><span class="stat__k">스택</span>
    <span class="stat__v">Claude API<small>Python SDK &middot; 로컬 임베딩</small></span></div>
  <div class="stat"><span class="stat__k">기능</span>
    <span class="stat__v">5<small>축</small></span></div>
  <div class="stat"><span class="stat__k">확정 주체</span>
    <span class="stat__v">사람<small>최종 합불</small></span></div>
</div>

<div class="role__sec">

  <h2><span class="role__num">1.</span> 미션</h2>

  <p class="role__p">
    버튼으로 안 되는 작업을 에이전트로 처리한다. 착수 시점에는 세 축
    (이력서 추출 &middot; 도구 호출 &middot; RAG 보조)이었고, 그 뒤 결정 문서로 두 축이 더해져
    지금은 다섯이다 &mdash;
    <b>① 이력서 비정형 &rarr; 정형 추출 ② 요약 &rarr; 평가 &rarr; 추천 3단 체인 기반 자동 서류 심사
    ③ 도구 호출 에이전트 ④ RAG 시맨틱 검색 ⑤ AI 면접의 표정 &middot; 음성 진위 판별과
    서류 &harr; 발언 대조.</b>
  </p>
  <p class="role__p">
    <b>최종 합격 &middot; 불합격 확정은 항상 사람</b>이다. 2026. 09. 10. ADR-0034가 "확정은 사람"의
    범위를 그 한 자리로 좁혔다 &mdash; 서류 점수와 그에 따른 단계 이동, 면접 점수는 아르가
    판정하고, <b>사람이 손으로 바꾸면 그쪽이 항상 이긴다</b>(단계를 사람이 바꾼 지원자는 이후
    자동 판정에서 빠진다). 화면에서는 AI 제안이 앰버 점선, 사람이 확정한 것이 실선으로 계속
    구분된다. 이것은 구현 편의가 아니라
    <b>채용이라는 도메인에서 되돌릴 수 없는 마지막 판단은 자동화하지 않겠다는 결정</b>이다.
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
        <li><b>자동 서류 심사</b> &mdash; 요약 &rarr; 평가 &rarr; 추천 3단 체인이 100점 만점 점수와
            근거를 내고, 공고별 임계로 단계를 옮긴다. 자동을 끄는 공고 스위치와 사람의 수동
            변경이 항상 우선한다</li>
        <li><b>도구 호출 에이전트</b> &mdash; 자연어 한 문장 &rarr; 검색 &middot; 조회(읽기) /
            단계 변경 &middot; 면접관 배정 &middot; 메일(쓰기) 순차 호출.
            도구 13종 &mdash; 읽기 7 &middot; 쓰기 6</li>
        <li>에이전트 API 라우터와 그 UI 스펙 (UI 구현은 프론트와 협업)</li>
        <li><b>음성 입력</b> &mdash; STT &rarr; 엔티티 해석 레이어 &rarr; 기존 텍스트 에이전트.
            <code>POST /agent/stt</code> 로 붙어 있다</li>
        <li><b>RAG 시맨틱 검색</b> &mdash; 자기소개서 &middot; 기술 임베딩 기반 의미 검색.
            "여유 시 보조"에서 정식 기능으로 올라왔다</li>
        <li><b>AI 면접의 표정 &middot; 음성 진위 판별</b> &mdash; 프레임 &middot; 개별 판정은
            저장하지 않고 세션 집계값만 남긴다. 함께 돌리는 <b>서류 &harr; 발언 대조</b>는
            일치 / 불일치 / 확인필요 세 갈래로만 내고 양쪽 원문을 인용한다 &mdash; 점수를 만들지 않는다</li>
      </ul>
    </div>

    <div class="scope__box scope__box--out">
      <h3>제외</h3>
      <ul>
        <li><b>최종 합격 &middot; 불합격 자동 확정 &mdash; 영구 제외</b></li>
        <li>음성 대 음성 응답 &middot; TTS</li>
        <li>SNS 크롤링 &middot; <b>3인 이상 다자 화상면접</b></li>
        <li><s>표정 분석</s> &middot; <s>1:1 실시간 화상면접</s> &mdash; 착수 때는 제외였으나
            2026. 09. 07. ADR-0029로 표정 &middot; 음성 진위 판별을 도입하고, 09. 08.에 1:1은
            한다로 뒤집었다. 지금은 둘 다 한다 &mdash; 진위 판별은 이 도메인, 1:1 화면은
            프론트 &middot; 앱 몫이다</li>
      </ul>
    </div>

  </div>

  <p class="role__note" style="margin-top:1.1rem; margin-bottom:0;">
    <b>부수효과가 있는 도구는 반드시 확인 단계를 거친다.</b> "김도현을 불합격으로 옮길까요?"를 사람이
    승인해야 실행된다. 게이트를 타는 것은 단계 변경 &middot; 면접관 배정 &middot; 일정 제안 &middot;
    메일 발송 &middot; 지원서 접수 5종이고, <b>메일 초안만 빠진다</b> &mdash; 초안은 텍스트만 돌려주고
    아무것도 바꾸지 않아서, 그것까지 확인 카드를 물리면 승인 한 번의 의미가 흐려진다.
    되돌릴 수 없는 것은 발송이고 그쪽이 게이트를 지난다. 발송에서는
    <b>수신자가 지원자 본인으로 고정</b>된다 &mdash; 도구가 주소를 인자로 받지 않는다.
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
        <td>당시 확정은 도구 호출 <code>claude-opus-5</code> &middot; 요약
            <code>claude-haiku-4-5</code>였다 &mdash; 도구 호출 정확도가 데모 품질을 좌우하므로
            그쪽에만 상위 모델을 쓴다는 판단이었다(ADR-0011).
            <b>실제 운영은 채팅 &middot; 요약 둘 다 <code>claude-haiku-4-5</code>다</b> &mdash;
            코드 기본값이 그렇고(<code>backends/anthropic_backend.py</code>),
            ADR-0032도 "실제로 도는 것은 <code>claude-haiku-4-5</code>"라고 적는다.
            도구 호출을 opus로 올린 기록은 문서에 없다.
            ADR-0011은 이 실제값에 맞춰 개정할 항목으로 남아 있다.
            사용 모델명은 레코드(<code>ai_summary_model</code>)에 기록해 발표 때 근거로 제시한다.</td>
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
        요약 1건이 haiku 단가로 약 $0.006이다(처음 계산 근거였던 opus 기준으로는 약 $0.03).
        성능 검증용 더미 10만 건에 그대로 호출을 걸면 <b>haiku로도 $550, opus였다면 $2,750짜리
        사고</b>가 된다 &mdash; 어느 모델이든 사고라서 <b>가드가 모델 선택보다 중요하다.</b>
        더미의 요약 필드는 비워두거나 문장 은행에서 채운다.
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
    에이전트는 초기 버전(09. 04.) 범위 밖이다. 아래 <b>W1 &middot; W2는 당시 오너 진수택의 기록</b>이고
    &mdash; 그 시점까지의 기여는 전환기 백엔드 분담과 UI &middot; 모델 결정(ADR-0009 &middot; 0011)이다
    &mdash; 박소연은 W2 마지막 날인 09. 04.에 인계받았으므로 <b>W3부터가 이 담당의 몫</b>이다.
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
        <td>음성 입력</td>
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
      <tr class="is-now">
        <td class="tbl__wk"><b>버퍼</b><span>09. 28. ~ 30.</span></td>
        <td>동결</td>
        <td>남은 이슈 처리. RAG는 여유 항목에서 빠졌다 &mdash; 시맨틱 검색으로 먼저 들어갔다</td>
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
        화면에서 "AI 제안"(앰버 점선)과 "사람 확정"(실선)이 색과 선으로 구분되어 보이게 설계했고,
        AI 점수 박스에는 "확정은 담당자가 합니다"를 상시 표기한다. ADR-0034 이후 <b>되돌릴 수 없는
        최종 합격 &middot; 불합격만</b> 사람의 명시적 액션으로 확정되고, 그 앞 단계의 아르 판정은
        사람이 언제든 덮어쓸 수 있다.
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
            전환기에 <b>당시 에이전트 오너였던 진수택이 평가 API(E2)와 면접관 배정(E3)을 직접 만들어
            선행을 스스로 풀었다.</b> 이 도메인은 2026. 09. 04.에 박소연이 인계받았다.</td>
      </tr>
      <tr>
        <td><b>표정 &middot; 음성 진위 판별이 누군가에게 불리하게 작동할 수 있다</b></td>
        <td>ADR-0029는 도입을 확정하면서 <b>미결 세 가지를 문서에 남겨 뒀다</b> &mdash;
            ① 정확도 &middot; 공정성 ② 지원자의 반박 경로 ③ 법 &middot; 제도 대응.
            분류기는 법정 영상 121 표본에 교차검증 76%라 "판정"이 아니라 일관성 신호다.
            그래서 면접 점수에서 진위 몫을 <b>30% 상한</b>으로 묶고(ADR-0034), 화면 문구는
            "진실 쪽에 가까움"까지만 쓴다. 미결이 풀리지 않으면 결과를 담당자에게 보이지 않고
            면접 진행에만 쓰는 대안으로 돌아간다 &mdash; 그 자리는 이미 있다.</td>
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
    <li><b>음성 인식 오류가 도구 호출로 전파되는 것을 어떻게 막았는가</b> &mdash; 엔티티 해석 레이어.</li>
    <li><b>왜 "버튼으로 되는 일"에 에이전트를 쓰지 않았는가</b> &mdash; 그리고 ADR-0034로 확정 지점을
        최종 합불 한 자리로 좁힌 뒤에도 그 원칙이 어디에 남았는가를 자기 언어로.</li>
  </ul>

</div>

<a class="role__back" href="{{ '/team/' | relative_url }}">&larr; 팀 구성 및 역할</a>

</div>
