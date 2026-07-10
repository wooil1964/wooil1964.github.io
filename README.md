# 들뫼생태연구회 공식 홈페이지 (wooil1964.github.io)

들뫼생태연구회의 공식 안내 홈페이지입니다. **대표 주소: https://wooil1964.github.io/**
기존 **네이버 카페**와 **전국 탐조지도**(별도 저장소 `birdmap`에서 운영)를 연결하는 공식 입구 역할을 합니다.

> 이 저장소는 GitHub **사용자 사이트**(username.github.io) 배포본입니다.
> 네이버 서치어드바이저가 호스트 단위 주소만 받기 때문에, 프로젝트 페이지 주소
> (`.../dulmoe-homepage/`) 대신 이 대표 주소로 배포합니다.
> 원본 개발 저장소는 [`dulmoe-homepage`](https://github.com/wooil1964/dulmoe-homepage)이며 그대로 보존됩니다.
> 내용을 수정할 때는 두 저장소가 어긋나지 않게 같은 변경을 양쪽에 반영하거나, 이 저장소를 기준으로 삼으세요.

## 파일 구성

| 경로 | 설명 |
|------|------|
| `index.html` | 첫 화면. 감성형 히어로 + 카페 게시판 바로가기 카드 + 이 달의 새(1~12월) |
| `map.html` | 전국 탐조지도 안내 페이지. 현재는 기존 지도(birdmap)로 외부 링크 연결 |
| `assets/hero-birds.svg` | 첫 화면 배경 그림(아침빛 습지와 새 실루엣, SVG 일러스트) |
| `robots.txt` | 검색엔진 수집 허용 설정 |
| `sitemap.xml` | 검색엔진용 사이트맵 |

## 배포 방법 (GitHub Pages)

저장소 이름이 `wooil1964.github.io`인 **사용자 사이트**이므로, `main` 브랜치에 push하면
보통 자동으로 배포됩니다. 잠시 후 `https://wooil1964.github.io/` 주소로 접속할 수 있습니다.
(배포가 안 되면 Settings → Pages에서 Source가 `Deploy from a branch`, Branch가 `main` / `/ (root)`인지 확인하세요.)

## 배포 후 반드시 해야 할 일 (TODO)

### 1. 네이버 카페 게시판별 URL 교체

카페 대문 주소는 실제 주소 **https://cafe.naver.com/withbirds** 로 적용되어 있습니다.
다만 게시판 카드들은 아직 게시판별 주소가 아니라 카페 대문으로 연결되므로,
각 링크 옆의 TODO 주석을 참고해 게시판별 주소로 교체하세요.

- 교체 대상 게시판: 심층탐구, 숙닥숙닥 이야기나누기, 함께 탐조 가요, 탐조지 소식,
  새이름이 궁금해요, 외국의 새, 가입인사, 1월의 새 ~ 12월의 새

게시판 URL은 네이버 카페에서 해당 게시판을 연 뒤 주소창의 URL(또는 "URL 복사")을 사용하면 됩니다.

### 2. sitemap.xml / robots.txt 주소 — 적용 완료

- 대표 배포 주소(`https://wooil1964.github.io/`)로 적용되어 있습니다.
- 나중에 도메인을 바꾸면 `sitemap.xml`의 `<loc>` 주소와 `robots.txt`의 `Sitemap:` 줄을 함께 바꿔 주세요.

### 3. 배경 그림을 실제 새 사진으로 교체하기 (선택)

현재 첫 화면 배경은 외부 이미지 없이 동작하는 SVG 일러스트(`assets/hero-birds.svg`)입니다.
실제 새 사진으로 바꾸고 싶으면:

1. 사진 파일을 `assets/hero-birds.jpg`(또는 `.png`)로 저장합니다.
   - 가로로 긴 사진(권장 1600×900 이상)이 좋습니다.
2. `index.html`과 `map.html`에서 `assets/hero-birds.svg`로 되어 있는 부분을
   새 파일 이름으로 바꿉니다. (각 파일에서 `hero-birds.svg`를 검색하면 됩니다)
   - `index.html`: 히어로 배경(`url("assets/hero-birds.svg")`)과 `og:image` 메타 태그
   - `map.html`: 상단 배너 배경
3. 사진 위 글자가 잘 안 보이면 CSS의 `linear-gradient(...)` 어둡기 값을 조절하세요.

### 4. 네이버 검색 등록

배포 후 [네이버 서치어드바이저](https://searchadvisor.naver.com/)에 사이트를 등록하고
`sitemap.xml`을 제출하면 네이버 검색 노출에 도움이 됩니다.

## 전국 탐조지도와의 관계

- 전국 탐조지도는 별도 저장소(`birdmap`)의 `index.html`에서 운영 중입니다.
- `map.html`은 그 지도로 연결하는 안내 페이지이며, 지도를 이 저장소로 옮길 때
  참고할 이관 안내 주석이 `map.html` 상단에 있습니다.
- 이 저장소의 작업은 기존 지도 운영에 영향을 주지 않습니다.
