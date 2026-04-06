# 🚻 화장실 지도

> 한국어 | [English](#-toilet-map)

**전국 공중화장실 5만 5천개 이상을 지도에서 바로 찾아보세요.**  
내 위치 기반으로 가장 가까운 화장실을 실시간으로 안내합니다.

🔗 **[지금 바로 사용하기 →](https://bigad2007.github.io/hwajangsil-jido/)**

---

## ✨ 주요 기능

| 기능 | 설명 |
|------|------|
| 📍 내 위치 기반 탐색 | GPS로 현재 위치를 감지해 가까운 화장실 순으로 표시 |
| 🗺️ 실시간 지도 | Leaflet 기반 인터랙티브 지도 |
| 🚨 긴급 모드 | 버튼 하나로 가장 가까운 화장실 즉시 안내 |
| 🔍 이름/주소 검색 | 원하는 장소 이름이나 주소로 검색 |
| 🏷️ 필터 | 장애인, 유아, 24시간, CCTV 등 조건별 필터 |
| 🧭 길 안내 | 도보 / 자전거 / 자동차 경로 안내 (OSRM) |
| ⭐ 별점 & 리뷰 | 화장실별 별점 및 리뷰 남기기 |
| 👍 투표 | 청결도, 냄새 등 항목별 투표 |
| 💬 카카오 로그인 | 카카오 계정으로 간편 로그인 후 리뷰 작성 |
| 📱 모바일 최적화 | 스마트폰에서도 편하게 사용 가능 |

---

## 🚀 사용 방법

설치 없이 브라우저에서 바로 사용할 수 있어요.

```
https://bigad2007.github.io/hwajangsil-jido/
```

1. 접속하면 위치 권한을 요청합니다 — **허용**을 눌러주세요
2. 내 주변 화장실이 지도에 자동으로 표시됩니다
3. 카드를 탭하면 상세 정보와 길 안내를 볼 수 있어요
4. 급하면 빨간 🚨 버튼을 누르세요 — 가장 가까운 화장실로 바로 이동합니다

---

## 🛠️ 직접 설치해서 사용하기

직접 로컬에서 실행하거나 자신의 GitHub Pages에 배포하고 싶은 분을 위한 가이드입니다.

---

### 1단계 — 필요한 프로그램 설치

#### Git
- [git-scm.com](https://git-scm.com) 에서 다운로드 후 설치
- 설치 확인:
  ```bash
  git --version
  ```

#### (선택) VS Code
- 코드를 보거나 수정하고 싶다면 [code.visualstudio.com](https://code.visualstudio.com) 에서 설치

---

### 2단계 — 코드 받기

터미널(맥: Terminal, 윈도우: cmd)을 열고 입력하세요.

```bash
git clone https://github.com/bigad2007/hwajangsil-jido.git
cd hwajangsil-jido
```

---

### 3단계 — 로컬에서 실행

이 프로젝트는 별도 서버 없이 HTML 파일 하나로 동작합니다.  
단, 브라우저 보안 정책 때문에 파일을 직접 더블클릭하면 일부 기능이 안 될 수 있어요.

아래 방법 중 하나를 사용하세요.

#### 방법 A — VS Code Live Server (추천)
1. VS Code에서 폴더 열기
2. 확장 프로그램에서 **Live Server** 설치
3. `index.html` 우클릭 → **Open with Live Server** 클릭
4. 브라우저에서 `http://localhost:5500` 자동으로 열림

#### 방법 B — Python 내장 서버
```bash
# Python 3
python -m http.server 8080
```
브라우저에서 `http://localhost:8080` 접속

---

### 4단계 — Firebase 설정 (리뷰/투표 기능 사용 시)

리뷰와 투표 기능은 **Firebase Firestore**를 사용합니다.  
이 기능이 필요하다면 아래 단계를 따라하세요. 필요 없으면 건너뛰어도 됩니다.

1. [console.firebase.google.com](https://console.firebase.google.com) 접속
2. **프로젝트 추가** 클릭 → 이름 입력 후 생성
3. 왼쪽 메뉴 **Firestore Database** → **데이터베이스 만들기** 클릭
4. **테스트 모드**로 시작 (나중에 보안 규칙 설정 가능)
5. 왼쪽 메뉴 **프로젝트 설정** → **웹 앱 추가** 클릭
6. 나오는 Firebase 설정 코드를 복사해서 `index.html` 안의 Firebase 설정 부분에 붙여넣기

```javascript
// index.html 안에서 이 부분을 찾아 교체하세요
const firebaseConfig = {
  apiKey: "여기에_붙여넣기",
  authDomain: "여기에_붙여넣기",
  projectId: "여기에_붙여넣기",
  ...
};
```

> Firebase 없이도 지도 탐색, 검색, 길 안내는 전부 정상 작동합니다.

---

### 5단계 — 카카오 로그인 설정 (선택)

카카오 로그인을 직접 사용하고 싶다면 카카오 개발자 키가 필요합니다.

1. [developers.kakao.com](https://developers.kakao.com) 접속
2. 로그인 후 **내 애플리케이션 → 애플리케이션 추가**
3. 앱 이름 입력 후 생성
4. **앱 키 → JavaScript 키** 복사
5. `index.html`에서 카카오 JavaScript 키 부분을 교체

> 카카오 로그인 없이도 지도 탐색은 모두 가능합니다.

---

### 6단계 — GitHub Pages로 배포 (선택)

내 계정에 올려서 인터넷에 공개하고 싶다면:

1. GitHub에서 새 저장소 만들기 (이름 예: `hwajangsil-jido`)
2. 코드 push:
   ```bash
   git remote set-url origin https://github.com/내_계정명/hwajangsil-jido.git
   git push origin main
   ```
3. 저장소 → **Settings → Pages → Branch: main** 선택 후 저장
4. 잠시 후 `https://내_계정명.github.io/hwajangsil-jido/` 로 접속 가능

---

## 📁 파일 구조

```
hwajangsil-jido/
├── index.html         # 전체 앱 (HTML + CSS + JS 통합)
└── toilets_data.js    # 전국 화장실 데이터 (55,000개+)
```

---

## 🛠️ 기술 스택

- **지도** — Leaflet.js
- **화장실 데이터** — 전국 공중화장실 공공데이터 (55,000개+)
- **경로 안내** — OSRM (Open Source Routing Machine)
- **DB** — Firebase Firestore (리뷰/투표)
- **로그인** — Kakao OAuth
- **배포** — GitHub Pages (서버 불필요)

---

## ❓ 자주 묻는 질문

**Q. 위치 권한을 허용했는데 내 위치가 안 잡혀요.**  
A. 브라우저 설정에서 위치 권한이 차단되어 있을 수 있어요. 주소창 왼쪽 자물쇠 아이콘을 클릭해서 위치 권한을 허용해주세요.

**Q. 화장실 정보가 실제와 다를 수 있나요?**  
A. 공공데이터 기준이라 운영시간이나 시설 정보가 변경되었을 수 있어요. 현장 확인을 권장합니다.

**Q. 데이터를 직접 수정하고 싶어요.**  
A. `toilets_data.js` 파일을 열어서 수정할 수 있어요. 각 항목의 구조는 아래와 같습니다:

```javascript
{
  "i": 1,          // ID
  "n": "화장실 이름",
  "a": "주소",
  "la": 37.574,   // 위도
  "ln": 126.985,  // 경도
  "h": "운영시간",
  "d": 1,          // 장애인 시설 (1=있음, 0=없음)
  "b": 0,          // 유아 시설
  "c": 0,          // CCTV
  "e": 1,          // 비상벨
  "t": 0           // 24시간
}
```

---

---

# 🚻 Toilet Map

> [한국어](#-화장실-지도) | English

**Find over 55,000 public restrooms across South Korea — right on a map.**  
Instantly shows the nearest restroom based on your current location.

🔗 **[Use it now →](https://bigad2007.github.io/hwajangsil-jido/)**

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 📍 Location-Based Search | Uses GPS to show nearby restrooms in order of distance |
| 🗺️ Interactive Map | Leaflet-powered real-time map |
| 🚨 Emergency Mode | One tap to instantly navigate to the nearest restroom |
| 🔍 Search | Search by name or address |
| 🏷️ Filters | Filter by accessibility, baby facilities, 24h, CCTV, etc. |
| 🧭 Navigation | Walking / cycling / driving routes via OSRM |
| ⭐ Ratings & Reviews | Leave star ratings and reviews |
| 👍 Voting | Vote on cleanliness, smell, and more |
| 💬 Kakao Login | Sign in with Kakao to write reviews |
| 📱 Mobile-Friendly | Fully optimized for smartphones |

---

## 🚀 How to Use

No installation needed — works in any browser.

```
https://bigad2007.github.io/hwajangsil-jido/
```

1. Allow location access when prompted
2. Nearby restrooms appear automatically on the map
3. Tap a card to see details and directions
4. In a hurry? Tap the red 🚨 button to jump to the nearest one

---

## 🛠️ Run It Yourself

Want to run it locally or deploy to your own GitHub Pages?

---

### Step 1 — Install Required Tools

#### Git
- Download from [git-scm.com](https://git-scm.com) and install
- Verify:
  ```bash
  git --version
  ```

#### (Optional) VS Code
- If you want to view or edit the code: [code.visualstudio.com](https://code.visualstudio.com)

---

### Step 2 — Clone the Repository

```bash
git clone https://github.com/bigad2007/hwajangsil-jido.git
cd hwajangsil-jido
```

---

### Step 3 — Run Locally

This project is a single HTML file — no server required.  
However, opening it directly in a browser may block some features due to security policies.

#### Option A — VS Code Live Server (Recommended)
1. Open the folder in VS Code
2. Install the **Live Server** extension
3. Right-click `index.html` → **Open with Live Server**
4. Opens at `http://localhost:5500`

#### Option B — Python Built-in Server
```bash
python -m http.server 8080
```
Then open `http://localhost:8080`

---

### Step 4 — Firebase Setup (For Reviews & Voting)

Reviews and voting use **Firebase Firestore**. Skip this if you don't need those features.

1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Create a new project
3. Set up **Firestore Database** in test mode
4. Add a web app and copy the config
5. Replace the Firebase config in `index.html`:

```javascript
const firebaseConfig = {
  apiKey: "your_key_here",
  authDomain: "your_domain_here",
  projectId: "your_project_id_here",
  ...
};
```

> The map, search, and navigation all work without Firebase.

---

### Step 5 — Kakao Login Setup (Optional)

1. Go to [developers.kakao.com](https://developers.kakao.com)
2. Create an app and copy the **JavaScript Key**
3. Replace the Kakao key in `index.html`

---

### Step 6 — Deploy to GitHub Pages (Optional)

1. Create a new GitHub repository
2. Push the code:
   ```bash
   git remote set-url origin https://github.com/your_username/hwajangsil-jido.git
   git push origin main
   ```
3. Go to **Settings → Pages → Branch: main** and save
4. Your site will be live at `https://your_username.github.io/hwajangsil-jido/`

---

## 📁 File Structure

```
hwajangsil-jido/
├── index.html         # Full app (HTML + CSS + JS in one file)
└── toilets_data.js    # Nationwide restroom data (55,000+ entries)
```

---

## 🛠️ Tech Stack

- **Map** — Leaflet.js
- **Data** — Korean public restroom open data (55,000+)
- **Routing** — OSRM (Open Source Routing Machine)
- **Database** — Firebase Firestore (reviews & votes)
- **Auth** — Kakao OAuth
- **Hosting** — GitHub Pages (no server needed)

---

## ❓ FAQ

**Q. My location isn't detected even after allowing access.**  
A. Check your browser's location permission settings. Click the lock icon in the address bar and allow location access.

**Q. Is the restroom info always accurate?**  
A. Data is based on public government records, so hours or facilities may have changed. Always verify on-site.

**Q. How do I edit the restroom data?**  
A. Open `toilets_data.js` — each entry looks like this:

```javascript
{
  "i": 1,          // ID
  "n": "Name",
  "a": "Address",
  "la": 37.574,   // Latitude
  "ln": 126.985,  // Longitude
  "h": "Hours",
  "d": 1,          // Disability facilities (1=yes, 0=no)
  "b": 0,          // Baby facilities
  "c": 0,          // CCTV
  "e": 1,          // Emergency bell
  "t": 0           // 24-hour access
}
```

---

> Made with ☕ by bigad2007
