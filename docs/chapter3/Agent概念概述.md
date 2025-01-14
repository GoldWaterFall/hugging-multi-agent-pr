## 3.1 Agent概念概述

在MetaGPT看来，我们把Agent想象成环境中的数字人，其中 Agent = 大语言模型（LLM） + 观察 + 思考 + 行动 + 记忆
这个公式概括了智能体的功能本质。为了理解每个组成部分，让我们将其与人类进行
类比：
1. 大语言模型（LLM）：LLM作为智能体的“大脑”部分，使其能够处理信息，从交
互中学习，做出决策并执行行动。
2. 观察：这是智能体的感知机制，使其能够感知其环境。智能体可能会接收来自另
一个智能体的文本消息、来自监视摄像头的视觉数据或来自客户服务录音的音频等一
系列信号。这些观察构成了所有后续行动的基础。
3. 思考：思考过程涉及分析观察结果和记忆内容并考虑可能的行动。这是智能体内
部的决策过程，其可能由LLM进行驱动。
4. 行动：这些是智能体对其思考和观察的显式响应。行动可以是利用 LLM 生成代
码，或是手动预定义的操作，如阅读本地文件。此外，智能体还可以执行使用工具的
操作，包括在互联网上搜索天气，使用计算器进行数学计算等。
5. 记忆：智能体的记忆存储过去的经验。这对学习至关重要，因为它允许智能体参
考先前的结果并据此调整未来的行动。

 MetaGPT 中定义的一个agent 运行示例如下：

![metagptagent](img/metagptagent.png)

• 一个agent在启动后他会观察自己能获取到的信息，加入自己的记忆中 • 下一步进行思考，决定下一步的行动，也就是从 Action1，Action2，Action3 中选择执行的 Action
• 决定行动后，紧接着就执行对应行动，得到这个环节的结果
而在**MetaGPT内 Role 类是智能体的逻辑抽象。**一个 Role 能执行特定的 Action，拥有记忆、思考并采用各种策略行动。基本上，它充当一个将所有这些组件 联系在一起的凝聚实体。目前，让我们只关注一个执行动作的智能体，并看看如何实现一个最简单的 Agent



