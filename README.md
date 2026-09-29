# ats.minahdev.cloud

**Arda (Eval-ATS) 개발 보고서** — Jekyll + minima 기반 정적 사이트. GitHub Pages 가 빌드·서빙한다.

- 배포: https://ats.minahdev.cloud
- 프로젝트 저장소: https://github.com/Seuk-Team/Arda
- 서비스: https://seuk.suvisdev.cloud · API: https://api.seuk.suvisdev.cloud/docs

보고서 본문은 루트의 `.md` 페이지들이다(`_posts/` 가 아니다). 각 페이지는 front matter 에
`permalink` 을 지정하고, 목차(`toc.md`)에서 링크한다. 구조·작업 규칙은 `CLAUDE.md` 참조.

로컬 미리보기:

```bash
bundle exec jekyll serve
```
