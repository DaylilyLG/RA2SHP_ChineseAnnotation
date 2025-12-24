 
# 前言和准备工作  
  
- 本文使用了 Markdown 标记语言来优化阅读体验，所以我们首先需要准备一个代码查看器（作者使用的是 [HBuilderX](https://www.dcloud.io/hbuilderx.html)，如果你使用 [VSCode](https://code.visualstudio.com/) 可能需要手动下载 Markdown 插件），或者用电脑自带的记事本，但不推荐（因为修改过程需要一个方便查看代码的环境），安装代码查看器后就可以用它来打开这个介绍文件了，打开后可以看到带有 “#”（井号）标题的前方有折叠按键，单击即可折叠/展开，看完了就能折叠隐藏起来，非常方便阅读。还可以到[我的个人网站](https://daylily.website/)在线观看哦（还在施工中）  
  
红色警戒2（简称 RA2）、尤里的复仇（简称 YR），由于游戏源码未公开，在大家 DIY（修改游戏数据或自定义内容）的时候或多或少会遇到游戏引擎中的硬编码限制。因此，许多红警爱好者在基于 YR 1.001 版本的基础上，开发了新的扩展引擎平台，来修复或扩充原版引擎的功能，这极大丰富了 DIY 的自由度，例如：Aers、Phobos、Kratos 等。但考虑到许多新人并没有接触过这些引擎，所以本次将不使用扩展引擎的功能进行介绍，以尽量贴合新人从 “0” 开始接触 DIY 的情景，但还是建议新人预装 Aers 和 Phobos 这两个引擎，可以改善游戏体验，例如提升原版引擎的启动速度。
  
内容讲解可能比较冗长或者啰嗦，但是讲得很细，新手推荐按顺序阅读，我会尽量用简单的方式介绍一些本人认为常见的 DIY 内容，从基础开始（不包含*覆盖物、污染物等杂项*和一些可能比较复杂，或者会运用到扩展引擎的内容）希望能给初次接触红警 DIY 的小伙伴提供便利~（以下内容中如果有出现“※”符号，表示这段内容是作者的备注）   
  
如果你想使用 YR 版本进行 DIY，这里推荐大家在 DIY 前预先安装 Ares 和 Phobos 引擎（下载链接和使用方法已经放在文章最底下的[资源和推荐区](# 资源)），然后使用INI修复版本：[INI修缮项目：Yrstandard-ini（这里十分感谢 ProsperousBeyond）](https://gitee.com/PB_LAB/yrstandard-ini)（安装前注意备份），安装完毕后，咱们就可以进入下面的章节了。这边要提醒一下 RA2 版本的 DIY 玩家，由于 YR 版本的官方内容和功能是最多且最新的（官方最新版为 YR 1.001），以及 YR 有更多的软件支持，例如对 YR 有针对性优化的地图编辑器，而最新版的地图编辑器已经不支持 RA2 了，所以我推荐使用 YR 进行 DIY，而不是 RA2，除非你需要 DIY 旧版引擎的内容（例如基于旧版引擎的 RA2，或使用旧版引擎的其他游戏版本），并*接受旧版引擎的缺陷*。  

# 第一章：rules(md).ini（规则配置文件）
  
这是包含了游戏基础规则的ini配置文件，简称规则文件，一般`红色警戒 2`对应的是 rules.ini 配置文件，而`尤里的复仇`则对应 rulesmd.ini 这个文件，两个文件的内容不同，为方便讲解，*以 rulesmd.ini 为准*。下面我们需要逐步理解这些配置文件中一些常用名词。  
  
  
首先，让我们打开规则文件：rulesmd.ini（规则配置文件）  
  
打开搜索（按 Ctrl + F 进行搜索），搜索 [AEGIS]，这是神盾巡洋舰的**注册名**，为确保搜索到正确内容，注意要带上`[]`括号，你会看到这样的代码：  
~~~ini
[AEGIS]  
UIName=Name:AEGIS  
Name=Aegis Cruiser  
Prerequisite=GAYARD,RADAR  
Primary=Medusa  
......中间省略一大段......  
;BuildLimit=2  
ElitePrimary=MedusaE  
Size=30  
TooBigToFitUnderBridge=true  
~~~
没错，这一部分就是神盾巡洋舰的**单位本体**（特指这部分的代码），还可以简称**单位**（泛指所有相关的代码）。而在 [AEGIS] 注册名下方的代码可以被称为**语句**，而**标签**涵盖范围广（个人理解），示意代码：  
~~~ini
[AEGIS]     注册名/标签/代码  
UIName=     语句/标签/代码  
Name=       语句/标签/代码 
......=     语句/标签/代码  
~~~
可以说是某个**标签**，或者某个**语句**，甚至统称为**代码**也是没问题的，请依据个人习惯来决定。  
仔细看看，还会发现有的语句或标签会带有 “;” 这个符号，这表示*在这符号之后的一行代码将无效化*，即成为**注释**，我们可以直接无视它们，例如控制单位建造数量的是这个语句：`;BuildLimit=2`，可以看到已经被注释了，所以不会有任何作用，忽略即可。我们也可以手动取消注释（把 “;” 这个符号删除），或把注释保留下来，另起一行，添加语句`BuildLimit=`，例如：  
~~~ini
[AEGIS]
......省略一大段......  
;BuildLimit=2  ←这是保留的注释，取消注释前要注意不能有重复的语句！绝对！不能！有重复语句！（  
BuildLimit=数字  ←另起一行，可以填写阿拉伯数字，例如谭雅的建造数量限制为一个，填 1 即可。  
ElitePrimary=MedusaE  ; ←像这样把注释放到后面也是可以的哦~
Size=30  ; ←注意是英文的 “;”、而不是中文的 “；”！  
TooBigToFitUnderBridge=true  
~~~
  
其实被注释的整段代码都可以删除，毕竟已经 “没有用” 了，但我们有时候可能会忘记一些代码上的改动，这时注释还可以起到备忘的作用，所以我们可以适当保留一些注释。   
  
在 [AEGIS] 标签的下方可以看到这个语句`Primary=Medusa`，我们可以把`Primary`和`Medusa`分成两部分来看，`Primary`可以看作是**武器类型**，`Medusa`则是**武器**（不难看出，这行代码给单位指定了 [Medusa] 作为它的武器），下面先来认识一下**武器类型**：  

- 主武器`Primary=`：单位的主要武器，以及单位的三星主武器`ElitePrimary=`，单位升级至三星后会立即换用`ElitePrimary=`所指定的武器，需要注意的是，有的单位是没有这种语句的，或者出现`ElitePrimary=`被注释等情况，一般常见于平民单位，以及遥控坦克、工程师等，即便升级到三星，也会因为没有`ElitePrimary=`语句，而继续使用`Primary=`所指定的武器。 

- 副武器`Secondary=`：单位的次要武器，以及三星副武器`EliteSecondary=`。例如天启坦克攻击飞行单位所使用的副武器`Secondary=MammothTusk`，但天启坦克没有三星副武器，所以无论有没有升级，都始终使用`Secondary=`所指定的武器。

- 死亡武器`DeathWeapon=`：单位被摧毁后所释放的武器，例如核子反应堆、自爆卡车和恐怖分子等。  

- 多种武器逻辑：上述几种类型的武器可同时存在于一个单位中，若要实现一个单位使用更多的武器通常需要配合 “多武器逻辑”。例如多功能步兵车（IFV逻辑）和盖特机炮（盖特逻辑），其中盖特逻辑的启用语句是：`IsGattling=yes`（你可以看到盖特机炮分阶段开火，那是因为它有多种武器），单位本体拥有这种语句时，才能够做进一步的设置（例如添加相关武器语句：`Weapon1=`、`EliteWeapon1=`）。有的逻辑（例如分裂、空爆逻辑）只在武器本体中添加启用语句，具体的咱们就不深入了，只需要了解这些情况是存在的即可。有兴趣可查阅词典，以下是常见的多武器逻辑：  
1. 盖特逻辑  
2. IFV逻辑  
3. 分裂逻辑  
4. 空爆逻辑  

以上即为武器类型的介绍，下面让我们回到`Primary=Medusa`这个语句，我们同样带上括号搜索`Medusa`这个武器，像这样：`[Medusa]`，搜索出来的结果如下：  
~~~ini
[Medusa]    
Damage=100;攻击力  
ROF=15;攻速      
Range=12;射程范围    
Speed=120;抛射体飞行速度（可理解为弹体飞行速度）（有速度上限）  
Projectile=MedusaProjectile;抛射体（重点）  
Warhead=SAMWH;弹头（重点）  
Report=AegisAttack;攻击的声音  
TurboBoost=yes;攻击飞行物是否使抛射体有速度加成  
OmniFire=yes;使无炮塔单位不用转向就能开火（反例：坦克杀手）  
~~~
现在你看到的部分就是**武器本体**（特指部分代码），简称**武器**（泛指相关代码），这些语句是武器的*基本属性*，例如修改单位的伤害（攻击力）`Damage=`、攻击范围`Range=`等，都是在该部分修改的。
  
可以看到武器中的语句并不多，其中最主要的就是`Projectile=MedusaProjectile`和`Warhead=SAMWH`这两个语句，所以我们再次用同样的方法搜索`[MedusaProjectile]`和`[SAMWH]`，可以分别看到以下内容：    
```ini
[MedusaProjectile]  （抛射体）  
Arm=1  
High=yes  
Shadow=no  
......中间省略......   
SubjectToCliffs=no  
SubjectToElevation=no  
SubjectToWalls=no  
  
[SAMWH]  （弹头）  
CellSpread=.3  
PercentAtMax=1  
Verses=100%,100%,100%,100%,100%,100%,0%,0%,0%,100%,100%  
InfDeath=3  
AnimList=XGRYSML1,XGRYSML2,EXPLOSML  
ProneDamage=100%  
```  
这些内容便是**武器**的中的**抛射体**和**弹头**，武器的*具体属性*都要通过它们设置，例如用抛射体决定武器是否隔着围墙也能打到对面`SubjectToWalls=`，以及在弹头的设置中对某种车辆或建筑的装甲造成特定的伤害比例`Verses=`，这些我们在之后都会讲到。  
  
**全局语句**（或全局标签）在规则文件中一般是指`[General]`标签下方的所有语句代码，可以理解为*独立存在的代码*，例如控制单位的维修速度、各个阵营的步兵类型（例如盟军玩家建造的建筑被摧毁时逃出来的就是美国大兵）、幻影坦克可以伪装的物体、间谍可以偷多少比例的钱等等，你甚至可以让“维修小扳手”自动维修建筑，而无需手动操作。这部分有兴趣可以查阅词典，新手只需粗略了解即可。  
  
现在我们来具体了解一下什么是**单位**，单位的类型有很多，例如：车辆、步兵、建筑、海军，还有空军等等都可以被称作**单位**。其中，车辆、直升机、飞艇、飞碟及海军被分类为***载具*** ← 重点，具体分类在下面介绍。  
  
首先，我们先来了解什么是*注册表*:
  
上面有提到过注册名，例如`[AEGIS]`是神盾巡洋舰的**注册名**，
你可能会有疑问，为啥叫**注册名**？它是咋来的？现在来搜索这个`[VehicleTypes]`，你会看到：  

```ini
[VehicleTypes]
1=AMCV;Allied MCV
2=HARV
3=APOC
4=HTNK
5=SAPC
6=CAR
7=BUS
8=WINI
9=PICK
10=MTNK
11=HORV
12=TRUCKA
13=TRUCKB
14=CARRIER
15=V3
16=ZEP
17=DRON
18=HTK
19=DEST
20=SUB
21=AEGIS;←我在这儿！←看我！←看我！←看我！←看我！←看我！←看我！
...
```
你很容易就发现了`AEGIS`（  
你可能会困惑，为啥 AEGIS 会在这里？好的，这里就是关键点，我们要请出一个专有名词：**注册表**，这就类似“登记表”，如果一个完整的犀牛坦克要在游戏里出现，就必须在登记表里登记名字！（而且名字不能重复）**注册**也是同理，如果你有新东西要添加，那就必须要找到对应的**注册表**进行**注册**，很好理解对不对？可以看到神盾巡洋舰（AEGIS）被“登记”在了这个注册表：`[VehicleTypes]`，这就说明它已经使用 AEGIS 这个注册名进行注册了，那么 AEGIS 就是它的注册名，这就是**注册名**的由来，它是单位*独一无二*的标识~  
  
`[VehicleTypes]`注册表只是其中的一部分哦！那么下面还有常用的注册表给大家展示一下：  
    
常用注册表：  
※这里已经把准备讲解的注册表都列出来了，具体讲解内容还没完成...大部分先留空  

[InfantryTypes] ;注册步兵单位(Infantry)  
  
[AircraftTypes]  ;注册空军单位(Aircraft)  
  
[VehicleTypes]  ;注册载具(Vehicle)  
  
需要注意，夜莺直升机、基洛夫空艇和磁悬幽浮（飞碟）这类单位的运动方式实际上为 Hover 悬浮速度类型，Hover 一般是归类为**载具**（即 Vehicle，而非 Aircraft）
  
[BuildingTypes]  ;注册建筑单位(Building)  
  
[Animations]  ;注册动画  
  
※关于修改动画的内容会在第二章讲解
  
[Warheads]  ;注册弹头  
  
[WeaponTypes]  ;Ares引擎的注册表，但建议了解的内容，介绍什么是挂载，什么情况下需要挂载武器
  
※超级武器  ;有Ares引擎内容，选择性了解  
  
（待完善）  
  
[SuperWeaponTypes]
  
 
 


※粒子系统准备讲解的部分：
  
注册新的粒子系统一般要用到两个注册表，一个是粒子系统，另一个是粒子：  
```ini
[ParticleSystems]  ;注册粒子系统   
[Particles]  ;注册粒子（注册后用在粒子系统） 
```
什么是**粒子系统**？烟雾（载具受损的烟雾效果）、火花（维修车修载具时喷溅的火花）、毒气（病毒狙击手击杀步兵后产生的毒气）是原版游戏中最常见的*粒子系统类型*，而我们在游戏中到处都能“看见”**粒子**，你可以把粒子看作一个隐形的“钉子”，粒子通常会携带一个以“钉子”为中心的图像（就像往照片的正中央钉钉子，但是钉子成精了！带着照片在墙上移动！），比如坦克受损时会产生一团团的烟雾，每一团烟雾代表一个粒子，而粒子都在向上运动，所以你能观察到不断向上冒出的烟雾。再比如病毒狙击手射杀一名步兵时，会产生一团团绿色的毒气，这些毒气到处飘动，也是因为这些粒子在运动。总而言之：图像负责显示，而*粒子负责带着图像移动*。  
  
我们可以直接用特定语句设置粒子系统，比如你可以直接在弹头中设置粒子系统（Particle=），以及坦克受损产生的粒子系统（在单位本体中设置：DamageParticleSystems=）这里就不展开讲了。除了特定语句，还有更具体的设置，新手过目即可：  

```ini
;在武器本体中，首先加入这个语句：
AttachedParticleSystem=;在粒子系统注册表中选择粒子系统

;然后使用以下三种任意语句即视为开启，在表现方式上由 BehavesLike= 定义，毒气Gas丨烟雾Smoke丨喷火Fire丨火花Spark丨轨道炮Railgun
IsRailgun=yes;地形高低差可能会导致粒子被截断...可使用 Phobos 修复
UseFireParticles=yes;使弹头动画不播放、武器本体中的伤害Damage无效（允许粒子伤害Damage）、粒子动画Image挂武器的伤害Damage无效，可使用 Ares 修复（无法修复粒子动画挂武器的伤害）
UseSparkParticles=yes;常见维修车使用

;※推荐使用的 Ares 内容：
;Ares 引擎中有提供代替语句，例如可将 IsRailgun= 改用 IsDetachedRailgun=，解决第一次攻击产生的粒子动画未消散前，无法进行第二次攻击的硬编码问题。
```
  
以上就是粒子系统具体的启用语句，再往下内容就比较多了，所以没有讲解，只展示代码，新手粗略过目一下即可：

以下仅展示喷火武器（BehavesLike=Fire）的粒子系统，遗留在规则文件中的废案：
```ini
[FireballLauncher];武器本体（使用喷火粒子系统）
Damage=0;无效（喷火粒子系统会使武器伤害无效）
AmbientDamage=2;穿透伤害必须先开启粒子系统，但喷火粒子系统穿透伤害无效
ROF=50;攻速，但受制于喷火粒子的消散时间
Range=4.25
Projectile=Invisible;这个抛射体不能用，需要改成例如 InvisibleLow
Speed=1;无效
Warhead=Fire
Report=FLAMTNK1
UseFireParticles=yes;开启
AttachedParticleSystem=FireStreamSys;要启用的粒子系统
Burst=2

[FireStreamSys];粒子系统
HoldsWhat=FireStream;要使用的粒子
Spawns=yes;是否用此系统不停刷出粒子
SpawnFrames=4;刷粒子的间隔，与Spawns=连用，
BehavesLike=Fire;类型：Gas丨Smoke丨Fire丨Spark丨Railgun
Image=TWLT036;喷火粒子系统的Image语句是无效的，可以删掉
Lifetime=30;设置用于产生粒子的时间（例如数值越高，会使喷火武器单次攻击的持续时间越长，期间将持续释放粒子，间接影响一次性产生的粒子数量）

[FireStream];粒子
Image=WCCLOUD1;每个粒子显示的图像，这里的喷火粒子需要有方向性，例如步兵有8个方向的朝向，这里也是如此，否则会有显示上的问题（关于图像素材(SHP)等讲解会集中在ART章节）
Deacc=0.01;粒子移动速度衰减，如果数值偏高，可能导致喷火粒子没有到达目的地就慢慢停下来了
Velocity=28.0;运动速度（视觉效果），如果设置太慢，可能导致火焰还没飞到那边，目标就已经被烧死了（
BehavesLike=Fire;类型：同上，和粒子系统的类型不一定要相同
;例如当[FireStream]-> BehavesLike=Smoke时，那么粒子将以烟雾Smoke的形式出现（粒子向"空中"升起），Gas则是将粒子释放在原地
MaxEC=500;粒子存在的最长时间限制
MaxDC=3;间隔多少帧产生一次伤害
Warhead=Fire;这里还可以挂弹头
Damage=2;粒子伤害，如果不需要可以删掉
StartStateAI=1;设置喷火粒子动画开始的帧数（从0开始为第1帧，1为第2帧）
EndStateAI=19;设置每个方向的喷火粒子动画结束的帧数（从1开始，如果每个方向都有20个图像就填20）
StateAIAdvance=6;控制图像的播放速度，数字越大越慢（喷火粒子系统貌似无效）
Translucent50State=15;产生一半攻击力的帧（图像透明度50%时）
Translucent25State=10;产生四分之一攻击力的帧（图像透明度75%时）
DeleteOnStateLimit=yes;图像播放结束后移除粒子
Normalized=yes;粒子动画播放速度是否随游戏速度改变
FinalDamageState=14;最后一个有伤害的帧数，如果设置太少，会出现火焰图像明明已经接触到目标却没有造成伤害的情况（从1开始）
Report=FLAMTNK1

;（例：共和国之辉 MOD 将喷火粒子系统重新利用在了喷火碉堡上）
```


熟悉了注册表以及单位的具体类型，下面我们再来了解一下什么是单位的基本*运动方式*：  
  
※运动方式（这部分还没弄好...）  
  Locomotor=运动模式  
  MovementZone=寻路方式  
  额外：  
  SpeedType=速度类型  
  配合`Locomotor=` `MovementZone=`  
  常见速度类型：  
  不常见速度类型：（选择性了解）  
  
  部分其他特殊运动模式：（选择性了解）  
  当配合额外语句`Teleporter=yes`时，单位运动模式会进行切换（例如超时空矿车传送回矿场再开回矿区）。  
  当配合额外语句`IsLocomotor=yes`时，`Locomotor=`一般要设置为`{92612C46-F71F-11d1-AC9F-006008055BB5}`（例如磁电坦克把单位举高高）  
（待完善）  
  
两栖   
  



  
（待完善） 

下面我们来看看如何修改单位的中文名称：  
  
你应该会在游戏根目录下看到 ra2.csf 或者 ra2md.csf 这两个文件，这是游戏语言文件（CSF文件），规则文件中的所有单位名字都通过该文件指定。我们可以进行自定义，例如将`美国大兵`的名字改为`美国队长`，或者制作新单位的时候添加新名字等等。 
  
我们来试着修改一下：  
这里推荐使用 SadPencil 制作的CSF文件修改器 [Ra2CsfToolsGUI](https://github.com/SadPencil/Ra2CsfToolsGUI)。  
   
以`v1.5.0`版本为例：  
直接将 csf 文件拖入，然后点击 `保存为.ini文件` （程序会自动询问是否跳转到刚刚保存的位置）。  

好，我们打开刚刚保存的 ini 文件来实践一下：  
  
首先我们要知道，在单位本体中指定单位名字的语句是：`UIName=Name:E1`（美国大兵），显然，我们只需在该文件中搜索`[Name:E1]`即可，你会发现`Value=美国大兵`，那么我们只需将`美国大兵`修改成你喜欢的名字就好~ 
  
修改完成后再将该文件拖回到程序窗口，点击`保存为.csf文件`（注意要将保存的 CSF 文件命名为 ra2 或者 ra2md），这样就算修改完成啦！ 

※其他一些手法：":"冒号[TEST2]:[TEST] 就是复制[TEST]的所有代码的前提下，再往[TEST2]中加入新代码或语句（注意不能加重复语句进行覆盖，以及可能会有些奇怪的问题，例如复制抛射体语句失败等问题），意为“继承”（不知道要不要放在介绍内容里讲...先预留）
  
## 单位结构 - 以神盾巡洋舰单位为例（删掉了部分无用注释）  
  
※了解完规则文件中的常用名词，现在我们可以直接来看单位的完整体代码了！不必担心，有的代码在后面的讲解中还会遇到，看不懂也没关系，现在只是让大家对代码的基本结构有个初步印象。  
  
我们来看一个示例单位：[AEGIS]（神盾巡洋舰）  

*以下语句之间有空行是为了方便查看，实际中是没有空行的。但在规则文件中你能发现一种规律，所有的单位本体、武器本体、抛射体和弹头等等这些部分都是分离开的，即在不同的部分之间留空行，修改时不应让单位、武器或弹头等代码一股脑黏在一起，否则，不规范的代码不仅影响观感，还可能会导致一系列莫名其妙的问题。*
  

首先是语句最多的第一部分：单位本体  
  
※注意看 “;” （注释）后面的解释内容：

```ini  
  
[AEGIS] ;单位本体

UIName=Name:AEGIS  ;配合CSF文件指定的单位名字

Name=Aegis Cruiser  ;名字全称，可随便填写，实际游戏中无作用

Prerequisite=GAYARD,RADAR  ;建造前提（例如造V3火箭需要雷达）

Primary=Medusa  ;主武器（神盾巡洋舰是没有副武器的，当然，你也可以手动在单位本体中添加副武器语句）  

;Secondary=  ;副武器（示例）  

;EliteSecondary=  ;三星副武器（示例） 

NavalTargeting=6  ;6

LandTargeting=1  ;1

ToProtect=yes  ;重点保护对象（对AI有用，当这个单位被攻击时，AI会调用闲置单位过来保护（只保护已方单位，不包括盟友）

Category=AFV;给AI判断用单位的分类，可忽略

Strength=800;单位生命值

Naval=yes;指定该单位是否为海军单位，并会被船坞类建筑生产

Armor=light

TechLevel=7

Sight=8

Speed=4

CrateGoodie=no

Owner=British,French,Germans,Americans,Alliance

AllowedToStartInMultiplayer=no

Cost=1200

Soylent=1200

Points=35

ROT=1

Crusher=no

Crewed=no

IsSelectableCombatant=yes

Weight=4;重量，影响单位被掀翻的难易度（例如基洛夫坠毁或无畏战舰用导弹攻击地面等，都能产生“气浪”，Damage伤害越高，ROF攻速越快，单位被“气浪”掀翻的概率越大。单位被恐怖机器人寄生，左右掀起的幅度也和重量有关）

RadialFireSegments=10

OpportunityFire=yes

DistributedFire=yes

Explosion=TWLT070,S_BANG48,S_BRNL58,S_CLSN58,S_TUMU60;单位被摧毁时产生的爆炸效果

VoiceSelect=AegisSelect  ;单位被玩家选中时的语音

VoiceMove=AegisMove  ;玩家命令其移动时的语音

VoiceAttack=AegisAttackCommand  ;玩家命令其攻击时语音

VoiceFeedback=  ;单位害怕时的语音（可自行添加，例如动员兵低血量时会害怕地叫妈咪...）

DieSound=  ;单位被摧毁的声音（单位被摧毁时的声音，而步兵一般是指死亡语音，例如各种惨叫声，可自行添加）

SinkingSound=GenLargeWaterDie  ;船被击毁后沉入水底的声音，需要Weight大于3时才会沉船，否则使用Explosion的爆炸效果

MoveSound=AegisMoveStart  ;移动的声音，例如坦克的轮子移动时发出的声音

Locomotor={2BEA74E1-7CCA-11d3-BE14-00104B62A16C}

SpeedType=Float

MovementZone=Water

ThreatPosed=25;单位的威胁值，给AI判断是否优先攻击这个单位（没有武器的单位除外）

DamAGeParticleSystems=SparkSys,SmallGreySSys;单位受损后，出现浓烟等效果的粒子系统，这里是常用的火花粒子系统[SparkSys]和烟雾粒子系统[SmallGreySSys]

VeteranAbilities=STRONGER,FIREPOWER,ROF,SIGHT,FASTER ;单位一星时赋予的额外增益属性，STRONGER 表示单位护甲获得额外加成（可以理解成更 “抗揍” 了，但单位总血量是不变的），还有 FIREPOWER 代表攻击力加成、ROF 代表攻击速度提升、SIGHT 视野变广、FASTER 移动速度变快。具体增益数值在全局代码中统一定义。

EliteAbilities=SELF_HEAL,STRONGER,FIREPOWER,ROF ;单位三星时赋予的额外增益属性，其中 SELF_HEAL 表示单位获得自动治愈能力（自动回血）。

ElitePrimary=MedusaE;单位的三星升级武器

Size=30;

TooBigToFitUnderBridge=true;

```
  
  ※至此，单位本体的基本结构展示结束，是不是觉得很多语句，比较难记？事实上一般人不大可能把所有代码都改一遍，像我们新人这种 “小修小改” 的程度，就更不用担心啦！之后还会有实操部分，熟悉了自然就会理解各类语句的含义~  
  
  下面开始是第二部分：武器本体  
  
~~~ini  

[Medusa] ;武器本体

Damage=100

ROF=15

Range=12

Speed=120

Projectile=MedusaProjectile

Warhead=SAMWH

Report=AegisAttack

TurboBoost=yes

OmniFire=yes



[MedusaE] ;武器本体（三星武器）  

可以对比未升级三星的武器，你会发现只多出了一个语句：

Burst=2 ;例如三星灰熊坦克开一次火会连发两个炮弹  
（没有这个语句将默认 Burst=1）
~~~
以上是武器本体的基本结构，下面是第三部分：抛射体和弹头
  
~~~

[MedusaProjectile] ;抛射体

Arm=1

High=yes

Shadow=no

AA=yes

AG=no

ImAGe=MEDUSA

CourseLockDuration=15

ROT=20

Scalable=yes

SubjectToCliffs=no

SubjectToElevation=no

SubjectToWalls=no



[SAMWH];弹头

CellSpread=.3

PercentAtMax=1

Verses=100%,100%,100%,100%,100%,100%,0%,0%,0%,100%,100%

InfDeath=3

AnimList=XGRYSML1,XGRYSML2,EXPLOSML

ProneDamAGe=100%
~~~  
  
※至此，神盾巡洋舰的单位结构已经展示完了！
  

## 小试身手 - 修改神盾巡洋舰  
好！看完了上面的部分，你已经对规则文件和单位结构有了初步认识，现在我们可以来改单位代码了！

你是否曾经有个疑问，为什么神盾巡洋舰不能对地攻击呢？那现在就让我们来实践一下，修改神盾巡洋舰的单位数据！

首先打开规则文件`rulesmd.ini`，跟着我的步骤修改：（不懂语句含义的可以再去看看单位结构哦）

①、神盾巡洋舰这个单位本体对应的英文是`[AEGIS]`，搜索`[AEGIS]`。记得带上括号（废话）

②、找到它的主武器代码`Primary=Medusa`，发现神盾的主武器是`Medusa`，那么搜索`[Medusa]`

③、再找到武器的抛射体代码`Projectile=MedusaProjectile`，同样搜索`[MedusaProjectile]`

④、之后发现对地攻击的代码为`AG=no`，要让它对地攻击就把no改为yes（不少人修改到这一步就以为成功了，其实不然，大多数问题是出在单位本身）

⑤、现在再来搜索一次`[AEGIS]`，回到单位本体，你可以发现以下两个代码：

`LandTargeting=1`（控制是否能够对地攻击），有0~2的选项，0表示能够，1表示不能，2用副武器对地攻击

`NavalTargeting=6`（控制对水中目标的攻击方式）有0~7选项，不多说，这里直接选择5

最后改为：

`LandTargeting=0`

`NavalTargeting=5`

到这一步感觉大功告成了？

错！其实神盾的弹头也被限制了，无法攻击建筑单位！下面来修改武器弹头

⑥、跳到②步搜索`[Medusa]`，找到弹头代码是`Warhead=SAMWH`，搜索`[SAMWH]`，你可以发现一串代码`Verses=100%,100%,100%,100%,100%,100%,0%,0%,0%,100%,100%`。

这个代码从左到右表示：无盔甲None、英雄盔甲Flak、重型盔甲Plate、轻型装甲Light、中型装甲Medium、重型装甲Heavy、**木质材料Wood、钢铁材料Steel、钢精混凝土材料Concrete**、轻型特殊装甲special_1、重型特殊装甲special_2。

这里简单解释一下：100% 表示对其有完全伤害，99%~2% 表示百分比伤害，1% 表示有伤害，但不主动攻击（例如狙击手不主动攻击坦克），0% 则无法攻击。比如开一次火造成的伤害`Damage=100` ，那么对某个装甲实际造成的伤害值就是 100 x 百分比%。不难看出`Verses=`的三个`0%`全部指向建筑，所以只要修改这三项即可。（搜索`[AEGIS]`可以看到神盾的装甲：`Armor=light`，Light对应的就是轻型装甲）

大功告成！现在你得到了一个能秒天秒地秒各种单位的神盾了！你可以根据需要，继续修改神盾的武器数据，这样就不至于那么 “变态” ···  
比如你可以继续修改武器本体：  
```ini
[Medusa]

Damage=100  ;伤害  

ROF=15  ;攻速  

Range=12  ;范围  

Speed=120  ;抛射体飞行速度（可理解为弹体飞行速度，且有速度上限）  

Projectile=MedusaProjectile  ;抛射体  

Warhead=SAMWH  ;弹头  

Report=AegisAttack  ;开火声音  

TurboBoost=yes  ;导弹攻击飞行物是否有速度加成（攻击飞行物时导弹速度是否获得倍数加成，全局语句中默认`1.5`倍）  

OmniFire=yes  ;是否可以360°无死角开火，用于无旋转炮塔单位（若没有这个语句默认为`no`，例如坦克杀手必须使自身朝向攻击目标才能开火）  
```
别忘了还有神盾升级后的武器本体：[MedusaE]  

还有控制是否能够摧毁树木`Wood=`、围墙`Wall=`和矿石`Tiberium=`的选项，这个有需要可以自行将语句添加到弹头中  
  
如果对弹头和抛射体不满意或者怕和其他单位起冲突（事实上爱国者导弹和神盾巡洋舰共用 [SAMWH] 这个弹头），可以手动添加新的弹头和抛射体，比如新增弹头，需要先复制弹头`[SAMWH]`的所有语句代码到任意位置（注意不同部分之间要留空行），改成好记的名字`[SAMWH2]`，并在弹头注册表中注册 `SAMWH2` ，这样新的弹头就做好啦~ 是不是很简单？像这样的做法当然还可以用在武器本体还有单位本体上，当然都要注册一下，注册是好习惯！（注意抛射体是无需注册的，只需记住：有对应注册表的都要注册，常用注册表都在前面列出来了，可以参考）  
  
  你可以参考多功能步兵车的弹头参数，多功能的弹头是`Warhead=HE`
  
  [HE]：`Verses=100%,100%,100%,70%,70%,35%,75%,40%,20%,80%,100%`  
    
  把对应装甲的伤害比例调低即可，甚至还可以调成负数`-100%`，攻击会给对方回血（和多功能步兵车搭载工程师的维修车不同的是，维修车的 Damage 是负数，所以它的 Verses 不是负数），或者觉得伤害不够，调成`200%`都是可以的。  
  
※需要注意的是，神盾巡洋舰并不能成为其他单位的完美模板，舰船、车辆、步兵和建筑等等，它们虽然多少都有相同的语句，但还是建议在制作新单位时，直接把相似的单位代码复制过来进行修改，例如要做一个新的直升机，就复制整个夜莺直升机的单位本体，也可以复制武器本体等其他需要的部分，这样就不至于从零开始写代码（应该没人会这么做）。  

PS：其实修改单位数据其实就跟翻目录一样，总共就三步：选取复制 → 打开搜索 Ctrl+F → 粘贴查找~  
新手需要善用搜索功能，在说明书或 [DIYRA2在线词典](https://wiki.ra2diy.com/w/Category:%E8%AF%8D%E5%85%B8) 中（Ctrl + F）自行查询标签和各种代码的功能和含义，简单又高效~  

## 随堂测试 
  
  1、在单位本体中可能会出现的语句？（ ）*单选*  
  A.Range=  
  B.Speed=  
  C.Report=  
  D.ROF=  
  E.ROT=  

  2、在武器本体中不可能出现的语句？（ ）*多选*  
  A.Strength=  
  B.Turret=  
  C.Report=  
  D.Speed=  
  E.Inviso=  

  3、以下说法正确的是：（ ）*多选*  
  A.写某一部分的单位代码时，可以不用考虑语句顺序和重复的情况  
  B.写注册表时，可以写汉字，例如在 [AircraftTypes] 里注册：13=阿帕奇  
  C.基洛夫空艇在游戏里被视为苏军的空中力量，但在代码层面上看则是载具，而不是空军  
  D.发现一些弹头和抛射体被许多武器使用了，那是因为弹头和抛射体在某些情况下具有可重复使用的特性  
   
   
   
  答案：  
  1、选B。Speed=在单位本体中代表单位移动速度。Range=在武器本体中代表攻击范围，Report=在武器本体中是开火声音，ROF=在武器本体中是攻击间隔，ROT=在抛射体中控制弹体的拐弯程度。  
  2、选ABE。Strength=在单位本体中代表单位生命值，Turret=在单位本体中代表是否有炮塔，Report=在武器本体中指开火声音，Speed=在武器本体中代表弹体飞行速度（注意区分单位本体中的Speed=），Inviso=可在抛射体中控制该抛射体是否不可见。  
  3、选CD。选项A说法错误，可不考虑顺序，但一定要考虑重复的情况；选项B说法错误，一般不可以使用特殊符号或者汉字；选项C说法正确，基洛夫空艇的运动方式为 Hover，所以被归类为载具，即 Vehicle(载具) ≠ Aircraft(空军)；选项D说法正确，一些弹头和抛射体是可以被重复利用的，很多情况下可以共用。   
  
※实际效果：（准备在博客里放图，这里放链接...）



神盾对空对地对建筑



# 第二章：art(md).ini（图像配置文件）
  
※巴拉巴拉（添加新单位打算放这里讲，不过作者更新速度非常慢...等啥时候有大把空闲时间再来做这个...B站还有许多UP主在视频中比我讲的还专业，可以去看看，像我这种纯文字的表述不一定适合所有人...）  

添加单位前，请打开压缩包里附带的一些素材，你可以看到我已经提前准备了一个单位SHP文件，

使用 Photoshop(PS) 制作图标：


不使用 Photoshop(PS) 制作图标：
[图标生成工具](https://github.bysb.net/ra2-cameo-gen/)（感谢手柄君制作的工具，如果觉得好用可以去赞助一下哦）

常用名词介绍： 
 
※SHP（图像素材文件）：  
例如步兵单位动画、建筑和图像等素材文件。  
  
※VXL（模型素材文件）、HAV（模型坐标文件）：  
例如坦克单位的模型文件，以及坦克旋转的炮塔等模型文件，一般VXL会附带一个模型坐标文件，即HAV，如果没设置好，可能会导致坦克模型浮空，或者出现单位被自身影子覆盖等等显示问题。  

※序列  

※帧  




## 随堂测试（） 
E.武器可以给不同的单位交替使用 
选项说法错误，武器一般需要根据自己的需求在相应位置进行修改，然后再给其他单位使用，随意替换武器可能会出现武器无法使用或游戏崩溃的情况。


# 第三章：sound(md).ini、eva(md).ini（语音配置文件）
  
※巴拉巴拉rerorero  


# 第四章：ai(md).ini（电脑AI配置文件）
  
※应该会配合ai(md).ini编辑器来讲解，然后大家就比较容易理解地图编辑器中作战小队之类的功能了，在找合适的工具中...（  
  
# 第五章：地图文件和地图编辑器
  
  常见的地图文件类型可以分为 `.map`、`.yrm`、`.mpr`这三种，在我们玩一些其他玩家制作的地图的时，你会发现一些单位的数值和遭遇战中的正规作战地图是不一样的，那是因为这些地图文件可以作为 “外置” 的规则文件，游戏首先读取的是地图文件内的规则，然后才是规则文件（如果规则文件中有相同规则代码，则会首先使用地图内的规则代码），这样就可以在不同的地图中放入不同的规则了，是不是很方便？当然，如果正规作战地图被修改了，比如把动员兵的 Cost 改为 Cost=0，把美国大兵的 Cost 改为 Cost=123456789 那就不叫正规作战地图了，应该叫不公平地图。  
  下面我们来了解一下*地图编辑器*（以下简称地编），我们若要修改地图（例如地形等），就要用到地编来打开这些地图文件：  
  

※特别提醒，需要改动地图时，最好手动备份一下地图文件。不应出现修改地图文件代码的同时，又打开地编对其进行修改的情况。  
※RA2 原版DIY玩家则需使用旧版的地编，里面的许多内容是相似的，所以不用担心。这里推荐使用 FA2SP，这应该是最后一个支持 RA2 原版的地编，下载：[FA2SP 1.6.2 安装包](https://pan.baidu.com/s/1u_zecwvom5cL9mt91qSDSw?pwd=RA2M) 。	  
	
  ※这里准备介绍韩大猫（Handama）的 [HDM Edition](https://github.com/handama/FA2sp/releases)  
（以下简称HDM）  
  
  ※这里准备介绍Rampastring的 [WorldAlteringEditor](https://github.com/CnCNet/WorldAlteringEditor/releases)  
（以下简称WAE）  
※（这里准备推荐一下TX地形~）  

  
  
## 其他零碎知识
  
其他零碎知识：由于考虑到新人获取参考资料的难度，以后我会贡献出目前正在制作的地图，里面有一些比较有参考意义的代码，都会作为给新人讲解的材料，目前咱们只需粗略了解一下地图文件和地图编辑器就好... 
  
  ※RGB&HSB：规则文件中[Colors]标签下方的数据看似R, G, B，但并非真的RGB格式，而是HSV格式：H(色调), S(饱和度), V(值)，需要使用[格式转换器(WWColorUtil)](https://ppmforums.com/download.php?id=63591&sid=55f42dd396e772a9aac559c34f3916fc)进行转换，例如将 LightGold=25,255,255 的 25,255,255 依次放入 H, S, V 即可算出RGB为：(255, 149, 0)，橙色。  
  
# 完事儿了
  
※如果你能完整看完这整篇 DIY 介绍，相信你是一位对红警 DIY 充满热情的新人~  
※好的，到此为止你已经是一名小有能力的 Modder 了，现在可以开始做你的 MOD 了（笑），当然，为了证明自己的学习成果，可以挑战一下章节里的随堂测试和结尾的期末测试，证明自己是不是位 “合格” 的 Modder 哦~ 
  
看到这里，有兴趣继续学习的小伙伴可以在RA2DIY论坛的 [WIKI](https://wiki.ra2diy.com/w/%E9%A6%96%E9%A1%B5) 上查阅所有语句代码，英语基础好的同学还可以去 [Modenc](https://modenc.renegadeprojects.com/Category:INI_Flags) 网站，如需文件版的中文代码手册，可以下载 [Tomny大佬的手册](https://pan.baidu.com/s/1j8yji6Mgfrkqi0Bsg36SAQ?pwd=9rwv)（文件版有参考价值，但文件版有过时的内容且不会更新，还是推荐查看wiki在线版，内容更准确和完整）。  

由于本次的 DIY 介绍尽量避开了 Ares 等扩展引擎的有关语句或代码，所以如果要了解进阶的 DIY 内容，可以查看这些引擎的说明书哦！链接和下载地址以及各种可能用到的工具都放在最底下了~ 
  
其他一些可能不怎么用到的配置文件，例如ui(md).ini，就没有介绍了，大家可以自行查阅代码解释。（如果有真的难以亲自解决的问题，可直接移步论坛 bbs.ra2diy.com，大多数问题都可以通过搜索或者询问解决，建议先搜索再询问，直接搜索关键词，例如 “动画”、“攻击” 等，多个关键词用空格分开，[推荐使用高级搜索→高级搜索入口](https://bbs.ra2diy.com/search.php?mod=forum&adv=yes)）  
  
# 期末测试  
  （PS：这人真的好喜欢出题！对于新手来说题目可能有“超纲”，请别在意...以后会慢慢补充这些相关题目的讲解！）  
## 单选测试题
  1、如何改变步兵或坦克的移动速度？（ ）  
  A.在武器本体中修改Speed=  
  B.在单位本体中修改Cost=  
  C.在单位本体中修改Speed=  
  D.在单位本体中修改Soylent=  
  
  2、某个武器的Damage=1，弹头对重型装甲的伤害比例是1%，让该武器击中某个Strength=2的重型装甲单位，不考虑其他因素，下面说法正确的是：（ ）  
  A.单位被该弹头击中后立即死亡  
  B.单位被该弹头击中后Strength=0  
  C.单位被该弹头击中后完好无损  
  D.单位被该弹头击中后Strength=1 
  
  4、下面说法正确的是？（ ）  
  A.单位分为车辆、步兵和建筑单位  
  B.副武器和主武器可以使用同一种武器  
  C.神盾巡洋舰的主武器弹头包含了抛射体  
  D.神盾巡洋舰的主武器包含抛射体和弹头  
    
  
  10、要使神盾巡洋舰不主动攻击敌方单位的可用方法有：（ ）  
  A.在弹头的Verses=中，将所有装甲的百分比改为0%  
  B.在弹头的Verses=中，将所有装甲的百分比改为1%  
  C.在单位本体中写NavalTargeting=6  
  D.在单位本体中写LandTargeting=1  
  
  答案：1、C：在单位本体中的`Speed=`是指该单位的移动速度
  
## 多选测试题  
 
  

  
  
  
  
## 判断对错题  



## 完形填空题  



## 实际操作题  
  1、使灰熊坦克的运动方式变为两栖，且无法攻击建筑和步兵。  
  例：  
  单位本体：  
  SpeedType=Amphibious  
  Locomotor={4A582742-9839-11d1-B709-00A024DDAFD1}  
  MovementZone=AmphibiousCrusher  
  或  
  SpeedType=Hover  
  Locomotor={4A582742-9839-11d1-B709-00A024DDAFD1}  
  MovementZone=AmphibiousDestroyer   
  （写其中一种移动方式即可）
  弹头：
  Verses=0%,0%,0%,100%,100%,100%,0%,0%,0%,100%,100%
  
  2、使多功能步兵车的运动方式变为飞行，并使主武器的弹头不能攻击空中单位。  
  
  
  3、使谭雅的主武器攻击范围变为`10`，并将主武器的攻击速度调整为`3`。
  
  
  
  ※注：操作题没有绝对的标准答案，能够使用其他方式在游戏中复现出与题目相同的效果即可。  


## 道德测试题  
  1、遇到某些单位代码问题无法解决时，正常应该：（多选）  
  A.在RA2DIY论坛里畅所欲言  
  B.照搬其他 MOD 的代码，然后自己修改  
  C.在RA2DIY论坛里无论如何都找不到解决方案时，在相应板块中提出问题  
  D.在RA2DIY的知识库（Wiki）中寻找答案或在论坛里搜索相关问题   
  
  
  2、想学习 MOD 中的某个效果或内容时，你可以：（多选）  
  A.修改其他 Modder 制作的代码或成品，并发布为自己的作品  
  B.解包他人的 MOD 内容，并在论坛中学术性地探讨 MOD 中的相关代码  
  C.学习那些允许修改的公开作品，或作者同意分享并允许修改的 MOD 内容  
  D.自己摸索相关代码，尝试复现相同的效果 

  
※作者的一些话：  
Modder 作为一个广泛性的词，不能很好地区分经验丰富的 DIY 大佬与 DIY 新人，而它们之间存在着 “隐形” 的分界线，且社区对新手的包容度是有限的（例如默认了新手使用 Ares 引擎），使新手获取帮助的方式变得些许曲折，一些新人由于没有使用论坛的经验，容易出现 “在错误的板块中提出‘错误’的问题” 或直接伸手要资源的情况，迎来了管理员劈头盖脸的责骂，甚至一记飞踢到垃圾桶，这种心情能够理解。其实，我是希望大家能够在论坛中多多交流与分享，大佬与新人之间友好讨论，但可惜，人性是贪婪的，大量新人索求帮助和资源，以及一些别有用心之人的存在，只能使论坛的管理愈加严格，并设置入场券等资源门槛，防止创作者们的作品被滥用。所以，作为 DIY 新人，应先懂得尊重别人的劳动成果，通过不断地学习，做出一个属于自己的优秀作品，一步步 “填充” 自己的知识储备量，总比剽窃别人的东西并声称是自己的这种行为来得 “充实” 得多，要实干、多做，有想法就要自己尝试去实现，不要希望天上掉馅饼，这就是我想对 DIY 新人说的话。  
  
※本人因为考虑到红警 DIY 圈的这种复杂环境，所以我制作了这篇针对新人的红警 DIY 介绍文章，希望能降低新手接触 DIY 的门槛。可能一些新人比较敬畏大佬，无形当中也增设了交流门槛，但我希望大家能在论坛中对大佬发布的资源或工具勇敢提出一些意见，希望新人不要因为论坛的管理方式而胆怯或放弃，你们口中的大佬，实际上也和我们一样是对 DIY 充满热情的爱好者和普通玩家，有些元老虽然离开了论坛，但有些人依旧在坚守，愿意保护曾经的创作者们留下来的心血，似乎是在捍卫着这片 “净土”，这或许也是RA2DIY论坛能够坚持下来的原因，因为他们都在用爱发电啊（  

---
#### Tips（小窍门和提示） 
1. Ares 引擎重新启用并增强了排错功能，你可以在 `RunAres.bat` 上单击鼠标右键以通过记事本或者其他文本编辑器进行编辑。建议改成以下字段：

```bash
start Syringe "gamemd.exe" %*  -NOLOGO -LOG
exit
```

> [!NOTE]
> 备注：
> - `-NOLOGO`
>   - 启动游戏时跳过 EA 商标的 LOGO 动画的播放（`ea_wwlogo.bik`）
> - `-LOG`
>   - 将实时输出 `debug.log` 日志文件至 `.\debug` 目录的功能设为默认开启。
  
2. Tail4Window 和 Tail Ace 工具：  

同时，推荐使用 [Tail4Window](https://github.com/tualatin/tailforwindows/releases) 或 [Tail Ace](https://sourceforge.net/projects/tailace/) 实现对 debug.log 文件的实时监控，查错更方便！  
  
Tail4Window：※我们主要用到的功能就是实时监控日志和筛选并高亮错误信息，这样查错比较方便  
  
我配置好了一些关键词和设置，直接导入即可：[下载配置链接](https://pan.baidu.com/s/1KKX2Ge7lh2xvtcnwQpsHHg?pwd=1111)，打开程序进入设置（[图示](https://www.picgo.net/image/%E8%AE%BE%E7%BD%AE.boTNTM)），导入配置文件（[图示2](https://www.picgo.net/image/%E8%AE%BE%E7%BD%AE2.boTYGK)）。打开 debug.log 再点击开始(Start)监控后会有延迟，开头一小部分可能会没有记录到，所以建议至少在载入页面（读条）之前进行监控，或者重新打开 debug.log，再点击开始(Start)监控，这样就能重新读取之前的所有信息。点选“Filter”即可筛选出应该注意的地方。  

Tail Ace：※这是备选工具，如果你的系统比较老旧，可以试试它，功能和 Tail4Window 相似，但不能导入配置，所以需要进行手动配置  
  
在设置里先填入[图示](https://www.picgo.net/image/%E8%AE%BE%E7%BD%AET.bo7OOL)中的数值，比如在缓冲区大小填写`2147483647`(这是最大上限)，这样几乎能无限记录数据，`0.1`表示每一毫秒刷新一次(0.1是最大下限)，`50`表示保留五十个日志历史记录(可忽略)，再下面是选择日志文件的路径(可选)，还有是否开启预先读取部分日志内容的选项(可选)。然后配置关键词时可以参考 [Tail4Window 中设置的关键词(图示)](https://www.picgo.net/image/%E8%AE%BE%E7%BD%AET2.bo7gmO)(需打开日志文件后再配置关键词)，可自由设置和调整字体大小，如果还有其他用得上的功能，大家可以试着摸索一下~  
  
  
3. Ares 引擎强化了测试手段，现在允许直接投放单位到地图进行测试了，下面放出模板代码，可直接复制使用：（具体实现手法可以查阅 Ares 说明书）  
  
*单位投放其实就是超级武器的一种，由 Ares 引擎实现。*

```ini
[Test] 
UIName=NOSTR:TEST        ;CSF 文件内对应的名称
IsPowered=false          ;false 表示无需供电
RechargeTime=-1          ;-1 表示无等待时间
Type=UnitDelivery        ;超级武器类型，这个不用修改
Cursor=Move              ;显示的鼠标指针图标
NoCursor=NoMove          ;不能投放时显示的鼠标指针图标
Range=4                  ;生效范围圆圈
LineMultiplier=2         ;圆圈的密度
Deliver.Types=AMCV,TESLA ;投放盟军基地车和磁暴线圈，可往后添加更多单位
Deliver.Owner=Invoker    ;投放出的单位归谁拥有
SW.Deferment=0           ;生效前等待的帧数
SW.AllowAI=no            ;AI电脑是否拥有这个武器
SW.AlwaysGranted=yes     ;无需建筑，直接使用（例如闪电风暴需要天气控制器这个建筑）
;PS：记得在超级武器注册表 [SuperWeaponTypes] 上注册这个超级武器  
```
  
  
  # 资源和推荐区  

※扩展引擎及说明书下载：  
 - Ares 引擎下载：[Ares下载页面](https://launchpad.net/ares/+download)（选择[目前最新版 3.0p1 ](https://launchpad.net/ares/3.0/3.0p1/+download/ares_3.0p1.zip)下载并解压至游戏目录，双击 RunAres.bat 就能用 Ares 引擎启动游戏了）
 - Ares 使用手册中文翻译版： [Ares 3.0 中文说明书（网页版）](https://ares-china.github.io/Ares-Manual/)、[Ares 3.0 中文说明书CHM文件（文件版）](https://pan.baidu.com/s/1t3p23uVwpXn32OX_4db3MQ?pwd=3jj2)
 - Phobos 引擎下载：[Phobos 下载页面](https://github.com/Phobos-developers/Phobos/releases)（选择 Release 稳定版或 Pre-release 预览版，将 Phobos.dll 和 Phobos.pdb 下载至游戏目录即可，建议和 Ares 一起安装）
 - Phobos 使用手册中文翻译版：[Phobos 中文说明书（网页版）](https://phobos.readthedocs.io/zh-cn/latest/)
   
※其他工具：  
 - XCC Mixer 下载：[XCC Mixer 安装程序](https://xhp.xwis.net/utilities/XCC_Utilities.exe)
 - Tail4Windows 实时监测日志工具：[Tail4Windows 发行版下载页面](https://github.com/tualatin/tailforwindows/releases)
 - Tail Ace 实时监测日志工具：[Tail Ace 安装程序下载](https://sourceforge.net/projects/tailace/)
 - Ra2YuriAna 分析工具：[Ra2YuriAna 作者网盘](http://1024bit.ys168.com/)
 - INIWeaver INI织网者：[INIWeaver 发行版下载页面](https://github.com/ra2diy/INIWeaver-1.0/releases)
---  
※推荐：  
 - 更多详细教程合集：[2019 年版入门教程](https://docs.qq.com/doc/p/99db114aba903e9ab82f7546990244dc9bf60ad3)  
 - KratosPP (奎秃斯) 扩展引擎和基础教程，观看 [艾木魁](https://space.bilibili.com/194846?spm_id_from=333.788.upinfo.head.click) 制作的红警DIY教程视频。 
 - 地图编辑器和红警 UI 界面等高级教程：[红警教程专栏](https://www.bilibili.com/read/readlist/rl321941)   
  
<center><font color=#FF0000><font color=#FF0000 size=6 face="Arial">DIY的初步了解 - 零基础小白也能看得懂的红警 DIY 基础介绍 V1.0</font><center>
<strong>BY DaylilyLG<strong> 
