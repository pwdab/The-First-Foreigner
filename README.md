# The First Foreigner <img src="https://img.shields.io/badge/Unreal%20Engine-0E1128?style=flat&logo=unrealengine&logoColor=white" align="absmiddle"/> <img src="https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white" align="absmiddle"/> <img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white" align="absmiddle"/> <img src="https://img.shields.io/badge/Steam-000000?style=flat&logo=steam&logoColor=white" align="absmiddle"/>
<!--
<p align="center">
  <img src="https://github.com/pwdab/Portfolio/raw/ver-3.0/images/The%20First%20Foreigner/The%20First%20Foreigner.png" alt="The First Foreigner" width="75%">
	<img src="https://github.com/pwdab/Portfolio/raw/ver-3.0/images/The%20First%20Foreigner/features1.gif" width="32%">
	<img src="https://github.com/pwdab/Portfolio/raw/ver-3.0/images/The%20First%20Foreigner/features2.gif" width="32%">
	<img src="https://github.com/pwdab/Portfolio/raw/ver-3.0/images/The%20First%20Foreigner/features3.gif" width="32%">
</p>
-->

<p align="center">
  <img src="https://github.com/pwdab/Portfolio/blob/ver-3.0/images/The%20First%20Foreigner/The%20First%20Foreigner_Steam.png?raw=true" width="75%">
</p>

<p align="center">
  <a href="https://youtu.be/AIy8zwr5r8M">
    <img src="https://img.youtube.com/vi/AIy8zwr5r8M/0.jpg" width="75%" alt="The First Foreigner 테스트 영상">
  </a>
</p>

## 게임 플레이
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/83/Steam_icon_logo.svg" width="15" align="absmiddle"/> [Steam](https://store.steampowered.com/app/3634090/The_First_Foreigner/)에서 게임 다운로드 후 실행합니다.

<br>

## 프로젝트 소개
- **프로젝트 유형**: 3D 캐주얼 멀티플레이 게임 개발 프로젝트 (2인 팀 프로젝트)
- **본인 역할**: 게임 클라이언트 프로그래밍
- **개발 기간**:
	- 2024.09.10 ~ 2024.12.06 : 리슨 서버 기반 빌드 개발 완료
	- 2025.05.17 ~ 2025.06.09 : Online Subsystem 기반 빌드 개발 완료 및 스팀 게시
- **개발 환경**: Unreal 5.2.1, Windows 10
- **주요 기술**:
	- Unreal Engine 5
	- Multiplayer Networking
	- Gameplay Framework
	- Animation Blueprint
	- UMG
	- Online Subsystem
- **담당 업무**:
	- UE5 기반 **2인 멀티플레이 게임**의 로비부터 인게임까지 **전체 플레이 흐름** 구현
	- 세션 생성, 검색, 참가, 종료를 포함한 **멀티플레이 로비 시스템** 구현
	- **GameMode, GameState, PlayerState**를 활용해 **게임 시작, 진행, 종료 흐름 관리**
	- 참가 인원, 제한 시간, 라운드 상태, 플레이어 라이프 등 주요 게임 정보를 **UI와 동기화**
	- 플레이어 입력, 캐릭터 이동, 상호작용 등 핵심 **게임 로직** 구현
	- 단어 선택 UI, 게임 진행 UI, 결과 UI 등 **핵심 UMG 화면** 구현

<br>

## 프로젝트 구조

<details>
<summary>프로젝트 구조 보기</summary>
	
```plaintext
Source/
├── Project_S/
│   ├── Project_S.h
│   ├── Project_S.cpp                       # 커스텀 로그 카테고리 선언
│   ├── PS_AnimInstance.h
│   ├── PS_AnimInstance.cpp                 # 폰의 상태에 대해 폰의 Transform 및 애님 블루프린트를 제어
│   ├── PS_BaseGrabUp.h
│   ├── PS_BaseGrabUp.cpp                   # 월드에 배치할 수 있는 액터로, 폰이 Grab하면 폰의 시선 방향에 액터가 고정됨
│   ├── PS_BasePickup.h
│   ├── PS_BasePickup.cpp                   # (미사용) 월드에 배치할 수 있는 액터로, 폰이 overlap하면 폰의 손에 무기로 장착됨
│   ├── PS_Character.h
│   ├── PS_Character.cpp                    # 유저가 직접 조종하는 폰으로, 키 바인딩과 같이 유저의 특정 행동에 대해 폰을 제어
│   ├── PS_Enemy.h
│   ├── PS_Enemy.cpp                        # (미사용) AI에 의해 월드를 돌아다니는 폰으로, 유저를 발견하면 추적함
│   ├── PS_GameInstance.h
│   ├── PS_GameInstance.cpp                 # Online Subsystem을 이용해 게임 호스트, 게임 참가를 구현
│   ├── PS_GameMode.h
│   ├── PS_GameMode.cpp                     # 게임의 규칙을 선언하고 게임의 흐름을 제어
│   ├── PS_GameState.h
│   ├── PS_GameState.cpp                    # 게임의 현재 상태를 저장하고 서버와 클라이언트 간에 상태를 동기화
│   ├── PS_Grabable.h                       # PS_BaseGrabUp 클래스의 인터페이스
│   ├── PS_HUD.h
│   ├── PS_HUD.cpp                          # UI와 GameState 간의 상태를 동기화하고 PlayerController의 행동에 대해 UI를 제어
│   ├── PS_Interactable.h                   # (미사용) BP_Interactable 클래스의 인터페이스
│   ├── PS_MainMenuPawn.h
│   ├── PS_MainMenuPawn.cpp                 # 메인 메뉴에 사용하는 폰
│   ├── PS_PlayerController.h
│   ├── PS_PlayerController.cpp             # 유저의 입력을 처리하고 UI와 Session을 관리
│   ├── PS_PlayerState.h
│   ├── PS_PlayerState.cpp                  # 클라이언트의 상태(SelectedWord)를 저장하고 서버와 클라이언트 간에 상태를 동기화
│   ├── PS_TimeUtility.h
│   ├── PS_TimeUtility.cpp                  # 블루프린트의 커스텀 노드를 선언 및 정의
└── └── PS_Words.h                          # DataTable의 Row를 커스텀으로 정의하기 위한 구조체
Content/
├── Blueprints/
│   ├── Grabup/
│   │   ├── BP_Grabup.uasset            # PS_BaseGrabUp을 상속 받는 Base 애셋
│   │   ├── BP_Grabup_*.uasset          # BP_Grabup을 상속 받아 구현한 애셋들
│   ├── Pickup/
│   │   ├── BP_Pickup_Weapon.uasset     # (미사용) PS_BasePickup을 상속 받는 Base 애셋
│   │   ├── BP_Pickup_*.uasset          # (미사용) BP_Pickup_Weapon을 상속 받아 구현한 애셋들
│   ├── UI/
│   │   ├── MainMenu/
│   │   │   ├── WB_MainMenu_*.uasset    # 메인 메뉴에서 사용하는 UI들
│   │   ├── Session/
│   │   │   ├── WB_Session_*.uasset     # 세션 메뉴에서 사용하는 UI들
│   ├── WB_*_HUD.uasset                 # 게임 내에서 사용하는 UI들
├── Inputs/
│   ├── IA_*.uasset                     # 각 Action에 대한 값과 트리거를 설정
└── └── IMC_Default.uasset              # InputAction과 키를 매핑
```


</details>
