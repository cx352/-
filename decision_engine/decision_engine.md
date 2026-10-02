# Decision Engine — Natural Bodybuilding System

## 1. Purpose

本文件是整个 Natural Bodybuilding Skill 的总决策控制器。

它不负责单独提供某一个训练动作、某一个饮食方案或某一个运动员模板。

它负责：

用户数据 → 状态判断 → 阶段判断 → 训练决策 → 营养决策 → 运动员案例参考 → 执行 → 监测 → 调整

核心原则：

> 不直接复制运动员，而是提取运动员案例中的可验证原则，并结合科学证据与用户个人反馈进行个体化决策。

---

# 2. Core Decision Architecture

整个系统遵循：

DATA
↓
STATE
↓
GOAL
↓
PHASE
↓
TRAINING STRATEGY
↓
NUTRITION STRATEGY
↓
RECOVERY STRATEGY
↓
PLAN
↓
MONITOR
↓
ADJUST

---

# 3. Step 1 — Collect User Data

首先收集当前用户信息。

## Basic Information

- 性别
- 年龄
- 身高
- 当前体重
- 当前体脂率（如果有）
- 腰围
- 训练年限

## Goal

确认主要目标：

- 增肌
- 减脂
- 增肌减脂
- 赛后恢复
- 自然健美备赛
- 维持体重
- 提高训练表现

## Training

收集：

- 当前训练分化
- 每周训练次数
- 每次训练时间
- 每个肌群训练频率
- 每周训练组数
- 主要动作
- 次数
- RIR
- 训练表现
- 最近是否停滞

## Nutrition

收集：

- 当前每日热量
- 蛋白质
- 碳水
- 脂肪
- 饮食执行情况
- 最近体重变化

## Activity

收集：

- 每日步数
- 有氧
- 日常活动水平

## Recovery

收集：

- 睡眠时间
- 睡眠质量
- 疲劳程度
- 肌肉酸痛
- 训练动力
- 工作/学习压力
- 关节不适

---

# 4. Step 2 — State Assessment

调用：

`state_assessment.md`

判断用户当前状态。

必须同时观察：

- 7天趋势
- 14天趋势
- 28天趋势
- 体重
- 腰围
- 训练表现
- 恢复
- 饮食
- 活动量

不要根据单日体重做重大决策。

---

# 5. State Classification

可能状态包括：

## Productive Training

特点：

- 训练表现稳定或提高
- 恢复良好
- 睡眠正常
- 训练动力正常

策略：

保持训练结构并逐步进步。

---

## Energy-Limited Training

特点：

- 体重下降
- 训练表现下降
- 恢复变差
- 饥饿增加

策略：

检查热量赤字和碳水摄入。

必要时降低训练量或提高能量摄入。

---

## Recovery-Limited Training

特点：

- 持续疲劳
- 睡眠下降
- 动作质量下降
- 训练表现下降
- 肌肉酸痛长期存在

策略：

优先恢复。

可以：

- 降低训练量
- 提高RIR
- 减少力竭训练
- 增加休息
- 必要时Deload

---

## Productive Gaining

特点：

- 体重缓慢增加
- 腰围增长可控
- 训练表现提高
- 恢复良好

策略：

维持当前增肌策略。

---

## Recomposition

特点：

- 体重稳定或缓慢变化
- 腰围下降
- 训练表现稳定或提高
- 体脂逐渐下降

策略：

维持或小幅调整热量。

---

## Plateau

特点：

- 体重长期稳定
- 腰围长期稳定
- 训练表现长期没有进步
- 恢复没有明显问题

策略：

依次检查：

1. 数据准确性
2. 饮食执行
3. 训练质量
4. 训练量
5. 训练频率
6. 睡眠
7. 日常活动
8. 是否需要调整热量

不要自动增加训练量或热量。

---

# 6. Step 3 — Goal Identification

根据用户目标确定主要方向。

## Muscle Gain

目标：

增加肌肉，同时控制脂肪增长。

进入：

`phase_selector.md`

然后调用：

`bulking.md`

---

## Fat Loss

目标：

降低脂肪，同时尽可能保持肌肉和训练表现。

进入：

`phase_selector.md`

然后调用：

`cutting.md`

如果文件尚未建立，则使用科学证据和现有决策框架进行处理，并在后续完善模块。

---

## Recomposition

目标：

在较小能量赤字或接近维持热量情况下，同时改善肌肉量和体脂。

重点：

- 高蛋白
- 保持力量训练
- 控制赤字
- 观察训练表现
- 观察腰围和体重趋势

---

## Post-Competition Recovery

如果用户刚结束自然健美比赛：

进入赛后恢复逻辑。

重点：

- 恢复正常训练
- 恢复正常饮食
- 避免极端补偿
- 控制体脂快速反弹
- 逐渐恢复训练表现

---

## Contest Preparation

如果目标是比赛：

进入：

`contest_prep.md`

重点：

- 体重趋势
- 体脂下降
- 肌肉保持
- 训练表现
- 有氧
- 恢复
- 备赛时间

---

# 7. Step 4 — Phase Selection

调用：

`phase_selector.md`

判断当前最适合的阶段。

可能结果：

- Maintenance
- Recomposition
- Conservative Gain
- Standard Gain
- Fat Loss
- Post-Competition Recovery
- Contest Preparation
- Deload / Recovery Phase

不要仅根据体脂率决定阶段。

必须结合：

- 用户目标
- 当前体脂
- 训练水平
- 体重趋势
- 训练表现
- 恢复
- 比赛时间

---

# 8. Step 5 — Training Decision

调用：

`training_state.md`

确定：

- Training Split
- Frequency
- Weekly Volume
- Exercise Selection
- Sets
- Reps
- RIR
- Rest
- Exercise Order
- Progression
- Deload

---

# 9. Training Level

根据训练经验和表现大致判断：

## Beginner

通常：

训练经验较少。

重点：

- 技术
- 基础动作
- 稳定训练
- 渐进超负荷

---

## Intermediate

已经建立：

- 稳定训练习惯
- 基础力量
- 一定肌肉量

重点：

- 有效训练量
- 频率
- 恢复
- 弱项管理

---

## Advanced

特点：

- 长期训练
- 增肌速度较慢
- 对训练变量更加敏感

重点：

- 精确训练量
- 高质量训练
- 恢复
- 个体化动作
- 弱项管理

不要仅通过训练年限机械判断训练水平。

---

# 10. Training Split Selection

根据训练水平、时间、恢复能力选择。

## Full Body

适合：

- 初学者
- 时间有限
- 希望提高训练频率

---

## Upper / Lower

适合：

- 初中级训练者
- 每周训练3–4次

---

## Push / Pull / Legs

适合：

- 中高级训练者
- 训练时间较充足

---

## Body Part Split

适合：

- 高训练水平
- 能够管理恢复
- 需要更高单肌群训练集中度

---

## Push / Pull Based System

可参考：

Wang Zhenghao Case

适用于：

- 高频训练
- 希望分散单次疲劳
- 有一定训练经验的用户

---

# 11. Frequency Decision

频率不是固定标准。

需要根据：

- 每周总训练量
- 单次训练量
- 恢复能力
- 时间安排
- 肌群优先级

进行调整。

核心原则：

> Frequency follows recoverability.

如果增加频率导致：

- 表现下降
- 疲劳增加
- 睡眠下降
- 动作质量下降

则降低频率或减少单次训练量。

---

# 12. Volume Decision

训练量采用动态调整。

不要认为：

更多组数 = 更多肌肉。

优先考虑：

有效训练量 / 刺激疲劳比。

参考起点可以根据训练水平和肌群调整。

不要将任何固定组数视为普适标准。

如果：

训练表现提高
+
恢复良好

可以逐步增加训练量。

如果：

训练表现下降
+
恢复变差

优先减少训练量。

---

# 13. Intensity Decision

一般肌肥大训练可使用较宽的重复次数范围。

常用起点：

## Compound

约5–10次。

## Hypertrophy Work

约8–15次。

## Isolation

约10–20次。

这些范围不是硬性限制。

只要：

- 目标肌群获得足够刺激
- 技术稳定
- 接近力竭程度合理
- 可以持续进步

其他重复次数同样可以使用。

---

# 14. RIR Decision

一般情况下：

大部分训练：

约1–3 RIR。

较稳定的孤立动作：

可以更接近力竭。

高疲劳状态：

提高RIR。

恢复良好且训练目标允许：

部分训练可以接近0–1 RIR。

不要要求所有训练都达到力竭。

---

# 15. Rest Decision

复合动作：

通常约2–3分钟或更长。

孤立动作：

通常约1–2分钟。

如果下一组表现明显下降：

延长休息。

休息时间的目标：

维持高质量训练，而不是追求最短休息。

---

# 16. Exercise Selection Engine

动作选择依次考虑：

1. 目标肌群
2. 个体结构
3. 稳定性
4. ROM
5. 目标肌肉张力
6. 刺激疲劳比
7. 长期进步能力

不存在：

“自由重量一定最好”

或：

“器械一定最好”。

选择应根据用户实际反馈调整。

---

# 17. Progression Engine

优先使用多维度进步。

包括：

- Reps ↑
- Load ↑
- ROM ↑
- Technique ↑
- Stability ↑
- Target Muscle Stimulus ↑

不要只把增加重量作为唯一进步标准。

---

# 18. Weak Point Engine

如果用户存在弱项肌群：

先确认：

- 是否真的落后
- 是否训练不足
- 是否动作选择不合适
- 是否恢复不足

然后再决定：

- 增加频率
- 增加训练量
- 更换动作
- 调整动作顺序

不要直接大量增加训练量。

---

# 19. Nutrition Decision

根据：

- 当前阶段
- 体重趋势
- 腰围
- 训练表现
- 恢复
- 活动量

决定热量策略。

---

# 20. Muscle Gain Nutrition

目标：

获得足够能量支持训练和肌肉增长，同时控制脂肪增长。

优先：

- 足够蛋白质
- 足够碳水
- 合理脂肪
- 小幅热量盈余

增肌阶段不追求快速增重。

---

# 21. Conservative Gain

当用户：

- 训练水平较高
- 容易增加脂肪
- 希望控制体脂

可以采用较小热量盈余。

初始参考：

约+100–200 kcal/day。

根据7–14天趋势调整。

---

# 22. Recomposition Nutrition

如果目标是增肌减脂：

可以考虑：

- 维持热量
- 小幅热量赤字

同时：

- 蛋白质充足
- 保持力量训练
- 保持训练质量

判断是否有效：

不能只看体重。

必须结合：

- 腰围
- 体脂趋势
- 训练表现
- 视觉变化

---

# 23. Fat Loss Nutrition

减脂时：

重点是建立可持续能量赤字。

同时：

- 保持高蛋白
- 保持力量训练
- 控制训练疲劳
- 根据恢复调整有氧和训练量

如果：

体重下降过快
+
表现明显下降
+
恢复恶化

则重新评估赤字大小。

---

# 24. Carbohydrate Adjustment

碳水调整优先根据：

- 训练表现
- 体重趋势
- 恢复
- 总热量
- 活动量

进行。

小幅调整优先。

可以使用：

约20–40g/day

作为一次调整的起点范围。

调整后观察7–14天。

不要同时大幅修改多个变量。

---

# 25. Protein

一般健身和增肌减脂阶段可将：

约1.6–2.2 g/kg/day

作为常见起始参考范围。

具体摄入需要结合：

- 体脂
- 总热量
- 饮食偏好
- 训练阶段

不要把单一数字视为绝对要求。

---

# 26. Fat

脂肪需要满足：

- 基本营养需求
- 饮食可持续性
- 总热量目标

不要为了提高碳水而无限压低脂肪。

---

# 27. Monitoring Engine

所有重大调整之后：

至少观察：

7天
14天
28天

重点观察：

- 平均体重
- 腰围
- 训练表现
- 恢复
- 饥饿
- 睡眠
- 活动量

---

# 28. Weight Trend Rules

## Weight Slowly Increasing + Performance Improving

可能说明：

增肌策略有效。

维持。

---

## Weight Rapidly Increasing + Waist Rapidly Increasing

可能说明：

热量盈余过高。

考虑：

小幅降低热量。

---

## Weight Stable + Waist Decreasing + Performance Improving

可能说明：

Recomposition正在发生。

不要因为体重不增加就立即增加热量。

---

## Weight Decreasing + Performance Stable

如果目标是减脂：

通常可以继续观察。

---

## Weight Decreasing + Performance Decreasing + Recovery Decreasing

检查：

- 热量赤字
- 碳水
- 训练量
- 睡眠
- 有氧

必要时降低赤字或训练疲劳。

---

# 29. Adjustment Rules

一次调整优先只改变一个主要变量。

例如：

先调整：

碳水

而不是同时：

- 碳水
- 脂肪
- 训练量
- 有氧

全部改变。

原因：

否则无法判断哪一个变量造成结果。

---

# 30. Athlete Case Integration

运动员数据库不是固定模板库。

它用于：

案例比较、假设验证和实践参考。

---

# 31. Chengyi Tan Case

主要参考：

- 高水平自然竞技
- Natural Pro比赛
- 备赛
- 高质量训练
- 体成分控制

适用于：

高训练水平或竞技目标用户的案例参考。

不能直接复制其训练计划。

---

# 32. Yuan Shilin Case

主要参考：

- 年轻竞技训练
- 国内比赛实践
- 长期训练成长
- 增肌与备赛转换

适用于：

年轻、高训练动力、竞技发展型案例。

自然身份相关证据仍需持续验证。

---

# 33. Wang Zhenghao Case

主要参考：

- Push / Pull训练理念
- 高频训练
- 单次疲劳管理
- 状态调整
- 动作质量
- 弱项训练

适用于：

需要长期训练结构和高频训练管理的用户。

---

# 34. Kaisheng Wang Case

主要参考：

- 普通训练者指导
- 长期训练实践
- 动作执行
- 增肌减脂执行
- 教练实践逻辑

自然竞技身份证据不足。

不得作为Natural Pro核心竞技样本。

---

# 35. Cross-Case Validation

任何运动员案例中的方法：

都必须经过：

Scientific Evidence

↓

Athlete Case Evidence

↓

Individual Response

三层验证。

如果：

科学证据支持
+
多个自然案例出现类似实践
+
用户实际反馈良好

则提高推荐信心。

如果：

只有单个运动员使用
+
缺乏科学支持

则只能作为低置信度案例参考。

---

# 36. Evidence Confidence

每个建议可以标记：

## High Confidence

科学证据较强，并且实践案例一致。

## Moderate Confidence

科学证据有限，但存在多个实践案例支持。

## Low Confidence

主要来自单个运动员或教练实践。

## Unknown

缺少可靠数据。

---

# 37. Documented vs Derived

所有运动员数据必须区分：

## Documented

直接公开记录。

## Athlete Reported

运动员本人明确说明。

## Secondary Source

可靠第三方来源。

## Derived

根据公开数据计算或推导。

## Unknown

没有足够证据。

禁止：

UNKNOWN → 当作事实使用。

---

# 38. Safety and Uncertainty

如果用户提供的数据不足：

不要假设。

先指出缺失数据。

如果数据存在明显冲突：

指出冲突。

如果无法判断：

给出需要继续观察的指标。

---

# 39. Output Structure

最终给用户的建议应按照：

## 1. Current State

当前身体、训练、营养和恢复状态。

## 2. Current Phase

当前阶段。

## 3. Training Decision

- 分化
- 频率
- 训练量
- 动作
- 次数
- RIR
- 休息
- 渐进

## 4. Nutrition Decision

- 热量
- 蛋白质
- 碳水
- 脂肪
- 调整策略

## 5. Recovery Decision

- 睡眠
- 休息
- 疲劳管理

## 6. Monitoring

未来7/14/28天观察指标。

## 7. Adjustment Trigger

明确说明：

什么情况下增加训练量、减少训练量、增加热量、减少热量或调整频率。

---

# 40. Final Decision Principle

整个系统最终遵循：

DATA
↓
STATE
↓
PHASE
↓
STRATEGY
↓
PLAN
↓
MONITOR
↓
ADJUST

核心原则：

> 不复制运动员。

> 不迷信单一训练体系。

> 不根据单日数据做重大调整。

> 不把运动员案例当成因果证据。

> 优先使用科学证据。

> 使用多个自然训练案例进行交叉验证。

> 最终以用户自身长期反馈作为个体化决策的重要依据。

---

# 41. Final Formula

Scientific Evidence

+

Natural Athlete Case Database

+

Individual Response

+

Recovery Capacity

+

Adherence

=

Personalized Natural Bodybuilding Strategy

# END
