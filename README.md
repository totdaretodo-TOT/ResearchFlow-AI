# 【SOLO技能创作赛】ResearchFlow AI：一个帮科研人自动读论文、整理实验和写代码的 Skill

大家好，我做了一个面向科研人员的 AI Skill，名字叫 **ResearchFlow AI**。

它的定位很简单：不是替代科研人员做研究，而是把论文阅读、文献整理、实验记录、数据分析代码和科研写作这些高频重复工作，变成一套更自动、更结构化、更容易积累的科研工作流。

## 为什么想做这个 Skill

科研里真正难的部分，往往不是“有没有努力”，而是每天都有大量细碎任务在消耗注意力：

- 读完论文后，摘要有了，但不知道它和自己的课题有什么关系。
- 文献越攒越多，Reference 很难分类，也很难判断哪些适合写 Introduction，哪些适合写 Related Work。
- 实验记录写得很散，过几天再看，参数、现象和下一步计划都不够清楚。
- 数据分析经常要重复写读取 CSV、曲线拟合、画图、算 linewidth、算 SNR 的代码。
- 想做科研 idea，但不知道怎么同时评估创新性、可行性和短期验证路线。

所以我希望 ResearchFlow AI 能像一个“科研工作流助手”：帮科研人把零散输入整理成可复用的知识资产。

## ResearchFlow AI 能做什么

ResearchFlow AI 主要覆盖 7 类科研任务。

## 1. 论文阅读与精读

用户上传或粘贴论文内容后，它不会只做普通摘要，而是会按科研人员真正关心的问题来分析：

- 研究背景是什么？
- 核心科学问题是什么？
- 方法和实验设计是什么？
- 关键参数有哪些？
- 主要结果和创新点是什么？
- 局限性在哪里？
- 这篇论文对我自己的研究有什么启发？
- 哪些内容可以用于 Introduction、Related Work 或实验设计？

我特别希望它能回答一个问题：**这篇论文对我的研究到底有什么用？**

## 2. 文献卡片生成

ResearchFlow AI 可以把单篇论文整理成 Paper Card，包括：

- Basic Information
- Core Problem
- Method
- Key Results
- Important Parameters
- Innovation
- Limitations
- Useful Sentences for Writing
- Connection to My Research
- Potential Future Work

这样读论文不再只是“读过了”，而是能沉淀成后面写论文、开题和组会都能继续使用的材料。

## 3. Reference 分类整理

当用户提供多篇论文、标题列表或 reference 时，它可以按研究主题和写作用途进行整理：

- 基础文献
- 方法文献
- 实验文献
- 综述文献
- 最新进展
- 适合写 Introduction 的文献
- 适合写 Related Work 的文献
- 适合做性能对比的文献

它还会给出推荐阅读顺序，帮助用户从“堆文献”进入“建立文献地图”。

## 4. 实验记录整理

科研实验记录经常是碎片化的，比如：

> 今天把 cell temperature 从 45℃ 调到 55℃，EIT signal 变强，但 linewidth 也变宽了。Laser power 保持不变，coupling beam power 是 80 mW。

ResearchFlow AI 会自动整理成标准实验日志：

- Experiment Goal
- Changed Parameters
- Fixed Parameters
- Observation
- Possible Explanation
- Data / Result Summary
- Problems
- Next Step
- Parameters to Supplement

它会区分“已观察到的现象”和“可能解释”，并提醒还需要补充哪些参数。

## 5. 实验数据分析代码生成

对于实验数据分析，它默认使用 Python，并优先使用：

- numpy
- pandas
- scipy
- matplotlib

支持的任务包括：

- 读取 CSV / Excel 数据
- 数据清洗
- Lorentzian fitting
- Gaussian fitting
- 线性拟合
- 峰值提取
- linewidth 计算
- signal-to-noise ratio 计算
- error bar 计算
- publication-quality figure 绘制
- 数据误差来源分析

例如用户可以直接问：

> 请帮我对 EIT spectrum 做 Lorentzian fitting，计算中心频率和 linewidth。

它会给出完整可运行的 Python 代码，并解释 center、gamma、linewidth 等参数的物理意义。

## 6. 科研 Idea 生成

当用户给出自己的研究方向后，ResearchFlow AI 可以生成可行的科研 idea。每个 idea 不只是一个标题，而是包含：

- Background
- Core Problem
- Innovation
- Feasibility
- Required Conditions
- Possible Difficulties
- Short-term Verification
- Long-term Plan
- Suitable Output

我希望它生成的 idea 不是“看起来很厉害但很虚”，而是能落到短期验证、实验条件和风险判断上。

## 7. 科研写作辅助

它也可以帮助生成：

- 论文大纲
- Introduction 逻辑
- Related Work 总结
- Method 描述
- Result 分析
- Discussion 思路
- Conclusion 草稿
- 组会汇报提纲
- 开题报告结构
- PhD proposal 初稿

写作风格会尽量保持正式、克制、适合科研场景，不会过度夸大结论。

## 专业方向适配

我在 Skill 里特别加入了对 Rydberg 原子电场探测、EIT、太赫兹探测、光学和量子传感方向的适配。

它会重点关注：

- EIT
- Autler-Townes splitting
- Rydberg atoms
- Electric field sensing
- Microwave / THz detection
- Linewidth
- Rabi frequency
- Sensitivity
- Frequency range
- Signal-to-noise ratio
- Vapor cell
- Probe laser / coupling laser
- Calibration method
- Noise analysis
- Lorentzian / Gaussian fitting

这样在分析实验记录、论文或数据时，它不只是泛泛总结，而是会尽量结合实验参数、物理机制、灵敏度、信噪比和可复现实验设计。

## 我给它加的边界

ResearchFlow AI 有几个很重要的约束：

- 不编造论文不存在的数据。
- 不伪造引用、DOI 或实验结果。
- 不假装已经读取用户没有提供的文件。
- 信息不足时，会明确列出缺少什么。
- 对不确定内容，会标注“可能”“需要进一步验证”。
- 涉及最新论文或精确引用时，会提醒需要检索和核对来源。

科研场景里，可靠性比“看起来很完整”更重要。

## 示例用法

你可以这样使用它：

```text
请帮我分析这篇论文，重点总结它的创新点、实验方法、关键参数和对我研究的启发。
```

```text
请帮我把这些 Rydberg sensing 文献按照研究方向分类，并指出哪些适合写 Introduction。
```

```text
今天 coupling laser power 从 60 mW 提高到 90 mW，EIT peak 增强，但背景噪声变大。请整理成实验日志，并分析可能原因。
```

```text
请帮我对 EIT spectrum 做 Lorentzian fitting，计算中心频率和 linewidth，并画出适合论文发表的图。
```

```text
我的方向是 Rydberg 原子电场探测，请帮我生成 5 个适合研究生阶段尝试的科研 idea。
```

## 一句话总结

**ResearchFlow AI：让 AI 成为科研人员的第二大脑。**

它的价值不只是提高效率，更重要的是帮助科研人员建立系统化、可复用、可积累的科研工作方式。

如果你也经常读论文、整理实验、写分析代码或者准备组会，希望这个 Skill 能给你一点帮助。
