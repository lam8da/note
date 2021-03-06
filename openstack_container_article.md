OpenStack专家讨论小组中唯一的女性，云编排平台厂商Cloudsoft的业务开发副总裁Caroline McCrory说：“你能够开始使用容器，并不意味着你应该使用它们。”McCrory并不是唯一有此想法的人。如今已经有越来越多的OpenStack专业人士开始怀疑Docker的影响范围。作为一种容器技术，Docker的颠覆性影响已经影响到了全球一些主要的数据中心。

抽象层之上的抽象层

在加拿大温哥华召开的OpenStack Summit于5月20日举行了一场专家讨论会，McCrory和五位专家在发表意见之时正值一艘远洋货轮的集装箱失火并被浓烟吞噬。（编者注：容器Containers的英文直译为集装箱，在讨论现场主办方真的投射出一幅大大的集装箱货轮失火的图片，请大家结合配图自行脑补。）

OpenStack的初衷是管理混合云上的虚拟机，而Docker正在以一种完全不同的方式对工作负载进行虚拟化。这些专家所讨论的问题是：“Docker 是正在为OpenStack提供帮助，还是正在对OpenStack构成威胁？”
OpenStack 私有云提供商Blue Box的创始人兼CTO Jesse Proudman说：“你会有许多基于抽象层的抽象层，这些本来用于追踪和解决问题的抽象层正变得异常棘手。”

Proudman讲述了Blue Box每天所面临的情况，几乎天天都要处理一些故障事件。如今，通过OpenStack追踪故障源头已经变得非常困难，但由OpenStack工具管理的虚拟机和由Kubernetes和Mesos等Docker工具所管理的容器让Blue Box摆脱了这样的困境。（编者注：显然，OpenStack在容器的帮助下，变得更加强大了。）

包括我在内，许多人都认为再将Docker称之为“极简”系统已经不再准确了。过去，我也曾经以此作为虚拟化的特点。

但是等一下

你可能会问，它们不是同一件事吗？就驾驶波音747飞机和驾驶侦察机来说，它们都是飞行。但是它们根本无法以相同的方式完成相同的目，因为两者是截然不同的两回事。

虚拟化让应用工作负载可以在服务器和云之间迁移。不过，虚拟机是让这些工作负载能够迁移的首要工具。当这些工作负载正在沿着虚拟层向着更高层不断上升时，这些虚拟机围绕应用构建了一个环境，让它们“相信”自己正处于处理器最底层的操作系统内。（编者注：容器虽然提供了比虚拟机更小的颗粒度，但虚拟机依然是企业应用的主流。）

由VMware领导的厂商创建了一个产业，该产业主要是管理复杂的虚拟机生态环境，让虚拟机可以获得物理资源。NASA率先对OpenStack概念进行了验证，让虚拟机在没有复杂映射情况下能够使用庞大的资源池。这给了vSphere的周密计划以致命一击。

鞋子正在改变脚

VMware时代的数据中心架构是否应该为新一代的OpenStack让路呢？在某一方面，即便是Rackspace的OpenStack联合创始人也认为，尽管OpenStack赢得了一个发展机遇，但是两个架构应该共存。

然而这一表态的时间是在2014年4月。在这一时间以后，Docker由引发人们的好奇心逐步发展成了IT领域中的重要话题，它们让OpenStack陷入到2014年vSphere的处境之中。也就是说，老的技术要么跟上潮流，要么面临淘汰。

如今，OpenStack的支持者发现，他们正在讨论vSphere支持者在2014年讨论过的内容。即，老的应该不会很快被淘汰，用于实现老应用虚拟化的架构必须要有一席之地。（编者注：OpenStack用了五年的时间快速迭代并开始走向成熟。Docker的出现是否意味着OpenStack就此老化尚需要现实环境加以验证，但毫无疑问的是，Docker的企业应用之路才刚刚开始。）

McCrory对于“用户是否仅因为自己能够使用容器，就应该使用容器”这个问题发表了评论，并就这一话题给出了自己的看法。容器不仅要有最佳使用案例，Docker和其他容器技术还必须要有能够证明自己的其他一些使用案例。

她说：“我看到许多人正在等着使用容器，他们似乎将要替换掉自己的虚拟机，摆脱VMware的许可。然而许多应用有着特定的行为，我们无法将它们放到容器当中。目前，容器距离成熟到足够处理这些工作负载尚有一段距离。”

Mirantis的联合创始人兼首席营销官Boris Renski也对此进行了补充。他说：“虽然有容器优于虚拟机的许多使用案例，但是大量事实表明，OpenStack是以虚拟机为中心的。OpenStack在许多架构方面的决策都是围绕着解决如何管理虚拟机这一问题的。目前确实存在着一些威胁。我认为，开诚布公地进行讨论对所有的人都有好处。”

Renski的这一看法在这一次的专题讨论中获得了认同。他对一名提问者表示，他自己是一名营销人员，任何含有容器和OpenStack两个词的标题都会吸引人们的注意。

从历史的发展看来，Renski的说法极具预见性。2012年9月在Mirantis的公司博客上，Renski曾撰文称，OpenStack基金会接纳VMware成为其会员是一个“错误”。在那篇文章中，Renski称，他担心OpenStack会被VMware削弱，因为VMware的唯一兴趣是，在继续推进vSphere作为端到端解决方案的同时，让OpenStack陷入困境。

精心策划最后阶段

VMware进入OpenStack基金会后，不仅提供了支持和专业技术，还为OpenStack两个主要的PaaS平台中的Cloud Foundry提供了实际代码。Cloud Foundry是OpenStack中一个争议性产品，它由VMware创建，后来交由VMware的衍生公司Pivotal负责。

Mirantis的Renski在讨论中说：“Docker存在着过度宣传，其价值主要是作为一个打包机。从长远看来，我认为其关键价值在于容器的编排上。这是目前所有人都在追求的目标。容器编排实际上就是PaaS。”（编者注：借助Docker，包括OpenStack在内的IaaS层资源将会获得更高的利用率，而相比融入IaaS层，容器似乎更有可能在PaaS层开辟出一片新的天地。）

小组讨论成员的讨论话题还包括： Docker是否会发展成一个PaaS平台？Docker在未来几年（或是几个月）中是否会威胁到OpenStack作为支持Cloud Foundry和红帽OpenShift PaaS平台的地位？目前红帽正在整理包括OpenShift在内的OpenStack产品组合，努力强化OpenStack作为“端到端解决方案”的地位。

Blue Box的Proudman认为：“问题不应该是‘容器是否将成为OpenStack的威胁？’，而应该是‘容器是否将创建新型PaaS？’”

观察这些公司在竞争中的角色互换其实非常有意思，他们经常会在恶人与受害者、征服者与挑战者、创新者与制造商之间发生角色互换。不过，观察信息技术随着时间的演进则更加令人着迷。（原文作者为Scott M. Fulton III/范范编译）