---
layout: default
title: 개발 로그
permalink: /log/
---

<style>
.log { max-width: 46rem; margin: 2.5rem auto 4rem; }
.log__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.log__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; }
.log__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }
.log__entry { margin-bottom: 2.5rem; }
.log__date {
  display: flex;
  gap: .75rem;
  align-items: baseline;
  margin: 0 0 .9rem;
  padding-bottom: .5rem;
  border-bottom: 1px solid #e5e7eb;
}
.log__day {
  font-size: 1.1rem;
  font-weight: 700;
  color: #111827;
  font-variant-numeric: tabular-nums;
}
.log__week { font-size: .8rem; color: #9ca3af; }
.log__entry ul { list-style: none; margin: 0; padding: 0 0 0 2.1rem; }
.log__entry li { padding: .3rem 0; color: #374151; font-size: .95rem; word-break: keep-all; }
.log__entry li::before { content: "—"; color: #d1d5db; margin-right: .6rem; }
.log__entry li code { font-size: .84rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; border: 0; }
.log__tag {
  display: inline-block;
  margin-left: .5rem;
  padding: .05rem .4rem;
  border-radius: 3px;
  background: #f3f4f6;
  color: #6b7280;
  font-size: .72rem;
  font-weight: 600;
  letter-spacing: .02em;
  vertical-align: .05em;
}
.log__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }
</style>

<div class="log">

<div class="log__head">
  <h1>개발 로그</h1>
  <p>AI 기반 채용 프로세스 자동화 및 지원자 통합 관리 플랫폼 &middot; 작업 기록
     &middot; 착수 2026. 08. 20. &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 09. 21. ~ 09. 22.</span>
    <span class="log__week">6주차 &middot; W5 &middot; 심사 대응과 최종 정리</span>
  </div>

  <ul>
    <li>제출 프리즈 이후 저장소 커밋은 멈췄다 — 마지막 코드 커밋이 <b>09. 18.</b>이고, 이후로는 문서와 시각화만 손댄다<span class="log__tag">기획</span></li>
    <li>Qwen vs Claude 정량 &middot; 품질 비교 보고서 — 같은 자(<code>judge.py</code>)로 동일 23건을 재서 학습 전 Qwen 26.1%(6/23) &rarr; Claude Haiku 4.5 69.6%(16/23) &rarr; Qwen v9 73.9%(17/23)<span class="log__tag">AI</span></li>
    <li>pass/fail 너머를 네 축으로 분해했다 — 판정 항목별(학습 전 Qwen 의 약점은 도구 이름 일치 26% 한 축뿐이고 no-tool 위반 없음은 100%), 질문 유형별, 실패의 질, 요약 어댑터 정성 품질<span class="log__tag">AI</span></li>
    <li><b>위험한 실패</b>(임의 실행 &middot; 지어낸 도구)는 세 모델 모두 0건이었다 — 갈린 곳은 정확도가 아니라 수치 추론과 형식 안정성이다<span class="log__tag">AI</span></li>
    <li>비용 &middot; 지연을 한 문서로 모았다 — 평가 1건 $0.0139 &middot; 실사용 호출당 $0.0075 &middot; Qwen $0 + GPU $0.71/h &middot; 콜드 스타트 78초<span class="log__tag">AI</span></li>
    <li>해석 주의를 보고서에 명시했다 — 채점기가 Qwen gold 기준이라 편향이 있고 표본이 23건뿐이라 "동급"이 정직한 표현이다<span class="log__tag">문서</span></li>
    <li>정리 서류 13종 본문을 클라우드 기준으로 재작성하고 온프레미스에 의존하는 결론이 0건임을 확인, 크레덴셜과 전화번호를 걷어냈다<span class="log__tag">문서</span></li>
    <li>프로젝트 소개 슬라이드(html &middot; png &middot; jpg)와 09. 18. 멘토링 피드백을 지킬 사이트에 기록<span class="log__tag">문서</span></li>
    <li>보고서 사이트 각 장을 09. 22. 기준으로 갱신 — 개발 로그를 착수일부터 오늘까지로 확장<span class="log__tag">문서</span></li>
    <li>09. 22. 기준 규모 — API 라우트 107 &middot; DB 테이블 28(ERD v2.8) &middot; alembic 리비전 26 &middot; 웹 화면 25 &middot; 앱 화면 23 &middot; pytest 1,165건 통과 &middot; AI 프롬프트 18 &middot; ADR 36편 &middot; 커밋 1,095<span class="log__tag">기획</span></li>
  </ul>

</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 09. 14. ~ 09. 20.</span>
    <span class="log__week">5주차 &middot; W4 &middot; 온프레미스와 제출 프리즈</span>
  </div>

  <ul>
    <li><b>09. 14.</b> SQS 메일 워커 폐기, n8n 단일 발송 경로로 고정(ADR-0036) — 발송은 이미 n8n 으로 넘어가 워커는 놀고 있었다. 살아 있는 경로가 아니라 죽어도 알림이 없었고, <code>MAIL_DISPATCH</code> 기본값이 <code>worker</code> 라 변수를 비우면 큐에 실린 채 아무도 소비하지 않는 조용한 실패가 났다<span class="log__tag">인프라</span></li>
    <li><b>09. 14.</b> 종합 평가 페이지 신설 — 공고별 지원자 점수 &middot; 요약, 이름을 누르면 서류 &middot; 인적성 &middot; 면접 종합 상세로<span class="log__tag">프론트</span></li>
    <li><b>09. 14.</b> 학습 손실을 assistant 응답 구간에만 걸도록 바꾸고(completion-only), T4 OOM 을 left-truncation 과 <code>max_length</code> 축소(2048 &rarr; 재발 뒤 1024 + <code>PYTORCH_CUDA_ALLOC_CONF</code>)로 해소<span class="log__tag">AI</span></li>
    <li><b>09. 15.</b> 운영 STT 를 OpenAI whisper-1 API 로 확정(ADR-0038) — t3.large(2 vCPU)에서 로컬 large-v3-turbo 가 44초 발화를 180초 안에 못 끝내고 밀린 시간이 뒤 답변까지 연쇄로 죽였다. 분당 $0.006 &middot; 면접당 약 $0.06<span class="log__tag">AI</span></li>
    <li>무음에 유튜브 자막 문구("다음 영상에서 만나요")를 지어내 답변으로 저장하던 것은 조각별 <code>no_speech_prob</code> 게이트로 막았다<span class="log__tag">AI</span></li>
    <li><b>09. 15.</b> opus-5 를 실측하고 미채택 — 비용상 채팅 &middot; 요약 기본 모델은 claude-haiku-4-5 로 유지한다<span class="log__tag">결정</span></li>
    <li><b>09. 15.</b> 종합평가 화면에서 최종 합격 &middot; 불합격을 바로 확정, 공고 마감 &middot; 다시 열기 버튼 추가 — 최종 판단은 끝까지 사람이 쥔다<span class="log__tag">프론트</span></li>
    <li><b>09. 16.</b> 웹 지원자 AI 면접의 영상 &middot; 음성을 담당자 화상 면접방으로 1:1 WebRTC 송신. 3인 이상(SFU)은 집단 면접으로 미뤘다<span class="log__tag">백엔드</span></li>
    <li><b>09. 16.</b> 지원자 비밀번호 로그인을 웹 &middot; 앱 양쪽에 붙였다(ADR-0033 개정) — 생년월일은 비밀번호를 아직 안 정한 계정만<span class="log__tag">앱</span></li>
    <li><b>09. 16.</b> 비밀번호 설정 메일이 <b>한 통도 안 나가고 있던 것</b>을 발견해 수정 — 단계 제약이 발송을 막고 있었다<span class="log__tag">백엔드</span></li>
    <li><b>09. 17.</b> lie-detection 을 GPU(<code>VIT_DEVICE=cuda</code>)로 이관 — T4 실측 STT 275ms/3초 &middot; ViT 75ms/crop, 8명 동시 접속에서 대기줄 0<span class="log__tag">인프라</span></li>
    <li><b>09. 17.</b> Qwen3-8B QLoRA 자체학습 완결 — chat v9 73.9%. <code>eval_loss</code> 는 0.339 &rarr; 0.074 로 떨어졌는데 도구 호출이 전멸하던 모순을 풀었다: 손실이 7,347자 공통 시스템 프롬프트에 쏠리고 <code>tool_call</code> 은 전체 토큰의 1.8%라 기울기가 닿지 않았다<span class="log__tag">AI</span></li>
    <li>학습 데이터 222건(실측 21 + 합성 192 + 시드 9), 어댑터는 chat &middot; summary &middot; interview 3갈래. v9 실패 6건 중 5건은 UX상 정상이라 실질 95% 선이다<span class="log__tag">AI</span></li>
    <li><b>09. 17.</b> n8n 이 웹훅만 받고 죽어 <code>queued</code> 로 남은 메일을 API 가 5분마다 SMTP 로 재발송(최대 3회) — 발송 경로가 하나뿐이라 생긴 단일 장애점을 없앴다<span class="log__tag">백엔드</span></li>
    <li><b>09. 17.</b> CI 에 AI 면접 서버 &middot; Flutter 앱 시험 잡을 추가해 잡 5개(ruff F &middot; pytest &middot; 프론트 빌드 &middot; AI 서버 &middot; Flutter)로<span class="log__tag">인프라</span></li>
    <li><b>09. 16. ~ 18.</b> 학원 PC 3대로 온프레미스를 실제 구축 &middot; 운영했다 — Cloudflare Tunnel &middot; Ollama 어댑터 3갈래 &middot; MinIO<span class="log__tag">인프라</span></li>
    <li><b>09. 18. 온프레미스 폐쇄를 결정했다.</b> 로컬 sLLM 이 <code>list_postings</code> 를 건너뛰고 <code>posting_id</code> 를 추측하는 다단계 도구 호출 불안정, 브라우저에서 내부 MinIO 에 닿지 못하는 문제, 프롬프트 예시 숫자를 베껴 전원 64~65점으로 수렴하던 채점, JSON 따옴표 깨짐, 면접 중 컨테이너 재기동으로 답변이 사라지는 사고가 심사 직전에 누적됐다<span class="log__tag">결정</span></li>
    <li>심사 서빙은 검증된 클라우드 스택(Claude &middot; 실 S3)으로 확정하고, 온프레미스 코드 &middot; 어댑터 &middot; GPU 이미지는 자산으로 보존한 뒤 구축 &middot; 오류 &middot; 폐쇄 경위를 종합보고로 남겼다<span class="log__tag">문서</span></li>
    <li><b>09. 18.</b> 심사위원 데모 로그인 — 담당자 &middot; 지원자 데모 버튼, 데모 계정은 사용자 &middot; 권한 관리와 메일 템플릿을 못 바꾸게 읽기 전용으로 잠갔다. 심사자가 비번을 바꿔 서로 못 들어가는 사고를 막는 것이 목적이다<span class="log__tag">프론트</span></li>
    <li>지원자 데모 계정은 로그인할 때마다 인적성 &middot; 면접 시간 &middot; AI 면접 세 화면을 초기화하고 만료를 미래로 갱신한다 — 여럿이 같은 계정을 써도 매번 처음 상태가 된다<span class="log__tag">프론트</span></li>
    <li><b>09. 18.</b> 인사 &middot; 능력 &middot; 사용법 같은 정적 발화를 규칙 라우터의 캔드 응답으로 돌렸다 — 호출당 약 $0.02 나가던 것이 $0 이 된다<span class="log__tag">에이전트</span></li>
    <li><b>09. 18.</b> 무관 질문 거절 기준을 카테고리 열거식에서 <b>"답의 근거가 우리 데이터냐"</b> 로 재작성. 인물 질문에 설명을 다 생성한 뒤 거절을 덧붙이던 토큰 낭비를 없앴고, 이력서 &middot; 자소서 속 인물은 원문을 조회해 정상 답변한다<span class="log__tag">에이전트</span></li>
    <li><b>09. 18.</b> 자료 부족(요약 <code>insufficient=true</code>) 지원자를 <code>applied</code>&rarr;<code>screening</code>&rarr;<code>rejected</code> 로 옮겨 「서류 탈락」 라벨이 붙게 했다(ADR-0034 확장) — 직행시키면 「불합격」으로 보여 사유가 사라진다. 실제 역량이 있는 지원자는 건드리지 않아 대량 탈락을 막는다<span class="log__tag">에이전트</span></li>
    <li><b>09. 18.</b> 로그아웃을 우측 상단 계정 메뉴로 통일 — 담당자 웹만 진입점이 예외적으로 달랐다. 지원자 「내 정보」의 비밀번호 칸이 실제와 다른 값을 보여주던 것도 함께 고쳤다<span class="log__tag">프론트</span></li>
    <li><b>09. 17. ~ 18.</b> 문서 정비 — 09. 12. 폴더 재편으로 깨진 링크 35개, 기준 문서에 남은 옛 코드 경로 11곳을 따라가 고치고 ERD 를 v2.8 로. <code>STT_BACKEND</code> 빈 값을 두 컨테이너가 다르게 읽는다는 것도 4곳에 적었다<span class="log__tag">문서</span></li>
    <li><b>09. 20. 해커톤 제출 코드 프리즈.</b> 심사 기간은 09. 20. ~ 10. 17.<span class="log__tag">기획</span></li>
  </ul>

</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 09. 07. ~ 09. 12.</span>
    <span class="log__week">4주차 &middot; W3 &middot; AI 면접과 구조 재편</span>
  </div>

  <ul>
    <li><b>09. 07.</b> 발표 전 인프라 안정화를 한 묶음으로 넣었다 — 매일 04:00 KST DB 를 S3 로 백업(압축 &middot; <code>gzip -t</code> 검증 &middot; 수명주기 30일), CloudWatch 지표 3종과 SNS 메일 경보, 15분마다 밖에서 찌르는 외부 헬스체크, EC2 상태 검사 실패 시 자동 복구<span class="log__tag">인프라</span></li>
    <li>컨테이너 로그 상한을 서비스당 20MB &times; 3 으로 걸었다 — 29GB 디스크에서 로그 하나가 수 GB 로 부푸는 사고를 먼저 잘랐다<span class="log__tag">인프라</span></li>
    <li>운영 체인을 Amoy &rarr; Ethereum Sepolia 로 옮겼다 — Amoy 무료 수도꼭지 6곳이 전부 막혀 앵커 게시에 필요한 가스를 구할 수 없었다<span class="log__tag">인프라</span></li>
    <li>n8n 컨테이너 도입(ADR-0030 1단계) — 메일 &middot; 알림을 워커 코드에서 워크플로 도구로 분리했다. 발송은 노드 하나만 바꾸면 공급자가 바뀐다<span class="log__tag">인프라</span></li>
    <li><b>09. 07.</b> 결정 문서 개정 원칙을 확정했다 — 확정 ADR 23개에 "오너가 개정 ADR 을 쓰면 바뀐다" 한 줄, 지시서 36개와 로드맵 5개에 "작성 시점의 설계" 한 줄. 팀장 확정 대기 게이트를 폐지했다<span class="log__tag">문서</span></li>
    <li>표정 &middot; 음성 진위 판별을 도입하며 ADR-0002 &middot; 0026 두 결정을 개정했다(ADR-0029) — 담당자 화면에 수치로 보이되 점수 &middot; 합불에는 쓰지 않는 참고 지표까지다<span class="log__tag">결정</span></li>
    <li><b>09. 07. ~ 09.</b> AI 면접 실시간 경로를 붙였다 — 답변이 끝나는 지점에서 다음 질문으로 넘기는 WebSocket 흐름(09. 07.), 지원자 폰과 담당자 PC 사이 1:1 WebRTC 시그널링과 faster-whisper 실시간 받아쓰기(09. 08.), 담당자 실시간 분석 화면(09. 09.)<span class="log__tag">백엔드</span></li>
    <li>표정 분류 ViT 를 네 차례 다시 학습했다 — FER2013 69.84% 로 시작해 FERPlus 라벨로 바꿔 무서움 49% &rarr; 76%, 적은 표정을 살려 평균 63.6% &rarr; 70.4%, 4차에서 전체 74.91% &rarr; <b>86.18%</b> &middot; 역겨움 정밀도 5.9% &rarr; 64.2%<span class="log__tag">AI</span></li>
    <li>lie-detection 메모리 상한을 1.5g 에서 4g 까지 다섯 번 올리고 인스턴스를 t3.large 로 옮겨도 계속 OOM 이었다. 원인은 코드 기본값 하나 — faster-whisper "default" 가 CPU 에서 float32 로 잡혀 3.0~3.8GB 를 썼다. <code>int8</code> 을 명시하니 223MB(1/4) &middot; 속도 2.3배<span class="log__tag">인프라</span></li>
    <li><b>09. 10.</b> N1 자동 심사(ADR-0034) — 서류 100점 채점, 임계 기준 자동 이동, 면접관 자동 배정, 면접 AI 점수와 최종 등급까지<span class="log__tag">에이전트</span></li>
    <li>fit-check 지원자 24명을 실측 분석했다. 인수인계에 적힌 "자동 불합격 3명"이 실제로는 8명이었고, 8명 각각의 요건 &middot; 우대 &middot; 문화 세 축 점수를 근거로 수치화했다<span class="log__tag">데이터</span></li>
    <li>그 근거로 판정 가중치를 개정했다(PR #182) — 요건 50&rarr;60, 우대 20&rarr;10, 문화 30 유지에 "요건 70 이상이면 문화 하한 50" 규칙. 요건이 우수한 지원자를 문화 한 문구로 떨어뜨리지 않기 위해서다<span class="log__tag">AI</span></li>
    <li>서버 디스크 여유가 떨어져 EBS 를 29 &rarr; 50GB 로 온라인 확장했다 — 무중단, 여유 27GB 확보<span class="log__tag">인프라</span></li>
    <li>AWS 통합 결제 조직(ETECH)에 편입해 비용을 조직 지급인 계정으로 넘겼다. 사용량 조회가 제한될 수 있어 내부는 수동 계산으로 추적하고, 학습 &middot; 시연 총 사용 시간을 15시간 이내로 관리한다<span class="log__tag">운영</span></li>
    <li>시연 리허설에서 나온 답변 저장 실패(Q9 을 시도하면 Q1 로 되돌아감)를 원인 세 갈래로 좁혀 인계 문서로 넘겼고, 백엔드가 <code>answered_at</code> 기준으로 원인을 규명해 고쳤다 — "답했다"와 "받아썼다"를 나눈 것이 열쇠였다<span class="log__tag">운영</span></li>
    <li><code>.env</code> 를 고쳤는데 반영이 안 되던 함정을 규칙으로 못 박았다 — <code>docker compose restart</code> 는 <code>env_file</code> 을 다시 읽지 않는다. <code>up -d --force-recreate</code> 로 컨테이너를 다시 만들어야 한다<span class="log__tag">환경</span></li>
    <li>시연 데이터로 지원자 24명을 일괄 재접수했다 — 23명은 새 STAR 4문항 자기소개서, 1명만 구 콘텐츠를 남겨 "내용이 바뀜" 배지를 시연하게 했다<span class="log__tag">데이터</span></li>
    <li><b>09. 11.</b> Qwen3-8B QLoRA 학습 파이프라인과 시연 배포 스크립트를 새 폴더로 올렸다<span class="log__tag">AI</span></li>
    <li><b>09. 12. 폴더 재편</b> — 헥사고날 부분 적용과 Bounded Context 4개로 백엔드를 다시 짰다(ADR-0035). <code>models.py</code> 를 71개 파일이 직접 참조하던 것을 5개 파일 분할 + Repository 4종으로 끊고, 라우터 22개를 컨텍스트 폴더로 옮긴 뒤 <code>api/</code> 를 삭제했다. PR #184~#203 스무 건을 하루에 머지했다<span class="log__tag">백엔드</span></li>
    <li><b>09. 12.</b> Claude 를 파인튜닝 Qwen 과 <b>같은 자</b>로 재기 위해 판정기를 분리하고 러너를 추가했다 — 비교의 기준을 먼저 만들었다<span class="log__tag">AI</span></li>
  </ul>

</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 08. 31. ~ 09. 04.</span>
    <span class="log__week">3주차 &middot; W2 &middot; 팀장 이탈과 초기 버전 게이트</span>
  </div>

  <ul>
    <li>공개 지원 폼(C1)과 업로드 파일 <code>files[]</code> 연결을 붙여 로그인 없이 지원서를 받는 경로를 열었다. 면접관이 자기 가용 시간을 등록하는 화면도 함께<span class="log__tag">백엔드</span></li>
    <li>RAG 시맨틱 검색(임베딩 + pgvector)과 프롬프트 체이닝(요약&rarr;평가&rarr;추천)을 도입했다(ADR-0021 &middot; 0022)<span class="log__tag">에이전트</span></li>
    <li>면접 일정 조율을 에이전트가 끝까지 하게 했다 — 일정 도구 4개와 <code>search_users</code>, 지원자가 메일 링크의 대화형 페이지에서 고르면 확정되는 전 구간<span class="log__tag">에이전트</span></li>
    <li>이력서 &middot; 자소서 파일 텍스트를 AI 요약 입력에 포함시켰다(pdf &middot; docx &middot; hwpx 추출, 실패는 <code>None</code> 폴백). 요약이 지원 폼 필드만 읽어 이력서를 충실히 낸 지원자도 "제출물 부족"이 나던 오판이 사라졌다<span class="log__tag">에이전트</span></li>
    <li>지원자 FAQ 응답 API — 토큰 인증 stateless 1문1답, 차단은 키워드 블랙리스트가 아니라 프롬프트의 맥락 판단으로. 실호출 5개 시나리오 전부 정상<span class="log__tag">에이전트</span></li>
    <li><b>09. 01.</b> alembic 도입으로 손 SQL 시대를 끝냈다 — 이제 스키마 변경은 코드와 같은 커밋에 리비전이 따라붙고, 남들은 <code>upgrade head</code> 한 줄로 따라온다<span class="log__tag">백엔드</span></li>
    <li><b>09. 02. 인프라 &middot; 총괄 오너(팀장)가 이탈했다.</b> 서비스가 한 사람 계정에 묶여 있었다 — AWS 루트 &middot; IAM, GitHub org 오너, Vercel, 도메인, Anthropic &middot; OpenAI 키, 서버 <code>.env</code> 의 AWS 키까지 전부 개인 명의였다<span class="log__tag">운영</span></li>
    <li>권한을 사람이 아니라 역할에 붙이기로 하고(ADR-0025) 팀장 키를 09. 02. 폐기, 시크릿을 전부 재발급했다. 콘솔용 IAM 과 서버 전용 IAM 을 분리해 유출 시 재발급 범위를 서버 유저 하나로 좁혔다<span class="log__tag">인프라</span></li>
    <li><b>09. 02.</b> CI 도입 — 게이트가 아니라 "깨졌다는 사실만 즉시 보이게"가 목적이다. 백엔드 pytest + 프론트 빌드, 첫 실행 실측 51초. 그전까지는 깨진 main 을 하루 두 번, 둘 다 우연히 발견했다<span class="log__tag">인프라</span></li>
    <li><b>09. 02.</b> AI 면접 백엔드 3단계 착수(ADR-0026) — 면접 테이블 3종과 스키마 이행, 세션 생성과 지원자 공개 링크, 질문 설정 &middot; 답변 제출 &middot; 종료<span class="log__tag">백엔드</span></li>
    <li>인적성 설문을 도입했다(ADR-0027) — 발송 &middot; 공개 링크 응답 &middot; 통계 &middot; 관찰 요약 전 구간. AI 는 관찰만 하고 성격 판정과 합불 판단에는 쓰지 않는다<span class="log__tag">에이전트</span></li>
    <li><b>09. 02. ~ 03.</b> 앱에 JWT 로그인을 붙여 처음으로 네트워크가 생겼고, 이어 공고 &middot; 지원자 &middot; 상세 &middot; 평가 &middot; 메일 &middot; 캘린더까지 서버 실연동을 하루에 마무리했다<span class="log__tag">앱</span></li>
    <li><b>09. 04. 도메인을 재배치했다</b> — 남은 4명으로 5도메인. 팀장은 진수택이 승계하며 인프라를 겸하고, 에이전트는 박소연이, 프론트엔드는 김민아가 앱과 함께 맡는다<span class="log__tag">기획</span></li>
    <li><b>09. 04. 저장소를 <code>Team-Seuk/Arda</code> 에서 <code>Seuk-Team/Arda</code> 로 이관</b>하고 인프라를 개인 AWS 계정(서울)으로 전체 이전했다 — EC2 <code>arda-api</code>(t3.small) &middot; S3 &middot; SQS &middot; SES &middot; IAM 3단 분리 &middot; Caddy HTTPS<span class="log__tag">인프라</span></li>
    <li><b>09. 04. main 직접 push 를 막고 브랜치&rarr;PR&rarr;자체 머지로 전환했다</b>(CI 초록 필수, 승인 불요). 동시에 <code>main</code> 머지 2분 뒤 자동 배포되는 systemd 폴링 CD 를 개통해 "push 하면 배포"를 전원이 공유한다<span class="log__tag">운영</span></li>
    <li>더미 15명 리허설에서 presigned URL 서명 버그를 실전 검출했다 — 새 버킷 업로드가 403 이던 것으로, 서명 대상이 리전 엔드포인트여야 했다<span class="log__tag">인프라</span></li>
    <li>서명 개인키를 서버에서 빼 GitHub Actions 로 옮기고 OpenTimestamps 를 병행했다(ADR-0028) — 서버에 개인키가 없다<span class="log__tag">인프라</span></li>
    <li>pytest-timeout 60초와 Anthropic 옵트인 가드를 넣었다 — 죽은 테스트가 무한히 걸리던 것과 실수로 유료 AI 를 부르는 상황을 함께 막았다<span class="log__tag">테스트</span></li>
    <li>프론트엔드를 다크 딥네트워크 테마로 전면 교체하고, 데스크톱에 아예 없던 로그아웃 진입점을 설정 화면에 붙였다<span class="log__tag">프론트</span></li>
    <li><b>초기 버전 게이트 4항목을 실측으로 충족</b>했다 — 프론트 전 화면 배포 URL 동작, 코어 API 배포 Swagger 동작, 공개 지원 폼 &rarr; DB &rarr; 담당자 확인 수직 슬라이스 관통<span class="log__tag">기획</span></li>
  </ul>

</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 08. 24. ~ 08. 28.</span>
    <span class="log__week">2주차 &middot; 도메인 주차 W1 &middot; 오너제 전환</span>
  </div>

  <ul>
    <li><b>08. 24. 작업 풀 + 팀장 지시서 발행 체계를 도메인 오너제로 전환했다</b>(ADR-0007). 리뷰가 팀장 한 명에게 몰려 다른 사람 작업이 최대 일주일씩 대기하던 구조를 없애는 것이 목적이었다<span class="log__tag">기획</span></li>
    <li><b>08. 24.</b> ERD v1.0 확정, FastAPI 앱 뼈대, Docker compose 로컬 실행 환경(db + api)까지 같은 날에 올렸다<span class="log__tag">인프라</span></li>
    <li>인증(회원가입 &middot; 로그인 &middot; me), 공개 지원서 제출 API, 지원자 검색 &middot; 필터 API — W2 물량이던 코어 API 를 W1 안에 소화했다<span class="log__tag">백엔드</span></li>
    <li>검색 인덱스를 튜닝해 10만 건에서 <b>111ms &rarr; 7.8ms</b> 로 줄였다<span class="log__tag">백엔드</span></li>
    <li>메일 큐 워커와 재시도 &middot; 확인 메일, S3 presigned 업로드와 더미 10만 건 투입까지 붙였다<span class="log__tag">백엔드</span></li>
    <li>에이전트 뼈대를 세웠다 — 도구 명세, 프롬프트 뼈대와 요약 출력 규약, 한글 PDF 추출 PoC, M2~M4 요약 &middot; 읽기 &middot; 쓰기 도구. ADR-0009(에이전트 UI 위치)와 ADR-0011(모델 &middot; 비용)을 함께 확정했다<span class="log__tag">에이전트</span></li>
    <li>E2E 데모 4단계를 실호출로 검증했다(검색&rarr;조회&rarr;상태 변경&rarr;이메일 초안) — 4단계 전부 정상, 비용 실측 $0.045. 엣지 케이스 8종도 전부 PASS, 비용 $0.083<span class="log__tag">에이전트</span></li>
    <li>대화가 길어지면 <code>application_id</code> 를 엉뚱한 값으로 참조하던 문제를 프롬프트 규칙 두 줄로 잡았다 — 직전 도구 결과에서 확인된 ID 만 쓰고, "이 지원자"는 최근 조회 지원자 기준<span class="log__tag">에이전트</span></li>
    <li>테스트를 <b>185개</b>로 늘려 전부 통과시켰다 — api_agent TestClient 41 &middot; entity_resolver 35 &middot; write_tools 19 &middot; stages 15 &middot; stt 15 &middot; cost 13 등<span class="log__tag">테스트</span></li>
    <li>STT 에 빠져 있던 비용 로깅을 채워 채팅 &middot; 요약 &middot; STT 3기능의 AI 원가 관측을 통일했다($0.006/분 &times; 오디오 길이)<span class="log__tag">에이전트</span></li>
    <li>앱 스택을 Flutter 로 재확정했다(ADR-0010) — iOS 를 시연 범위에서 빼면서 Expo 채택 근거가 사라졌다<span class="log__tag">앱</span></li>
    <li>05-design 토큰을 Dart 로 이식하고 IBM Plex Sans KR 을 번들해 내비게이션 뼈대를 세웠다. 계획상 W2 물량을 08. 26.에 끝냈다<span class="log__tag">앱</span></li>
    <li>목업에 없던 화면 5건은 임의로 그리지 않고 프론트 담당자에게 시안을 요청했다 — 같은 날 도착해 전부 반영했다<span class="log__tag">앱</span></li>
    <li>앱 테스트를 36 &rarr; 42개로. 퍼널 막대 높이가 0 이 되던 버그를 크기를 재는 테스트로 봉인했다 — 눈으로는 "가늘어서 안 보임"과 "높이 0"이 구분되지 않는다<span class="log__tag">테스트</span></li>
    <li>React(Vite &middot; TS) 라우팅 &middot; 레이아웃 뼈대를 세우고 로그인 &middot; 공고 목록 &middot; 대시보드 화면을 올렸다<span class="log__tag">프론트</span></li>
  </ul>

</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 08. 22. ~ 08. 23.</span>
    <span class="log__week">1주차 &middot; 개발 3~4일차</span>
  </div>

  <ul>
    <li>01-erd.md 의 테이블 9개를 SQLAlchemy 모델로 옮겼다 — 문서가 먼저고 코드가 그것을 따른다<span class="log__tag">백엔드</span></li>
    <li>지원자 상세 패널의 AI 요약 &middot; 메모 설계를 확정하고 스키마 &middot; API &middot; ADR 을 같이 묶었다<span class="log__tag">기획</span></li>
    <li>UI 화면 지시서 8장 작성 — 로그인 &middot; 공고 목록 &middot; 대시보드 &middot; 통합검색 &middot; 평가 현황 &middot; 설정 &middot; 지원 폼 &middot; 모바일 리스트<span class="log__tag">문서</span></li>
    <li>브레이크포인트 확정 — 1100 &middot; 768 &middot; PC 최소 1280<span class="log__tag">기획</span></li>
    <li>더미데이터 지시서를 재료 사전 + 문장 은행 방식으로 재작성하고 생성 스크립트를 함께 배치했다<span class="log__tag">문서</span></li>
    <li>지시서에 "막히면 &middot; 되돌리기" 규칙을 추가했다 — 막힌 사람이 혼자 판단하지 않게<span class="log__tag">문서</span></li>
    <li>CODEOWNERS 도입 — 이 시점에는 모든 PR 이 팀장 승인 대상이었다. 이 구조가 병목이 되어 이틀 뒤 오너제로 바뀐다<span class="log__tag">운영</span></li>
  </ul>

</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 08. 21.</span>
    <span class="log__week">1주차 &middot; 개발 2일차</span>
  </div>

  <ul>
    <li>AWS 루트 계정에서 IAM 사용자 생성 후 IAM 계정으로 재로그인<span class="log__tag">인프라</span></li>
    <li>RDS 인스턴스 생성 및 접속 엔드포인트 확보<span class="log__tag">인프라</span></li>
    <li>Jekyll + minima 기반 보고서 사이트 스캐폴드 구성<span class="log__tag">인프라</span></li>
    <li>GitHub Pages 배포 파이프라인 연결 — <code>main</code> push 시 자동 빌드<span class="log__tag">인프라</span></li>
    <li>프로젝트 페이지 경로에 맞춰 <code>baseurl</code> 설정<span class="log__tag">인프라</span></li>
    <li>보고서 표지 및 목차(11장) 작성<span class="log__tag">문서</span></li>
    <li>리포지터리명을 <code>ats.minahdev.cloud</code>로 변경하고 참조 경로 일괄 정리<span class="log__tag">인프라</span></li>
    <li>표지를 라벨 / 값 2단 그리드로 재구성, 팀명 <code>seuk</code> 반영<span class="log__tag">문서</span></li>
    <li>로컬 미리보기 환경 구축 — Ruby 3.2.3 / Jekyll 3.10.0<span class="log__tag">환경</span></li>
    <li>Tailscale Funnel로 외부 기기 미리보기 경로 확보<span class="log__tag">환경</span></li>
  </ul>

</div>

<div class="log__entry">

  <div class="log__date">
    <span class="log__day">2026. 08. 20.</span>
    <span class="log__week">1주차 &middot; 개발 1일차</span>
  </div>

  <ul>
    <li>프로젝트 착수, 개발 범위 및 목차 구조 확정<span class="log__tag">기획</span></li>
    <li>팀 구성 및 역할 분담 논의<span class="log__tag">기획</span></li>
  </ul>

</div>

<a class="log__back" href="{{ '/' | relative_url }}">&larr; 표지로</a>

</div>
