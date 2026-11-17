<div align="center">

#제목 없는 권총 아레나 (Untitled Pistol Arena)

** 1대1 PvP 1인칭 모바일/PC FPS 게임**

<p>
  <img src="https://img.shields.io/badge/Unity-2022.3%2B-black?style=for-the-badge&logo=unity&logoColor=white" />
  <img src="https://img.shields.io/badge/Language-C%23-239120?style=for-the-badge&logo=csharp&logoColor=white" />
  <img src="https://img.shields.io/badge/Platform-Android%20%2F%20PC-00FFAA?style=for-the-badge&logo=android&logoColor=white" />
  <img src="https://img.shields.io/badge/Status-CBT%20Developing-orange?style=for-the-badge" />
</p>

</div>

---

##  프로젝트 소개 (Overview)
Unity 엔진을 기반으로 개발 중인 인디 모바일 FPS 게임 **'제목 없는 권총 아레나'**입니다. 
사이버펑크 밀리터리 허드(HUD) 디자인과 정밀한 1인칭 사격 매커니즘, 그리고 1대1 AI 봇 대결 시스템을 구현하고 있습니다.

---

##  주요 기능 (Key Features)

### 1.  메인 로비 & 하이테크 UI/UX
* **닉네임 캐시 시스템:** 최초 실행 시 플레이어 닉네임을 입력받고 `PlayerPrefs`를 통해 우측 상단 프로필 및 보유 재화(`🪙 1,000 G`)와 실시간 연동.
* **스마트 모드 선택:** [시작하기] 버튼 클릭 시 **[PvP 모드 (1대1 봇 대결)]**과 **[Normal 모드 (개발 중 안내 팝업)]** 선택 가능.
* **택티컬 허드 패널:** 무기 스펙 카드, 실시간 공지사항(NOTICE BOARD), 글래스모피즘 스타일의 설정 및 크레딧창.

### 2.  1인칭 PvP 전투 씬 (FPS Combat)
* **정밀 1인칭 카메라:** Mixamo 캐릭터의 `Head` 본 눈 높이에 카메라를 밀착시키고 메시 가림 현상 방지 처리.
* **오른손 무기 장착 (`handgun1.fbx`):** 손바닥 위치에 자연스럽게 권총을 쥐도록 오프셋 적용, 내부에 포함된 불필요한 `bullet` 오브젝트는 코드로 자동 정산·제거.
* **전투 시스템:** 15발 탄창 및 재장전 메커니즘, Raycast 정밀 사격, 모바일 가상 조이스틱/PC 조작 호환, 그리고 엄폐물 활용 AI 봇 전투.

---

##  기술 스택 (Tech Stack)

| Category | Technology / Tool | Description |
| :--- | :--- | :--- |
| **Engine** | Unity (C#) | 게임 로직 및 UI/UX 구현 |
| **Design Style** | Cyberpunk HUD (`#00FFAA`) | 네온 민트 포인트, 글래스모피즘 UI |
| **Character & Animation** | Mixamo (Humanoid) | 휴머노이드 캐릭터 릭 및 애니메이션 매핑 |
| **Data & Storage** | `PlayerPrefs` | 닉네임, 옵션 설정 로컬 캐싱 |
| **Weapon Asset** | `handgun1.fbx` | 1인칭 권총 모델 (불필요 오브젝트 자동 분리) |

---

##  프로젝트 구조 (Project Structure)

```text
Assets/
├── Scripts/
│   ├── LobbyManager.cs       # 로비 UI, 닉네임 캐시, 모드 선택 및 설정 관리
│   ├── GamePlayManager.cs    # 1인칭 아레나 맵 생성 및 전투 총괄
│   ├── PlayerController.cs   # 1인칭 이동, 카메라 시점, 사격 및 조작계
│   └── BotAI.cs              # 1대1 봇 전투 및 추적/사격 AI 로직
├── Models/
│   └── handgun1.fbx          # 권총 3D 모델 ('bullet' 자동 분리/삭제 처리)
├── Sounds/
│   └── lobby.mp3             # 로비 배경음악 (무한 루프)
└── Textures/
    ├── logo.jpg              # 게임 로고
    └── background.jpg        # 로비 배경 이미지
