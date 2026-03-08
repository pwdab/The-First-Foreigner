# The First Foreigner <img src="https://img.shields.io/badge/Unreal%20Engine-0E1128?style=for-the-badge&logo=unrealengine&logoColor=white" align="absmiddle"/> <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" align="absmiddle"/> <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" align="absmiddle"/> <img src="https://img.shields.io/badge/Steam-000000?style=for-the-badge&logo=steam&logoColor=white" align="absmiddle"/>
<p align="center">
  <img src="https://github.com/pwdab/Portfolio/raw/ver-3.0/images/The%20First%20Foreigner/The%20First%20Foreigner.png" alt="The First Foreigner" width="75%">>
	<img src="https://github.com/pwdab/Portfolio/raw/ver-3.0/images/The%20First%20Foreigner/features1.gif" width="32%">
	<img src="https://github.com/pwdab/Portfolio/raw/ver-3.0/images/The%20First%20Foreigner/features2.gif" width="32%">
	<img src="https://github.com/pwdab/Portfolio/raw/ver-3.0/images/The%20First%20Foreigner/features3.gif" width="32%">
</p>

## 🎮 게임 플레이
- **직접 플레이**   
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/83/Steam_icon_logo.svg" width="15" align="absmiddle"/> [Steam](https://store.steampowered.com/app/3634090/The_First_Foreigner/)에서 게임 다운로드 후 실행합니다.
- **플레이 영상**   
  <img src="https://upload.wikimedia.org/wikipedia/commons/0/09/YouTube_full-color_icon_%282017%29.svg" width="15" align="absmiddle"/> [YouTube](https://www.youtube.com/watch?v=AIy8zwr5r8M)에서 플레이 영상을 시청할 수 있습니다.

## 📌 프로젝트 소개
- **프로젝트 개요**   
  Unreal Engine으로 제작한 3D 멀티플레이 캐주얼 게임\
  두 명의 플레이어가 번갈아 제시어를 행동이나 사물로 표현하고 상대가 이를 추리해 맞춤
- **개발 기간**   
  2024.09.10 ~ 2024.12.06 : 리슨 서버 기반 빌드 개발 완료\
  2025.05.17 ~ 2025.06.09 : Online Subsystem 기반 빌드 개발 완료
- **개발 상태**   
  Steam 게시 완료 (개발 종료)
- **개발 환경**   
  Unreal 5.2.1\
  Windows 10 (64bit)
- **멤버 구성**   
  기획 및 레벨 디자인 1명\
  프로그래밍 1명

## 🎯 담당 업무
- Unreal Gameplay Framework 기반 **게임 플레이 로직** 구현   
- Replication·RPC 기반 클라이언트–서버 **데이터 동기화 및 명령 처리**   
- Animation Blueprint·AnimInstance·State Machine 기반 캐릭터 **애니메이션 제어**   
- Widget Blueprint 기반 **동적 UI** 제작 및 **데이터 연동**   
- Online Subsystem 기반 **세션 관리**

## 프로젝트 구조
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
