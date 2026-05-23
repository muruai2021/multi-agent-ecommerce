# Multi-Agent E-commerce

[English](#english) | [中文](#中文)

---

## English

### Overview

**Multi-Agent E-commerce** is a complete e-commerce AI customer service solution. Through intelligent intent recognition and professional agent routing, it achieves automated service across six modules: order inquiry, product consultation, complaint handling, after-sales service, logistics inquiry, and promotional activities.

**Core Features:**
- Intelligent intent recognition, precise routing to professional agents
- Emotion detection, automatic calming for agitated customers
- Standardized compensation system, AI directly handles common issues

### Workflow

```
Customer says "Where is my order?"
         ↓
Editor receives message
         ↓
Intent recognition agent analyzes → Identified as: logistics inquiry
         ↓
Route to logistics agent
         ↓
Logistics agent executes query + emotion detection
         ↓
Editor assembles final response
         ↓
Customer receives professional answer
```

### Agent Team

| Agent | Output | Responsibilities |
|-------|--------|------------------|
| Editor-in-Chief | Task scheduling + final delivery | Receive messages, coordinate agents, assemble responses |
| Intent Recognition | Intent classification report | Analyze customer intent, identify one of 6 modules |
| Order Inquiry Agent | Order status + suggestions | Query orders, handle shipping/payment issues |
| Product Consultant Agent | Product info + comparisons | Answer product questions, spec comparisons |
| Complaint Handler Agent | Complaint resolution plan | Handle bad reviews, soothe, compensate |
| After-sales Agent | After-sales solution | Handle returns/exchanges/repairs |
| Logistics Agent | Logistics tracking + prediction | Query logistics, predict arrival |
| Promotion Agent | Promotion plans | Recommend coupons, interpret activities |

### Six Customer Service Modules

| Module | Trigger Keywords |
|--------|-----------------|
| Order Inquiry | Check order, shipped?, order status |
| Product Consultation | Product quality, specs, comparison |
| Complaint Handling | Complaint, bad review, terrible |
| After-sales Service | Return, exchange, broken, repair |
| Logistics Inquiry | Logistics, express, where is it |
| Promotional Activities | Discount, coupon, promotion |

### Emotion Detection & Response

| Emotion | Detection Criteria | Response Strategy |
|---------|---------------------|-------------------|
| Agitated | Many exclamation marks, repeated words | Calm with 3 sentences first, then handle |
| Dissatisfied | Neutral words but with disappointment | Apologize first, then handle |
| Calm | Normal inquiry tone | Handle directly |
| Satisfied | Thanks, positive review related | Guide for positive review + recommendations |

### Compensation Standards

| Issue Type | Compensation | Permission |
|------------|--------------|------------|
| Logistics delay | 5% of order amount, max 50 yuan | AI direct |
| Product quality | 10-30% of order amount | AI direct |
| Service attitude | 10-20 yuan coupon | AI direct |
| Refund >200 yuan | Requires supervisor | Transfer |
| Fraud involved | Requires supervisor | Transfer |

### Quick Commands

```
/customer [customer question]
/query-order [last 4 digits]
/handle-complaint [order ID] [issue]
```

---

## 中文

### 概述

**Multi-Agent E-commerce** 是一个完整的电商AI客服解决方案。通过智能意图识别和专业Agent路由，实现订单查询、产品咨询、投诉处理、售后服务、物流查询、优惠活动六大模块的自动化服务。

**核心特性：**
- 智能意图识别，精准路由到专业Agent
- 情绪检测，激动客户自动安抚
- 标准化补偿体系，AI直接处理常见问题

### 工作流程

```
客户说"我的订单到哪了"
         ↓
主编接收消息
         ↓
意图识别Agent分析 → 识别为：物流查询
         ↓
路由到物流Agent
         ↓
物流Agent执行查询 + 情绪检测
         ↓
主编组装最终回复
         ↓
客户收到专业解答
```

### Agent团队

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

### 六大客服模块

| 模块 | 触发关键词 |
|------|-----------|
| 订单查询 | 查订单、发货了吗、订单状态 |
| 产品咨询 | 产品好不好、规格、对比 |
| 投诉处理 | 投诉、差评、太差了 |
| 售后服务 | 退货、换货、坏了、维修 |
| 物流查询 | 物流、快递、到哪了 |
| 优惠活动 | 优惠、折扣、优惠券 |

### 情绪检测与应对

| 情绪 | 检测标准 | 应对策略 |
|------|----------|----------|
| 激动 | 感叹号多、重复词、情绪词 | 先安抚3句再处理 |
| 不满 | 中性词但含失望词 | 先道歉再处理 |
| 平静 | 正常询问语气 | 直接处理 |
| 满意 | 感谢词、好评相关 | 引导好评+推荐 |

### 补偿标准

| 问题类型 | 补偿标准 | 权限 |
|----------|----------|------|
| 物流延迟 | 订单金额5%，最高50元 | AI直接补偿 |
| 产品质量 | 订单金额10-30% | AI直接补偿 |
| 服务态度 | 10-20元优惠券 | AI直接补偿 |
| 退款>200元 | 需主管确认 | 转人工 |
| 涉及欺诈 | 需主管确认 | 转人工 |

### 快捷指令

```
/客服 [客户问题]
/查询订单 [手机号后4位]
/处理投诉 [订单号] [问题描述]
```

---

MIT License