# fit-shape-coach-skill

[English](README.md) | **简体中文**

给编程智能体用的长期健康与运动指导技能。它按年龄、身体限制、时间和反馈安排活动、饮食、睡眠和习惯，而不是按体型打分。

它帮助使用者把运动做成可重复的安排、把一餐写到具体食物和份量，并在出现危险时先提示就医。它**不**诊断、**不**开处方、**不**代替医生，也**不**把体重或外貌当作这个人的价值。

技能正文和参考资料是英文，便于工作流稳定。对话使用对方正在使用的语言。档案用英文写。

```bash
npx skills add sendsoon/fit-shape-coach-skill
```

## 技能做什么

对方说出一个真实情况后，智能体会：

1. 用对方选定的昵称对应**一位**已有档案；对不上就先问，不把两个人的资料混在一起
2. 阅读该档案里的年龄、限制、器材、时间和最近一条日志
3. 先看有没有急救信号，再谈今天练什么、吃什么
4. 分开指南推荐、已有知识、针对此人的建议，以及尚未核实的信息
5. 给出下一餐、下一次训练可以执行的步骤，写明食物、份量、分钟或动作
6. 缺关键信息时只问最要紧的一个问题
7. 在对方确认后更新档案，并追加日志，不覆盖、不删除既往记录

未满 18 岁的人不设定减重目标，也不安排热量赤字。

## 档案

档案在当前工作区的 `fit-shape-records/<昵称>/`。目录名就是对方愿意被称呼的昵称。

每条健康信息标明来源：本人陈述、临床已确认、AI 评估，或未知/未核实。

除该目录下的说明文件外，档案和日志已写入 `.gitignore`，不应提交。仓库里没有真实档案。虚构格式见 [examples/record-template.md](examples/record-template.md)。

不要记录真实姓名、身份证号、街道住址、电话、婚姻状况或胸围。

## 何时使用

适用于安排一周或当天的运动、三餐和加餐、便利店和外出吃饭、睡眠、恢复，以及某次没练完或身体情况变化之后的调整。

不要用它为没有诊断的伤病编写康复方案，不要用它承诺体型变化，不要用它给未成年人做减重计划，也不要在胸痛、明显呼吸困难、晕厥或突发剧痛时继续常规问答。中国大陆医疗急救电话是 120，其他地区使用当地急救电话。

## 安装

```bash
npx skills add sendsoon/fit-shape-coach-skill
```

也可克隆本仓库，把 `SKILL.md`、`references/`、`examples/` 复制到所用智能体的 skills 目录，并保持相对路径不变。

安装后，目录页由 [skills.sh](https://skills.sh/) 在收到遥测后展示。

## 如何更新技能

若当初用 Skills CLI 安装，从 GitHub 拉取最新的 `SKILL.md`：

```bash
npx skills check
npx skills update fit-shape-coach-skill
```

`check` 只检查是否有新版本。`update` 会把本技能重装到原先那些智能体。要更新本机已安装的全部技能：

```bash
npx skills update
```

跳过确认提示：

```bash
npx skills update fit-shape-coach-skill -y
```

再执行一次安装命令也会覆盖为最新文件：

```bash
npx skills add sendsoon/fit-shape-coach-skill
```

若是手动复制安装的，先 `git pull` 本仓库，再把 `SKILL.md`、`references/`、`examples/` 覆盖到原来的 skills 目录。

## 用法

```text
我下班后能在家练 25 分钟，通常 0:30 才睡。今天怎么安排？
昨天没练，今天要不要加倍？
下楼膝盖痛，能给我一套康复动作吗？
```

影响安全的事实缺失时，智能体只问一个问题，不猜测伤病诊断。

## 回答长什么样

有急救症状时，整段回答就是急救步骤。

简单问题不强制写满五段。

当天安排用中文时按这五段：

1. 今日健康状态
2. 今日饮食建议
3. 今日运动建议
4. 今日睡眠建议
5. 今日心理建设

虚构示例见 [examples/output-template.md](examples/output-template.md)。

## 项目结构

```text
fit-shape-coach-skill/
├── SKILL.md
├── skills.sh.json
├── skills-lock.json
├── README.md
├── README.zh-CN.md
├── LICENSE
├── references/
├── examples/
└── fit-shape-records/        # 本地档案，除 README 外不提交
```

| 文件 | 作用 |
|---|---|
| `SKILL.md` | 智能体执行的流程、安全规则和档案规则。 |
| `references/` | 需要时才阅读的运动、饮食、睡眠、特殊情况、急救和复盘资料。 |
| `examples/` | 回答结构和虚构档案，不是真人。 |
| `fit-shape-records/` | 每位使用者一个昵称目录。 |
| `skills.sh.json` | 若将来发布，用于 skills.sh 分组。不改变指导内容。 |
| `skills-lock.json` | 本地锁。尚无上游哈希，因为这份副本还不是已发布版本。 |

## 资料来源

参考资料引用 WHO 2020 身体活动指南、WHO 健康饮食事实页和 2012 年钠摄入指南、《中国居民膳食指南（2022）》、AASM/SRS 2015 成人睡眠共识、AASM 2016 儿童与青少年睡眠共识、CDC 说话测试强度，以及 ACOG 委员会意见 804 关于孕期活动的说明。核对日期是 2026-11-23。这些笔记不能代替现行官方全文，也没有编造未能定位的文献。

## 许可证

[MIT](LICENSE)
