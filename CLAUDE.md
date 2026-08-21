# demo.minahdev.cloud

Jekyll + minima 테마 정적 사이트. GitHub Pages가 빌드·서빙한다.

- 리포: `minahdev/demo.minahdev.cloud` (public)
- **배포된 사이트**: https://minahdev.github.io/demo.minahdev.cloud/ (항상 접속 가능)
- 배포 방식: GitHub Pages **legacy 빌드** (Deploy from a branch → `main`, 루트 `/`)
- `main`에 push하면 자동으로 다시 빌드된다. CI 워크플로 파일은 없다.

---

## 핵심 원칙

**사이트 자체는 로컬 Ruby 없이도 만들고 배포할 수 있다.**

마크다운 → HTML 변환은 GitHub이 자기 서버에서 한다. 글을 쓰고 페이지를 만들고
설정을 바꾸는 일은 전부 텍스트 편집이다. 실제로 이 사이트의 초기 구축과 첫 배포는
로컬에 Ruby가 없는 상태에서 이뤄졌다.

로컬 Ruby/Jekyll은 **미리보기 전용**이다. 지금은 설치돼 있다(아래 참조).

### 하지 말 것

- **rbenv로 Ruby를 소스 빌드하지 말 것.** 이미 apt `ruby-full`(3.2.3)로 설치돼 있고
  잘 동작한다. 수 분간 컴파일할 이유가 없다.
- **systemd 서비스로 jekyll serve를 등록하지 말 것.** WSL은 Windows 부팅 시
  자동 시작되지 않아 상시 구동에 부적합하고, 실제 배포는 GitHub Pages가 한다.
- **다른 프로젝트의 계획서를 그대로 따르지 말 것.** 헤드리스 홈서버(Odyssey),
  `fin.ragtaylor.com`, dreamscape 네트워크를 전제로 쓰인 문서가 돌아다니는데
  이 프로젝트의 환경과 다르다.

---

## 환경

- 작업 셸: WSL2 Ubuntu (`ddu@DESKTOP-M1E9ACP`), systemd 활성화됨
- 리포 경로: `/home/ddu/projects/demo-minahdev/demo.minahdev.cloud`
- Ruby 3.2.3 (apt `ruby-full`), bundler 4.0.19 (`gem install --user-install`)
  - user gem 경로가 `~/.bashrc`의 PATH에 등록돼 있다
- Jekyll 3.10.0 — `github-pages` 232 gem 경유. GitHub Pages 빌더와 같은 버전이다
  - gem은 `vendor/bundle`에 설치됨 (`bundle config set --local path vendor/bundle`)
- `gh` CLI: `minahdev` 계정 인증됨 → Pages 설정·빌드 상태 조회 가능
- git push: 자격증명 설정돼 있어 프롬프트 없이 성공
- **sudo는 비밀번호를 요구한다.** 에이전트가 대신 실행할 수 없으므로,
  apt 설치 등이 필요하면 사용자에게 명령 한 줄을 주고 직접 실행하도록 요청할 것

### Windows에서 WSL 명령을 실행할 때 (Claude Code가 Git Bash에서 도는 경우)

```bash
MSYS_NO_PATHCONV=1 wsl -d Ubuntu -- bash /home/ddu/script.sh
```

- `MSYS_NO_PATHCONV=1` 없이 `/home/ddu/...` 경로를 넘기면 Git Bash가
  `C:/Program Files/Git/home/ddu/...`로 바꿔버려 "No such file or directory"가 난다
- **`bash -lc '...'` 문자열 안에 리다이렉트(`2>/dev/null`, `>`)나 복잡한 제어문을
  넣지 말 것.** 인자 전달 과정에서 깨져 syntax error가 나거나 출력이 사라진다.
  조금이라도 복잡하면 **스크립트 파일로 써서 실행**할 것 (Write 도구 → `wsl bash 파일`)
- 파일 읽기/쓰기는 UNC 경로로 Read/Write 도구를 쓰는 게 안전하다:
  `\\wsl.localhost\Ubuntu\home\ddu\projects\demo-minahdev\demo.minahdev.cloud\...`

---

## 파일 구조

```
_config.yml                        사이트 설정
Gemfile                            github-pages gem
index.md                           홈 — layout: home (글 목록 자동 생성)
about.md                           /about/ 페이지
_posts/YYYY-MM-DD-slug.md          글
.gitignore                         _site/, vendor/, Gemfile.lock 등 제외
```

`_site/`, `vendor/`, `Gemfile.lock`은 커밋하지 않는다. legacy Pages 빌드는 GitHub이
고정한 gem 세트를 쓰므로 로컬 lock 파일은 배포에 영향이 없다.

---

## 글 쓰는 규칙

파일명은 반드시 `_posts/YYYY-MM-DD-slug.md` 형식이다. 어긋나면 **조용히 무시되어**
빌드는 성공하는데 글만 안 나타난다.

```markdown
---
layout: post
title: "글 제목"
date: 2026-08-21 10:00:00 +0900
categories: jekyll
---

본문.
```

- **날짜는 작성 시점의 실제 날짜를 쓸 것.** 기존 글을 복사해 날짜를 그대로 두지 말 것
- **미래 날짜 금지.** Jekyll은 기본 설정에서 미래 글을 빌드에서 제외한다.
  글이 안 보이면 이것부터 확인할 것
- `title`에 콜론(`:`)이 들어가면 반드시 따옴표로 감쌀 것 (YAML 파싱 에러)
- 타임존은 `+0900`으로 통일
- URL은 `categories`에 따라 결정된다:
  `categories: jekyll` → `/demo.minahdev.cloud/jekyll/2026/08/21/slug.html`
  발행된 글의 카테고리를 바꾸면 URL이 깨지므로 함부로 바꾸지 말 것

## 페이지 만드는 규칙

리포 루트에 `.md` 파일을 만들고 front matter에 `permalink`를 명시한다.

```markdown
---
layout: page
title: 페이지 제목
permalink: /경로/
---
```

- `permalink`는 앞뒤 슬래시를 모두 붙일 것 (`/about/`)
- `permalink`에 `baseurl`을 직접 쓰지 말 것 — Jekyll이 알아서 붙인다

## 링크와 이미지 규칙

**절대경로를 그대로 쓰면 안 된다.** 배포본은 `baseurl`이 붙은 프로젝트 페이지라
`/assets/img.png`처럼 쓰면 404가 난다. 반드시 필터를 쓸 것:

```liquid
{{ '/assets/img.png' | relative_url }}
{{ '/about/' | relative_url }}
```

같은 이유로 `<img src="/assets/...">` 같은 생 HTML 절대경로도 금지.
로컬 미리보기는 `--baseurl ""`로 돌리므로 절대경로가 **로컬에서만 우연히 동작**할 수
있다. 배포 후 실제 URL로 확인하는 이유가 이것이다.

---

## `_config.yml` 주의사항

`baseurl`과 도메인은 한 몸이다. 지금은 프로젝트 페이지로 서빙되므로:

```yaml
baseurl: "/demo.minahdev.cloud"
url: "https://minahdev.github.io"
```

**커스텀 도메인 `demo.minahdev.cloud`를 붙이게 되면 반드시 함께 바꿀 것:**

```yaml
baseurl: ""
url: "https://demo.minahdev.cloud"
```

둘 중 하나만 바꾸면 CSS와 모든 내부 링크가 깨진다.

- 현재 `demo.minahdev.cloud`는 **DNS 레코드가 없다.** DNS가 GitHub Pages를 가리키기
  전에 `CNAME` 파일을 추가하면 사이트가 접속 불가가 되므로, DNS 확인 후에 추가할 것
- `_config.yml`을 고쳐도 `jekyll serve`는 자동 반영하지 않는다. 서버를 재시작할 것
- **플러그인은 GitHub Pages 화이트리스트에 있는 것만 동작한다.** legacy 빌드는
  임의의 gem을 무시한다. 화이트리스트 밖 플러그인이 필요하면 GitHub Actions 배포로
  전환해야 하고, 그건 별도 결정 사항이다

---

## 작업 절차

1. 파일을 수정한다
2. 커밋하고 `main`에 push한다
3. **배포 결과를 실제로 확인한다** — push 성공은 사이트가 떴다는 뜻이 아니다

```bash
gh api repos/minahdev/demo.minahdev.cloud/pages/builds/latest --jq '.status, .error.message'
curl -sS -o /dev/null -w '%{http_code}\n' https://minahdev.github.io/demo.minahdev.cloud/
```

`status`가 `built`이고 HTTP 200이어야 완료다. `errored`면 `.error.message`에 원인이 있다.
새 글·새 페이지를 추가했으면 **해당 URL까지** 200인지 확인할 것 — 빌드는 성공했는데
파일명 규칙 위반으로 글만 누락되는 경우가 흔하다.

---

## 로컬 미리보기

```bash
cd ~/projects/demo-minahdev/demo.minahdev.cloud
bundle exec jekyll serve --host 0.0.0.0 --port 4000 --baseurl ""
```

- `--baseurl ""`는 **미리보기 전용**이다. 루트(`localhost:4000`)에서 바로 뜨게 해
  주소를 짧게 만들기 위함이고, `_config.yml`은 건드리지 않는다
- Windows 브라우저에서 `http://localhost:4000/` 로 접속된다. WSL2가 localhost를
  자동 연결하므로 포트포워딩이나 방화벽 설정은 필요 없다
- 백그라운드로 띄웠으면 `pkill -f 'jekyll serve'`로 종료
- 로그: `/tmp/jekyll.log`

---

## Tailscale — 폰/외부 기기 미리보기

**사이트를 남에게 보여주는 용도가 아니다.** 배포된 사이트는 이미 공개 URL이 있고
PC를 꺼도 접속되므로, 공유 목적이면 GitHub Pages 주소를 쓰는 게 낫다.
Tailscale은 **아직 push하지 않은 작업 중인 미리보기**를 다른 기기에서 볼 때만 쓴다.

### 현재 구성 (설정 완료됨)

- WSL에 Tailscale 설치됨, `tailscaled` systemd 서비스로 상시 실행
- 노드: `desktop-m1e9acp` / IP `100.66.220.47` / 계정 `minmom7898@`
- DNS 이름: `desktop-m1e9acp.tail103416.ts.net`
- `sudo tailscale set --operator=ddu` 적용됨 → **funnel/serve 조작에 sudo 불필요**
- Funnel 활성화됨 (관리 콘솔 승인 완료)

### Funnel — 폰에 앱 없이 보는 방법 (권장)

```bash
tailscale funnel --bg 4000          # 켜기
tailscale funnel status             # 상태
tailscale funnel --https=443 off    # 끄기
```

공개 주소: **https://desktop-m1e9acp.tail103416.ts.net/**

- 폰에 Tailscale 앱·로그인 **불필요**. 링크만 열면 된다
- ⚠️ **인터넷에 공개된다.** 링크를 아는 사람은 누구나 접속 가능하고,
  켜두면 몇 분 내로 취약점 스캐너 봇이 붙는다(`/login.action`,
  `/___proxy_subdomain_cpanel` 등이 `/tmp/jekyll.log`에 찍힌다).
  정적 사이트라 실질 위험은 낮지만, **미리보기가 끝나면 끌 것**
- Funnel은 `127.0.0.1:4000`으로 프록시한다. jekyll serve가 떠 있어야 동작한다

### tailnet 직접 접속 (앱 필요)

`http://100.66.220.47:4000/` — 단, 보려는 기기에도 Tailscale을 설치하고
**같은 계정(`minmom7898@`)으로 로그인**해야 한다. `100.x` 주소는 tailnet 안에서만
존재하므로 앱이 없으면 "사이트에 연결할 수 없음"이 뜬다(정상 동작).

기기가 들어왔는지는 `tailscale status`로 확인한다. 목록에 한 줄만 있으면 이 PC뿐이다.

### 증상 구분

| 폰 화면 | 원인 |
|---|---|
| "사이트에 연결할 수 없음" | tailnet 밖에 있음. 주소 자체를 못 찾는 상태 |
| 404 페이지 | 연결은 됨. 경로가 틀렸거나 서버의 baseurl 설정 문제 |

---

## 진행 상황 (최종 갱신: 2026-08-21)

**완료**

- Jekyll 사이트 스캐폴드 및 GitHub Pages 배포 — 빌드 성공, 홈·`/about/`·글·CSS·feed 모두 200
- 프로젝트 페이지 경로에 맞춰 `baseurl` 설정
- 로컬 Ruby 3.2.3 + Jekyll 3.10.0 환경 구축, `bundle install` 완료
- Tailscale 설치·로그인, operator 등록, Funnel 활성화 및 접속 검증 완료

**미완 / 결정 대기**

- **커스텀 도메인 `demo.minahdev.cloud`** — DNS 미설정. DNS를 걸면
  `CNAME` 파일 추가 + `baseurl`/`url` 변경을 함께 해야 한다
- **콘텐츠** — 예시 글 1개뿐. 실제 글은 아직 없다
- **Funnel** — 현재 켜져 있음. 미리보기가 끝났으면 끌 것
