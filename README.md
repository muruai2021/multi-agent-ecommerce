<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multi-Agent E-commerce</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; line-height: 1.6; color: #24292e; background: #f6f8fa; padding: 20px; }
        .container { max-width: 900px; margin: 0 auto; background: #fff; border-radius: 8px; box-shadow: 0 2px 8px rgba(0,0,0,0.1); overflow: hidden; }
        .header { background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%); color: #fff; padding: 40px; text-align: center; }
        .header h1 { font-size: 2.5em; margin-bottom: 10px; }
        .header p { font-size: 1.2em; opacity: 0.9; }
        .lang-switch { display: flex; justify-content: center; gap: 10px; padding: 20px; background: #f6f8fa; border-bottom: 1px solid #e1e4e8; }
        .lang-btn { padding: 10px 30px; border: 2px solid #11998e; background: #fff; color: #11998e; border-radius: 25px; cursor: pointer; font-weight: 600; transition: all 0.3s; }
        .lang-btn:hover { background: #11998e; color: #fff; }
        .lang-btn.active { background: #11998e; color: #fff; }
        .content { padding: 40px; }
        .content[lang="en"] { display: none; }
        h2 { color: #11998e; margin: 30px 0 15px; padding-bottom: 10px; border-bottom: 2px solid #11998e; }
        h3 { color: #333; margin: 20px 0 10px; }
        p { margin: 15px 0; }
        ul { margin: 15px 0; padding-left: 25px; }
        li { margin: 8px 0; }
        code { background: #f6f8fa; padding: 2px 6px; border-radius: 3px; font-family: Monaco, monospace; color: #e74c3c; }
        pre { background: #1e1e1e; color: #d4d4d4; padding: 20px; border-radius: 8px; overflow-x: auto; margin: 15px 0; font-size: 14px; }
        pre code { background: none; color: inherit; }
        table { width: 100%; border-collapse: collapse; margin: 15px 0; }
        th, td { border: 1px solid #e1e4e8; padding: 12px; text-align: left; }
        th { background: #11998e; color: #fff; }
        tr:nth-child(even) { background: #f6f8fa; }
        .badge { display: inline-block; padding: 4px 12px; border-radius: 20px; font-size: 0.85em; margin: 2px; }
        .badge-primary { background: #11998e; color: #fff; }
        .badge-success { background: #27ae60; color: #fff; }
        .badge-warning { background: #f39c12; color: #fff; }
        .footer { text-align: center; padding: 30px; color: #666; border-top: 1px solid #e1e4e8; }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Multi-Agent E-commerce</h1>
            <p>多Agent协作电商客服系统 | Multi-Agent E-commerce Customer Service</p>
        </div>
        <div class="lang-switch">
            <button class="lang-btn active" onclick="switchLang('zh')">中文</button>
            <button class="lang-btn" onclick="switchLang('en')">English</button>
        </div>
        <div class="content" lang="zh">
            <h2>概述</h2>
            <p>Multi-Agent E-commerce 是一个完整的电商AI客服解决方案。通过智能意图识别和专业Agent路由，实现订单查询、产品咨询、投诉处理、售后服务、物流查询、优惠活动六大模块的自动化服务。</p>
            <h3>核心特性</h3>
            <ul>
                <li>智能意图识别，精准路由到专业Agent</li>
                <li>情绪检测，激动客户自动安抚</li>
                <li>标准化补偿体系，AI直接处理常见问题</li>
            </ul>
            <h2>工作流程</h2>
            <pre><code>客户说"我的订单到哪了"
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
客户收到专业解答</code></pre>
            <h2>Agent团队</h2>
            <table>
                <tr><th>Agent</th><th>输出</th><th>职责</th></tr>
                <tr><td>主编</td><td>任务调度+最终交付</td><td>接收消息、协调Agent、组装回复</td></tr>
                <tr><td>意图识别</td><td>意图分类报告</td><td>分析客户意图，识别6大模块之一</td></tr>
                <tr><td>订单查询Agent</td><td>订单状态+建议</td><td>查询订单、处理发货/付款问题</td></tr>
                <tr><td>产品咨询Agent</td><td>产品信息+对比</td><td>解答产品问题、规格对比</td></tr>
                <tr><td>投诉处理Agent</td><td>投诉处理方案</td><td>处理差评、安抚、补偿</td></tr>
                <tr><td>售后Agent</td><td>售后处理方案</td><td>处理退货/换货/维修</td></tr>
                <tr><td>物流Agent</td><td>物流轨迹+预测</td><td>查询物流、预测到达</td></tr>
                <tr><td>优惠Agent</td><td>优惠方案</td><td>推荐优惠券、活动解读</td></tr>
            </table>
            <h2>六大客服模块</h2>
            <table>
                <tr><th>模块</th><th>触发关键词</th></tr>
                <tr><td>订单查询</td><td>查订单、发货了吗、订单状态</td></tr>
                <tr><td>产品咨询</td><td>产品好不好、规格、对比</td></tr>
                <tr><td>投诉处理</td><td>投诉、差评、太差了</td></tr>
                <tr><td>售后服务</td><td>退货、换货、坏了、维修</td></tr>
                <tr><td>物流查询</td><td>物流、快递、到哪了</td></tr>
                <tr><td>优惠活动</td><td>优惠、折扣、优惠券</td></tr>
            </table>
            <h2>情绪检测与应对</h2>
            <table>
                <tr><th>情绪</th><th>检测标准</th><th>应对策略</th></tr>
                <tr><td>激动</td><td>感叹号多、重复词、情绪词</td><td>先安抚3句再处理</td></tr>
                <tr><td>不满</td><td>中性词但含失望词</td><td>先道歉再处理</td></tr>
                <tr><td>平静</td><td>正常询问语气</td><td>直接处理</td></tr>
                <tr><td>满意</td><td>感谢词、好评相关</td><td>引导好评+推荐</td></tr>
            </table>
            <h2>补偿标准</h2>
            <table>
                <tr><th>问题类型</th><th>补偿标准</th><th>权限</th></tr>
                <tr><td>物流延迟</td><td>订单金额5%，最高50元</td><td><span class="badge badge-success">AI直接补偿</span></td></tr>
                <tr><td>产品质量</td><td>订单金额10-30%</td><td><span class="badge badge-success">AI直接补偿</span></td></tr>
                <tr><td>服务态度</td><td>10-20元优惠券</td><td><span class="badge badge-success">AI直接补偿</span></td></tr>
                <tr><td>退款>200元</td><td>需主管确认</td><td><span class="badge badge-warning">转人工</span></td></tr>
                <tr><td>涉及欺诈</td><td>需主管确认</td><td><span class="badge badge-warning">转人工</span></td></tr>
            </table>
            <h2>快捷指令</h2>
            <pre><code>/客服 [客户问题]
/查询订单 [手机号后4位]
/处理投诉 [订单号] [问题描述]</code></pre>
        </div>
        <div class="content" lang="en">
            <h2>Overview</h2>
            <p>Multi-Agent E-commerce is a complete e-commerce AI customer service solution. Through intelligent intent recognition and professional agent routing, it achieves automated service across six modules: order inquiry, product consultation, complaint handling, after-sales service, logistics inquiry, and promotional activities.</p>
            <h3>Core Features</h3>
            <ul>
                <li>Intelligent intent recognition, precise routing to professional agents</li>
                <li>Emotion detection, automatic calming for agitated customers</li>
                <li>Standardized compensation system, AI directly handles common issues</li>
            </ul>
            <h2>Workflow</h2>
            <pre><code>Customer says "Where is my order?"
         ↓
Editor receives message
         ↓
Intent recognition agent analyzes
→ Identified as: logistics inquiry
         ↓
Route to logistics agent
         ↓
Logistics agent executes query + emotion detection
         ↓
Editor assembles final response
         ↓
Customer receives professional answer</code></pre>
            <h2>Agent Team</h2>
            <table>
                <tr><th>Agent</th><th>Output</th><th>Responsibilities</th></tr>
                <tr><td>Editor-in-Chief</td><td>Task scheduling + final delivery</td><td>Receive messages, coordinate agents, assemble responses</td></tr>
                <tr><td>Intent Recognition</td><td>Intent classification report</td><td>Analyze customer intent, identify one of 6 modules</td></tr>
                <tr><td>Order Inquiry Agent</td><td>Order status + suggestions</td><td>Query orders, handle shipping/payment issues</td></tr>
                <tr><td>Product Consultant Agent</td><td>Product info + comparisons</td><td>Answer product questions, spec comparisons</td></tr>
                <tr><td>Complaint Handler Agent</td><td>Complaint resolution plan</td><td>Handle bad reviews, soothe, compensate</td></tr>
                <tr><td>After-sales Agent</td><td>After-sales solution</td><td>Handle returns/exchanges/repairs</td></tr>
                <tr><td>Logistics Agent</td><td>Logistics tracking + prediction</td><td>Query logistics, predict arrival</td></tr>
                <tr><td>Promotion Agent</td><td>Promotion plans</td><td>Recommend coupons, interpret activities</td></tr>
            </table>
            <h2>Six Customer Service Modules</h2>
            <table>
                <tr><th>Module</th><th>Trigger Keywords</th></tr>
                <tr><td>Order Inquiry</td><td>Check order, shipped?, order status</td></tr>
                <tr><td>Product Consultation</td><td>Product quality, specs, comparison</td></tr>
                <tr><td>Complaint Handling</td><td>Complaint, bad review, terrible</td></tr>
                <tr><td>After-sales Service</td><td>Return, exchange, broken, repair</td></tr>
                <tr><td>Logistics Inquiry</td><td>Logistics, express, where is it</td></tr>
                <tr><td>Promotional Activities</td><td>Discount, coupon, promotion</td></tr>
            </table>
            <h2>Emotion Detection & Response</h2>
            <table>
                <tr><th>Emotion</th><th>Detection Criteria</th><th>Response Strategy</th></tr>
                <tr><td>Agitated</td><td>Many exclamation marks, repeated words</td><td>Calm with 3 sentences first, then handle</td></tr>
                <tr><td>Dissatisfied</td><td>Neutral words but with disappointment</td><td>Apologize first, then handle</td></tr>
                <tr><td>Calm</td><td>Normal inquiry tone</td><td>Handle directly</td></tr>
                <tr><td>Satisfied</td><td>Thanks, positive review related</td><td>Guide for positive review + recommendations</td></tr>
            </table>
            <h2>Compensation Standards</h2>
            <table>
                <tr><th>Issue Type</th><th>Compensation</th><th>Permission</th></tr>
                <tr><td>Logistics delay</td><td>5% of order amount, max 50 yuan</td><td><span class="badge badge-success">AI direct</span></td></tr>
                <tr><td>Product quality</td><td>10-30% of order amount</td><td><span class="badge badge-success">AI direct</span></td></tr>
                <tr><td>Service attitude</td><td>10-20 yuan coupon</td><td><span class="badge badge-success">AI direct</span></td></tr>
                <tr><td>Refund >200 yuan</td><td>Requires supervisor</td><td><span class="badge badge-warning">Transfer</span></td></tr>
                <tr><td>Fraud involved</td><td>Requires supervisor</td><td><span class="badge badge-warning">Transfer</span></td></tr>
            </table>
            <h2>Quick Commands</h2>
            <pre><code>/customer [customer question]
/query-order [last 4 digits]
/handle-complaint [order ID] [issue]</code></pre>
        </div>
        <div class="footer">
            <p>Multi-Agent E-commerce | MIT License</p>
        </div>
    </div>
    <script>
        function switchLang(lang) {
            document.querySelectorAll('.content').forEach(el => {
                el.style.display = el.getAttribute('lang') === lang ? 'block' : 'none';
            });
            document.querySelectorAll('.lang-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
        }
    </script>
</body>
</html>