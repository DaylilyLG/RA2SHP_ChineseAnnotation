 
# 前言和准备工作  
  
- 本文使用了 Markdown 标记语言来优化阅读体验，所以我们首先需要准备一个代码查看器（作者使用的是 [HBuilderX](https://www.dcloud.io/hbuilderx.html)，[VSCode](https://code.visualstudio.com/) 可能需要手动下载 Markdown 插件），或者用电脑自带的记事本，但不推荐（因为修改过程需要一个方便查看代码的环境），安装代码查看器后就可以用它来打开这个介绍文件了，打开后可以看到带有 “#”（井号）标题的前方有折叠按键，单击即可折叠/展开，看完了就能折叠隐藏起来，非常方便阅读。还可以到[我的个人网站](https://daylily.website/)在线观看哦（还在施工中）  
  
红色警戒2（简称 RA2）、尤里的复仇（简称 YR），由于游戏源码未公开，在大家 DIY（修改游戏数据或自定义内容）的时候或多或少会遇到游戏引擎中的硬编码限制。因此，许多红警爱好者在基于 YR 1.001 版本的基础上，开发了新的扩展引擎平台，来修复或扩充原版引擎的功能，这极大丰富了 DIY 的自由度，例如：Aers、Phobos、Kratos等。但考虑到许多新人并没有接触过这些引擎，所以本次将不使用扩展引擎的功能进行介绍，以尽量贴合新人从 “0” 开始接触 DIY 的情景。
  
内容讲解可能比较冗长或者啰嗦，但是讲得很细，新手推荐按顺序阅读，我会尽量用简单的方式介绍一些本人认为常见的 DIY 内容，从基础开始（不包含*覆盖物、污染物等杂项*和一些可能比较复杂，或者会运用到扩展引擎的内容）希望能给初次接触红警 DIY 的小伙伴提供便利~   
如果你想使用 YR 版本进行 DIY，这里推荐大家在 DIY 前预先安装 Ares 和 Phobos 引擎（下载链接放在 README.md），然后使用该修复版本：[Yrstandard-ini](https://gitee.com/PB_LAB/yrstandard-ini)（安装前注意备份），安装完毕后，咱们就可以进入下面的章节了。这边要提醒一下 RA2 版本的 DIY 玩家，由于 YR 版本的官方内容和功能是最多且最新的（官方最新版为 YR 1.001），以及 YR 有更多的软件支持，例如对 YR 有针对性优化的地图编辑器，而最新版的地图编辑器已经不支持 RA2 了，所以我推荐使用 YR 进行 DIY，而不是 RA2，除非你需要 DIY 旧版引擎的内容（例如基于旧版引擎的 RA2，或使用旧版引擎的其他版本），并*接受旧版引擎的缺陷*。  

# 第一章：rules(md).ini（规则配置文件）
  
这是包含了游戏基础规则的ini配置文件，简称规则文件，一般`红色警戒 2`对应的是 rules.ini 配置文件，而`尤里的复仇`则对应 rulesmd.ini 这个文件，两个文件的内容不同，为方便讲解，*以 rulesmd.ini 为准*。下面我们需要逐步理解这些配置文件中一些常用名词。  
  
  
首先，让我们打开规则文件：rulesmd.ini（规则配置文件）  
  
打开搜索（按 Ctrl + F 进行搜索），搜索 [AEGIS]，这是神盾巡洋舰，为确保搜索到正确内容，注意要带上`[]`括号，你会看到这样的代码：  
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
没错，这一部分就是神盾巡洋舰的`单位本体`（特指这部分的代码），还可以简称`单位`（泛指所有相关的代码）。而在 [AEGIS] 下方的代码可以被称为`语句`，而`标签`涵盖范围广（个人理解），示意代码：  
~~~ini
[AEGIS]     标签/代码  
UIName=     语句/标签/代码  
Name=       语句/标签/代码 
......=     语句/标签/代码  
~~~
可以说是某个`标签`，或者某个`语句`，甚至统称为`代码`也是没问题的，请依据个人习惯来决定。  
仔细看看，还会发现有的语句或标签会带有 “;” 这个符号，这表示*在这符号之后的一行代码将无效化*，即成为`注释`，我们可以直接无视它们，例如控制单位建造数量的是这个语句：`;BuildLimit=2`，可以看到已经被注释了，所以不会有任何作用，忽略即可。我们也可以手动取消注释（把 “;” 这个符号删除），或把注释保留下来，另起一行，添加语句`BuildLimit=`，例如：  
~~~ini
[AEGIS]
......省略一大段......  
;BuildLimit=2  ←这是保留的注释，取消注释前要注意不能有重复的语句！  
BuildLimit=数字  ←另起一行，可以填写阿拉伯数字，例如谭雅的建造数量限制为一个，填 1 即可。  
ElitePrimary=MedusaE  ; ←像这样把注释放到后面也是可以的哦~
Size=30  ; ←注意是英文的 “;”、而不是中文的 “；”！  
TooBigToFitUnderBridge=true  
~~~
  
其实被注释的整段代码都可以删除，毕竟已经 “没有用” 了，但我们有时候可能会忘记一些代码上的改动，这时注释还可以起到备忘的作用，所以我们可以适当保留一些注释。   
  
在 [AEGIS] 标签的下方可以看到这个语句`Primary=Medusa`，我们可以把`Primary`和`Medusa`分成两部分来看，`Primary`可以看作是`武器类型`，`Medusa`则是`武器`（不难看出，这行代码给单位指定了 [Medusa] 作为它的武器），下面先来认识一下`武器类型`：  

- 主武器`Primary=`：单位的主要武器，以及单位的三星主武器`ElitePrimary=`，单位升级至三星后会立即换用`ElitePrimary=`所指定的武器，需要注意的是，有的单位是没有这种语句的，或者出现没有指定武器、`ElitePrimary=`被注释等情况，一般常见于平民单位，以及遥控坦克、工程师等，即便升级到三星，也会因为没有`ElitePrimary=`语句，而继续使用`Primary=`。 

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
Damage=100  
ROF=15      
Range=12    
Speed=120  
Projectile=MedusaProjectile  
Warhead=SAMWH  
Report=AegisAttack  
TurboBoost=yes  
OmniFire=yes  
~~~
现在你看到的部分就是`武器本体`（特指部分代码），简称`武器`（泛指相关代码），这些语句是武器的*基本属性*，例如修改单位的伤害（攻击力）`Damage=`、攻击范围`Range=`等，都是在该部分修改的。
  
可以看到武器中的语句并不多，其中最主要的就是`Projectile=MedusaProjectile`和`Warhead=SAMWH`这两个语句，所以我们再次用同样的方法搜索`[MedusaProjectile]`和`[SAMWH]`，可以分别看到以下内容：    
```INI
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
这些内容便是`武器`的中的`抛射体`和`弹头`，武器的*具体属性*都要通过它们设置，例如用抛射体决定武器是否隔着围墙也能打到对面`SubjectToWalls=`，以及在弹头的设置中对某种车辆或建筑的装甲造成特定的伤害比例`Verses=`，这些我们在之后都会讲到。  
  
  现在我们来简单了解一下什么是*单位*，单位的类型有很多，例如：车辆、步兵、建筑、海军、和空军等等都可以称作*单位*。其中，车辆、直升机、飞艇、飞碟及海军为*载具*（具体分类会在下面介绍）。  
※运动方式  
  Locomotor=运动模式  
  MovementZone=寻路方式  
  额外：  
  SpeedType=速度类型  
  配合`Locomotor=` `MovementZone=`  
  常见速度类型：  
  不常见速度类型：（选择性了解）  
  
  部分其他特殊移动例：  
  当配合额外语句`Teleporter=`时，单位运动模式会进行切换（例如超时空矿车传送回矿场再开回矿区）。  
  当配合额外语句`IsLocomotor=`时，`Locomotor=`一般要设置为`{92612C46-F71F-11d1-AC9F-006008055BB5}`（例如磁电坦克把单位举高高）  
（待完善）  
  
两栖  
  
※全局标签/语句  
  
※注册表及注册内容  
  
（待完善）
  
部分常用注册表：  
[InfantryTypes] ;注册步兵单位(Infantry)  
  
[AircraftTypes]  ;注册空军单位(Aircraft)  
  
[VehicleTypes]  ;注册载具(Vehicle)  
  
需要注意，夜莺直升机和基洛夫空艇的运动方式实际上为 Hover 悬浮速度类型，Hover 一般是归类为*载具*（即 Vehicle，而非 Aircraft）
  
[BuildingTypes]  ;注册建筑单位(Building)  
  
[Animations]  ;注册动画  
  
  关于修改动画的具体内容我们会在第二章详细讲解
  
[Warheads]  ;注册弹头  
  
[WeaponTypes]  ;Ares引擎内容，选择性了解  
  
※超级武器  ;有Ares引擎内容，选择性了解  
  
（待完善）  
  
[SuperWeaponTypes]
  
※粒子系统  
  
[Particles]  ;注册粒子
[ParticleSystems]  ;注册粒子系统
  
（待完善） 
  
你应该会在游戏根目录下看到 ra2.csf 或者 ra2md.csf 这两个文件，这是游戏语言文件（CSF文件），规则文件中的所有单位名字都通过该文件指定。我们可以进行自定义，例如将`美国大兵`的名字改为`美国队长`，或者制作新单位的时候添加新名字等等。 
  
让我们来试着修改一下：  
这里推荐使用 [Ra2CsfToolsGUI](https://github.com/SadPencil/Ra2CsfToolsGUI) 来修改 CSF 文件。  
   
以`v1.5.0`版本为例：  
直接将 csf 文件拖入，然后点击 `保存为.ini文件` （程序会自动询问是否跳转到刚刚保存的位置）。  

好的，我们打开刚刚保存的 ini 文件来实践一下：  
  
首先我们要知道，在单位本体中指定单位名字的语句是：`UIName=Name:E1`（美国大兵），显然，我们只需在该文件中搜索`[Name:E1]`即可，你会发现`Value=美国大兵`，那么我们只需将`美国大兵`修改成你喜欢的名字就好~ 
  
修改完成后再将该文件拖回到程序窗口，点击`保存为.csf文件`（注意要将保存的 CSF 文件命名为 ra2 或者 ra2md），这样就算修改完成啦！ 

  
## 单位结构 - 以神盾巡洋舰单位为例（删掉了部分无用注释）  
  
※了解完规则文件中的常用名词，现在我们可以直接来看单位的完整体代码了！不必担心，有的代码在后面的讲解中还会遇到，看不懂也没关系，现在只是让大家对代码的基本结构有个初步印象。  
  
我们来看一个示例单位：[AEGIS]（神盾巡洋舰）  

*以下语句之间有空行是为了方便查看，实际中是没有空行的。但在规则文件中你能发现一种规律，所有的单位本体、武器本体、抛射体和弹头等等这些部分都是分离开的，即在不同的部分之间留空行，修改时不应让单位、武器或弹头的代码一股脑黏在一起，否则，不规范的代码不仅影响观感，还可能会导致一系列莫名其妙的问题。*
  

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

Category=AFV

Strength=800

Naval=yes

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

Weight=4

RadialFireSegments=10

OpportunityFire=yes

DistributedFire=yes

Explosion=TWLT070,S_BANG48,S_BRNL58,S_CLSN58,S_TUMU60

VoiceSelect=AegisSelect  ;单位被玩家选中时的语音

VoiceMove=AegisMove  ;玩家命令其移动时的语音

VoiceAttack=AegisAttackCommand  ;玩家命令其攻击时语音

VoiceFeedback=  ;单位害怕时的语音（一般步兵才有害怕语音，例如动员兵低血量时会害怕地叫妈咪...可自行添加）

DieSound=  ;单位被摧毁的声音（单位被摧毁时的声音，而步兵一般是指死亡语音，例如各种惨叫声，可自行添加）

SinkingSound=GenLargeWaterDie  ;船被击毁后沉入水底的声音

MoveSound=AegisMoveStart  ;移动的声音，例如坦克的轮子移动时发出的声音

Locomotor={2BEA74E1-7CCA-11d3-BE14-00104B62A16C}

SpeedType=Float

MovementZone=Water

ThreatPosed=25

DamAGeParticleSystems=SparkSys,SmallGreySSys

VeteranAbilities=STRONGER,FIREPOWER,ROF,SIGHT,FASTER ;单位一星时赋予的额外增益属性，STRONGER 表示单位护甲获得额外加成（可以理解成更 “抗揍” 了，但单位总血量是不变的），还有 FIREPOWER 代表攻击力加成、ROF 代表攻击速度提升、SIGHT 视野变广、FASTER 移动速度变快。具体增益数值在全局代码中统一定义。

EliteAbilities=SELF_HEAL,STRONGER,FIREPOWER,ROF ;单位三星时赋予的额外增益属性，其中 SELF_HEAL 表示单位获得自动治愈能力（自动回血）。

ElitePrimary=MedusaE

Size=30

TooBigToFitUnderBridge=true

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
  ※以上是武器本体的基本结构，下面是第三部分：抛射体和弹头
  
~~~ini  

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

①、神盾巡洋舰这个单位本体对应的英文是[AEGIS]，搜索[AEGIS]。记得带上括号（废话）

②、找到它的主武器代码Primary=Medusa，发现神盾的主武器是Medusa，那么搜索[Medusa]

③、再找到武器的抛射体代码Projectile=MedusaProjectile，同样搜索[MedusaProjectile]

④、之后发现对地攻击的代码为AG=no，要让它对地攻击就把no改为yes（不少人修改到这一步就以为成功了，其实不然，大多数问题是出在单位本身）

⑤、现在再来搜索一次[AEGIS]，回到单位本体，你可以发现以下两个代码：

LandTargeting=1（控制是否能够对地攻击），有0~2的选项，0表示能够，1表示不能，2用副武器对地攻击

NavalTargeting=6（控制对水中目标的攻击方式）有0~7选项，不多说，这里直接选择5

最后改为：

LandTargeting=0

NavalTargeting=5

到这一步感觉大功告成了？

错！其实神盾的弹头也被限制了，无法攻击建筑单位！下面来修改武器弹头

⑥、跳到②步搜索[Medusa]，找到弹头代码是Warhead=SAMWH，搜索[SAMWH]，你可以发现一串代码`Verses=100%,100%,100%,100%,100%,100%,0%,0%,0%,100%,100%`。

从左到右：`无盔甲None`、`英雄盔甲Flak`、`重型盔甲Plate`、`轻型装甲Light`、`中型装甲Medium`、`重型装甲Heavy`、**木质材料Wood、钢铁材料Steel、钢精混凝土材料Concrete**、`轻型特殊装甲special_1`、`重型特殊装甲special_2`。

这里简单解释一下：100% 表示对其有完全伤害，99%~2% 表示百分比伤害，1% 表示有伤害，但不主动攻击（例如狙击手不主动攻击坦克），0% 则无法攻击。比如开一次火造成的伤害`Damage=100` ，那么对某个装甲实际造成的伤害值就是 100 x 百分比%。不难看出`Verses=`的三个`0%`全部指向建筑，所以只要修改这三项即可。（搜索`[AEGIS]`可以看到神盾的装甲：`Armor=light`，Light对应的就是轻型装甲）

※大功告成！现在你得到了一个能秒天秒地秒各种单位的神盾了！你可以根据需要，继续修改神盾的武器数据，这样就不至于那么... “变态” ···  
比如你可以继续修改武器本体：  

[Medusa]

Damage=100  ;伤害  

ROF=15  ;攻速  

Range=12  ;范围  

Speed=120  ;弹体飞行速度  

Projectile=MedusaProjectile  ;抛射体  

Warhead=SAMWH  ;弹头  

Report=AegisAttack  ;开火声音  

TurboBoost=yes  ;导弹攻击飞行物是否有速度加成（攻击飞行物时导弹速度是否获得倍数加成，全局语句中默认`1.5`倍）  

OmniFire=yes  ;是否可以360°无死角开火，用于无旋转炮塔单位（若没有这个语句默认为`no`，例如坦克杀手必须使自身朝向攻击目标才能开火）  

别忘了还有神盾升级后的武器本体：[MedusaE]  
  
你还可以参考多功能步兵车的弹头参数，多功能的弹头是`Warhead=HE`

[HE]：Verses=100%,100%,100%,70%,70%,35%,75%,40%,20%,80%,100%  
  
把对应装甲的伤害比例调低即可，当然还可以调成负数 -100%，攻击会给对方回血（和多功能步兵车搭载工程师的维修车不同的是，维修车的 Damage 是负数，所以它的 Verses 并非负数），或者 200% 都是可以的。

当然，如果对弹头不满意，还可以新增弹头，比如复制弹头 [SAMWH] 的所有语句代码到任意位置（注意不同部分之间要留空行），改成好记的名字 [SAMWH2]，并在弹头注册表中注册 `SAMWH2` ，这样新的弹头就做好啦！是不是很简单！像这样的做法当然还可以用在武器本体还有单位本体上，当然都要注册一下，注册是好习惯！（注意抛射体是无需注册的，只需记住：有对应注册表的都要注册）。  
  
※需要注意的是，神盾巡洋舰并不能成为其他单位的完美模板，舰船、车辆、步兵和建筑等等，它们虽然都有共同的语句，但还是建议在制作新单位时，直接把相似的单位代码复制过来进行修改，例如要做一个新的直升机，就复制整个夜莺直升机的单位本体，也可以复制武器本体等其他需要的部分，这样就不至于从零开始写代码（应该没人会这么做）。  

PS：其实修改单位数据其实就跟翻目录一样，总共就三步：选取复制 → 打开搜索 Ctrl+F → 粘贴查找~  
DIY 新手需要善用搜索功能，在说明书或 [DIYRA2在线词典](https://wiki.ra2diy.com/w/Category:%E8%AF%8D%E5%85%B8) 中（Ctrl + F）自行查询标签和各种代码的功能和含义，简单高效~  

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



  
  
  
  
  
  
  
  
  
  
  
  答案：  
  1、选B，Speed=在单位本体中代表单位移动速度。Range=在武器本体中代表攻击范围，Report=在武器本体中是开火声音，ROF=在武器本体中是攻击间隔，ROT=在抛射体中控制弹体的拐弯程度。  
  2、选ABE，Strength=在单位本体中代表单位生命值，Turret=在单位本体中代表是否有炮塔，Report=在武器本体中指开火声音，Speed=在武器本体中代表弹体飞行速度（注意区分单位本体中的Speed=），Inviso=可在抛射体中控制该抛射体是否不可见。
  
实际效果：

null

神盾对空对地对建筑



# 第二章：art(md).ini（图像配置文件）
  
巴拉巴拉  

常用名词介绍： 
 
※SHP（图像素材文件）：  
例如步兵单位动画、建筑和图像等素材文件。  
  
※VXL（模型素材文件）、HAV（模型坐标文件）：  
例如坦克单位的模型文件，以及坦克旋转的炮塔等模型文件，一般VXL会附带一个模型坐标文件，即HAV，如果设置不对，会导致坦克模型在游戏里看起来像浮空一样，或者出现遁地和斜着开等等显示位置上的问题。  

※序列  

※帧  








# 第三章：sound(md).ini、eva(md).ini（语音配置文件）
  
巴拉巴拉  


# 第四章：ai(md).ini（电脑AI配置文件）
  
这个配置文件中的内容对于新手来说可能比较难懂，我会尝试用简单的方式来介绍：巴拉巴拉  

# 第五章：地图文件和其他零碎知识
  
  常见的地图文件类型可以分为 `.map`、`.yrm`、`.mpr`这三种，在我们玩一些其他玩家制作的地图的时，你会发现一些单位的数值和遭遇战中的正规作战地图是不一样的，那是因为这些地图文件可以作为 “外置” 的规则文件，游戏首先读取的是地图文件内的单位规则，然后才是规则文件（如果规则文件中有相同规则代码，则会首先使用地图内的规则代码），这样就可以在不同的地图中放入不同的规则了，是不是很方便？当然，如果正规作战地图被修改了，比如把动员兵的 Cost 改为 Cost=0，把美国大兵的 Cost 改为 Cost=123456789 那就不叫正规作战地图了，应该叫不公平地图。
  
  其他零碎知识：由于考虑到新人获取参考资料的难度，以后我会贡献出目前正在制作的地图，里面有一些比较有参考意义的代码，都会作为给新人讲解的材料（因为除非作者允许，一般不提倡解包其他 MOD 的内容），目前咱们只需粗略了解一下什么是地图文件就好...
  



# 完事儿了
  
※如果你能完整看完这整篇 DIY 介绍，相信你是一位对红警 DIY 充满热情的新人~  
※好的，到此为止你已经是一名小有能力的 Modder 了，现在可以开始做你的 MOD 了（笑），当然，为了证明自己的学习成果，可以挑战一下章节里的随堂测试和结尾的期末测试，证明自己是不是位 “合格” 的 Modder 哦~ 
  
看到这里，有兴趣继续学习的小伙伴可以在红警DIY论坛的wiki百科上学习基础语句代码，英语基础好的同学还可以去[modenc](https://modenc.renegadeprojects.com/Category:INI_Flags)，如需文件版的代码手册，可以下载[Tomny大佬的手册](https://pan.baidu.com/s/1j8yji6Mgfrkqi0Bsg36SAQ?pwd=9rwv)（文件版有参考价值，但文件版有过时的内容，且不会更新，还是推荐查看wiki在线版，内容更准确和完整）  
其他一些可能不怎么用到的配置文件，例如ui(md).ini，就没有介绍了，大家可以自行查阅代码解释。

（如果有真的难以亲自解决的问题，可直接移步论坛 bbs.ra2diy.com，大多数问题都可以通过搜索或者询问解决，建议先搜索再询问，直接搜索关键词，例如 “动画”、“攻击” 等，多个关键词用空格分开，[推荐使用高级搜索→高级搜索入口](https://bbs.ra2diy.com/search.php?mod=forum&adv=yes)）  
  
# 期末测试  
  
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
  
  
  
  ※注：操作题没有绝对的标准答案，能够使用其他方式在游戏中复现出与答案相同的效果即可。  


## 道德测试题  
  1、遇到某些单位代码问题无法解决时，正常应该：  
  A.在RA2DIY论坛里畅所欲言  
  B.照搬其他 MOD 的代码，然后自己修改  
  C.使用百度或谷歌等搜索引擎搜索答案  
  D.在RA2DIY的知识库（Wiki）中寻找答案或在论坛里搜索问题关键词  
  E.在RA2DIY论坛里无论如何都找不到解决方案时，在相应板块中提出问题  

  
※作者的一些话：  
Modder 作为一个广泛性的词，不能很好地区分经验丰富的 DIY 大佬与 DIY 新人，而它们之间存在着 “隐形” 的分界线，且社区对新手的包容度是有限的（例如默认了新手使用 Ares 引擎），使新手获取帮助的方式变得些许曲折，一些新人由于没有使用论坛的经验，容易出现 “在错误的板块中提出‘错误’的问题” 或直接伸手要资源的情况，迎来了管理员劈头盖脸的责骂，甚至一记飞踢到垃圾桶，这种心情能够理解。其实，我是希望大家能够在论坛中多多交流与分享，大佬与新人之间友好讨论，但可惜，人性是贪婪的，大量新人索求帮助和资源，以及一些别有用心之人的存在，只能使论坛的管理愈加严格，并设置入场券等资源门槛，防止创作者们的作品不被滥用。所以，作为 DIY 新人，应先懂得尊重别人的劳动成果，通过不断地学习，做出一个属于自己的优秀作品，一步步 “填充” 自己的知识储备量，总比剽窃别人的东西并声称是自己的这种行为来得 “充实” 得多，要实干、多做，有想法就要自己尝试去实现，不要希望天上掉馅饼，这就是我想对 DIY 新人说的话。  
  
※本人因为考虑到红警 DIY 圈的这种复杂环境，所以我制作了这篇针对新人的红警 DIY 介绍文章，希望能降低新手接触 DIY 的门槛。可能一些新人比较敬畏大佬，无形当中也增设了交流门槛，但我希望大家能在论坛中对大佬发布的资源或工具勇敢提出一些意见，希望新人不要因为论坛的管理方式而胆怯或放弃，你们口中的大佬，实际上也和我们一样是对 DIY 充满热情的爱好者和普通玩家，有些元老虽然离开了论坛，但有些人依旧在坚守，愿意保护曾经的创作者们留下来的心血，似乎是在捍卫着这片 “净土”，这或许也是RA2DIY论坛能够坚持下来的原因，因为他们都在用爱发电啊（
  
#### Tips（小窍门和提示） 
※ Ares 引擎增强了查错功能，你可以鼠标右键对 RunAres.bat 进行编辑，用记事本或者其他的代码查看器打开，改成以下字段：  
    
	Syringe "gamemd.exe" %*  -NOLOGO -LOG
    exit

    备注：-NOLOGO(关闭EA商标的LOGO动画) -LOG(实时输出debug.log)，实时输出的 debug.log 日志文件在 debug 文件夹。
	
同时，推荐使用 [Tail4Window](https://github.com/tualatin/tailforwindows/releases) 或 [Tail Ace](https://sourceforge.net/projects/tailace/) 实现对 debug.log 文件的实时监控，查错更方便！  
  
  ~
  
※ Ares 引擎强化了测试手段，现在允许直接投放单位到地图进行测试了，下面放出模板代码，可直接复制使用：（具体实现手法可以查阅 Ares 说明书）  
  
`单位投放其实就是超级武器的一种，由 Ares 引擎实现，所以这里我又要推荐安装一下 Ares 引擎了（啰嗦），当然还可以考虑安装其他拓展引擎，例如 Phobos（Phobos 的功能作者还在探索学习中...Phobos 与 Ares 结合使用达到最佳效果）。`

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
	;PS：记得在超级武器注册表[SuperWeaponTypes]上注册这个超级武器
  
<center><font color=#FF0000><font color=#FF0000 size=6 face="Arial">DIY的初步了解 - 零基础小白也能看得懂的红警 DIY 基础介绍 V1.0</font><center>
<strong>BY Daylily<strong> 
