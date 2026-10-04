# TSPG ENG 개념제안 앱

미팅 현장에서 최소 질문으로 자동창고 제안 방향·개략 규모·투자비를 보여 주는 앱입니다.
설치형 웹앱(PWA)이라 휴대폰 홈 화면에 앱처럼 설치해 쓰고, 한 번 연 뒤에는 오프라인에서도 열립니다.

## 배포 (GitHub Pages)
1. 저장소 **Settings → Pages**
2. Source: **Deploy from a branch**, Branch: **main** / **/(root)** → Save
3. 1~2분 뒤 주소: `https://lms-0517.github.io/ENG/`

## 휴대폰에 앱으로 설치
- **안드로이드(크롬)**: 위 주소를 크롬으로 열기 → 오른쪽 위 ⋮ → **앱 설치**(또는 홈 화면에 추가)
- **아이폰(사파리)**: 사파리로 열기 → 공유 버튼 → **홈 화면에 추가**

설치하면 주소창 없이 전체 화면 앱으로 열리고, 새 버전이 올라오면 화면 아래에
"새 버전이 나왔습니다 · 눌러서 적용" 버튼이 뜹니다.

## 구성
| 파일 | 내용 |
|---|---|
| `index.html` | 앱 본체(입력·계산·결과·소개서 보기) |
| `simulation.js/.css`, `higgsfield*.js`, `vendor/` | 3D 자동창고 시뮬레이션(three.js) |
| `assets/warehouse-higgsfield.glb` | 3D 설비 모델 |
| `pdfjs/`, `*_intro.pdf` | 회사소개서 보기 |
| `sw.js`, `manifest.webmanifest`, `icon-*.png` | 설치·오프라인(PWA) |
| `tests/verify.cjs` | 계산 회귀 검사 — `node tests/verify.cjs` |

## 수정 후 배포할 때
`index.html` 상단의 빌드 번호와 `sw.js` 의 `CACHE` 값을 함께 올려야
설치된 앱이 새 버전을 받아 갑니다.
