# 提示词工程指南：从结构到应用

## 一、结构化提示词方法

### 标签式结构

标签式结构使用明确标识符组织内容，适合快速构建和线性思维。

**基本语法：**
```
#[标签名称] [内容]
```

**核心标签集：**
```
#角色         # 定义AI的专业身份
#上下文       # 提供必要背景信息
#需求         # 列出具体要求
#约束         # 明确限制条件
#任务         # 描述核心任务
#输出         # 定义期望输出形式
```

**使用示例：**
```
#角色 数据科学专家
#上下文 电商平台需优化推荐系统
#需求 提升点击率和转化率
#约束 现有技术栈基于Python和TensorFlow
#任务 设计改进的推荐算法架构
#输出 包含数据流、模型架构和评估方法
```

### XML格式结构

XML格式提供严格的层次结构，适合复杂任务和模板重用。

**基本结构：**
```xml
<prompt>
  <role>...</role>
  <context>...</context>
  <requirements>
    <requirement priority="high">...</requirement>
    <requirement priority="medium">...</requirement>
  </requirements>
  <constraints>...</constraints>
  <task>...</task>
  <output>...</output>
</prompt>
```

**使用示例：**
```xml
<prompt>
  <role>软件架构师</role>
  <context>金融科技公司需构建高可用支付系统</context>
  <requirements>
    <requirement priority="high">支持99.99%可用性</requirement>
    <requirement priority="high">符合PCI DSS标准</requirement>
    <requirement priority="medium">支持国际交易</requirement>
  </requirements>
  <constraints>
    <constraint>现有基础设施基于AWS</constraint>
    <constraint>6个月实施时间</constraint>
  </constraints>
  <task>设计分布式支付处理架构</task>
  <output>架构图、组件规格、部署策略</output>
</prompt>
```

## 二、核心提示模式

### 专家咨询模式

定义明确的专业角色，激活特定知识领域。

```
#角色 你是一位精通分布式系统的架构师，有设计高并发金融系统的专长

<role>
  <expertise>分布式系统架构师</expertise>
  <specialization>高并发金融系统</specialization>
</role>
```

### 思维链模式

引导AI展示推理过程，增强复杂问题解决能力。

```
#思维过程 请分步分析此问题，说明每一步的推理逻辑和考量因素

<reasoning>
  <approach>step-by-step</approach>
  <verbosity>detailed</verbosity>
</reasoning>
```

### 多角度分析模式

要求从不同维度评估问题，获得全面解决方案。

```
#分析框架 从技术、成本、风险和长期维护四个维度评估方案

<perspectives>
  <perspective>技术可行性</perspective>
  <perspective>成本效益</perspective>
  <perspective>实施风险</perspective>
  <perspective>长期维护</perspective>
</perspectives>
```

### 约束优化模式

明确区分必须满足和希望满足的条件。

```
#硬约束 必须符合ISO27001安全标准
#软约束 尽量降低基础设施成本

<constraints>
  <hard>符合ISO27001安全标准</hard>
  <soft>最小化基础设施成本</soft>
</constraints>
```

### 输出模板模式

精确定义期望的输出格式和结构。

```
#输出格式
[标题]
[执行摘要：200字]
[分析：3个关键点]
[建议：分短期和长期]
[实施步骤：列表形式]

<output_template>
  <title />
  <executive_summary max_words="200" />
  <analysis>
    <key_points count="3" />
  </analysis>
  <recommendations>
    <short_term />
    <long_term />
  </recommendations>
  <implementation type="list" />
</output_template>
```

## 三、场景化应用模板

### 技术架构设计

```
#角色 系统架构师

#上下文
[系统背景]
[现有架构限制]
[业务驱动因素]

#需求
1. 功能需求
   1.1 [核心功能1]
   1.2 [核心功能2]
2. 非功能需求
   2.1 [性能指标]
   2.2 [安全要求]

#约束
1. [技术约束]
2. [业务约束]
3. [资源约束]

#输出格式
1. 架构概述
2. 组件分解
3. 通信模式
4. 数据流
5. 部署视图
6. 风险评估

#任务 设计符合上述要求的系统架构
```

### 数据分析计划

```xml
<prompt>
  <role>数据分析专家</role>
  
  <context>
    <data_source>[数据源描述]</data_source>
    <business_questions>[待解决的业务问题]</business_questions>
  </context>
  
  <analysis_objectives>
    <primary>[主要分析目标]</primary>
    <secondary>[次要分析目标]</secondary>
  </analysis_objectives>
  
  <methods>
    <required>[必要分析方法]</required>
    <optional>[可选分析方法]</optional>
  </methods>
  
  <output_format>
    <report>
      <section>执行摘要</section>
      <section>方法论</section>
      <section>发现</section>
      <section>建议</section>
    </report>
    <visualizations>[所需可视化类型]</visualizations>
  </output_format>
  
  <task>创建全面的数据分析计划</task>
</prompt>
```

### 产品设计评估

```
#角色 产品设计评估专家

#上下文
[产品概念]
[目标市场]
[竞争格局]

#评估标准
1. 用户价值
   - [核心价值主张]
   - [痛点解决效果]
2. 市场潜力
   - [市场规模]
   - [增长趋势]
3. 可行性
   - [技术可行性]
   - [商业可行性]

#约束
1. [资源限制]
2. [时间限制]
3. [合规要求]

#输出格式
1. 评估摘要
2. 详细分析
3. SWOT分析
4. 推荐决策
5. 风险缓解策略

#任务 对产品概念进行全面评估，提供基于证据的推荐意见
```

### 研究方法设计

```
#角色 研究方法学专家

#上下文
[研究问题]
[领域背景]
[现有知识差距]

#需求
1. [数据收集要求]
2. [分析方法要求]
3. [验证策略要求]

#约束
1. [资源约束]
2. [时间约束]
3. [伦理考量]

#输出格式
1. 研究设计概述
2. 方法选择与理由
3. 数据收集策略
4. 分析框架
5. 效度保障措施
6. 局限性讨论

#任务 设计适合此研究问题的方法学框架
```

## 四、高级技巧

### 1. 精确指示词缩窄范围

使用精确术语而非模糊描述：

❌ "设计好的架构"  
✅ "设计高可用、低延迟、水平可扩展的微服务架构"

### 2. 参数量化

明确期望的具体数值，避免模糊表述：

❌ "高性能的系统"  
✅ "响应时间<200ms，支持每秒1000事务的系统"

### 3. 关键信息前置

重要内容放在提示词前部：

```
#核心需求(重要) 设计支持跨区域容错的数据复制策略
#次要考虑(可选) 优化网络带宽使用
```

### 4. 角色精细定义

超越简单职业标签，提供具体专长：

❌ "数据科学家"  
✅ "专注于电商领域用户行为分析的数据科学家，精通时间序列和RFM模型"

### 5. 反馈循环设计

内置评估和修正机制：

```
#反馈机制 评估初步方案可行性(1-10)，指出需要更多信息的方面

<feedback>
  <confidence_assessment scale="1-10" />
  <information_gaps />
</feedback>
```

### 6. 条件决策树

设计条件逻辑处理不同情况：

```
#条件处理
IF 数据量>1TB THEN 考虑分布式处理架构
ELSE IF 数据量>100GB THEN 考虑单机优化方案
ELSE 考虑内存处理方案

<conditional>
  <condition>
    <test>数据量>1TB</test>
    <action>考虑分布式处理架构</action>
  </condition>
  <condition>
    <test>数据量>100GB</test>
    <action>考虑单机优化方案</action>
  </condition>
  <default>
    <action>考虑内存处理方案</action>
  </default>
</conditional>
```

### 7. 语言精度控制

明确的表达风格要求：

```
#语言风格 技术精确，使用领域术语，避免模糊表述

<language>
  <precision>technical</precision>
  <terminology>domain-specific</terminology>
  <avoid>ambiguity</avoid>
</language>
```

## 五、实战应用指南

### 提示词开发流程

1. **需求分析**
   - 明确任务目标和成功标准
   - 识别关键约束和资源

2. **结构选择**
   - 简单任务：标签式结构
   - 复杂任务：XML结构
   - 混合需求：选择主结构，适当借用另一种结构元素

3. **内容构建**
   - 定义专业角色
   - 提供足够上下文
   - 明确任务和约束
   - 设计输出格式

4. **迭代优化**
   - 从核心需求开始，逐步添加细节
   - 每次修改单一变量，观察输出变化
   - 识别并解决歧义和缺失信息

### 常见问题解决

1. **输出不一致**
   - 增加结构化约束
   - 提供明确的示例
   - 使用参数量化

2. **输出浅显**
   - 强化专家角色定义
   - 增加思维链提示
   - 明确分析深度要求

3. **内容偏离需求**
   - 厘清核心与次要需求
   - 增加约束条件
   - 设计输出模板

## 六、实用速查表

### 常见提示词标签

| 标签 | 用途 | 示例 |
|------|------|------|
| #角色 | 定义AI身份 | #角色 网络安全专家 |
| #上下文 | 提供背景信息 | #上下文 金融科技创业公司 |
| #需求 | 列出具体要求 | #需求 支持多因素认证 |
| #约束 | 设定限制条件 | #约束 必须符合GDPR |
| #任务 | 描述核心任务 | #任务 设计认证系统 |
| #输出 | 定义输出形式 | #输出 架构文档和流程图 |

### XML元素速查

| 元素 | 用途 | 示例 |
|------|------|------|
| `<role>` | 定义AI身份 | `<role>网络安全专家</role>` |
| `<context>` | 提供背景 | `<context>金融科技</context>` |
| `<requirement>` | 具体要求 | `<requirement>多因素认证</requirement>` |
| `<constraint>` | 限制条件 | `<constraint>GDPR合规</constraint>` |
| `<task>` | 核心任务 | `<task>设计认证系统</task>` |
| `<output>` | 输出形式 | `<output>架构文档</output>` |

### 常用修饰词

| 修饰词 | 用途 | 示例 |
|--------|------|------|
| priority | 优先级 | `<requirement priority="high">` |
| type | 类型 | `<constraint type="technical">` |
| format | 格式 | `<output format="diagram">` |
| level | 深度级别 | `<analysis level="expert">` |
| count | 数量 | `<key_points count="3">` |

## 结语

提示词工程是一项实用技能，通过结构化思维和系统方法可以显著提升AI协作效果。核心在于明确、精确和结构化的表达，以及持续的实践和迭代。
