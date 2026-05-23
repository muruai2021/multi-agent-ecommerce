# Multi-Agent E-commerce — 多Agent协作电商客服系统

> 主编调度 + 意图识别 + 6大专业客服Agent，让AI替你处理所有客户咨询。

---

# English Version

# Multi-Agent E-commerce — Multi-Agent E-commerce Customer Service System

> Editor-in-Chief scheduling + intent recognition + 6 professional customer service agents, let AI handle all customer inquiries for you.

## Overview

Multi-Agent E-commerce is a complete e-commerce AI customer service solution. Through intelligent intent recognition and professional agent routing, it achieves automated service across six modules: order inquiry, product consultation, complaint handling, after-sales service, logistics inquiry, and promotional activities.

**Core Features:**
- Intelligent intent recognition, precise routing to professional agents
- Emotion detection, automatic calming for agitated customers
- Standardized compensation system, AI directly handles common issues

## Workflow

```
Customer says "Where is my order?"
         ↓
Editor receives message
         ↓
Intent recognition agent analyzes
→ Identified as: logistics inquiry
         ↓
Route to logistics agent
         ↓
Logistics agent executes query
+ Emotion detection (if agitated → calming words)
         ↓
Editor assembles final response
         ↓
Customer receives professional answer
```

## Agent Team

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

## Six Customer Service Modules

| Module | Trigger Keywords |
|--------|-----------------|
| Order Inquiry | 查订单、发货了吗、订单状态 / Check order, shipped?, order status |
| Product Consultation | 产品好不好、规格、对比 / Product quality, specs, comparison |
| Complaint Handling | 投诉、差评、太差了 / Complaint, bad review, terrible |
| After-sales Service | 退货、换货、坏了、维修 / Return, exchange, broken, repair |
| Logistics Inquiry | 物流、快递、到哪了 / Logistics, express, where is it |
| Promotional Activities | 优惠、折扣、优惠券 / Discount, coupon, promotion |

## Intent Classification

| Intent Type | Example Keywords | Route To |
|-------------|------------------|----------|
| Order Inquiry | 查订单、发货了吗、订单状态 | Order Inquiry Agent |
| Product Consultation | 产品好不好、规格、对比 | Product Consultant Agent |
| Complaint Handling | 投诉、差评、太差了 | Complaint Handler Agent |
| After-sales | 退货、换货、坏了、维修 | After-sales Agent |
| Logistics | 物流、快递、到哪了 | Logistics Agent |
| Promotion | 优惠、折扣、优惠券 | Promotion Agent |

## Emotion Detection & Response

| Emotion | Detection Criteria | Response Strategy |
|---------|-------------------|-------------------|
| 😤 Agitated | Many exclamation marks, repeated words, emotion words | Calm with 3 sentences first, then handle |
| 😕 Dissatisfied | Neutral words but with disappointment | Apologize first, then handle |
| 😐 Calm | Normal inquiry tone | Handle directly |
| 😊 Satisfied | Thanks, positive review related | Guide for positive review + recommendations |

## Compensation Standards

| Issue Type | Compensation | Permission |
|------------|--------------|------------|
| Logistics delay | 5% of order amount, max 50 yuan | AI direct compensation |
| Product quality | 10-30% of order amount | AI direct compensation |
| Service attitude | 10-20 yuan coupon | AI direct compensation |
| Refund >200 yuan | Requires supervisor approval | Transfer to human |
| Fraud involved | Requires supervisor approval | Transfer to human |

## Quick Commands

```
/客服 [客户问题] /customer [customer question]
/查询订单 [手机号后4位] /query-order [last 4 digits]
/处理投诉 [订单号] [问题描述] /handle-complaint [order ID] [issue]
```

## Directory Structure

```
multi-agent-ecommerce/
├── SKILL.md                  ← Main entry (Editor-in-Chief scheduling)
└── references/
    ├── skill_order_query.md     ← 6 customer service modules
    ├── skill_product_query.md
    ├── skill_complaint.md
    ├── skill_after_sales.md
    ├── skill_logistics.md
    ├── skill_promotion.md
    ├── agents.md                ← 8 Agent templates
    ├── pipeline-multi-agent.md  ← Multi-agent pipeline details
    ├── intent-classifier.md     ← Intent classification
    ├── emotion-detection.md     ← Emotion detection & calming
    └── test_pool.md            ← Test case pool
```

## Related Skills

- `skill-factory` - Skill packaging basics
- `multi-agent-skill-factory` - Multi-agent SOP packaging
- `multi-agent-ui-styles` - UI style design

## License

MIT
