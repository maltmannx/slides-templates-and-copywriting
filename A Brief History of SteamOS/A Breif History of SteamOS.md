# SteamOS简史 - Linux和开源是游戏的未来

https://www.youtube.com/watch?v=rCGMiT0CQAI

## #0 引言

2022年3月，V社发布了其最新的移动游戏平台Steam Deck，凭借着出色的性能以及庞大的Steam生态加持，Steam Deck一经推出便迅速占满了掌机平台的热度。除了V社自带的光环外，与AMD定制APU的方案  更是降维打击了当时普遍使用Intel核显的Windows掌机圈。

Steam Deck不仅带动了整个行业发展，还让玩家和开发者看到了Linux平台的巨大潜力。

但你可能不知道的是，Steam Deck的成功并非一蹴而就，其背后融汇了V社和开源社区对未来游戏形态的不懈探索，从2012年Steam for Linux客户端发布至今，这项探索花费了十年。

## #1 SteamOS的诞生

和众多Windows掌机不同，Steam Deck运行GNU/Linux，其操作系统SteamOS则诞生于2013年。

SteamOS最初的设想是用来在局域网内串流游戏画面，并用作Steam Machine平台的一部分。Steam Machine是运行SteamOS的小型游戏主机，与PlayStation和XBOX相比，Steam Machine不对硬件做特定要求，厂商可以使用不同的硬件搭配推出自己的Steam Machine设备。但由于体验没有达到预期，该计划已经在2018年终止，V社将精力转到了SteamOS的后端开发中。

尽管硬件未达预期，与之配套的软件仍然延续了下来。局域网串流成为了Steam Link，而Steam Machine运行的SteamOS 1.0和2.0版本则添加了运行原生Linux游戏的能力。不过在那时，虽然各家都在积极优化Linux平台的兼容性，但开发者对OpenGL缺乏经验，再加上Linux上各种奇怪的驱动问题,同样的游戏在SteamOS上运行的效率往往远低于Windows。好在彼时SteamOS仍然为多平台游戏提供了新的方向，V社也对此充满信心。

> SteamOS始于2013年，基于Debian 7，在网络上能找到的信息少之又少，看起来只是steam针对游戏玩家出品的一个特别的linux发行版，2015年，官方推出了SteamOS2.0，相较于1.0升级到了Debian8,并将内核更改为lts版本。系统看似是个小升级，但在互联网上引起了部分关注度，因为同年Steam推出了Steam Machine和周边外设，而SteamOS2.0，就是运行在Steam Machine上的系统。这是Valve首次向游戏主机产业进军。
> 

> 虽然Steam Machine的背后是全球最大的游戏发行商Valve，但在游戏主机方面，完全不如当年的微软和索尼。Steam Machine的定位也很明确，一套客厅娱乐系统。相较于另外两家高性能主机，Steam Machine就像个准系统。SteamOS看起来潜力很大，实则短板明显。为Linux原生开发的游戏少之又少，其他大部分游戏都需要在局域网下靠高性能PC串流游玩，很难让人说这是个明智的选择。所以，SteamOS2.0苟延残喘到了2018年，随着周边硬件一起失去了音讯。
> 

## #2 为什么选择Linux

早在1999年，Valve就在Linux上部署了第一台游戏服务器。相比于Windows和其他平台，Linux对性能的干预更少且可靠性更强。时至今日，几乎所有的游戏服务器都在Linux运行。得益于Linux的特性，越来越多的开发者也开始在其之上为其他平台开发游戏。但医者难自医，Linux原生游戏的热度一直不温不火。

在之后的几年，Linux平台在游戏兼容性上始终处于下风，甚至不及同时期的macOS。

事情的转机出现在2018年，一个由Valve和CodeWeavers合作的开源项目悄然问世——**Proton**。

> 我们无从得知SteamOS基于linux的真正原因，因为以现在的视角来看，windows+steam大屏幕模式也能获得很棒的体验。不过显而易见的，linux给与steam定制系统更多自由，并且是开源免费的，按照一般剧情，G胖就像EA，看到财报亏损比杀了他麻麻还难受（毕竟长得就很资本家），这么没有前途的系统，应该停止开发，即使止损了。
> 

## #3 Project Proton

不同的平台使用不同的图形API建立计算机与显卡的通信。DirectX是微软为Windows开发的闭源图形API，是微软称霸PC游戏市场的基石。在Linux平台通常使用开源的Vulkan和OpenGL。

大家都有自己的图形API，但问题在于，Windows平台积累的庞大用户基数使游戏开发者往往过于注重对DirectX的优化，而忽略了对Vulkan等开源接口的兼容，导致游戏在Linux平台完全无法运行。

Proton是在DirectX与显卡之间的兼容层，基于Wine的一个分支。Proton使用DXVK等开源库将游戏对DirectX(D3D)的调用转换为Vulkan能理解的调用。这样一来，即使是Windows独占的应用和游戏也能在Linux上运行。

Proton与Wine的区别在于，后者为所有应用提供通用的方案。前者则针对游戏单独优化，使其在Linux平台也能拥有媲美Windows平台的性能。

SteamOS 1.0 2.0和Proton为Linux平台游戏提供了可能，但Proton介于计算机和开发者之间，无法增加开发者本身对游戏兼容性的重视。想要改变Linux平台的劣势，需要一个契机吸引开发者主动使用开源图形API，为Linux平台单独优化。

## #4 SteamOS 3.0

2022年三月，契机出现了。Steam Deck带着SteamOS 3.0又一次让开发者窥见了GNU/Linux平台的潜力——~~基于神秘而又强大的Arch Linux，~~凭借更简洁的系统和更高效的图形API，首批适配的游戏在性能方面几乎全线优于Windows且功耗更低。在Windows掌机天价的情况下，Steam Deck 399美元的定价迅速掀起热潮，Valve还趁热打铁推出Deck Verified，厂家可以根据Deck性能调整游戏，也更方便玩家确认哪些游戏与Steam Deck兼容。

为了实现滚动更新，SteamOS 3.0也从Debian迁移到了Arch Linux，并附带KDE Plasma——除了使用摇杆操控游戏外，还可以连接键鼠进入桌面模式，体验与PC无异。

V社深知社区的力量同样不容小觑。所以除了游戏开发商对Steam Deck的支持，SteamOS 3.0还将创意工坊完整的带到了Steam Deck上，极大程度的丰富了游戏的内容。

> 回到刚才的问题上，Why Linux？你可以从最朴素的角度上来想，因为G 胖是个商人，Linux发展到现在在使用体验上和Windows差距越来越小，有不少人换成了Win+Linux甚至于单Linux，G胖想打开这个逐渐变大的市场。当然，如果你是个像0191一样的理想主义者，认为Windows一家独大就是地球毁灭的开始，这个世界不能没有Linux，并且G胖也这么想。其实这种可能性也不是不存在。Valve作为一家不一般的游戏企业，为计算机图形学作出相当大的贡献，如今去发展Linux也是很合理的，毕竟Valve做到了承担起社会责任。反观某苹果，开源的东西拿来改改就用了，一家市值前三的公司居然只有[9个自己写的开源项目](https://opensource.apple.com/projects/)，还喜欢培养毛承添这种低能脑残粉，和Valve简直不能比。
> 

## #5 更快的开放标准

创意工坊为Steam Deck提供了无限的可能，这与早期Steam对开放的追求息息相关。

几十年前，电子游戏必须依靠专用的硬件才能运行，在那时家用机是主要的娱乐载体，平台在内容分发和定价上有绝对的话语权，但它们后来被PC平台和衍生硬件所取代，因为PC是一个开放的硬件标准，它的发展速度远超专有平台，且在内容上赋予了用户更多控制权。这与将来以**用户为中心的制作模式不谋而合。**

## #6 用户的角色转变

就像主流游戏平台从主机转向PC一样，用户的角色也在不断向开发者靠近。

一旦为用户提供工具，让其参与制作自己认为有价值的内容，他们就会迅速占据游戏的主导地位，最后，游戏中大量的内容将由用户创建，而不是开发者本身。这种以**用户为中心的制作模式**已经获得了巨大的成就，Garry’s Mod和Steam创意工坊就是最明显的例子。

Steam的开放性也将用户制作的内容转化为数字商品和服务在平台流通，游戏在本质上也成为了互联网经济中的节点。内容创作者到内容消费者的循环带动游戏市场的发展——Steam的用户活跃度和粘性都远超任何其他平台。

正如开头所说，当下，Linux的游戏生态并非一蹴而就。这一过程中，V社、开发者、玩家社区三方的努力缺一不可。在各个大厂都在拼命建立技术壁垒的今天，一个开源理念主导的项目顺利落地，显然还不足以得出开放平台大获成功的结论，但至少Steam Deck让玩家和市场看到了一丝希望。

## #7 尾声

2018年Proton 1.0问世，首批支持的游戏仅有27个，而今天已经有超过17000款游戏可以借助Proton 8.0在Linux平台运行。但这就够了吗？

在ProtonDB网站，你会发现目前已测试在Linux平台运行良好的游戏仅占Steam总量的13%。专有系统和专利在不同平台的玩家之间建立了深壑，无论Wine和Proton怎样努力，都无法改变其中间层的地位。

但SteamOS和Steam Deck的出现让局势发生了些许改变，随着技术的发展以及用户的角色转变，开放系统和开源的优势正不断扩大。占比1%的Linux点起了星星之火，属于开源游戏的未来已经初见端倪。 

## #Finale 游戏的未来

现在你能看到，Steam for Linux让多平台游戏成为了可能，Proton的出现颠覆了Linux的游戏体验，Steam Deck则证明了Linux平台的优秀性能，不少主流游戏已经提供开源图形API选项。

游戏社区的内容每年都以超乎想象的速度扩大，越来越多的用户参与到游戏的创作中，开源平台将用户与游戏相互连结，内容创作者和内容消费者之间的距离从未如此接近。

站在玩家背后的，是Valve在10年前对Linux和开源的展望，是SteamOS，Proton，Steam Deck和开源社区、游戏开发者以及所有玩家共同的努力，才造就了今天如此多元化的游戏市场。

SteamOS的历史是一部游戏发展史，书写它的是所有对未来充满希望并满怀开源精神的人。

书中正文谱写了游戏行业的创新和进步，而十年前Gabe Newell写下了序章的标题——**“Linux和开源是游戏的未来”**。