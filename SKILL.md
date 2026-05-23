---
name: multi-agent-ecommerce
description: Use when 需要搭建电商AI客服系统、处理客户咨询或配置多Agent客服工作流。一键触发：意图识别→智能路由→专业Agent执行（订单/产品/投诉/售后/物流/优惠），循环处理直到客户满意。
version: 1.1.0
author: Muru AI
license: MIT
platforms: [linux, macos, windows]
type: workflow
metadata:
  hermes:
    tags: [multi-agent, ecommerce, customer-service, chatbot, intent-classification, workflow]
    related_skills: [skill-factory, multi-agent-skill-factory, multi-agent-ui-styles]
business_domain: 电商 · 客户服务
complexity: medium
status: production
---

# Multi-Agent E-commerce — 多Agent协作电商客服系统

> 主编调度 + 意图识别 + 6大专业客服Agent，让AI替你处理所有客户咨询。

## 工作流概览

```
客户说"我的订单到哪了"
         ↓
主编接收消息
         ↓
意图识别Agent分析
→ 识别为：物流查询
         ↓
路由到物流Agent
         ↓
物流Agent执行查询
+ 情绪检测（如激动→安抚话术）
         ↓
主编组装最终回复
         ↓
客户收到专业解答
```

## Agent团队配置

| Agent | 输出 | 职责 |
|-------|------|------|
| 主编 | 任务调度+最终交付 | 接收消息、协调Agent、组装回复 |
| 意图识别 | 意图分类报告 | 分析客户意图，识别6大模块之一 |
| 订单查询Agent | 订单状态+建议 | 查询订单、处理发货/付款问题 |
| 产品咨询Agent | 产品信息+对比 | 解答产品问题、规格对比 |
| 投诉处理Agent | 投诉处理方案 | 处理差评、安抚、补偿 |
| 售后Agent | 售后处理方案 | 处理退货/换货/维修 |
| 物流Agent | 物流轨迹+预测 | 查询物流、预测到达 |
| 优惠Agent | 优惠方案 | 推荐优惠券、活动解读 |

## 6大客服模块（references/目录下）

| 模块 | 文件 | 触发关键词 |
|------|------|-----------|
| 订单查询 | [references/skill_order_query.md](references/skill_order_query.md) | 查订单、发货了吗、订单状态 |
| 产品咨询 | [references/skill_product_query.md](references/skill_product_query.md) | 产品好不好、规格、对比 |
| 投诉处理 | [references/skill_complaint.md](references/skill_complaint.md) | 投诉、差评、太差了 |
| 售后服务 | [references/skill_after_sales.md](references/skill_after_sales.md) | 退货、换货、坏了、维修 |
| 物流查询 | [references/skill_logistics.md](references/skill_logistics.md) | 物流、快递、到哪了 |
| 优惠活动 | [references/skill_promotion.md](references/skill_promotion.md) | 优惠、折扣、优惠券 |

## 模板文件

| 文件 | 说明 |
|------|------|
| [references/agents.md](references/agents.md) | 8个Agent的系统提示词模板 |
| [references/pipeline-multi-agent.md](references/pipeline-multi-agent.md) | 多Agent流水线详解 |
| [references/intent-classifier.md](references/intent-classifier.md) | 意图识别分类器 |
| [references/emotion-detection.md](references/emotion-detection.md) | 情绪检测与安抚话术 |
| [references/test_pool.md](references/test_pool.md) | 测试用例池 |

## 核心工作流

### 标准流程（主编调度5步）

```
Step 1: 客户发送消息
         ↓
Step 2: 意图识别Agent分析 → 识别客户意图（6大模块之一）
         ↓
Step 3: 情绪检测 → 判断情绪状态（平静/不满/激动）
         ↓
Step 4: 路由到专业Agent → 执行对应模块流程
         ↓
      ┌── 情绪激动？ ──┐
      ↓              ↓
     是            否
  安抚话术      直接执行
      ↓              ↓
      └── 正常执行流程 ──┘
         ↓
Step 5: 主编组装回复 → 输出最终解答
```

## 意图识别分类

| 意图类型 | 关键词示例 | 路由Agent |
|----------|-----------|-----------|
| 订单查询 | 查订单、发货了吗、订单状态 | 订单查询Agent |
| 产品咨询 | 产品好不好、规格、对比、能不能用 | 产品咨询Agent |
| 投诉处理 | 投诉、差评、太差了、不满意 | 投诉处理Agent |
| 售后处理 | 退货、换货、坏了、维修、三包 | 售后Agent |
| 物流查询 | 物流、快递、到哪了、什么时候到 | 物流Agent |
| 优惠咨询 | 优惠、折扣、优惠券、有活动吗 | 优惠Agent |
| 综合咨询 | 多个问题、模糊描述 | 主编自行判断 |

## 情绪检测与应对

| 情绪状态 | 检测标准 | 应对策略 |
|----------|---------|----------|
| 😤 激动 | 感叹号多、重复词、情绪词 | 先安抚3句再处理 |
| 😕 不满 | 中性词但含失望词 | 先道歉再处理 |
| 😐 平静 | 正常询问语气 | 直接处理 |
| 😊 满意 | 感谢词、好评相关 | 引导好评+推荐 |

## 补偿标准（客服Agent参考）

| 问题类型 | 补偿标准 | 权限 |
|----------|---------|------|
| 物流延迟 | 订单金额5%，最高50元 | AI直接补偿 |
| 产品质量 | 订单金额10-30% | AI直接补偿 |
| 服务态度 | 10-20元优惠券 | AI直接补偿 |
| 退款>200元 | 需主管确认 | ❌ 转人工 |
| 涉及欺诈 | 需主管确认 | ❌ 转人工 |

## 快捷指令

```
/客服 [客户问题]
/查询订单 [手机号后4位]
/处理投诉 [订单号] [问题描述]
```

## Not For
- 跨境电商多语言客服（需翻译模块）
- 线下实体店客服（需人脸识别）
- 技术专业售后（需专业知识库）

## 目录结构

```
multi-agent-ecommerce/
├── SKILL.md                  ← 主入口（主编调度）
└── references/
    ├── skill_order_query.md     ← 6个客服模块
    ├── skill_product_query.md
    ├── skill_complaint.md
    ├── skill_after_sales.md
    ├── skill_logistics.md
    ├── skill_promotion.md
    ├── agents.md                ← 8个Agent模板
    ├── pipeline-multi-agent.md  ← 多Agent流水线详解
    ├── intent-classifier.md     ← 意图识别分类器
    ├── emotion-detection.md     ← 情绪检测与安抚
    └── test_pool.md            ← 测试用例池
```

## 验证清单

- [ ] description以"Use when"开头
- [ ] frontmatter包含完整字段（含type: workflow）
- [ ] references/目录包含agents.md + pipeline-multi-agent.md
- [ ] test_pool.md在references/目录下
- [ ] 8个Agent角色定义清晰
- [ ] 6个客服模块文件完整
