# 초록 하루

생활 습관(약, 영양제, 식사, 걸음 수)을 체크하고, 일정과 알람, 달력으로 한눈에 보는 안드로이드 앱이에요.
웹 한 장(`www/index.html`)으로 만든 앱을 [Capacitor](https://capacitorjs.com)로 감싸 안드로이드 앱으로 만들었어요.

## 설치 (안드로이드)

1. 폰 크롬에서 **최신 APK** 받기: https://github.com/aanirri07-ai/aanirri/releases/latest/download/chorok-haru.apk
2. 받은 파일을 열어 설치해요. 처음 한 번 "출처를 알 수 없는 앱 허용"을 켜 달라고 해요.
3. 첫 실행 때 **알림 권한**을 허용해요.
4. (삼성 등) 알람이 늦게 오면: 설정 → 배터리 → 백그라운드 사용 제한 → 초록 하루를 **제한 없음**으로.

업데이트는 새 APK를 받아 그대로 설치하면 덮어쓰기돼요. 기록은 폰 안에 그대로 남아요.

## 어떻게 만들어지나

- `www/index.html` — 앱 화면과 기능 전부 (HTML/CSS/JS 한 파일)
- `www/capacitor.js` — 네이티브 기능(알람)을 부르는 다리
- `android/` — 안드로이드 프로젝트 (Capacitor가 생성, 아이콘·권한·서명 설정 포함)
- `.github/workflows/build-apk.yml` — `main`에 코드가 올라오면 GitHub가 APK를 만들어 Releases에 올려요

## 서명 키에 대해

`android/app/release.keystore`는 강한 비밀번호로 잠겨 있고, 비밀번호는 GitHub **Secret `KEYSTORE_PASSWORD`** 에만 있어요.
Secret이 없으면 테스트 서명으로 빌드돼요. 같은 키로 서명해야 덮어쓰기 설치가 되니, Secret을 먼저 넣고 설치하는 걸 권해요.

## 고치고 싶을 때

코드를 직접 만질 필요 없어요. Claude에게 "식사 카드에 간식 버튼도 넣어줘"처럼 말하면 `www/index.html`을 고쳐 올리고, 몇 분 뒤 새 APK가 Releases에 생겨요.
