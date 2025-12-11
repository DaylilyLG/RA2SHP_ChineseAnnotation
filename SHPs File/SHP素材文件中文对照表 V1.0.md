# 对照表
 ***使用了 Markdown 标记语言优化阅读体验，推荐在线阅览，或使用 HBuilder、VScode 等软件打开***

## 前言：
- 这是给初次接触红警DIY的朋友们制作的，将所有shp文件名用中文标注，方便用中文查找shp素材，新手用中文查找更方便，对照中文并搜索shp文件名就能在相关位置找到想要的素材。该对照表是单独附带在shp提取文件的压缩包内的，若你熟练使用 XCC Mixer 工具进行提取，则只需解压此对照表即可。压缩包解压后的文件体积较大，你需要解压到磁盘空间充足的位置。（个人推荐使用 Ra2YuriAna 作为从零开始的DIY工具，附带简单的语句标签翻译，在这之上就推荐INI辅助工具 INIWeaver，对于制作复杂单位非常有帮助，但不支持实时修改 INI 内容） 

## 注意事项：
- 有些shp官方未注册，例如在artmd.ini中的apmuzzle天启坦克开火、yuricntl尤里攻击，即便在地图文件（yrm、map等）中注册也无法修复，需要单独注册在规则文件(rules.ini, rulesmd.ini)，若没有使用规则文件，则须在地图文件中另外注册并替换。
- 有的shp是Westwood(西木)制作组遗留下来的产物，例如红警2(RA2)的前身"命令与征服2：泰伯利亚之日"(TS2)游戏的素材，若要使用遗留的素材通常要进行调整（例如修改规则文件、换用正确的色盘来显示等），以及一些用来测试的shp可能会没有色盘或者找不到对应的注册名，有的虽然注册了也添加了色盘，但游戏里没有使用这个素材等等，均为正常现象。（游戏还存在诸多遗留的硬编码，在DIY过程中可能会遇到无法解决的硬性问题，推荐安装ares或phobos等平台，能改善或解决很多问题）
- 由于文件实在太多，而且本人DIY水平也不高，就只能粗略地进行分类了，可能还有描述错误或遗漏的地方，还请见谅... 一些地方打了问号`？`，表示我不确定是什么东西或者不知道怎么解释... 需要注意的是，shp存在*共用现象*，例如美国大兵射击地面的效果PIFFPIFF，游戏经常使用在其他单位上，以及坦克、船只还有步兵都可能会用到的120mm炮弹等等，泛用性很高。还有每个阵营的工程师共用engineer单个shp，“技师”与“绿衣男平民”共用单个shp，超时空传送共用同种传送动画等等，都是使用同一种素材，更多的我就不列举了。还有一些我认为会经常用到或者合适拿来DIY的动画效果，我会给它们备注`通用素材`给大家参考。

* 以下所有shp文件使用了 XCC Mixer 1.47 提取，提取位置已标明，这些shp素材 ***仅包含单位、建筑、动画及建造栏图标！***，其他shp或素材均未提取（tem覆盖图文件或其他零碎素材等）。※目前只有建筑部分未完成，其他部分供参考！

- 格式：`shp文件名   中文描述  （说明备注）`
	
## 红色警戒2原版mix的shp中文名称：（位置：ra2.mix）

### 一、动画和步兵单位（位置：ra2.mix > conquer.mix）
#### 1、未分类：
    120mm        炮弹（坦克、驱逐舰、防空步兵等单位开火后的出膛炮弹，通用素材)
    50cal        两帧会动的点？（啥玩意）
    bbblelrg     潜艇抛射体产生的气泡
    beacon       信标（泰伯利亚的shp，如果颜色显示不正确，一般换用泰伯利亚的对应色盘即可正确显示，下同
    bomb         正在旋转的炸弹（泰伯利亚
    buildngz     给建筑用的色盘？
    canister     正在旋转的霰弹筒（泰伯利亚
    cellsel      带颜色的框
    chronobm     离子炮光束？（泰伯利亚
    chronodb     离子炮爆炸？（泰伯利亚
    chronofs     离子炮爆炸？（球状）（泰伯利亚
    chronosb     离子炮爆炸？（泰伯利亚
    crat0a       弹坑？（泰伯利亚
    crat0b       弹坑？（泰伯利亚
    crat0c       弹坑？（泰伯利亚
    crat01       弹坑？（泰伯利亚
    crat02       弹坑？（泰伯利亚
    crat03       弹坑？（泰伯利亚
    crat04       弹坑？（泰伯利亚
    dbris1lg     摧毁建筑后蹦出的碎片1lg
    dbris1sm     摧毁建筑后蹦出的碎片1sm
    dbris2lg     摧毁建筑后蹦出的碎片2lg
    dbris2sm     摧毁建筑后蹦出的碎片2sm
    dbris3lg     摧毁建筑后蹦出的碎片3lg
    dbris3sm     摧毁建筑后蹦出的碎片3sm
    dbris4lg     摧毁建筑后蹦出的碎片4lg
    dbris4sm     摧毁建筑后蹦出的碎片4sm
    dbris5lg     摧毁建筑后蹦出的碎片5lg
    dbris5sm     摧毁建筑后蹦出的碎片5sm
    dbris6lg     摧毁建筑后蹦出的碎片6lg
    dbris6sm     摧毁建筑后蹦出的碎片6sm
    dbris7lg     摧毁建筑后蹦出的碎片7lg
    dbris7sm     摧毁建筑后蹦出的碎片7sm
    dbris8lg     摧毁建筑后蹦出的碎片8lg
    dbris8sm     摧毁建筑后蹦出的碎片8sm
    dbris9lg     摧毁建筑后蹦出的碎片9lg
    dbris9sm     摧毁建筑后蹦出的碎片9sm
    dbri-wm1     摧毁建筑后蹦出的碎片wm1
    dbri-wm2     摧毁建筑后蹦出的碎片wm2
    dbri-wm3     摧毁建筑后蹦出的碎片wm3
    dbrs10lg     摧毁建筑后蹦出的碎片s10lg
    dbrs10sm     摧毁建筑后蹦出的人s10sm
    death_a      尸体逐渐消失动画（头朝左下
    death_b      尸体逐渐消失动画（头朝右上
    death_c      尸体逐渐消失动画（头朝上
    death_d      尸体逐渐消失动画（头朝右
    death_e      尸体逐渐消失动画（头朝左
    death_f      尸体逐渐消失动画（头朝下
    discus       铁饼（泰伯利亚）
    dragon       较长的导弹（黄蜂、入侵者战机、黑鹰战机等单位发射的导弹，通用素材
    dredmiss     正在旋转的导弹（泰伯利亚
    droppod      空降仓逐渐消失动画，朝左（泰伯利亚
    droppod2     空降仓逐渐消失动画，朝右（泰伯利亚
    drum01       桶（泰伯利亚
    drum02       桶2（泰伯利亚
    durasmoke    导弹尾焰（类似无畏舰发射导弹的尾焰，但这个小一点
    e_enhn       黄色地块
    ebtn-dn      ？（往下按的按钮？
    ebtn-up      ？（往上按的按钮？
    emp_fx01     EMP效果（泰伯利亚
    fire01       着火，燃烧1（一般用在建筑残血 DamageFireTypes=，尤里新兵的弹头火焰也是这个
    fire02       着火，燃烧2（一般用在建筑残血 DamageFireTypes=
    fire03       着火，燃烧3（一般用在建筑残血 DamageFireTypes=
    fog          战争迷雾？（可能是未探索黑幕和已探开区域的衔接部分
    gaslrgmk     一缕绿色的烟（泰伯利亚
    gghunt       ？（游戏未使用的素材，不清楚是什么
    h2o_exp1     炮弹或导弹攻击水面溅起的水花（大
    h2o_exp2     炮弹或导弹攻击水面溅起的水花（中
    h2o_exp3     炮弹或导弹攻击水面溅起的水花（小
    healone      医疗（泰伯利亚
    hlight       灯光色盘？
    inviso       无图像的两帧（一般用在不需要图像的地方，可在抛射体下写 Image=inviso，也可直接写防空步兵用的 Inviso=yes，例如防空步兵打飞机，就没有120mm炮弹显示了，而且与 Image=inviso 不同的是，使用 Inviso=yes 开火后可立即击中目标，无需间隔时间）
    ionbeam      轨道炮光束（泰伯利亚
    lgrysmk1     毒气（这个动画没有在art里，不清楚是什么原因，可能是由粒子系统控制，一般shp需要在art里进行调整
    medusa       较短的导弹（神盾、多功能步兵车等单位发射的导弹，通用素材
    missile      导弹（未使用素材
    null         ？（打不开，估计是真的 null，无效的shp
    oilleak      石油泄露（泰伯利亚
    oregath      矿车采矿吸取矿石？（好像art里找不到注册名
    palet01      调色板？
    palet02      调色板？
    palet03      调色板？
    palet04      调色板？
    parabomb     空投炸弹（未使用素材
    parach       空降伞
    patriot      导弹（未使用素材
    pipbrd       这是单位血条的背景，例如点击基地车，你会看到基地车上方的血条外面包裹着白色框（注意要选择红警一的色盘）
    pips         这是单位血条的素材，例如单位头顶血条的绿色黄色红色像素就是用它来显示，还有单位升星的图标，占领医院后在血条后方显示的红十字治疗图标等等都在这里（注意要选择红警一的色盘）
    pips2        剩余弹药颜色，运输船下方的容量框显示的颜色等等（注意要选择红警一的色盘）
    place        地表
    pmatkmove    攻击（泰伯利亚   
    pmgrdarea    保护（泰伯利亚  
    pod          空降仓，左右视图（泰伯利亚
    podring      空降仓使用的落地动画40帧（未使用素材
    progbar      项目条？
    progbar2     项目条2？
    progbarm     项目栏？
    psiwarn      心灵探测器预测核弹的攻击位置（但游戏显示的色盘不对
    pulsball     推出去的球？（泰伯利亚
    select       选择框（泰伯利亚，选取单位时会有一个方框
    sgrysmk1     浓烟（建筑残血后冒出的浓烟，通用素材
    shroud       覆盖物色盘？
    ship         ？（他说是船，好吧
    smokey       烟雾（泰伯利亚
    smokey2      导弹尾焰2（类似 durasmoke，但这个尾焰看起来更长一些
    spdg         乌贼缠绕（乌贼缠绕船只或潜艇，左右摇摆
    sqdp         乌贼的影子？（未使用素材
    sqdwake      乌贼苏醒（未使用素材，水面冒泡效果
    sredsmk1     爆炸效果？（泰伯利亚
    t4_ib        迷你水花（狙击手或谭雅等单位攻击水面溅起水花，但游戏未使用该素材
    torpedo      鱼雷（泰伯利亚
    twnk1        矿石闪烁效果（特殊全局语句控制：OreTwinkle=
    ucblood      石头？（清除驻军建筑部队的动画？
    ucelec       石头？（清除驻军建筑部队的动画？
    v3takoff     V3火箭起飞尾气
    v3trail      V3火箭尾焰
    wake1        单位在水中行驶的水流效果
    warpaway     某单位被超时空军团兵传送走的效果
    warpin       某单位被传送入地图？（未使用素材
    warpout      超时空矿车、超时空军团兵等单位传送的效果（通用素材
    wethb        离子炮光束？（未使用素材
 
#### 2、单位：
    adog         盟军狗（警犬
    adogp        盟军狗飞扑攻击
    all          鳄鱼
    ccomand      超时空海豹突击队
    civ1         黄衣女平民
    civ2         白衣男平民
    civ3         绿衣男平民（技师）
    civa         德克萨斯平民A
    civan        超时空伊文
    civb         德克萨斯平民B
    civbbp       棒员运动员
    civbf        海滩女平民
    civbfm       海滩胖男平民
    civbtm       海滩男平民
    civc         黑衣蓝裤平民（牛仔）
    civsf        红衣女平民
    civsfm       灰衣老人
    civstm       蓝衣男平民
    cleg         超时空军团兵
    cons         动员兵
    cow          奶牛
    deso         辐射工兵
    dlph         海豚
    dog          苏军狗（警犬
    dogp         苏军狗飞扑攻击
    dron         恐怖机器人
    dronp        恐怖机器人飞扑攻击
    engineer     工程师
    flakt        防空步兵
    gi           美国大兵
    ivan         疯狂伊文
    josh         猴子
    pentgen      绿衣服将军
    polarb       北极熊 
    pres         总统
    ptroop       心灵突击队
    rock         火箭飞行兵
    seal         海豹突击队
    seala        海豹突击队雪地
    shk          磁爆步兵
    snipe        狙击手
    spy          间谍
    sqd          乌贼
    ssrv         保镖
    tany         谭雅
    trst         恐怖分子
    vladimir     黄衣服将军
    yuri         尤里
    yuripr       尤里改
 
#### 3、开火/攻击动画：（一般用在武器本体 Anim=）
    apmuzzle     天启坦克开火
    flak         高射炮开火（游戏未使用素材，可以作为通用素材
    gcmuzzle     巨炮开火
    gunfire      盖特机炮、坦克、武装采矿车等开火（通用素材
    mgun-e       开火动画右（用于夜莺直升机等，通用素材
    mgun-n       开火动画上（用于夜莺直升机等，通用素材
    mgun-ne      开火动画右上（用于夜莺直升机等，通用素材
    mgun-nw      开火动画左上（用于夜莺直升机等，通用素材
    mgun-s       开火动画下（用于夜莺直升机等，通用素材
    mgun-se      开火动画右下（用于夜莺直升机等，通用素材
    mgun-sw      开火动画左下（用于夜莺直升机等，通用素材
    mgun-w       开火动画左（用于夜莺直升机等，通用素材
    piff         狙击手、谭雅等单位攻击地面的效果（通用素材
    piffpiff     步兵、武装采矿车等单位攻击地面的效果（通用素材
    ring1        尤里副武器开火动画（尤里崩屁
    sqdg_e       乌贼攻击动画东（游戏未使用素材
    sqdg_n       乌贼攻击动画北（游戏未使用素材
    sqdg_ne      乌贼攻击动画东北（游戏未使用素材
    sqdg_nw      乌贼攻击动画西北（游戏未使用素材
    sqdg_s       乌贼攻击动画南（游戏未使用素材
    sqdg_se      乌贼攻击动画东南（游戏未使用素材
    sqdg_sw      乌贼攻击动画西南（游戏未使用素材
    sqdg_w       乌贼攻击动画西（游戏未使用素材
    ucflash      驻军建筑开火（由 OccupantAnim= 控制，通用素材
    vtmuzzle     坦克三星开火（通用素材
    yuricntl     尤里攻击动画（尤里控制敌人的时候，尤里头顶会有一个逐渐变大的圆圈，控制环
 
#### 4、弹头动画和爆炸效果：（弹头动画 AnimList=，爆炸效果 Explosion=，以及一些特殊爆炸效果）
`在弹头动画中，若有多种动画，则依据武器杀伤力从左到右显示不同的动画；爆炸效果指的是单位被摧毁后，地表会播放的爆炸动画（如果是建筑被摧毁，则是在其占地面积范围内的每个格子播放一次爆炸动画，若有多种动画，则每个格子随机播放任意一种）`

    apocexp      天启坦克弹头动画
    brrlexp1     小油桶爆炸
    brrlexp2     大油桶爆炸
    crivexp      疯狂伊文弹头动画
    crivexp2     疯狂伊文三星弹头动画（未使用素材
    demtexp      自爆卡车弹头动画
    explolrg     大爆炸（武装直升机副武器三星弹头等，通用素材
    explomed     中爆炸（磁悬幽浮坠落到地面的爆炸动画，游戏中少见的爆炸，通用素材
    explosml     小爆炸（爱国者导弹或驱逐舰弹头动画等，通用素材
    gtpowexp     电厂爆炸
    htrkpuff     防空步兵、海蝎、防空履带车弹头对地动画
    ironfx       幻影坦克弹头动画（铁幕生效时的单位被攻击后产生的抵挡动画
    ktstlexp     基洛夫空艇三星弹头动画
    mininuke     迷你核弹（用在V3火箭、恐怖分子等，通用素材
    nukeanim     核电站死亡武器弹头动画（也是核弹爆炸的效果
    s_bang16     大小为16的迷你爆炸（未使用素材
    s_bang24     大小为24的小型爆炸（未使用素材
    s_bang34     大小为34的中型爆炸（单位被摧毁爆炸，通用素材
    s_bang48     大小为48的大型爆炸（单位被摧毁爆炸，通用素材
    s_brnl20     大小为20的爆炸（未使用素材
    s_brnl30     大小为30的爆炸（未使用素材
    s_brnl40     大小为40的爆炸（未使用素材
    s_brnl58     大小为58的爆炸（单位被摧毁爆炸，通用素材
    s_clsn16     犀牛、灰熊等坦克弹头动画（通用素材
    s_clsn22     犀牛、灰熊等坦克弹头动画（通用素材
    s_clsn30     坦克杀手弹头动画等（通用素材
    s_clsn42     榴弹炮弹头动画（色盘有问题，用泰伯利亚anim.pal色盘正常显示
    s_clsn58     入侵者战机、黑鹰战机、米格战机弹头动画和单位被摧毁爆炸等（通用素材
    s_tumu22     大小为22的弹头动画（未使用素材，坦克弹头动画的扣帧版，这个帧数少
    s_tumu30     大小为30的弹头动画（未使用素材，坦克杀手弹头动画的扣帧版，这个帧数少
    s_tumu42     大小为42的弹头动画（未使用素材，榴弹炮弹头动画的扣帧版，榴弹炮弹头动画可以暂时改用这个
    s_tumu60     大小为60的爆炸动画，单位被摧毁爆炸等（通用素材
    smkpuff      防空步兵、海蝎、防空履带车的弹头对空动画
    tstimpct     磁能坦克弹头动画
    tstlexp      磁能反应炉爆炸（好像官方是准备弄个磁能坦克三星弹头动画，但只用在磁能反应炉的 Explosion=
    twlt026      桥被炸断（桥被炸断产生的爆炸效果，由全局语句 BridgeExplosions= 控制
    twlt036      桥被炸断（桥被炸断产生的爆炸效果，由全局语句 BridgeExplosions= 控制
    twlt050      桥被炸断（桥被炸断产生的爆炸效果，由全局语句 BridgeExplosions= 控制
    twlt070      桥被炸断（桥被炸断产生的爆炸效果，由全局语句 BridgeExplosions= 控制，工具箱的爆炸类型1
    twlt100      超大型爆炸（用在工具箱的爆炸类型2 
    vtexplod     坦克三星弹头动画（通用素材
    xgrymed1     多功能步兵车三星弹头动画、武装直升机副武器弹头动画等（通用素材
    xgrymed2     小型爆炸（光棱坦克弹头动画等，可作为通用素材
    xgrysml1     迷你爆炸（游戏中少见的爆炸，可作为通用素材
    xgrysml2     迷你爆炸2（多功能步兵车、重装大兵副武器、登月飞行兵弹头动画等，通用素材
    yuricntl     尤里弹头动画（尤里控制敌人的时候，敌方头顶会有一个逐渐变大的圆圈
 
#### 5、光标、方向箭头指针和指示：
    arrow        左箭头（红色）
    arrwdest     向下箭头
    arrwe        右下箭头
    arrwn        右上箭头
    arrwne       向右箭头
    arrwnw       向上箭头
    arrws        左下箭头
    arrwse       向下箭头
    arrwsw       向左箭头
    arrww        左上箭头
    behind       隐藏物品
    mouse        鼠标指针（这个足足有450帧，具体细节可到鼠标指针shp的段落查看
    ring         提示环（鼠标指针选取单位并点击路径点命令其移动时，在路径点下方产生的提示环
 [跳转到鼠标指针段落](### 鼠标指针shp)，代码查看器(如 HBuilder)可按住 Alt 并单击蓝色字段跳转
 
#### 6、工具箱图标和类型：（添加不会在正常对局中出现的箱子图标和类型）
    armor        装甲
    chemisle     一次核弹使用权（正常对局未使用，泰伯利亚中这个图标是化学弹，使用泰伯利亚 anim.pal 色盘可正确显示）
    cloak        隐形（正常对局未使用，使用泰伯利亚 anim.pal 色盘可正确显示
    firepowr     火力
    healall      医疗
    mltimisl     凝固汽油弹（未使用素材，使用泰伯利亚 anim.pal 色盘可正确显示
    money        金钱
    reveal       获得全图视野
    shroudx      失去全图视野（正常对局未使用，使用泰伯利亚 anim.pal 色盘可正确显示
    speed        速度	
                 金矿（正常对局未使用，类似矿柱，拾取后金矿会在原地蔓延，这个是tem覆盖图文件，就没有提取了
    twlt070      爆炸类型1（正常对局未使用，多重爆炸效果，对任何单位都有伤害。这个爆炸素材还被用在桥被炸断后的其中一种视觉效果
    twlt100      爆炸类型2（正常对局未使用，一次大爆炸，比类型1伤害高，但似乎对建筑无伤害
	veteran      升级
	wccloud1     毒气（正常对局未使用，调用的是闪电风暴的乌云图像，且强制使用anim.pal色盘，可换成其他使用anim.pal色盘的图像
                 
##### 工具箱注册表[Powerups]（可在规则文件里搜索这个注册表并修改它的数据）
- *可进一步修改全局注册表中的数据[CrateRules]: 例如箱子生效范围 CrateRadius=3.0(3.0为5x5面积,2.0为3x3面积)*
- *部分箱子的参数是无效的，可根据情况在其他配置文件中修改数据（例如增加 Gas 这类箱子的图像附加伤害，可在 art.ini 中写伤害和弹头：Damage=、Warhead=）* 
- *注：工具箱注册表无法正常读取在地图文件内注册的动画，也无法在地图文件中使用这个注册表，应在规则文件内修改* 

 `为方便查看，将“=”纵向对齐（突发强迫症）`  
  
    格式例：箱子类型=生成概率,图像,能否在水上出现,参数（“生成概率” 的总和一般不超过 110，必须不小于 100）  
	
                Armor=10,ARMOR,yes,1.5    ; 附近5x5范围单位的护甲增加>参数：护甲乘数 x1.5  
            Firepower=10,FIREPOWR,yes,2.0 ; 附近5x5范围单位的火力增加>参数：火力乘数 x2.0  
             HealBase=10,HEALALL,yes      ; 所有已方单位立即满血（指全图已方单位立即满血，且效果不受范围限制）  
                Money=20,MONEY,yes,2000   ; 立即获得一笔钱>参数：一次获得2000现金（单人战役控制SoloCrateMoney=  
               Reveal=10,REVEAL,yes       ; 显示整个雷达地图  
                Speed=10,SPEED,yes,1.2    ; 附近5x5范围单位的速度增加>参数：速度乘数 x1.2  
              Veteran=20,VETERAN,yes,1    ; 单位升级>参数：一次升1级  
                 Unit=20,<none>,no        ; 获得车辆（不能设置动画，已有50个单位或箱子在水上/沙滩上将会转为现金，当遭遇战中玩家目前资金不足1500，同时没有基地车或任何一个建筑，那么箱子会强制生成基地车）  
			   
    以下是原版游戏中未使用的箱子，修改概率可重新利用，无效箱子除外（注意概率总和 100 ≤ x ≤ 110）  
	
      Invulnerability=0,ARMOR,yes,1.0     ; 无敌>参数：持续1分钟【无效】（图标是装甲箱，可删掉图标当空箱子用...红警1的遗留）  
             IonStorm=0,<none>,yes        ; 引起离子风暴【无效】  
                  Gas=0,<none>,yes,100    ; 泰伯利亚气体（毒气）>参数：每团气体云造成100伤害【参数无效】（默认图像 wccloud1）  
             Tiberium=0,<none>,no         ; 泰伯利亚矿（金矿），拾取后生成金矿并在原地蔓延  
                  Pod=0,<none>,no         ; 获得一次DropPod【无效】（泰伯利亚遗留空降仓功能  
                Cloak=0,CLOAK,yes         ; 附近5x5范围单位获得隐形  
             Darkness=0,SHROUDX,yes       ; 关闭全图（间谍渗透雷达效果  
            Explosion=0,<none>,yes,500    ; 大爆炸>参数：每次爆炸产生500的伤害  
                 ICBM=0,CHEMISLE,yes      ; 获得一次核弹发射权  
               Napalm=0,<none>,no,600     ; 火焰杀伤（大爆炸）>参数：每次爆炸产生600的伤害（似乎无法对建筑造成伤害）  
                Squad=0,<none>,no         ; 随机步兵小队【无效】（好像会强制换成钱？  

#### 7、超级武器效果：
    chronoar     超时空传送-选择（在原地显示的传送准备动画）
    chronofd     超时空传送-传送（在原地显示的传送动画）
    chronosk     超时空传送-单位特效（单位附带亮闪闪的特效，也用于超时空军团等传送单位）
    chronotg     超时空传送-传送（传送目的地显示的动画，chronofd 和 chronotg 共用相同动画，只是文件名不同）
    explolb      闪电风暴的闪电劈到地上的蓝色爆炸效果
    ironblst     铁幕（释放铁幕
    ironfx       铁幕生效时的单位被攻击后产生的抵消动画（幻影坦克的弹头动画
    nkmsldn      下落中的核弹
    nkmslup      上升中的核弹
    nukeanim     核弹爆炸（也是核电站死亡武器的弹头动画
    nukeball     核弹落地（核弹落地后产生的预爆炸效果，像馒头
    nukepuff     核弹尾焰（核弹升空后附带的尾焰
    nukestm      四缕烟（可能是核弹的部分效果，但未使用这个素材 
    nuketo       核弹升空（核弹刚升空时吹向地面的一团尾焰
    wccloud1     乌云1（闪电风暴的乌云
    wccloud2     乌云2（闪电风暴的乌云，这个官方漏注册了
    wccloud3     乌云3（闪电风暴的乌云
    wclbolt1     闪电1（闪电风暴的闪电
    wclbolt2     闪电2（闪电风暴的闪电
    wclbolt3     闪电3（闪电风暴的闪电
 
#### 8、步兵死亡效果：
    electro      电死（被磁暴线圈之类的单位电死 InfDeath=5
    flameguy     烧死（身上着火到处跑 InfDeath=4
    infdie       步兵死亡（泰伯利亚
    nukedie      辐射融化（被辐射而融化 InfDeath=7
    yuridie      震荡成碎片（被尤里的副武器震荡成碎片 InfDeath=6

### 二、建造栏图标：（位置：language.mix > cameo.mix） 
    adogicon     盟军警犬
    adoguico     盟军警犬一星（未使用图标
    aengicon     盟军工程师（未使用图标，箱子上有盟军图案
    aenguico     盟军工程师一星（未使用图标，箱子上有盟军图案
    agapgen      裂缝产生器（未使用图标，需要泰伯利亚的图标色盘
    agisicon     神盾巡洋舰
    ahrvicon     超时空矿车
    ahrvuicon    超时空矿车一星（未使用图标
    aparicon     空降部队(美国伞兵)
    asaticon     间谍卫星
    ayaricon     造船厂(盟军船厂)
    beagicon     黑鹰战机
    bolticon     闪电风暴
    brrkicon     盟军兵营
    carricon     航空母舰
    ccomicon     超时空突击队
    ccomuico     超时空突击队一星
    chroicon     超时空转换
    clegicon     超时空军团兵
    cleguico     超时空军团兵一星
    clonicon     复制中心
    cnsticon     盟军建造厂（未使用图标，需要泰伯利亚图标色盘
    csphicon     超时空传送仪
    darken       ？（好像是图标背景的形状
    desoicon     辐射工兵
    desouico     辐射工兵一星
    desticon     驱逐舰
    dlphicon     海豚
    dlphuico     海豚一星（未使用图标，需要泰伯利亚图标色盘
    dogicon      苏军警犬
    doguico      苏军警犬一星（未使用图标
    dredicon     无畏级战舰
    dronicon     恐怖机器人
    e1icon       动员兵（未使用图标，需要泰伯利亚图标色盘
    e1uico       动员兵一星（未使用图标，需要泰伯利亚图标色盘
    e2icon       动员兵
    e2uico       动员兵一星
    engnicon     工程师（阵营通用图标
    falcicon     入侵者战机
    fixicon      盟军维修厂
    flakicon     防空炮
    flkticon     防空步兵
    flktuico     防空步兵一星
    forticon     堡垒轰炸机（未使用图标，需要泰伯利亚图标色盘
    fvicon       多功能步兵车
    fvuico       多功能步兵车一星
    gapicon      裂缝产生器
    gcanicon     巨炮
    giicon       美国大兵
    giuico       美国大兵一星
    gorep        矿石精炼器
    gtnkicon     灰熊坦克
    gtnkuico     灰熊坦克一星
    gwepicon     盟军战车工厂
    handicon     苏军兵营
    harvicon     武装采矿车
    harvuico     武装采矿车一星
    heliicon     空指部(盟军雷达)
    hindicon     雌鹿运输机（未使用图标，需要泰伯利亚图标色盘
    hovricon     海蝎
    htkicon      防空履带车
    htkuico      防空履带车一星
    htnkicon     犀牛坦克
    htnkuico     犀牛坦克一星
    ircricon     无敌
    ivanicon     疯狂伊文
    ivanuico     疯狂伊文一星（未使用图标，疯狂伊文无法通过间谍偷兵营升星，弃用图标
    ivncicon     超时空伊文
    ivncuico     超时空伊文一星（未使用图标，超时空伊文无法通过间谍偷兵营升星，弃用图标
    jjeticon     火箭飞行兵
    jjetuico     火箭飞行兵一星
    landicon     两栖运输艇(盟军运输船)
    mcvicon      盟军机动基地车(盟军基地车)
    mcvuico      盟军机动基地车一星（未使用图标
    msslicon     核弹发射井
    mtnkicon     天启坦克
    mtnkuico     天启坦克一星
    npwricon     磁能反应炉(苏军电厂)
    nradicon     苏军雷达
    nrcticon     核子反应堆
    nreficon     苏军矿石精炼厂
    ntchicon     苏军作战实验室
    nukeicon     核弹攻击
    nwalicon     苏军围墙
    nwepicon     苏军战车工厂
    paraicon     伞兵（这是占领科技机场给的伞兵，美国伞兵的图标是：空降部队
    pillicon     机枪碉堡
    plticon      哨戒炮
    powricon     发电厂(盟军电厂)
    prisicon     光棱塔
    psicicon     心灵突击队
    psicuico     心灵突击队一星
    psisicon     心灵探测器
    psiticon     超能力部队（未使用图标
    psituico     超能力部队一星（未使用图标
    reficon      盟军矿石精炼厂
    rfixicon     维修工厂(苏军维修厂)
    rtnkicon     幻影坦克
    rtnkuico     幻影坦克一星
    samicon      爱国者飞弹
    sapcicon     装甲运兵船(苏军运输船)
    sealicon     海豹部队
    sealuico     海豹部队一星
    shadicon     夜莺直升机
    shaduico     夜莺直升机一星
    shkicon      磁爆步兵
    shkuico      磁爆步兵一星
    smcvicon     苏联机动基地车(苏军基地车)
    smcvuico     苏联机动基地车一星（未使用图标
    snipicon     狙击手
    snipuico     狙击手一星
    spyicon      间谍
    spyuico      间谍一星（未使用图标
    sqdicon      巨型乌贼
    sreficon     光棱坦克
    srefuico     光棱坦克一星
    stnkicon     隐形坦克
    subicon      攻击潜艇(苏军潜艇)
    tanyicon     谭雅
    tanyuico     谭雅一星
    techicon     盟军作战实验室
    tempicon     图标方框背景
    teslaicon    磁暴线圈（未使用图标，需要泰伯利亚图标色盘
    tnkdicon     坦克杀手
    tnkduico     坦克杀手一星
    trkaicon     自爆卡车
    trsticon     恐怖分子
    trstuico     恐怖分子一星（未使用图标
    tslaicon     磁暴线圈
    ttnkicon     磁能坦克
    ttnkuico     磁能坦克一星
    v3icon       V3火箭(V3火箭发射车)
    v3uico       V3火箭(V3火箭发射车)
    wallicon     盟军围墙
    wethicon     天气控制机(天气控制器)
    xxicon       Missing Cameo - 图标缺失时显示的通用图标
    yardicon     船坞(苏军船厂)
    yuriicon     尤里
    yuriuico     尤里一星
    yurpicon     尤里改
    yurpuico     尤里改一星
    zepicon      基洛夫空艇
    zepuico      基洛夫空艇一星
    
#### 泰伯利亚之日的残留图标
*泰伯利亚除了图标，对应的一些模型也有残留，需要的可以去mix里找找*  
*英文名大部分摘自泰伯利亚游戏中显示的图标名称，官方没有中文译名，故采用社区翻译或衍生作品所使用的译名，若遇到音译或翻译不准确的问题，还请见谅*  
    
    apchicon     （泰伯利亚，Harpy - 哈比武装直升机
    apcicon      （泰伯利亚，Amphibious APC - 两栖运兵车
    artyicon     （泰伯利亚，Artillery - 自行火炮
    batricon     （泰伯利亚，Battery - 电池
    bggyicon     （泰伯利亚，Attack Buggy - 突袭者四驱车
    chemicon     （泰伯利亚，Chemical Missile - 化学飞弹
    clckicon     （泰伯利亚，Stealth Generator - 隐形发生器(提供范围隐身)
    crryicon     （泰伯利亚，Orca Transport - 奥卡运输机(运输步兵)
    detnicon     （泰伯利亚，Hunter Seeker - 狩猎者
    e4icon       （泰伯利亚，Rocket Infantry - 火箭兵
    empicon      （泰伯利亚，EMP Cannon - 电磁脉冲炮
    facticon     （泰伯利亚，Construction Yard - 建造厂
    fsdicon      （泰伯利亚，Fire Storm Generator - 风暴防御中心
    fspicon      （泰伯利亚，FireStorm Wall Section - 火风暴围墙
    fstdicon     （泰伯利亚，FireStorm Defense - 火风暴防御(开关)
    gat2icon     （泰伯利亚，Gate - 闸门(GDI)(面朝西北)
    gateicon     （泰伯利亚，Gate - 闸门(GDI)(面朝东北)
    gbayicon     （泰伯利亚，Dropship Bay - 空投支援站
    hmecicon     （泰伯利亚，Mammoth MK.II - 猛犸 MK.2
    ioncicon     （泰伯利亚，Ion Cannon - 离子炮
    lasricon     （泰伯利亚，Laser Fence Post - 激光栅栏(NOD)
    liteicon     （泰伯利亚，Light - 白色照明光源(灯柱)
    lpsticon     （泰伯利亚，Mobile Sensor Array - 移动传感器部队(NOD)
    metricon     （泰伯利亚，Meteor Storm - 陨石风暴
    mltiicon     （泰伯利亚，Multi Missile - 集束飞弹
    mmchicon     （泰伯利亚，Taitan - 泰坦机甲
    mutcicon     （泰伯利亚，变异人步兵，GDI人物左到右：Mutant Sniper(Umagon), McNeil, Ghost Stalker. 
    nga2icon     （泰伯利亚，Gate - 闸门(NOD)(面朝西北)
    ngaticon     （泰伯利亚，Gate - 闸门(NOD)(面朝东北)
    ngaticon     （泰伯利亚，Helipad - 停机坪(NOD)
    npsiicon     （泰伯利亚，NOD Radar - NOD雷达站
    obliicon     （泰伯利亚，Obelisk of Light Icons - 光明石碑(光明方尖碑)
    obmbicon     （泰伯利亚，Orca Bomber - 奥卡轰炸机
    orcaicon     （泰伯利亚，Orca Fighter - 奥卡战斗机
    otrnicon     （泰伯利亚，Orca Carryall - 奥卡运输机(运输车辆)
    plugicon     （泰伯利亚，GDI Upgrade Center - GDI升级中心
    podsicon     （泰伯利亚，Drop Pod - 空降仓
    proicon      （泰伯利亚，Banshee - 报丧女妖轰炸机
    rad1icon     （泰伯利亚，Drop Pod Node - 空降仓节点(需在“GDI升级中心”安装该升级组件后方可使用“空降仓”)
    rad2icon     （泰伯利亚，Seeker Control - 狩猎者控制器(需在“GDI升级中心”安装该升级组件后方可使用“狩猎者”)
    rad3icon     （泰伯利亚，Ion Cannon Uplink - 离子炮上行线(需在“GDI升级中心”安装该升级组件后方可使用“离子炮”)
    radricon     （泰伯利亚，Radar - 雷达站(GDI)
    rboticon     （泰伯利亚，Mobile Repair Vehicle - 机动维修车
    sapicon      （泰伯利亚，Subterranean APC - 钻地运兵车
    sbagicon     （泰伯利亚，Sandbags - 沙袋
    seekicon     （泰伯利亚，Hunter Seeker Droid - 狩猎者机器人
    smchicon     （泰伯利亚，Wolverine - 狼獾机甲
    soniicon     （泰伯利亚，Disruptor - 破坏者(声波坦克)
    spoticon     （泰伯利亚，Searchlight Tower - 探照灯塔
    subticon     （泰伯利亚，Devil's Tongue - “恶魔之舌”坦克(钻地喷火坦克)
    tickicon     （泰伯利亚，Tick Tank - 扁虱坦克
    towricon     （泰伯利亚，Component Tower - 守卫塔
    turbicon     （泰伯利亚，Power Turbine - 电力涡轮机(给电厂升级的组件)
    twr1icon     （泰伯利亚，Vulcan Cannon - 火神机炮(升级组件)
    twr2icon     （泰伯利亚，RPG - 火箭推进榴弹(升级组件)
    twr3icon     （泰伯利亚，SAM - 防空导弹(升级组件)
    weapicon     （泰伯利亚，War Factory - 战车工厂
    weaticon     （泰伯利亚，Riot Soldier - 镇暴步兵、Elite Cadre - 精英干部、Toxin Soldier - 毒素步兵
    weedicon     （泰伯利亚，Weed Eater - 收割机
    
### 三、建筑（不包含大部分覆盖图、地形对象及地形污染等）：

建筑动画：（位置：ra2.mix > generic.mix）

倒塌动画、废墟（位置：ra2.mix > isogen.mix）

建筑本体：（位置：ra2.mix > isourb.mix）

温和气候建筑 Part 1：（位置：ra2.mix > isotemp.mix）

温和气候建筑 Part 2：（位置：ra2.mix > tem.mix）

雪地气候建筑 Part 1：（位置：ra2.mix > isosnow.mix）

雪地气候建筑 Part 2：（位置：ra2.mix > snow.mix）


建筑的shp以及围墙：（位置：ra2.mix > temperat.mix）


建筑的shp以及围墙：（位置：ra2.mix > urban.mix）

***
## 尤里的复仇版本mix的shp中文名称：（位置：ra2md.mix）

### 一、步兵单位和动画（位置：ra2md.mix > conqmd.mix）

#### 1、未分类：（尤里复仇
    buildngz     给建筑用的色盘2？
	cdgas        神经突击车的神经毒气（AnimList=CDGAS，弹头动画很少就不单独分类了）
	diskray      磁悬幽浮吸取电厂、矿场产生的吸取环（DrainAnimationType=
	forcshld     力场护盾效果（ForceShieldInvokeAnim=
	gunfires     开火（未使用素材
	gunfirey     开火（未使用素材，而且图像错位了...
	mindanim     被心灵控制塔等控制的单位头顶特效（ControlledAnimationType=
	mindanimr    被超级武器控制的单位头顶特效：心灵控制器（PermaControlledAnimationType=
	mutate       被废弃的建造栏图标（基因突变（英文
    pips         这是单位血条的素材，例如单位头顶血条的绿色黄色红色像素就是用它来显示，还有单位升星的图标，占领医院后在血条后方显示的红十字治疗图标等等都在这里（注意要选择红警一的色盘）
    pips2        剩余弹药颜色，运输船下方的容量框显示的颜色等等（注意要选择红警一的色盘）
	schpdepl     武装直升机展开动画
	txgasg       绿色病毒气体（病毒狙击手击杀步兵后产生的毒气
	txgasr       红色病毒气体（未使用素材，可能是神经毒气的废案
	ucall3       驻军建筑开火（未使用素材，三个驻军开火动画的拼接
	uccons       驻军建筑开火
	ucinit       尤里新兵的驻军开火动画
	
#### 2、单位：（尤里复仇
    arnd         魔鬼终结者
	boris        鲍里斯
	brute        狂兽人
	caml         骆驼
	dnoa         暴龙
	dnob         腕龙
	eins         爱因斯坦
	ggi          重装大兵
	init         尤里新兵
	lunr         登月火箭员
	mumy         木乃伊
	rmnv         洛马诺夫总理
	slav         奴隶
	stln         蓝波
	virus        病毒狙击手
	yurix        尤里X

#### 3、超级武器效果：（尤里复仇
    pdfxcld      心灵控制器发动（尤里头像动画
	pdfxloc      心灵控制器释放（类似尤里部署攻击的特效

#### 4、步兵死亡效果：（尤里复仇
    brutdie      被狂兽人锤碎 InfDeath=8
	gendeath     转化为狂兽人 InfDeath=9
	virusd       被病毒狙击手杀死 InfantryVirus=

#### 5、光标、方向箭头指针和指示：（尤里复仇
    mouse        鼠标指针（尤里复仇版本添加的鼠标指针有67帧  
具体细节可到这个段落查看：[跳转](### 鼠标指针shp)，代码查看器(如 HBuilder)可按住 Alt 并单击蓝色字段跳转

### 二、建造栏图标：（位置：langmd.mix > cameomd.mix）
    bfrticon     战斗要塞
	bfrtuico     战斗要塞一星
	bnkricon     战斗碉堡
	bplnicon     米格战机（未使用图标
	brckicon     尤里兵营
	brisicon     青英战斗兵(鲍里斯)
	brisuico     青英战斗兵一星
	bruticon     狂兽人
	brutuico     狂兽人一星
	bsubicon     雷鸣潜艇
	bsubuico     雷鸣潜艇一星（未使用图标
	caosicon     神经突击车
	caosuico     神经突击车一星（未使用图标
	chrpicon     Chrono Prison - 超时空监狱（未使用图标，预留图标？
	citwicon     护城墙(尤里围墙)
	clonicon     尤里复制中心
	diskicon     镭射幽浮
	diskuico     镭射幽浮一星
	forcicon     力场护盾
	gdgiicon     重装大兵
	gdgiuico     重装大兵一星
	ggunicon     盖特机炮
	grndicon     部队回收厂
	gtncicon     基因突变器
	indpicon     工业工厂
	initicon     尤里新兵
	inituico     尤里新兵一星
	ltnkicon     狂风坦克
	ltnkuico     狂风坦克一星
	lunricon     登月火箭员
	lunruico     登月火箭员一星
	mindicon     精神控制车
	minduico     精神控制车一星（未使用图标
	muteicon     基因突变
	pdomicon     心灵控制
	psisicon     心灵感应器
	psyricon     心灵控制感测
	psyticon     心灵控制塔
	pupticon     心灵控制器
	rbccicon     控制中心
    roboicon     遥控坦克
	robouico     遥控坦克一星（未使用图标
	samicon      爱国者飞弹（怎么cameomd.mix里也有这个···估计西木不小心放进去了
	schpicon     武装直升机
	schpuico     武装直升机一星
	sminicon     奴隶矿场
	sminuico     奴隶矿场一星
	spypicon     侦察机
	tbnkicon     坦克碉堡
	teleicon     磁电坦克
	teleuico     磁电坦克一星
	vrusicon     病毒狙击手
	vrusuico     病毒狙击手一星
	yclnicon     尤里复制人
	yclnuico     尤里复制人一星
	yconicon     Con Yard(Construction Yard) - 建造厂（未使用图标，预留图标？
	yengicon     尤里工程师（未使用图标
	yenguico     尤里工程师一星（未使用图标
	yhvricon     装甲运兵船(尤里运兵船)
	yhvruico     装甲运兵船一星(尤里运兵船)（未使用图标
	ypcvicon     尤里机动基地车(尤里基地车)
	ypcvuico     尤里机动基地车一星（未使用图标
	ypwricon     生化反应炉(尤里电厂)
	ytchicon     尤里作战实验室
	ytnkicon     盖特坦克
	ytnkuico     盖特坦克一星
	ywepicon     尤里战车工厂
	yypricon     尤里X
	yypruico     尤里X一星
	yyrdicon     海军船坞(尤里船厂)
	
### 三、建筑

Part 1：（位置：ra2md.mix > isoubn.mix）

    c_shadow   可能是影子？游戏里好像没用这个


    city01     办公楼（色盘 cityno.pal 可正常显示
    city02     中型建筑（色盘 cityno.pal 可正常显示
    city03     有底部支撑柱的办公楼（色盘 cityno.pal 可正常显示
    city04     有底部支撑柱和停机坪的科技建筑（色盘 cityno.pal 可正常显示
    city05     有四个烟囱的工厂（色盘 cityno.pal 可正常显示
    city06     有路灯的破损办公楼（泰伯利亚色盘 isotem.pal 可正常显示

Part 2：（位置：ra2md.mix > isoubnmd.mix）


Part 3：（位置：ra2md.mix > isourbmd.mix）




### 鼠标指针shp（Ares 3.0 光标注册表中文对照）：

#### 注意事项
 **下面将涉及到 Ares 引擎，Ares 在尤里复仇版本的基础上扩展了许多功能，对于DIY来说非常有用！推荐下载！（该引擎不支持红警2原版，对于红警2原版DIY玩家，以下内容可忽略）**
[Ares下载页面](https://launchpad.net/ares/+download)< 如使用代码查看器(如 HBuilder)可按住 Alt 并单击蓝色字段跳转  

 **下载解压至游戏本体目录即安装完成，现在你可以在规则文件里手动添加新的注册表了，初次使用需要参照 Ares 说明书使用，具体使用说明这里就不再复述。**
[Ares 3.0 中文说明书](https://pan.baidu.com/s/1t3p23uVwpXn32OX_4db3MQ?pwd=3jj2)< 在说明书内直接搜索注册表：[MouseCursors]，即可看到详细使用说明
#### Ares自定义光标格式说明
- 格式：
    Name=Frame,Count,Interval,MiniFrame,MiniCount,HotSpotX,HotSpotY  
	Name：最长31个字符  
    Frame：第几帧（从0开始数）开始  
    Count：持续多少帧  
    Interval：光标动画速率  
    MiniFrame：游戏右上角小地图版帧数，Frame，MiniCount同理  
    HotSpotX可以写：Left, Center, Right  
    HotSpotY可以写：Top, Middle, Bottom  
	默认值分别为：0,1,0,-1,-1,Left,Top  
    光标播放速率一般为4，有的光标附带几帧动画，但播放速率被设为0，可手动修改  

- [Ares 的默认鼠标指针文件](https://ares-developers.github.io/Ares-docs/_downloads/MouseCursors.txt)

##### 中文补充版`MouseCursors.txt`（按帧数Frame重新排列）
```ini
[MouseCursors] ;Ares鼠标指针注册表
Default=0,1,0,1,1,Left,Top                    ;正常鼠标指针
MoveN=2,1,0,-1,-1,Center,Top                  ;移动视角上
MoveNE=3,1,0,-1,-1,Right,Top                  ;移动视角右上
MoveE=4,1,0,-1,-1,Right,Middle                ;移动视角右
MoveSE=5,1,0,-1,-1,Right,Bottom               ;移动视角右下
MoveS=6,1,0,-1,-1,Center,Bottom               ;移动视角下
MoveSW=7,1,0,-1,-1,Left,Bottom                ;移动视角左下
MoveW=8,1,0,-1,-1,Left,Middle                 ;移动视角左
MoveNW=9,1,0,-1,-1,Left,Top                   ;移动视角左上
NoMoveN=10,1,0,-1,-1,Center,Top               ;无法移动视角上
NoMoveNE=11,1,0,-1,-1,Right,Top               ;无法移动视角右上
NoMoveE=12,1,0,-1,-1,Right,Middle             ;无法移动视角右
NoMoveSE=13,1,0,-1,-1,Right,Bottom            ;无法移动视角右下
NoMoveS=14,1,0,-1,-1,Center,Bottom            ;无法移动视角下
NoMoveSW=15,1,0,-1,-1,Left,Bottom             ;无法移动视角左下
NoMoveW=16,1,0,-1,-1,Left,Middle              ;无法移动视角左
NoMoveNW=17,1,0,-1,-1,Left,Top                ;无法移动视角左上
Select=18,13,4,-1,-1,Center,Middle            ;选取
Move=31,10,4,42,10,Center,Middle              ;移动
NoMove=41,1,0,52,1,Center,Middle              ;无法移动
Attack=53,5,4,63,5,Center,Middle              ;在攻击范围内选择攻击目标
AttackOutOfRange=58,5,4,63,5,Center,Middle    ;在攻击范围外选择攻击目标
Protect=68,5,4,73,5,Center,Middle             ;保护(好像注册表漏了这个...)
DesolatorDeploy=78,10,4,-1,10,Center,Middle   ;辐射工兵展开(原版未使用光标)
NoTargrt=88,1,0,-1,-1,Center,Middle           ;无目标(原版未使用光标)
Enter=89,10,4,100,10,Center,Middle            ;进入
TakeVehicle=89,10,4,100,10,Center,Middle      ;劫持车辆（Ares 添加注册
Sabotage=89,10,4,100,10,Center,Middle         ;破坏（Ares 添加注册
NoEnter=99,1,0,63,1,Center,Middle             ;无法进入
Deploy=110,9,4,-1,-1,Center,Middle            ;展开
NoDeploy=119,1,0,-1,-1,Center,Middle          ;无法展开
UnDeploy=120,9,4,-1,-1,Center,Middle          ;收起(原版未使用光标)
Sell=129,10,4,-1,-1,Center,Middle             ;变卖建筑
SellUnit=139,10,4,-1,-1,Center,Middle         ;变卖单位(原版未使用光标)
NoSell=149,1,0,-1,-1,Center,Middle            ;无法变卖建筑
Repair=150,20,4,-1,-1,Center,Middle           ;工程师维修建筑
UnitRepair=150,20,4,-1,-1,Center,Middle       ;单位维修（Ares 添加注册
RepairTrench=150,20,4,-1,-1,Center,Middle     ;维修战壕（Ares 添加注册
EngineerRepair=170,20,4,-1,-1,Center,Middle   ;维修小扳手
NoRepair=190,1,0,-1,-1,Center,Middle          ;无法维修
Target=191,8,4,-1,-1,Center,Middle            ;目标(原版未使用光标)
Disguise=199,5,0,-1,-1,Center,Middle          ;伪装(原版未使用光标)
IvanBomb=204,5,4,-1,-1,Center,Middle          ;疯狂伊文炸弹
MindControl=209,5,0,-1,-1,Center,Middle       ;心灵控制/干预(原版未使用光标)
RemoveSquid=214,5,0,-1,-1,Center,Middle       ;移除乌贼(原版未使用光标)
Crush=219,5,0,-1,-1,Center,Middle             ;碾压(原版未使用光标)
SpyTech=224,5,0,-1,-1,Center,Middle           ;间谍渗透建筑(原版未使用光标)
SpyPower=229,5,0,-1,-1,Center,Middle          ;间谍渗透电厂(原版未使用光标)
Target2=234,5,4,-1,-1,Center,Middle           ;目标2(原版未使用光标)
GIDeploy=239,10,0,-1,-1,Center,Middle         ;美国大兵部署(原版未使用光标)
Ion=249,10,4,516,1,Center,Middle              ;离子炮(原版未使用光标)
Paradrop=259,10,4,516,-1,Center,Middle        ;空降部队
Flag=269,10,4,-1,-1,Center,Middle             ;设置路径点(原版未使用光标)
LightningStorm=279,20,4,514,1,Center,Middle   ;闪电风暴
Detonate=299,10,4,-1,-1,Center,Middle         ;引爆
EngineerDamage=299,10,4,-1,-1,Center,Middle   ;工程师破坏（Ares 添加注册
Demolish=309,10,4,-1,-1,Center,Middle         ;C4爆破
Nuke=319,10,4,513,1,Center,Middle             ;核弹
Tote=329,10,4,-1,-1,Center,Middle             ;蓝色搬运光标（Ares 添加注册
TogglePower=339,6,0,-1,-1,Center,Middle       ;切换电源（Ares 添加注册
NoTote=345,1,0,52,1,Center,Middle             ;蓝色无法搬运光标(原版未使用光标)
IronCurtain=346,5,4,-1,-1,Center,Middle       ;铁幕
Heal=351,5,4,-1,-1,Center,Middle              ;治疗(原版未使用光标)
InfantryHeal=355,1,0,-1,-1,Center,Middle      ;部队治疗（Ares 添加注册
ReTarget=356,1,0,-1,-1,Center,Middle          ;重设目标(原版未使用光标)
Chronosphere=357,12,4,-1,-1,Center,Middle     ;超时空传送
Disarm=369,15,0,-1,-1,Center,Middle           ;工程师拆除炸弹
NoTogglePower=384,1,0,-1,-1,Center,Middle     ;无法切换电源（Ares 添加注册
Scroll=385,1,0,-1,-1,Center,Middle            ;右键移动视角
ScrollESW=386,1,0,-1,-1,Center,Middle         ;右键移动视角上方尽头
ScrollSW=387,1,0,-1,-1,Center,Middle          ;右键移动视角右上方尽头
ScrollNSW=388,1,0,-1,-1,Center,Middle         ;右键移动视角右方尽头
ScrollNW=389,1,0,-1,-1,Center,Middle          ;右键移动视角右下方尽头
ScrollNEW=390,1,0,-1,-1,Center,Middle         ;右键移动视角下方尽头
ScrollNE=391,1,0,-1,-1,Center,Middle          ;右键移动视角左下方尽头
ScrollNES=392,1,0,-1,-1,Center,Middle         ;右键移动视角左方尽头
ScrollES=393,1,0,-1,-1,Center,Middle          ;右键移动视角左上方尽头
Protect2=394,10,4,-1,-1,Center,Middle         ;保护2(注册表没这个...补一下)
AttackMove=404,9,4,63,5,Center,Middle         ;移动攻击
Deploy2=413,9,4,-1,-1,Center,Middle           ;展开2(原版未使用光标)
InfantryAbsorb=422,9,4,-1,-1,Center,Middle    ;步兵吸收(原版未使用光标)
NoMindControl=431,1,0,-1,-1,Center,Middle     ;无法心灵控制/干预(原版未使用光标)
NoFlag=432,1,0,-1,-1,Center,Middle            ;无法设置路径点(原版未使用光标)
MiniProtect=433,1,0,-1,-1,Center,Middle       ;迷你护盾/保护(原版未使用光标)
MiniAttack=434,1,0,-1,-1,Center,Middle        ;迷你攻击(原版未使用光标)
Beacon=435,15,4,-1,-1,Center,Middle           ;信标
```
##### 第 451 帧开始为尤里复仇版本的光标↓
```ini
ForceShield=450,10,4,-1,1,Center,Middle       ;力场护盾
NoForceShield=460,10,4,-1,-1,Center,Middle    ;无法使用力场护盾
GeneticMutator=470,10,4,-1,-1,Center,Middle   ;基因突变
AirStrike=480,8,4,-1,-1,Center,Middle         ;空袭（鲍里斯使用的空袭
PsychicDominator=488,8,4,516,-1,Center,Middle ;心灵控制
PsychicReveal=496,8,4,515,1,Center,Middle     ;心灵控制感测
SpyPlane=504,8,4,512,1,Center,Middle          ;侦察机
```

# 推荐区
### 推荐B站 fhy093 大佬制作的地形文件和用户界面的修改方法
1. [地形文件修改](https://www.bilibili.com/opus/665780992473038852/?from=readlist)
2. [用户界面修改](https://www.bilibili.com/opus/989753283313664002/?from=readlist)


#### 还有其他的一些高级教程，有兴趣的同学可以过去观摩学习鸭↓↓↓
- [红警教程专栏](https://www.bilibili.com/read/readlist/rl321941)
---
#### Tips（小窍门和提示） 
※ Ares 引擎重新启用并增强了排错功能，你可以在 `RunAres.bat` 上单击鼠标右键以通过记事本或者其他文本编辑器进行编辑。建议改成以下字段：

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
	
同时，推荐使用 [Tail4Window](https://github.com/tualatin/tailforwindows/releases) 或 [Tail Ace](https://sourceforge.net/projects/tailace/) 实现对 debug.log 文件的实时监控，查错更方便！  
  
)
  
※ Ares 引擎强化了测试手段，现在允许直接投放单位到地图进行测试了，下面放出模板代码，可直接复制使用：（具体实现手法可以查阅 Ares 说明书）  
  
 - 单位投放其实就是超级武器的一种，由 Ares 引擎实现，所以这里我又要推荐安装一下 Ares 引擎了（啰嗦），当然还可以考虑安装其他拓展引擎，例如 Phobos（Phobos 的功能作者还在探索学习中...Phobos 与 Ares 结合使用达到最佳效果）。`
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
   000  
   
~~~
  
  1
  
  1  
测试1  
测试2
测试3
测试4
~~~


  
<center><font color=#FF0000><font color=#FF0000 size=6 face="Arial">红色警戒2 + 尤里的复仇 SHP素材文件中文对照表 V1.0</font><center>
<strong>BY DaylilyLG<strong>
