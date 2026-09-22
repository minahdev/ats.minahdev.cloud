---
layout: default
title: 배포 및 운영
permalink: /deployment/
---

<style>
.dpl { max-width: 64rem; margin: 2.5rem auto 4rem; }

.dpl__head { border-bottom: 2px solid #111827; padding-bottom: 1rem; margin-bottom: 2.5rem; }
.dpl__crumb { margin: 0 0 .5rem; font-size: .82rem; color: #9ca3af; }
.dpl__crumb a { color: #9ca3af; }
.dpl__head h1 { font-size: 1.9rem; margin: 0 0 .5rem; letter-spacing: -.01em; word-break: keep-all; }
.dpl__head p { margin: 0; color: #6b7280; font-size: .9rem; word-break: keep-all; }

.dpl__sec { margin-bottom: 3.25rem; }
.dpl__sec > h2 {
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
.dpl__num { font-variant-numeric: tabular-nums; font-weight: 700; }
.dpl__sub {
  font-size: .93rem;
  color: #111827;
  margin: 2rem 0 .7rem;
  word-break: keep-all;
}
.dpl__note { margin: -.4rem 0 1.2rem; color: #6b7280; font-size: .88rem; line-height: 1.7; word-break: keep-all; }
.dpl__note code { font-size: .82rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }
.dpl__note b { color: #374151; }
.dpl__body { margin: 0 0 1.1rem; color: #374151; font-size: .9rem; line-height: 1.8; word-break: keep-all; }
.dpl__body code { font-size: .82rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

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
.who-b { background: #d1fae5; color: #065f46; }
.who-c { background: #fce7f3; color: #9d174d; }
.who-d { background: #fef3c7; color: #92400e; }
.who-e { background: #e0f2fe; color: #075985; }

/* 표 공통 — schedule.md 와 같은 규격 */
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
.tbl .num { text-align: right; font-variant-numeric: tabular-nums; white-space: nowrap; }
.tbl .nowrap { white-space: nowrap; }

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
.tag--drop { background: #fee2e2; color: #991b1b; }
.tag--free { background: #e0f2fe; color: #075985; }

/* 구성도 */
.arch__scroll { overflow-x: auto; padding-bottom: .4rem; }
.arch {
  min-width: 46rem;
  margin: 0 0 1.1rem;
  padding: 1rem 1.1rem;
  background: #f9fafb;
  border: 1px solid #e5e7eb;
  border-radius: 6px;
  font-family: ui-monospace, SFMono-Regular, Menlo, monospace;
  font-size: .78rem;
  line-height: 1.75;
  color: #374151;
  white-space: pre;
}

/* 파이프라인 단계 */
.pipe { border: 1px solid #e5e7eb; border-radius: 6px; overflow: hidden; margin-bottom: 1.1rem; }
.pipe__step { display: flex; gap: .85rem; padding: .75rem 1rem; border-bottom: 1px solid #f3f4f6; }
.pipe__step:last-child { border-bottom: 0; }
.pipe__n {
  flex: none;
  width: 1.5rem;
  height: 1.5rem;
  border-radius: 50%;
  background: #eff6ff;
  color: #1e40af;
  font-size: .74rem;
  font-weight: 700;
  display: flex;
  align-items: center;
  justify-content: center;
  font-variant-numeric: tabular-nums;
}
.pipe__t { margin: 0; font-size: .87rem; line-height: 1.7; color: #374151; word-break: keep-all; }
.pipe__t b { color: #111827; }
.pipe__t code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }

/* 사고 → 장치 */
.inc { display: grid; grid-template-columns: repeat(auto-fit, minmax(14rem, 1fr)); gap: .75rem; }
.inc__item { border: 1px solid #e5e7eb; border-left: 3px solid #dc2626; border-radius: 6px; padding: .8rem .9rem; }
.inc__item h3 { margin: 0 0 .35rem; font-size: .86rem; color: #111827; word-break: keep-all; line-height: 1.55; }
.inc__item p { margin: 0; font-size: .83rem; color: #6b7280; line-height: 1.7; word-break: keep-all; }
.inc__k { display: block; font-size: .72rem; color: #9ca3af; letter-spacing: .03em; margin-bottom: .25rem; }

/* 강조 박스 */
.box { border: 1px solid #e5e7eb; border-left: 3px solid #2a7ae2; border-radius: 6px; padding: .95rem 1.1rem; margin-bottom: 1.2rem; }
.box--warn { border-left-color: #dc2626; }
.box h3 { margin: 0 0 .45rem; font-size: .95rem; color: #111827; word-break: keep-all; }
.box p { margin: 0 0 .6rem; font-size: .86rem; line-height: 1.75; color: #4b5563; word-break: keep-all; }
.box p:last-child { margin-bottom: 0; }
.box code { font-size: .8rem; background: #f3f4f6; padding: .05rem .3rem; border-radius: 3px; }
.box b { color: #111827; }

.dpl__back { display: inline-block; margin-top: 1rem; font-size: .9rem; }
</style>

<div class="dpl">

<div class="dpl__head">
  <p class="dpl__crumb"><a href="{{ '/toc/' | relative_url }}">목차</a> &rsaquo; 9. 배포 및 운영</p>
  <h1>배포 및 운영</h1>
  <p>main 머지가 곧 프로덕션 배포다 &mdash; 서버가 2분마다 확인해 pull &middot; build &middot; up 한다
     &middot; 인프라 오너 <span class="who who-e">수택 E</span> 진수택
     &middot; 최종 갱신 2026. 09. 22.</p>
</div>

<div class="dpl__sec">

  <h2><span class="dpl__num">1.</span> 배포 구성</h2>
  <p class="dpl__note">
    프론트는 <b>Vercel</b>, 백엔드와 AI 서비스는 <b>AWS EC2 한 대 위의 docker compose</b>다.
    둘 다 트리거는 같다 &mdash; <code>main</code> 머지. 파일은 브라우저가 S3 로 직접 올려
    서버를 거치지 않고, 메일은 API 가 n8n 웹훅으로 넘긴다.
  </p>

  <div class="arch__scroll">
  <div class="arch">브라우저 ── https ──&gt; Vercel (frontend/app · main 머지 시 자동 배포 · seuk.suvisdev.cloud)
 
브라우저/앱 ── https ──&gt; Caddy(443, 인증서 자동) ──&gt; FastAPI  api:8000        ┐
                                                   PostgreSQL 16 + pgvector  ├ EC2 · docker compose
                                                   lie-detection  (/ai/*)    │   (api.seuk.suvisdev.cloud)
                                                   n8n            (/n8n/*)   ┘
 
파일: 브라우저 ── presigned URL ──&gt; S3 (서버 미경유)
메일: api ── 웹훅 ──&gt; n8n ──&gt; SMTP   (실패하면 api 가 5분마다 직접 재발송)</div>
  </div>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>무엇</th><th>주소 &middot; 구성</th><th>비고</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="nowrap"><b>서비스(프론트)</b></td>
        <td><code>https://seuk.suvisdev.cloud</code></td>
        <td>Vercel. 환경변수 <code>VITE_API_BASE</code> 로 API 를 직접 부른다</td>
      </tr>
      <tr>
        <td class="nowrap"><b>API</b></td>
        <td><code>https://api.seuk.suvisdev.cloud</code></td>
        <td>Swagger <code>/docs</code> &mdash; 라우트 107개. HTTPS만, 8000 직접 접근은 막혀 있다</td>
      </tr>
      <tr>
        <td class="nowrap">컨테이너</td>
        <td><code>db</code> <code>api</code> <code>lie-detection</code> <code>n8n</code> <code>caddy</code> &mdash; 5개</td>
        <td>전부 <code>restart: unless-stopped</code> &mdash; 재부팅 자동 복구. DB 이미지는 <code>pgvector/pgvector:pg16</code></td>
      </tr>
      <tr>
        <td class="nowrap">인스턴스</td>
        <td>EC2 서울 &middot; Elastic IP &middot; EBS <b>29 &rarr; 50GB</b></td>
        <td>t3.micro &rarr; t3.small &rarr; t3.medium(4GB, 월 +$17) &rarr; t3.large. 올린 이유는 매번 메모리였다</td>
      </tr>
      <tr>
        <td class="nowrap">파일</td>
        <td>S3 presigned URL 직접 업로드</td>
        <td>버킷 CORS 에 프론트 출처를 넣어야 한다 &mdash; 빠지면 브라우저에서만 조용히 실패한다</td>
      </tr>
      <tr>
        <td class="nowrap">메일</td>
        <td>api &rarr; n8n 웹훅 &rarr; 지메일 SMTP</td>
        <td>n8n 은 같은 EC2 self-host. n8n Cloud 는 쓰지 않는다 &mdash; 지원자 개인정보가 외부 SaaS 를 거친다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <h3 class="dpl__sub">인스턴스를 세 번 올렸고, 이유는 매번 메모리였다</h3>
  <p class="dpl__body">
    t3.small(2GB)에서 t3.medium(4GB)으로 올린 것은 <b>거짓말 탐지 서비스가 분석 1건에 574MiB</b> 를 써서
    api 와 같이 못 돌았기 때문이다(월 +$17). 그 다음 t3.large 까지 간 것은 실시간 면접 STT 였는데,
    <b>원인은 인스턴스 크기가 아니라 코드 기본값 하나였다</b> &mdash; faster-whisper 가 CPU 에서
    <code>float32</code> 로 잡혀 로드에만 3,835MB 를 썼다. <code>int8</code> 을 명시하자 891MB(1/4)로 내려갔고
    전사도 2.3배 빨라졌다. 메모리를 다섯 번 올리고 인스턴스를 옮긴 뒤에야 찾은 값이다.
    디스크는 빌드 캐시와 컨테이너 이미지 때문에 EBS 를 29GB 에서 <b>50GB</b> 로 온라인 확장했다(무중단, 여유 27GB).
    <b>현재 타입은 단정하지 않는다</b> &mdash; 운영 문서에 남은 기록이 <code>t3.medium</code> 과 <code>t3.large</code> 로
    갈려 있어, 확인되는 것은 위의 증설 이력까지다.
  </p>

  <h3 class="dpl__sub">GPU 는 구성도에 없다 &mdash; 켜고 끄는 전제이기 때문이다</h3>
  <p class="dpl__body">
    운영 EC2 에는 GPU 가 없고, <b>상시 GPU 가 필요한 경로도 없다.</b> 거짓말 탐지는 CPU 로 돌고
    (MediaPipe &middot; scikit-learn), 실시간 전사는 <b>ADR-0038 로 기본이 OpenAI API</b> 가 됐다.
    GPU 는 로컬 STT 와 Qwen 어댑터를 실제로 돌려 볼 때만 켠다 &mdash; lie-detection 을
    <code>VIT_DEVICE=cuda</code> 로 옮긴 T4 실측이 <b>STT 275ms/3초 음성 &middot; ViT 75ms/crop</b> 이고,
    CPU 에서 7.5초 걸리던 전사가 <b>약 1초</b>로 줄며 8명 동시 접속에도 대기줄이 생기지 않았다.
    그런데도 상시로 두지 않은 이유는 예산이다(위 표 &mdash; 24시간이면 월 ≈$470).
    <b>그래서 이 장의 구성도에는 GPU 가 없다</b> &mdash; 심사 서빙에 항상 떠 있어야 하는 것만 그렸다.
  </p>

  <h3 class="dpl__sub">인프라 이전 &mdash; 개인 명의에서 역할 기반으로</h3>
  <p class="dpl__body">
    2026-09-02 팀장 이탈 시점에 <b>AWS 루트·IAM·GitHub org·Vercel·도메인·API 키·서버 <code>.env</code> 의 AWS 키가 전부
    한 사람 개인 명의</b>였다. 그가 빠지면 배포·메일·업로드가 멎고 아무도 고칠 수 없는 구조였고, 실제로
    09-02 저녁 팀장 개인 키가 폐기되자 <b>AI 기능이 전면 중단</b>됐다 &mdash; <code>/health</code> 는 200 이고 읽기 API 도 200 인데
    요약 호출만 <b>0초에 422</b> 로 떨어졌다. 0초는 LLM 호출이 시작조차 안 됐다는 뜻이다.
    09-04 에 개인 AWS(서울)로 전체를 이전하고 IAM 을 <code>suvisdev</code>(관리) &middot; <code>arda-viewers</code>(팀 열람) &middot;
    <code>arda-server</code>(서버 키) 세 갈래로 나눴다. <b>키가 새면 서버 유저 하나만 재발급하면 된다.</b>
  </p>

  <h3 class="dpl__sub">AWS 표면적을 8종에서 3종으로</h3>
  <p class="dpl__body">
    예산이 <b>$400 · 2026-10-27 까지</b>라, 그 이후에도 서비스가 이어 돌 수 있어야 했다.
    ADR-0031 로 <b>EC2 &middot; S3 &middot; IAM 세 개만 남기고</b> 나머지는 self-host 대안 뒤로 물렸다.
    폐기가 아니라 <b>스위치</b>로 둔 것이 요점이다 &mdash; 코드에 이미 갈림길이 있어 값 하나로 갈아탄다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>쓰던 것</th><th>대체</th><th>스위치</th><th>상태</th></tr>
    </thead>
    <tbody>
      <tr><td class="nowrap">SES</td><td>n8n + SMTP(지메일 앱 비밀번호)</td><td><code>MAIL_DISPATCH=n8n</code></td><td><span class="tag tag--done">이관 완료</span> 09-08</td></tr>
      <tr><td class="nowrap">SQS + 워커</td><td>(불필요 &mdash; 발송 경로가 n8n 으로 바뀜)</td><td>&mdash;</td><td><span class="tag tag--drop">폐기</span> 09-14 (#213)</td></tr>
      <tr><td class="nowrap">CloudWatch</td><td><code>~/metrics.log</code> 파일 append + <code>~/status.sh</code></td><td><code>push-metrics.sh</code> 재작성</td><td>대안 준비</td></tr>
      <tr><td class="nowrap">SNS 경보</td><td>관측 스크립트가 임계 넘으면 SMTP 발송</td><td>&mdash;</td><td>대안 준비</td></tr>
      <tr><td class="nowrap">S3</td><td>MinIO</td><td><code>S3_ENDPOINT_URL</code></td><td>코드에 이미 있음</td></tr>
      <tr><td class="nowrap">GPU</td><td>g4dn.xlarge 켜고 끄기 &middot; 또는 로컬 GPU PC</td><td><code>GPU_TARGET=aws|local</code></td><td>켜고 끄기 전제 &mdash; 24시간 가동은 월 ≈$470 이라 불가(8시간×20일이면 ≈$105)</td></tr>
    </tbody>
  </table>
  </div>

  <p class="dpl__body">
    <b>앵커 게시만은 이전 대상이 아니다.</b> 서명 개인키가 서버가 아니라 GitHub Actions Secret 에 있어서,
    AWS 를 떠나도 그 경로는 그대로 돈다(2절).
  </p>

  <h3 class="dpl__sub">온프레미스 3대를 구축했고, 심사 직전에 닫았다</h3>
  <p class="dpl__body">
    AWS 예산 만료에 대비해 <b>09-16 ~ 09-18 학원 PC 3대로 온프레미스 스택을 실제로 구축해 운영했다</b> &mdash;
    Cloudflare Tunnel 로 외부 노출, Ollama 로 Qwen 어댑터 3갈래 서빙, S3 자리에는 MinIO.
    읽고 끝낸 검토가 아니라 돌아가는 물건이었다. 그런데 <b>AWS 에서는 나지 않던 오류가 심사 직전에 누적됐다.</b>
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>드러난 것</th><th>내용</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="nowrap">브라우저 &harr; 내부 MinIO 불가</td>
        <td>presign URL 이 <code>minio:9000</code>(컨테이너 내부 호스트)이라 브라우저에서 이름이 안 풀렸다.
            <b>공개 지원폼에서 아무도 이력서를 못 올렸다.</b> 파일 본문을 Postgres 에 저장하고 1회용 티켓 API 로
            스트리밍하는 경로를 따로 만들어 막았다</td>
      </tr>
      <tr>
        <td class="nowrap">로컬 sLLM 다단계 도구 호출</td>
        <td><code>list_postings</code> 로 공고 id 를 확인하지 않고 <code>create_application</code> 을 한 번에 부르며
            <code>posting_id</code> 를 추측했다. 안내를 줘도 반복 &mdash; <b>폐쇄의 결정타</b></td>
      </tr>
      <tr>
        <td class="nowrap">예시 숫자 베끼기</td>
        <td>프롬프트의 출력 예시 70/40/60 을 소형 모델이 그대로 베껴 <b>전 지원자가 64~65점으로 수렴</b>, 변별력 상실.
            Claude 는 베끼지 않아 AWS 에서는 드러나지 않았다</td>
      </tr>
      <tr>
        <td class="nowrap">JSON 깨짐 &middot; 답변 소실</td>
        <td>문자열 안 이스케이프 안 된 따옴표로 요약 파싱 실패(56명 중 2명 점수 NULL) &middot;
            면접 중 컨테이너를 재기동하자 메모리에만 있던 발화가 사라졌다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <div class="box box--warn">
    <h3>결론 &mdash; 심사 서빙은 AWS + Claude 로 확정 (2026-09-18)</h3>
    <p>
      코드 프리즈가 09-20 이었다. 프롬프트와 데이터로 매번 땜질해야 하는 로컬 모델을 그 앞에 두는 것은
      감당할 수 있는 위험이 아니라고 판단해 <b>온프레미스를 닫고 검증된 클라우드 스택(실 S3 · Anthropic Claude)으로
      심사를 확정</b>했다. 온프레 코드 · Ollama 어댑터 · GPU 이미지는 지우지 않고 <b>R&amp;D 자산으로 보존</b>했고,
      구축과 오류와 폐쇄 경위를 종합보고 문서로 남겼다.
    </p>
    <p>
      <b>만들어 봤기 때문에 접을 수 있었다는 것이 이 항목의 값이다.</b> "온프레미스도 됩니다"가 아니라
      "해 봤고, 이 지점에서 안 돼서 접었습니다"가 남았다.
    </p>
  </div>

</div>

<div class="dpl__sec">

  <h2><span class="dpl__num">2.</span> CI/CD 파이프라인</h2>
  <p class="dpl__note">
    CI 와 CD 는 목적이 다르다. <b>CI 는 깨진 것을 보이게 하고, CD 는 초록인 것을 사람 손 없이 운영에 올린다.</b>
    둘을 잇는 규칙이 하나다 &mdash; <b>CI 빨간불이면 머지할 수 없고, 머지되면 2분 안에 배포가 시작된다.</b>
  </p>

  <h3 class="dpl__sub">CI &mdash; 게이트가 아니라 "깨졌다는 사실만 즉시 보이게"</h3>
  <p class="dpl__body">
    도입 계기는 명확하다. <b>2026-09-01 하루에 깨진 main 을 두 번 발견했고 둘 다 우연이었다</b>(<code>d7fdd10</code> &middot; <code>d96749e</code>).
    사람 승인 게이트를 세우는 대신 <b>깨진 사실만 즉시 보이게</b> 하는 쪽을 택했다 &mdash;
    도메인 오너제에서 리뷰 게이트는 곧 병목이기 때문이다. push 와 PR 마다 <b>5개 잡</b>이 돈다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>잡</th><th>무엇을 돌리나</th><th>왜 그렇게 했나</th></tr>
    </thead>
    <tbody>
      <tr>
        <td class="nowrap"><b>백엔드 린트</b></td>
        <td><code>uvx ruff@0.16.7 check --select F</code></td>
        <td>헥사고날 이동 뒤 <b>미정의 이름 2건이 프로덕션 500 까지 갔다</b> &mdash; 그 줄을 타는 테스트가 없어
            pytest 는 초록이었다. F821·F401 만 켠다. 스타일 규칙까지 켜면 기존 파일 수백 줄이 빨개져
            <b>아무도 안 보는 빨간 CI</b> 가 된다. 버전을 못 박은 것은 새 규칙이 생겨 남의 커밋에서 터지는 것을 막기 위해서다</td>
      </tr>
      <tr>
        <td class="nowrap"><b>백엔드 테스트</b></td>
        <td>실제 PostgreSQL + pgvector 서비스에 <code>alembic upgrade head</code> &rarr;
            모델↔이행 결과 비교 &rarr; <code>pytest</code> <b>1,165건</b></td>
        <td>SQLite 목이 아니라 운영과 같은 DB 다. <b>모델↔이행 비교</b>(2026-09-17)는 CI 가 이행 누락을 못 잡던 틈을 막는다 &mdash;
            인덱스 이름까지 비교한다. <code>pytest-timeout</code> 60초는 <b>pytest 가 24분간 조용히 멈춘</b> 사고 뒤에 붙였다 &mdash;
            멈춤을 침묵이 아니라 실패로 만든다</td>
      </tr>
      <tr>
        <td class="nowrap"><b>프론트</b></td>
        <td><code>oxlint</code> + <code>tsc -b</code> + <code>vite build</code> (Node 22)</td>
        <td>빌드까지 돌린다 &mdash; 타입이 맞아도 번들이 깨지는 것은 Vercel 에서야 드러나기 때문이다</td>
      </tr>
      <tr>
        <td class="nowrap"><b>AI 면접 서버</b></td>
        <td><code>pytest</code> 3파일 (Python 3.13)</td>
        <td>실시간 전사 &middot; 판정 중계 &middot; 화자 매칭. <code>ai/</code> 는 백엔드와 런타임이 달라 잡을 나눴다</td>
      </tr>
      <tr>
        <td class="nowrap"><b>앱</b></td>
        <td><code>flutter analyze</code> + <code>flutter test</code> (테스트 파일 30개)</td>
        <td>앱은 배포가 APK 빌드라 운영 반영이 늦다 &mdash; 깨진 것을 머지 시점에 잡아야 한다</td>
      </tr>
    </tbody>
  </table>
  </div>

  <p class="dpl__body">
    같은 브랜치에 연달아 push 하면 <b>앞의 실행을 취소</b>한다(<code>cancel-in-progress</code>) &mdash; 무료 러너 분을 아끼기 위해서다.
    머지 경로는 2026-09-04 에 하나로 좁혔다: <b><code>main</code> 직접 push 와 force push 는 GitHub 브랜치 보호가 차단</b>하고,
    브랜치 &rarr; PR &rarr; <b>CI 초록 확인 &rarr; 자체 머지</b>다. 사람 승인 게이트는 없다.
    <b>CI 빨간불 = 머지 불가가 오너제의 유일한 안전망</b>이므로, 테스트를 주석 처리해 통과시키는 것은 금지돼 있다.
  </p>

  <h3 class="dpl__sub">CD &mdash; main 머지가 곧 프로덕션 배포</h3>
  <p class="dpl__body">
    서버의 systemd 타이머 <code>arda-deploy.timer</code> 가 <b>2분마다</b> <code>origin/main</code> 을 확인하고,
    새 커밋이면 <code>deploy-arda.sh</code> 를 돌린다. <b>빌드 포함 총 5~10분.</b> 로그는 <code>~/deploy.log</code>.
    스크립트 전체가 <code>set -euo pipefail</code> 이라 <b>중간에 실패하면 거기서 멈추고 돌던 컨테이너는 계속 산다.</b>
    "배포해 주세요"라는 요청이 사라진 것이 이 장치의 실제 효과다.
  </p>

  <div class="pipe">
    <div class="pipe__step">
      <span class="pipe__n">1</span>
      <p class="pipe__t"><b>fetch &middot; ff-only merge</b> &mdash; 새 커밋이 없으면 아무것도 하지 않고 끝낸다.</p>
    </div>
    <div class="pipe__step">
      <span class="pipe__n">2</span>
      <p class="pipe__t"><b>선택적 빌드</b> (2026-09-14) &mdash; <code>$LOCAL..$REMOTE</code> diff 로 무엇이 바뀌었는지 판정한다.
        <code>backend/</code> 나 compose 가 바뀌면 <code>api</code>, <code>ai/lie-detection/</code> 이 바뀌면 그 이미지만.
        <b>문서·프론트만 바뀌면 재빌드가 없다.</b> 옛 스크립트는 매번 둘 다 재빌드해
        <b>프론트만 고쳐도 10분이 걸리고 lie-detection 이 torch 200MB 를 다시 받았다.</b></p>
    </div>
    <div class="pipe__step">
      <span class="pipe__n">3</span>
      <p class="pipe__t"><b><code>alembic upgrade head</code></b> &mdash; 기동 <b>전에</b> 돈다. 아래 별도 항목.</p>
    </div>
    <div class="pipe__step">
      <span class="pipe__n">4</span>
      <p class="pipe__t"><b><code>up -d --remove-orphans</code></b> &mdash; <code>--remove-orphans</code> 는 09-14 에 붙였다.
        없으면 compose 에서 지운 서비스가 계속 산다 &mdash; <b>SQS 워커를 폐기한 뒤에도 <code>arda-worker-1</code> 이 남아
        SQS 를 계속 폴링했다.</b></p>
    </div>
    <div class="pipe__step">
      <span class="pipe__n">5</span>
      <p class="pipe__t"><b>헬스 확인 &mdash; 최대 60초 재시도</b>(3초 간격 20회). 10초에 한 번만 보던 때는 api 가 뜨는 중이라
        <b>가짜 WARN</b> 이 기록됐다(2026-09-09).</p>
    </div>
    <div class="pipe__step">
      <span class="pipe__n">6</span>
      <p class="pipe__t"><b>uvicorn 워커 1개 재확인</b> (2026-09-17) &mdash; 세션 방 &middot; 티켓 &middot; 잠금 &middot; STT 모델이
        프로세스 메모리에 있어, 워커가 둘이면 <b>지원자와 담당자가 다른 프로세스에 앉아 서로를 못 본다.</b>
        compose 에 <code>--workers 1</code> 이 있어도 실제 프로세스 수를 한 번 더 센다.</p>
    </div>
    <div class="pipe__step">
      <span class="pipe__n">7</span>
      <p class="pipe__t"><b><code>image prune</code> &middot; <code>builder prune --keep-storage 3g</code></b> &mdash;
        배포마다 청소한다. 이 두 줄이 없던 09-07 이전에는 <b>빌드 캐시가 12GB</b> 쌓여 있었다.</p>
    </div>
  </div>

  <p class="dpl__body">
    <b>빌드와 <code>up</code> 을 분리한 것은 규칙이다.</b> 빌드가 깨져도 돌던 컨테이너가 안 죽는다 &mdash;
    <code>up -d --build</code> 한 번으로 가면 빌드가 깨질 때 서비스가 같이 내려간다.
    디스크 고갈로 api 를 실제로 내려야 했던 배포(다운타임 약 6분)를 겪고 스크립트에 박았다.
    시연 직전에는 <code>sudo systemctl stop arda-deploy.timer</code> 로 배포를 잠시 멈출 수 있다.
    프론트는 별도로 <b>Vercel 이 main 머지 후 1~2분 내 자동 배포</b>하고, 앱은
    <code>flutter build apk --dart-define=API_BASE=&lt;API 주소&gt;</code> 로 굽는다.
  </p>

  <div class="box">
    <h3>alembic 이 CD 에 들어간 과정</h3>
    <p>
      <b>계기는 사고다.</b> 리비전 0009 가 만든 컬럼이 운영 DB 에 없어 <code>/integrity/*</code> 가 500 났다.
      스키마는 <code>create_all</code> 로 만들지만 <b><code>create_all</code> 은 기존 테이블에 컬럼을 못 붙인다</b> &mdash;
      pull 로는 DB 가 따라오지 않는다. 그래서 09-04 에 배포 스크립트에 <code>alembic upgrade head</code> 단계를 넣었다.
      현재 리비전은 <b>26개</b>이고, 스키마를 바꾸면 코드 &middot; ERD 문서 &middot; 리비전이 <b>같은 커밋</b>이어야 한다.
    </p>
    <p>
      처음에는 호스트에 코드를 마운트해 alembic 을 돌렸다. 09-07 에 <b>이미지가 alembic 을 직접 가지게</b> 바꿔
      마운트를 없앴다(PR #20) &mdash; 서버 호스트에 저장소 사본이 있어야 이행이 되는 구조를 끊은 것이다.
      이행이 실패하면 <code>set -euo pipefail</code> 로 배포가 거기서 멈춘다. <b>깨진 스키마 위에 새 코드가 올라가지 않는다.</b>
    </p>
    <p>
      그 전사(前史)가 <b>손 SQL 시대</b>였고 2026-09-01 에 끝났다. 운영 DB 를 alembic 관리 아래로 넣을 때
      인계받은 안내는 "운영은 이행을 이미 마쳤으니 <code>stamp</code> 만 하면 된다"였는데,
      <b>실측해 보니 <code>ai_summary_model</code> 컬럼 폭이 50 이었다.</b> 그대로 찍었으면 alembic 이
      "0002 를 적용했다"고 기록하고 <b>다시는 안 고쳤다.</b> 컬럼을 200 으로 넓힌 뒤에 stamp 했고,
      실제로 저장된 태그는 91자였다. <b><code>stamp</code> 는 선언이지 확인이 아니다</b> &mdash; 이 순서가 뒤바뀌었으면
      그 차이가 영구히 숨었다.
    </p>
  </div>

  <div class="box">
    <h3>서명 개인키를 서버 밖(GitHub Actions)으로 뺀 결정</h3>
    <p>
      제출물 무결성 앵커(ADR-0028)는 이력서·자소서의 SHA-256 해시 사슬 머리를 <b>매일 09:10 공개 체인에 게시</b>한다.
      게시에는 서명이 필요하고, 서명에는 개인키가 필요하다. <b>그 키를 서버 <code>.env</code> 에 두지 않기로 했다</b>(PR #13 &middot; #15) &mdash;
      서버가 털리면 공격자가 <b>자기가 고친 내용으로 새 앵커를 찍을 수 있기</b> 때문이다. 키를 GitHub Actions Secret 에 두고
      게시를 Actions 가 대신하면, 서버는 <b>해시를 만들 뿐 서명할 수 없다.</b> 시간 증명은 OpenTimestamps 를 병행한다.
    </p>
    <p>
      부수 효과가 하나 더 있다. AWS 를 종료해도 <b>앵커 경로는 이전 대상이 아니다</b> &mdash; 서버 밖에 있으니 옮길 것이 없다.
    </p>
    <p>
      운영 중 두 번 손을 봤다. <b>앵커 cron 이 12시간 만료 토큰으로 죽어 이틀 동안 아무도 몰랐다</b>(09-05~06) &mdash;
      매 실행마다 새로 로그인하게 고치고 <b>실패하면 GitHub 이슈를 열게</b> 했다(PR #21 &middot; #25 &middot; #31).
      또 <code>CHAIN_NETWORK</code> 이름표와 실제 RPC 체인 식별자가 어긋나면 전송 전에 멈추게 해 잘못된 체인 오염을 막았다.
      체인 자체는 <b>Polygon Amoy &rarr; Ethereum Sepolia</b> 로 옮겼다(PR #29) &mdash; Amoy 무료 faucet 6곳이 전부 막혀
      가스를 구할 수 없었기 때문이다.
    </p>
  </div>

</div>

<div class="dpl__sec">

  <h2><span class="dpl__num">3.</span> 모니터링 및 로그 관리</h2>
  <p class="dpl__note">
    설계가 아니라 사고에서 나왔다. <b>앵커 cron 이 이틀 죽었는데 아무도 못 봤고</b>(09-05~06),
    "주 1회 <code>~/status.sh</code> 를 본다"는 습관은 까먹는다. 그래서 <b>사람이 안 봐도 되게</b> 만들었다 &mdash;
    임계를 넘으면 메일이 온다. 전체 비용은 <b>0원</b>이다(무료 구간 안).
  </p>

  <h3 class="dpl__sub">안에서 보는 눈 &mdash; CloudWatch + SNS</h3>
  <p class="dpl__body">
    서버 cron 이 <b>10분마다</b> <code>push-metrics.sh</code> 로 숫자를 CloudWatch 에 보낸다(네임스페이스 <code>Arda</code>,
    차원 <code>Host=arda-api</code>). <b>관측 에이전트를 따로 설치하지 않았다</b> &mdash; 이미 있는 aws-cli 만 쓴다.
    알람은 <b>6개</b>이고 전부 SNS 주제 <code>arda-alerts</code> 로 메일을 쏜다.
    알람 정의는 <b>CloudFormation 템플릿 파일 하나</b>(<code>infra/cloudwatch-alarms.yml</code>)다 &mdash;
    콘솔 클릭 30번 대신 파일 업로드 한 번이고, 지우려면 스택을 지운다.
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>지표</th><th>뜻</th><th>알람 조건</th><th>누락 데이터</th></tr>
    </thead>
    <tbody>
      <tr><td class="nowrap"><code>DiskUsedPercent</code></td><td><code>/</code> 사용률</td><td class="nowrap"><b>≥ 85</b> (1회)</td><td>무시</td></tr>
      <tr><td class="nowrap"><code>BackupAgeHours</code></td><td>마지막 백업 파일 나이</td><td class="nowrap"><b>≥ 30시간</b> (1회)</td><td>무시 &mdash; 하루 1회인데 빠졌다는 뜻</td></tr>
      <tr><td class="nowrap"><code>ApiHealthy</code></td><td><code>localhost:8000/health</code> 가 ok 면 1</td><td class="nowrap"><b>&lt; 1</b> (2회 연속 = 20분)</td><td><b>경보로 취급</b> &mdash; 인스턴스가 통째로 죽어 숫자가 안 와도 울린다</td></tr>
      <tr><td class="nowrap"><code>MemUsedPercent</code></td><td>(total−available)/total</td><td class="nowrap"><b>≥ 90</b> (2회)</td><td>무시 &mdash; 거짓말 탐지가 같은 서버에 있다</td></tr>
      <tr><td class="nowrap"><code>N8nHealthy</code></td><td>n8n <code>/healthz</code> 가 200 이면 1</td><td class="nowrap"><b>&lt; 1</b> (2회 연속 = 20분)</td><td>무시 &mdash; 인스턴스가 통째로 죽은 것은 <code>ApiHealthy</code> 가 울린다</td></tr>
      <tr><td class="nowrap"><code>StatusCheckFailed_System</code></td><td>EC2 시스템 상태 검사 (AWS 기본 지표)</td><td class="nowrap"><b>≥ 1</b> (2분 연속)</td><td><b>AWS 가 인스턴스를 자동 복구</b>한다 &mdash; 같은 IP·디스크 유지</td></tr>
    </tbody>
  </table>
  </div>

  <p class="dpl__body">
    비용이 0인 근거는 <b>CloudWatch 상시 무료 구간</b>(사용자 지정 지표 10개 &middot; 알람 10개 &middot; API 100만 건/월)과
    <b>SNS 메일 월 1,000통 무료</b> 안에 전부 들어가기 때문이다.
    <span class="tag tag--free">비용 0</span>
  </p>

  <h3 class="dpl__sub">밖에서 보는 눈 &mdash; GitHub Actions 헬스체크</h3>
  <p class="dpl__body">
    서버 안에서만 보면 <b>서버는 멀쩡한데 밖에서 안 닿는 경우</b>를 못 잡는다.
    그래서 GitHub 러너가 <b>15분마다 공개 주소 두 개</b>(<code>api…/health</code> &middot; 프론트)를 밖에서 찌른다.
    <b>30초 간격으로 두 번 실패해야 알린다</b> &mdash; 한 번 삐끗한 것으로 알리지 않기 위해서다.
    실패하면 이슈를 열거나 열린 이슈에 코멘트하고, <b>복구되면 코멘트를 달고 자동으로 닫는다.</b>
  </p>
  <div class="box">
    <h3>둘을 조합해서 읽는 법</h3>
    <p>
      <b>둘 다 울리면 서버</b>, <b>밖에서만 울리면 DNS · TLS · Caddy · 보안그룹</b>이다.
      경보 두 벌을 따로 둔 이유가 이 한 줄이다 &mdash; 울린 조합이 곧 어디를 볼지를 알려 준다.
    </p>
  </div>

  <p class="dpl__body">
    자동 경보와 별개로 사람이 보는 계기판도 있다. <code>~/status.sh</code> 는
    <b>디스크 &middot; 컨테이너 &middot; 마지막 배포 &middot; 마지막 백업 &middot; 헬스 응답</b>을 한 화면에 낸다.
    읽기 전용이고, 주 1회 눈으로 훑는 용도다.
  </p>

  <h3 class="dpl__sub">로그 관리 &mdash; 디스크가 차면 배포가 멈춘다</h3>
  <p class="dpl__body">
    로그 관리가 운영 과제가 된 것은 <b>29GB 디스크에서 로그 하나가 수 GB 로 부푼 사고</b> 때문이다.
    compose 에 로그 드라이버 옵션을 걸어 <b>서비스당 20MB × 3개</b> 로 상한을 뒀다.
    운영 로그는 목적별로 나뉜다 &mdash; 배포 <code>~/deploy.log</code> &middot; 백업 <code>~/backup.log</code> &middot;
    지표 <code>~/metrics.log</code>(10분마다 <code>disk=..% backup_age=..h api=1</code> 이 찍힌다).
  </p>
  <p class="dpl__body">
    가장 컸던 디스크 사고는 로그가 아니라 <b>컨테이너 쓰기 레이어</b>였다. 재배포 빌드가
    <code>No space left on device</code> 로 죽었는데(디스크 97%, 590MB 남음), 원인은
    <b>컨테이너가 뜰 때마다 venv 를 쓰기 레이어에 다시 설치하고 있던 것</b>이었다. 이미지는 382MB 인데
    컨테이너 둘이 10.8GB 를 먹고 있었고, 게다가 런타임에 받은 것은 CPU 가 아니라 <b>CUDA torch</b> 였다.
    <code>CMD</code> 를 <code>/app/.venv/bin/…</code> 직접 호출로 바꾸자 &mdash; 기동이 곧 실행이라 재설치가 일어나지 않는다:
  </p>

  <div class="tbl__scroll">
  <table class="tbl">
    <thead>
      <tr><th>항목</th><th class="num">전</th><th class="num">후</th></tr>
    </thead>
    <tbody>
      <tr><td>컨테이너 쓰기 레이어</td><td class="num">api 5.62GB · worker 5.18GB</td><td class="num"><b>각 4.1kB</b></td></tr>
      <tr><td>이미지</td><td class="num">382MB (venv 없음)</td><td class="num">1.42GB (CPU torch 포함)</td></tr>
      <tr><td>디스크 사용률</td><td class="num">97%</td><td class="num"><b>48%</b></td></tr>
      <tr><td>기동 &rarr; 서비스</td><td class="num">약 2분</td><td class="num"><b>15초</b></td></tr>
    </tbody>
  </table>
  </div>

  <p class="dpl__body">
    <b>"배포 직후 502 가 계속되면 기다릴 게 아니라 로그를 본다"</b> 가 이 수치에서 나온 규칙이다 &mdash;
    2분을 기다리는 것이 정상이던 시절이 끝났기 때문이다.
  </p>

  <h3 class="dpl__sub">백업 &mdash; 서버가 털려도 백업은 못 지우게</h3>
  <p class="dpl__body">
    EC2 한 대, EBS 볼륨 하나다. 인스턴스 사고 한 번이면 <b>지원자 개인정보와 무결성 원장이 같이 사라지고</b>,
    앵커 증명은 잃으면 다시 만들 수 없다. 그래서 매일 <b>04:00 KST</b> 에 <code>pg_dump | gzip</code> 으로 뜨고
    <code>gzip -t</code> 로 검증한 뒤 전용 S3 버킷에 올린다. 로컬에는 최근 3개만 두고,
    <b>S3 수명주기로 30일 뒤 자동 삭제</b>해 스토리지 비용에도 상한을 뒀다. n8n 볼륨도 같은 cron 이 함께 올린다.
  </p>
  <div class="box">
    <h3>권한을 쓰기 전용으로 좁혔다</h3>
    <p>
      서버 IAM 유저 <code>arda-server</code> 는 백업 버킷에 <b><code>PutObject</code> 하나만</b> 있다 &mdash; 읽기도 삭제도 없다.
      <b>서버가 털려도 백업을 지우거나 내려받지 못한다.</b> 백업은 사고를 막는 장치인데,
      사고를 낸 쪽이 백업까지 닿을 수 있으면 장치가 아니다. 버킷은 퍼블릭 차단 · SSE-S3 암호화이고
      <b>복원은 관리자만</b> 한다. 복원할 때도 기존 DB 를 덮지 않고 <code>arda_restore</code> 라는 새 DB 에 넣어
      <code>alembic current</code> 로 리비전을 확인한 뒤에 교체한다.
    </p>
    <p>
      <b>다만 복원 리허설은 아직 하지 않았다.</b> 절차는 위처럼 문서에 적혀 있지만 실제로 복원해 본 기록이 없고,
      W4 중간 점검 항목으로 남아 있다. <b>복원해 본 적 없는 백업은 아직 백업이 아니다</b> &mdash;
      이 장에서 "했다"고 말할 수 없는 자리다.
    </p>
  </div>

  <h3 class="dpl__sub">사고가 남긴 장치</h3>
  <p class="dpl__note">
    아래는 전부 <b>먼저 터진 뒤에 생긴 것</b>이다. 설계 단계에서 예상해 넣은 것이 아니라,
    한 번 당하고 규칙으로 승격시킨 것들이다.
  </p>

  <div class="inc">

    <div class="inc__item">
      <span class="inc__k">사고</span>
      <h3>깨진 main 을 하루 두 번, 둘 다 우연히 발견</h3>
      <p><b>장치</b> &mdash; CI 5개 잡. 이후 브랜치 &rarr; PR &rarr; 자체 머지로 main 에 닿는 경로를 하나로.</p>
    </div>

    <div class="inc__item">
      <span class="inc__k">사고</span>
      <h3>디스크 고갈로 배포가 죽음</h3>
      <p><b>장치</b> &mdash; 컨테이너 로그 상한 20MB×3 · 배포마다 이미지·캐시 prune · EBS 29→50GB. 재발 0.</p>
    </div>

    <div class="inc__item">
      <span class="inc__k">사고</span>
      <h3>pytest 가 24분간 조용히 멈춤</h3>
      <p><b>장치</b> &mdash; <code>pytest-timeout</code> 60초. 멈춤을 침묵이 아니라 실패로 만든다.</p>
    </div>

    <div class="inc__item">
      <span class="inc__k">사고</span>
      <h3>미정의 이름 2건이 프로덕션 500</h3>
      <p><b>장치</b> &mdash; CI <code>ruff --select F</code>. pytest 가 못 잡던 부류를 1초에 잡는다.</p>
    </div>

    <div class="inc__item">
      <span class="inc__k">사고</span>
      <h3>앵커 cron 이 이틀 죽었는데 아무도 모름</h3>
      <p><b>장치</b> &mdash; CloudWatch 경보 + 실패 시 GitHub 이슈 자동 개폐. 사람 습관에 기대지 않는다.</p>
    </div>

    <div class="inc__item">
      <span class="inc__k">사고</span>
      <h3>n8n 이 웹훅만 받고 죽어 메일이 <code>queued</code> 로 잔류</h3>
      <p><b>장치</b> &mdash; API 가 5분마다 밀린 메일을 SMTP 로 재발송(최대 3회, 초과는 <code>failed</code> 로 접어 사람이 확인).</p>
    </div>

    <div class="inc__item">
      <span class="inc__k">사고</span>
      <h3><code>.env</code> 를 고쳤는데 반영이 안 됨</h3>
      <p><b>장치</b> &mdash; <code>docker compose restart</code> 는 <code>env_file</code> 을 다시 읽지 않는다.
         <code>up -d --force-recreate</code> 규칙화.</p>
    </div>

    <div class="inc__item">
      <span class="inc__k">사고</span>
      <h3>compose 를 <code>infra/</code> 로 옮기자 컨테이너·볼륨이 한 벌 더 생김</h3>
      <p><b>장치</b> &mdash; compose 는 프로젝트 이름이 없으면 폴더명을 쓴다. <code>name: arda</code> 를 박았다.</p>
    </div>

    <div class="inc__item">
      <span class="inc__k">사고</span>
      <h3>브라우저에서만 S3 업로드가 조용히 실패</h3>
      <p><b>장치</b> &mdash; 버킷 CORS. CORS 는 브라우저만 검사해 서버 간 PUT 은 통과한다 &mdash;
         "프론트 주소가 늘면 여기에도"를 문서 규칙으로.</p>
    </div>

  </div>

</div>

<a class="dpl__back" href="{{ '/toc/' | relative_url }}">&larr; 목차로</a>

</div>
