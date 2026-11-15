# 계정 로그인 상태

현재 공개 게임은 게스트로 플레이할 수 있다. 구글·애플·네이버 개발자 앱과 인증 서버가 아직 연결되지 않았으므로 소셜 로그인 버튼은 비활성화되어 있다. `스킵`이나 `스킵하고 플레이`로 기존 게임에 바로 입장한다. 비밀번호를 받거나 브라우저 저장값만으로 로그인 성공을 표시하지 않는다.

## 실제 연동에 필요한 것

1. 인증 서버를 실행할 HTTPS 주소와 영속 데이터베이스
2. 사용할 제공자별 개발자 앱과 허용된 콜백 주소
3. 서버에만 보관하는 인증 비밀키

공개 GitHub Pages와 게임 HTML에 비밀키를 넣으면 안 된다. 게임 기록은 현재 브라우저 저장 방식이며, 계정 동기화 기능으로 표시하지 않는다.

## 확인한 오픈소스

[Auth.js](https://authjs.dev/getting-started/authentication/oauth)는 Google, Apple, Naver 공급자를 지원한다. 별도 인증 서버를 연결할 때 사용할 수 있다. 현재 게임에는 인증 서버나 가짜 인증 대체 코드를 포함하지 않는다.

- [Google 연동](https://authjs.dev/getting-started/providers/google)
- [Apple 연동](https://authjs.dev/getting-started/providers/apple)
- [Naver 연동](https://authjs.dev/getting-started/providers/naver)
- [GitHub Pages는 정적 호스팅](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages)

Google·Apple·Naver의 일반 사용자 계정과 개발자 앱 등록은 서로 다르다. 실제 제공자 승인 없이 로그인이 활성화되었다고 표시해서는 안 된다.
