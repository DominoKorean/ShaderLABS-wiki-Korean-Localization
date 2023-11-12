# 셰이더팩 설치법
이 페이지는 shaderpacks를 실행하기 위해 필요한 내용과 [OptiFine]() 또는 Iris 및 [Shaderpacks]()을 설치하는 방법을 빠르게 다룰 것입니다.



# 시스템 요구 사항
셰이더팩은 CPU에 거의 영향을 미치지 않습니다. 단 효과 단 한개, 동적 그림자 매핑(dynamic shadowmapping)은 세계를 두 번 렌더링해야 합니다. 그러나 상대적으로 최신의 CPU라면 이를 처리할 수 있을 것이며, 노트북과 같이 성능이 낮은 CPU의 경우 플레이 가능한 프레임 속도를 위해 렌더 거리를 줄이는 것이 필요할 수 있습니다.

셰이더팩의 다른 모든 효과들은 GPU에서 스케일이 조절됩니다. 사용 가능한 셰이더팩이 매우 다양하기 때문에 단일한 시스템 요구 사항은 없습니다. [Shaderpacks]() 페이지에서 각 팩에 대한 대략적인 성능 범주를 나열하고 있으며, Potato(여러 세대 전의 통합 GPU에서도 작동해야 함)에서 Extreme(1080p에서 플레이 가능하려면 강력한 고성능 GPU가 필요한 수준)까지 다양합니다.

셰이더팩 자체는 RAM에 거의 영향을 미치지 않습니다. 그러나 고급 리소스팩 기능인 PBR 재질(PBR materials)을 활용할 수 있으며, 이는 RAM 사용량을 대략 세 배로 증가시킬 수 있습니다. 고해상도 리소스 팩을 실행하려는 경우 최고급 구성을 위해 32GB의 RAM과 약 10GB의 VRAM이 필요할 수 있습니다. 그러나 현대의 마인크래프트 버전에서는 이를 수용하기 위해 할당된 메모리 양을 변경할 필요가 없습니다.

운영 체제에 대해서는 대부분 또는 모든 팩이 Windows와 호환되지만, GNU/Linux 및 macOS 호환성은 시장 점유율이 낮아서 또는 각각의 난해한 드라이버 제한 때문에 보다 보편적이지 않습니다. 자세한 내용은 [Shaderpacks]() 페이지의 GPU 열을 참조하십시오.

마지막으로 항상 상대적으로 최근의 그래픽 드라이버 버전을 사용하는 것이 좋습니다. 이전 버전은 셰이더팩 개발자들이 더 이상 고려하지 않는 문제를 일으킬 수 있습니다.


# 셰이더 모드 선택
Iris와 OptiFine은 셰이더팩이 작동하도록 하는 마인크래프트 Java Edition의 주요 모드입니다. 또한 몇 가지 다른 모드도 있으며, 이 모드들은 셰이더와 셰이더팩을 로드하는 데 목적을 두고 있습니다. 만약 이러한 다른 모드에 관심이 있다면, 다음 단락을 읽어보세요. 그렇지 않다면 건너뛰어 다음 섹션으로 이동해도 괜찮습니다. 또한 Iris의 비공식 Forge 포트인 Oculus도 있으며, 이는 Forge 기반의 모드 팩과 결합하여 특정 Iris 전용 셰이더팩을 실행하는 데 필요할 수 있습니다.
 
ShadersMod는 Minecraft Java Edition에서 셰이더팩을 로드하는 최초의 모드였습니다. 그러나 OptiFine이 1.8에서 해당 기능을 포함하기 시작한 이후로 ShadersMod는 오랫동안 버려진 상태입니다. 그 결과 OptiFine는 ShadersMod가 갖고 있지 않았던 많은 새로운 기능을 갖추고 있으며 현대의 대부분 셰이더팩은 더 이상 ShadersMod와 호환되지 않습니다.
 
Focal은 Minecraft의 렌더링 파이프라인을 완전히 교체하고 셰이더팩이 자체로 이를 대체할 수 있도록 하는 새로운 모드입니다. 이로써 셰이더팩이 수행할 수 있는 범위가 확장되며 Vulkan을 사용할 수 있게 됩니다. 현재 Focal은 개발 중이며, 현재로서는 Focal을 사용할 수 있는 유일한 셰이더팩은 ContinuumRT입니다. 그러나 Focal이 좀 더 완성되면 다른 셰이더 개발자들도 이를 활용하기 시작할 것입니다. Focal과 ContinuumRT에 대한 더 많은 정보는 [Continuum 웹사이트](https://continuum.graphics/featured-release/2020/12/20/87433/continuum-rt-build-13-launch-blog/)에서 확인할 수 있습니다.
 
Canvas는 주로 모드 제작자에게 모드 블록의 렌더링에 대한 더 많은 제어와 옵션을 제공하기 위한 Fabric 모드입니다. 또한 셰이더팩을 만들기 위해 사용될 수 있지만, 설계는 OptiFine과 완전히 다르며 완전한 셰이더팩 구현에 필요한 모든 기능을 아직 지원하지 않습니다. OptiFine 셰이더팩과 달리, Canvas 셰이더팩은 여러 리소스팩을 추가하여 혼합할 수 있습니다. Canvas는 [Modrinth](https://modrinth.com/mod/canvas) 또는 [CurseForge](https://www.curseforge.com/minecraft/mc-mods/canvas-renderer)에서 다운로드할 수 있습니다.
 
기술적으로 Minecraft는 1.7부터 셰이더 지원을 가지고 있었지만, 그 당시에는 후처리 효과에만 셰이더가 사용되었습니다. 이러한 효과는 오늘날에도 크리퍼나 거미와 같은 특정 몹을 관전할 때 볼 수 있습니다. 그러나 1.17에서 Minecraft는 셰이더 지원을 확장하고 리소스팩이 셰이더를 포함할 수 있도록 했습니다. 몇 가지 셰이더팩은 바닐라 파이프라인을 사용하지만, OptiFine 파이프라인만큼 고급이나 강력하지는 않습니다. 바닐라 셰이더팩에 관한 더 많은 정보는 [Discord 서버](https://discord.gg/RpzWN9S)에서 확인할 수 있습니다.

# Iris 설치
Iris의 [공식 웹사이트](https://irisshaders.dev/download)에서는 Sodium과 Iris를 모두 포함한 설치 프로그램과 Sodium과 함께 Fabric 모드로 사용하도록 설계된 독립형 버전을 제공합니다. 후자는 mods 폴더에 넣어 다른 Fabric 모드처럼 설치할 수 있습니다. 독립형 버전을 사용할 때는 Iris가 작동하려면 반드시 Sodium이 설치되어 있어야 합니다.

# OptiFine 설치
[공식 다운로드 페이지](https://optifine.net/downloads)에는 많은 Minecraft 버전에 대한 링크가 포함되어 있습니다. 가장 최근 버전이 먼저 표시됩니다. 다른 모든 버전은 "Show all versions"를 클릭하여 찾을 수 있습니다. 이는 각 Minecraft 버전에 대한 OptiFine의 권장 버전을 보여줍니다. 권장 버전 대신 최신 버전을 시도하려면 사용 중인 Minecraft 버전에 대해 "+ Preview versions"를 클릭하여 찾을 수 있습니다. OptiFine의 이전 버전이 필요한 경우 "+ More"을 클릭하여 찾을 수 있습니다.

<details>
<summary>바닐라</summary>

OptiFine.jar 파일은 독립 실행형 설치 마법사로 작동합니다. OptiFine.jar 파일을 두 번 클릭하여 실행하고 "Install"을 클릭하면 됩니다.

OptiFine.jar 파일을 두 번 클릭했을 때 아무 작업도 수행되지 않는다면 Java가 설치되어 있는지 확인하세요. Java는 [Adoptium](https://adoptium.net/?variant=openjdk8&jvmVariant=hotspot)에서 다운로드할 수 있습니다.

OptiFine.jar 파일이 Java와 관련이 없는 다른 프로그램(예: 7zip 또는 WinRar)으로 열린 경우 [Jarfix](https://johann.loefflmann.net/en/software/jarfix/index.html)를 먼저 실행해 보세요.

**중요한 참고:** OptiFine 설치 마법사는 Mojang에서 제공하는 공식 Minecraft 런처와만 호환됩니다.

</details>

<br/>

<details>
<summary>Optifine</summary>

OptiFine는 Forge와 내장 호환성이 있습니다. 따라서 OptiFine.jar 파일을 다른 Forge 모드처럼 mods 폴더에 넣을 수 있습니다. [공식 다운로드 페이지](https://optifine.net/downloads)에서 다운로드한 OptiFine 버전에 대한 지원되는 Forge 버전이 명시되어 있습니다. 다른 버전의 Forge를 사용하는 경우 제대로 작동하지 않을 수 있습니다.

</details>

<br/>

<details>
<summary>Fabric</summary>

Fabric를 사용하는 경우 OptiFine 외에도 [OptiFabric](https://www.curseforge.com/minecraft/mc-mods/optifabric)를 설치해야 합니다. 그런 다음 OptiFabric.jar와 OptiFine.jar 파일을 모드 폴더에 Forge와 유사하게 넣으면 됩니다.

</details>



## MultiMC
OptiFine를 MultiMC와 함께 설치하는 방법에 대한 지침은 [MultiMC 위키](https://github.com/MultiMC/MultiMC5/wiki/MultiMC-and-OptiFine)에서 찾을 수 있습니다.

# 셰이더팩 설치
사용 가능한 셰이더팩 목록은 [셰이더팩 목록]()을 확인하세요.

팩을 다운로드한 후 다운로드한 zip 파일을 .minecraft/shaderpacks에 넣으세요. 일부 브라우저는 자동으로 다운로드한 파일을 압축 해제하는 경우가 있습니다. 그 경우에는 압축 해제된 폴더를 shaderpacks 폴더로 이동하고 폴더 구조가 다음과 같이 보이도록 하세요:
```
 - shaderpacks
     - [Shaderpack 이름]
          - shaders
```
일부 셰이더팩은 여러 버전을 하나의 zip으로 번들링하는 등 특별한 설치가 필요할 수 있습니다. 이 경우 zip 파일 이름에 일반적으로 표시가 있습니다.
shaderpacks 폴더가 없는 경우 게임을 한 번 실행하거나 수동으로 만드세요. 그런 다음 게임을 시작하고 옵션 > 비디오 설정 > 셰이더에서 선택하세요. 일반적으로 셰이더팩에는 구성할 수 있는 추가 옵션이 있습니다. 이 옵션은 셰이더 선택 화면에서 "셰이더 설정" 아래에서 찾을 수 있습니다.
