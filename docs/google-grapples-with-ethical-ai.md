# 谷歌与道德人工智能搏斗

> 原文：<https://thenewstack.io/google-grapples-with-ethical-ai/>

去年，当谷歌解雇了其道德人工智能团队的技术联席主管蒂姆尼特·格布鲁(Timnit Gebru)时，她与学术界人士和其他谷歌研究人员合著的一篇论文引发了争议，谷歌对其管理层明显表现出的偏见、其对支撑其核心搜索服务的人工智能的潜在缺陷的明显辩护，甚至对企业研究在整个人工智能领域的作用，发起了猛烈的批评。谷歌能接受研究必须提出的必要但令人不快的问题吗？

Gebru 的论文提出了一些可能令人不舒服的问题，这些问题是关于像谷歌搜索所使用的那种超大型语言模型的。

 这些大型语言模型，如 OpenAI 的 [GPT-3](https://thenewstack.io/openais-gpt-3-makes-big-leap-forward-for-natural-language-processing/) 、[微软的图灵-NLG](https://www.microsoft.com/en-us/research/blog/turing-nlg-a-17-billion-parameter-language-model-by-microsoft/) 和谷歌的[伯特](https://arxiv.org/pdf/1810.04805.pdf)可以使用自我监督学习而不是仔细标记的数据集，在理解和生成自然语言方面取得令人印象深刻的结果。但是这些结果也可能是肤浅的，或者倾向于肤浅的模式和偏见。正如[最近尝试](https://www.helpscout.com/blog/ai-in-customer-support/)使用 GPT-3 来创建服务台问题的答案所显示的，生成的答案可能写得很好，技术上正确——但不准确；其他研究表明，根据提交的提示，GPT-3 的结果可能会有所不同“[从近乎偶然到近乎最先进的](https://arxiv.org/pdf/2102.09690.pdf)”

 质疑这些大型模型(谷歌搜索现在主要基于这些模型)的效率和道德，从环境成本，到它们如何被训练和如何被使用的潜在偏见和伤害，听起来正是谷歌自己的道德人工智能小组应该做的，以遵守该公司[自己的人工智能原则](https://ai.google/principles/)。这些包括对社会有益、负责任、安全建造和测试以及避免产生或强化偏见。

 这是谷歌在 2018 年成立该小组要做的工作，因为人工智能的公平性问题变得越来越普遍。

 然而，如今更多的事情岌岌可危。

## 蔓延的种族偏见

2020 年乔治·弗洛伊德去世后不久，亚马逊、IBM 和微软宣布暂停、停止或限制面部识别工具的销售。但这些决定是在两年的研究表明许多面部识别工具中存在性别和种族偏见之后做出的，首先是麻省理工学院研究员 [Joy Buolamwini](https://www.media.mit.edu/people/joyab/overview/) 写的论文[算法正义联盟](https://www.ajl.org/)的创始人 [Timnit Gebru](https://scholar.google.com/citations?user=lemnAcwAAAAJ&hl=en) ，非营利组织 [Black in AI](https://blackinai2020.vercel.app/) 的联合创始人，当时是微软研究院的博士后学生。

虽然 IBM 最初试图改善然后取消其面部识别系统(该系统没有很大的市场份额),微软建议该技术应该受到与汽车和药品相同的政府监管，同时限制其使用对象，[亚马逊](https://aws.amazon.com/?utm_content=inline-mention)最初[公开争辩说该研究不准确——同时还投资于](https://aws.amazon.com/blogs/machine-learning/thoughts-on-recent-research-paper-and-associated-article-on-amazon-rekognition/)[人工智能公平性](https://www.nsf.gov/pubs/2020/nsf20566/nsf20566.htm),并在暂时限制其使用之前对亚马逊 Rekognition 服务进行了修改。(向执法部门提供面部识别技术的更受欢迎的供应商[没有做出改变或承诺](https://medium.com/@Joy.Buolamwini/announcing-the-sunset-of-the-safe-face-pledge-36e6ea9e0dc5)。)

> “基于互联网文本的大型数据集过度体现了霸权观点，并编码了可能对边缘化人群造成伤害的偏见。”
> 
> Timnit Gebru 等人

在聘请 Gebru 作为其第一位黑人女性研究科学家，共同领导由[玛格丽特·米歇尔](http://www.m-mitchell.com/)创立的伦理人工智能小组后，他从[微软研究院](https://www.microsoft.com/en-us/research/)转到谷歌“引领一种新的研究方法，在这种方法中，我们后退一步，寻找“更大的图景”，在这种情况下，研究[将](https://docs.google.com/document/d/1ERi2crDToYhYjEjxRoOzO-uOUeLgdoLPfnx1JOErg2w/)植根于人类价值观，包含多样化的经验，并从多个时间点和社会运动中学习，”谷歌现在的反应似乎更像亚马逊。

除了性别差异研究，米切尔和格布鲁都参与了安全和道德地使用机器学习的一些基础工作，引入了一些想法，如用于报告模型功效的模型卡[(想想食品包装上的营养面板)](https://arxiv.org/abs/1810.03993)和数据集数据表(标准化数据如何收集和打算如何使用的文档)。

这两位女性最近都获得了晋升，但 Gebru 在 2020 年底被迫离职，原因是她与米切尔和其他谷歌研究人员和学者合作的一篇论文引发了争议:“[关于随机鹦鹉的危险:语言模型会不会太大？](http://faculty.washington.edu/ebender/papers/Stochastic_Parrots.pdf)[谷歌人工智能部门负责人杰夫·迪恩](https://research.google/people/jeff/)说，这篇论文“忽略了太多关于[减轻](https://twitter.com/JeffDean/status/1334953632719011840)大型语言模型的环境成本和潜在危害的相关研究”,但它已经被本周晚些时候开始的[公平、问责和透明](https://facctconference.org/)会议接受。

Dean 还表示，论文提交的截止日期太短，谷歌无法审核，尽管它之前已经获得内部批准出版，然后传阅以获得进一步的内部反馈。2020 年，谷歌引入了一个新的审查流程[,涉及研究人员在涉及从中国和伊朗到新冠肺炎、推荐和个性化服务或公司自身服务偏见等“敏感话题”时，咨询法律、政策和公关团队。](https://www.reuters.com/article/us-alphabet-google-research-focus/google-told-its-scientists-to-strike-a-positive-tone-in-ai-research-documents-idUSKBN28X1CB)

一些研究人员还被要求在提出谷歌服务的潜在问题时“采取积极的语气”，米切尔公开质疑这是否会导致公司内部的审查。

该公司处理《随机鹦鹉》论文审查和删除 Gebru 的方式受到了广泛的批评。alphabet/谷歌首席执行官[桑德尔·皮帅](https://twitter.com/sundarpichai)称她为“[一位杰出的黑人女性领导人，拥有巨大的才华](https://www.axios.com/sundar-pichai-memo-timnit-gebru-exit-18b0efb0-5bc3-41e6-ac28-2956732ed78b.html)”，但她在说出自己受到的待遇后，在网上遭到了严重的骚扰。格布鲁的团队公开和内部抱怨这一过程，大量谷歌员工和学术研究人员签署了[一封信](https://googlewalkout.medium.com/standing-with-dr-timnit-gebru-isupporttimnit-believeblackwomen-6dadc300d382)呼吁官方承诺公司的研究诚信和学术自由，两名谷歌员工已经因格布鲁的待遇[辞职](https://www.theguardian.com/technology/2021/feb/04/google-timnit-gebru-ai-engineers-quit)。

谷歌对待人工智能研究人员的方式所产生的影响不仅仅是对他们的直接不公平(甚至是格布鲁因直言不讳而受到的骚扰)，因为谷歌自己的研究影响如此之大(甚至会阻碍一些领域的独立学术研究，在这些领域，探索人工智能问题的预算可能很难找到)。

## **公平与责任**

谷歌已经看到了不幸但可预见的后果，其新推出的搜索工具旨在使在黑人历史月期间更容易找到和支持黑人拥有的企业；这些企业现在正收到负面的、有时是种族主义的垃圾评论，这些评论似乎不太可能来自合法顾客。对于设计不良的多样性工作来说，这种反弹并不罕见，并且是一个多样化的人工智能伦理团队可以帮助解决的事情，建议包括的安全措施或如何用更有帮助的社区驱动的工作来取代它。

这就是迪安可能希望从宣布的变化中得到的团队(以及对他所谓的“[格布鲁博士的退出](https://www.axios.com/google-tweaks-diversity-research-policies-following-inquiry-8baa6346-d2a2-456f-9743-7912e4659ca2.html)”的处理方式的不全面的道歉)，这些变化将谷歌现在所说的“负责任的人工智能”(包括道德人工智能团队)交给了一个更高级的领导者。 [Marian Croak](https://blog.google/technology/ai/marian-croak-responsible-ai/) 是谷歌副总裁，拥有让公司接受威胁其商业模式的技术的经验(如 AT & T 的 VoIP ),他谈论妥协和外交途径(但没有人工智能研究的背景)。Croak 还领导了内部会议，旨在[平息一些内部反弹](https://www.bloomberg.com/news/articles/2021-02-18/google-to-reorganize-ai-teams-in-wake-of-researcher-s-departure)。

上个月，当谷歌[解雇了该公司道德人工智能部门的另一位领导](https://www.zdnet.com/article/google-fires-top-ethical-ai-expert-margaret-mitchell/)玛格丽特·米歇尔时，谷歌进一步发现自己受到了审查。

解雇米切尔似乎让迪安的希望有些成问题，尤其是在重组向媒体宣布之后，伦理人工智能团队才得知[重组的消息。](https://twitter.com/alexhanna/status/1362476196693303297)

米切尔“试图提出对种族和性别不平等的担忧，并大声说出谷歌解雇格布鲁博士的问题，”她在一条推文中说。在谷歌调查所谓的“多次违反我们的行为准则以及我们的安全政策，包括泄露机密的商业敏感文件和其他员工的私人数据”期间，她已经被锁定了五周的工作账户；Axios [报道说](https://www.axios.com/google-fires-another-ai-ethics-leader-6ef7dcd5-4583-4396-b5b3-129547ff3091.html)她正在寻找 Gebru 所经历的歧视和骚扰的证据。

时机再糟糕不过了，因为新政策还应该包括“围绕潜在敏感员工离职的新程序”，以及将高管奖金与多样性和包容性的进展挂钩(微软此前就采取了这一举措)。

## 超越谷歌

该公司持续的不安情绪出现之际，人工智能伦理正在从似乎是利基或次要的商业利益转向科技公司正在投资的领域，因为如果做错了，未来会给他们带来重大问题。

微软的 AETHER(人工智能，工程和研究中的伦理和效应)委员会包括计算机科学家和工程师，社会科学家，政策专家，律师和伦理学家。自 2017 年以来，它生产了像 [InterpretML](https://interpret.ml/) 这样的工具，这是一个开源工具包，帮助开发人员创建可以解释他们决定的人工智能系统，委员会的建议已经阻止了向外国政府和一些美国执法部门的“重大销售”，以及“控制和指导微软技术”，据微软首席科学官埃里克·霍维茨称[。Twitter 刚刚宣布任命](https://cltc.berkeley.edu/wp-content/uploads/2020/05/Decision_Points_AI_Governance.pdf)[rum man Chowdhury](http://www.rummanchowdhury.com/)([奇偶校验](https://www.getparity.ai/)的创始人和[埃森哲](https://www.accenture.com/us-en)的[公平工具](https://hbr.org/2018/10/auditing-algorithms-for-bias)的设计者)为机器学习道德、透明度和问责制总监。

谷歌自己之前试图建立一个外部(无薪)人工智能道德委员会，高级技术外部咨询委员会(ATEAC)，受到了包括 Gebru 和 Mitchell 在内的研究人员的批评，并在不到两周的时间内被取消[因为对谁被邀请进入董事会有争议。](https://www.vox.com/future-perfect/2019/4/4/18295933/google-cancels-ai-ethics-board)

机器学习和人工智能驱动的工具已经在一切事情中普遍使用，从你在选举前夕看到的广告，到标记欺诈的金融交易，到网飞和 YouTube 建议你接下来观看的视频，到谁被建议保释或在安全镜头中被错误识别的[。这是将对个人和社会产生重大影响的数字基础设施，尽管越来越多的开发人员可以使用人工智能技术，但许多人也将使用谷歌和微软等提供商预先构建的人工智能模型和服务。](https://www.nytimes.com/2020/06/24/technology/facial-recognition-arrest.html)

负责任地构建和公平地应用这些工具将变得至关重要，并可能在越来越多的国家受到政府监管。研究和人工智能服务受到审查的过程同样处于显微镜下，特别是当它们看起来像是科技行业试图通过“自我监管”来避免官方监管的时候。

这些角色和团队需要不仅仅是“AI 伦理——洗”；他们必须拥有改变工具、产品和平台的真正权力。这是谷歌需要为其新的负责任的人工智能“专家中心”展示的东西——这将更难做到，因为它在人工智能社区中失去了多少信任。梅雷迪思·惠特克(Meredith Whittaker)是谷歌开放研究小组的创始人、 [AI Now Institute](https://ainowinstitute.org/) 的联合创始人，也是 2018 年谷歌员工罢工的核心组织者之一，他在一条推文中建议，鉴于格布鲁和米切尔的遭遇，大学、会议、研究人员和开发人员可能希望[重新考虑他们与谷歌的关系](https://twitter.com/mer__edith/status/1362897163894800384)。

本周 ACM 公平、问责和透明会议的组织者[最近也决定](https://venturebeat.com/2021/03/02/ai-ethics-research-conference-suspends-google-sponsorship/)谷歌不会成为赞助商，一群学术研究人员和组织者使用# RecruitMeNot 标签要求学生承诺不接受谷歌的工作，直到该公司[承诺更多的问责和种族公正](https://www.change.org/p/google-research-leadership-stop-the-tech-talent-pipeline-recruitmenot-until-google-meets-racial-justice-demands?recruiter=723633914&utm_source=share_petition&utm_medium=twitter&utm_campaign=psf_combo_share_abi&recruited_by_id=4b92a0c0-3e17-11e7-9a75-19709134369d)。"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>