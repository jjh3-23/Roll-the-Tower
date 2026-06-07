🎲 Roll The Tower
📖 프로젝트 소개

Roll The Tower는 주사위를 굴려 어둠의 탑을 탐험하는 턴제 로그라이크 RPG 게임입니다.

플레이어는 다양한 속성의 무기와 방어구를 획득하며 몬스터와 전투를 진행하고, 층마다 다른 환경 효과를 극복하여 최종적으로 탑의 정상에 도달하는 것을 목표로 합니다.

각 플레이마다 맵 구조와 진행 경로가 달라지므로 매번 새로운 전략을 요구합니다.

🎮 게임 플레이
1. 탐험

플레이어는 주사위를 굴려 맵을 이동합니다.

맵에는 다음과 같은 타일이 존재합니다.

타일   설명
M   몬스터 방
S   상점
E   이벤트 방
B   보스 방
.   빈 방
P   플레이어


2. 전투

전투는 턴제 방식으로 진행됩니다.

플레이어는 다음 행동 중 하나를 선택할 수 있습니다.

기본 공격
무기 고유 스킬 사용
포션 사용
장비 교체

몬스터는 각자 고유한 행동 패턴(Intent)을 가지고 있으며 플레이어는 이를 확인하고 대응해야 합니다.


3. 장비 시스템

무기와 방어구를 장착하여 능력치를 강화할 수 있습니다.

무기 예시
무기   속성   특징
기본 검   무속성   밸런스형
화염도끼   화염   화상 부여
냉기창   냉기   방어력 증가
자연의 활   자연   지속 피해

각 무기는 고유 스킬을 보유하고 있습니다.
전투 중 상성이 불리 할 경우 인벤토리에서 장비를 바로 교체 할 수 있습니다.


4. 환경 시스템

각 층은 서로 다른 환경(Biome)으로 구성됩니다.

환경   효과
화산 지대   화염 피해 증가, 수속성 피해 감소
설원 지대   주사위 -1
바다 지대   수속성 피해 증가, 화염 피해 감소
무기고   무속성 강화

플레이어는 환경에 맞는 무기를 선택하여 전략적으로 전투를 진행할 수 있습니다.

⚔ 주요 시스템
✔ 로그라이크 진행 구조
-랜덤 맵 생성
-랜덤 이벤트
-다양한 장비 획득
-매 플레이마다 다른 경험 제공
✔ 속성 시스템
-화염
-냉기
-자연
-무속성

속성 간 상성과 상태이상이 존재합니다.

✔ 상태이상 시스템
-화상(Burn) : 화상 수 만큼 방어 무시 데미지, 매턴 감소
-취약(Vulnerable) : 입는 피해 증가
-약화(Weak) : 입히는 피해 감소
-힘(Strength) : 데미지 증가
-보호막(Block) : 피해를 막아줌
🏗 클래스 구조
Item 계층
Item
├── Weapon
├── Armor
├── Potion
└── ThrowPotion

Monster 계층
Monster
├── JawWorm
├── FireBat
├── Yeti
└── Boss

Skill 계층
Skill
├── StrikeSkill
├── FlameSlashSkill
├── FrostPierceSkill
└── NatureArrowSkill
💡 객체지향 설계

본 프로젝트는 객체지향 프로그래밍의 주요 개념을 활용하여 설계되었습니다.

캡슐화
 Player
 Status
 Inventory

상속
 Weapon → Item
 Armor → Item
 Potion → Item
 Monster → Monster Base Class

다형성
 virtual void Use(Player& player);
 virtual void executeIntent(Player& player);

각 객체가 동일한 인터페이스를 통해 서로 다른 동작을 수행합니다.

추상화
class Item
{
public:
    virtual void Use(Player& player)=0;
};

🛠 개발 환경
항목   내용
Language   C++
IDE   Visual Studio 2022
Standard   C++17
Platform   Windows
Version Control   Git / GitHub
