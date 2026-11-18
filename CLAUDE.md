# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 개요

여러모로 합창단(Yeoleomolo Chorus)의 정적 GitHub Pages 사이트로, https://yeoleomolo.github.io 에서 서비스된다. 빌드 시스템, 패키지 매니저, 린터, 테스트가 없다. HTML/CSS/JS를 직접 수정하고, 브라우저로 파일을 열거나 `python3 -m http.server`로 미리 본다. `main`에 푸시하면 배포된다.

## 구조

대부분의 페이지는 공통 레이아웃이나 템플릿 없이 인라인 `<style>`(과 인라인 스크립트)을 가진 **독립형 HTML 파일**이다. CSS를 고쳐도 다른 페이지에 반영되지 않는다.

- `index.html` — 현재 임시 랜딩 페이지("Loading.. / under destruction"). `assets/icon/*.png` 아이콘이 떠다니며, CSS/JS는 인라인이다.
- `telgrm/notice.html` — 제3회 정기공연(2027-02-24) 안내 페이지. 텔레그램/카카오톡 링크 미리보기를 위한 OG/Twitter 메타 태그와 `og-notice.png`가 있다(`noindex`). 메타 태그의 절대 URL이 `yeoleomolo.github.io/telgrm/...`을 가리키므로 파일 이름을 바꾸면 함께 수정해야 한다. 최근 커밋은 대부분 이 페이지의 연습 자료 링크/문구 수정이다.
- `2026/416/index.html` — 2026-04-16 공연 안내 페이지(og:image용 `cover.jpg`를 상대 경로로 참조).
- `2025/invite.01.html` — 2025년 초대장 페이지(이미지는 `assets/img/`).
- `book/TheGobalForest/` — 책 관련 독립 페이지들(디렉터리 이름의 철자에 주의).
- `intro.html`, `css/styles.css`, `css/Defaults.css`, `js/scripts.js` — Start Bootstrap "Stylish Portfolio" 테마의 잔재. `scripts.js`는 현재 `index.html`에 없는 Bootstrap 마크업(`.menu-toggle`, `#sidebar-wrapper`)을 전제로 한다.
- `test.html`, `test2.html`, `index.test.0812.html` — 실험/초안 파일. `index.test.0812.html`은 gitignore 대상이다.

## 규칙

- 콘텐츠는 한국어(`lang="ko"`)이며, 폰트는 Google Fonts 또는 시스템 한글 폰트 스택을 사용한다.
- 공용 이미지는 `assets/img`, `assets/icon`에 두고, 페이지 전용 이미지는 해당 페이지 옆에 둔다.

## 프로젝트 규칙

1. 모든 대화, 코드 주석, git commit 메시지는 한국어로 작성한다. 커밋 말머리는 `기능` / `수정` / `디자인` / `문서` 중에서 고른다. (예: `수정: 공지 페이지 링크 오류 정정`)
2. 지시하지 않은 기존 HTML/CSS/JS 코드를 임의로 삭제하거나 파일 전체를 재포맷하지 않는다.
3. 답변은 서론 없이 핵심만 간결하게 쓴다.
4. `git push` 전에 변경된 파일 내역을 먼저 요약해서 알린다.
