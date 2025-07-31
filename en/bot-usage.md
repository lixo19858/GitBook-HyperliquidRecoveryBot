# Bot Usage Guide

This document provides detailed instructions on all functions and usage methods of Hyperliquid Recovery Bot.

## 🤖 Bot Commands

### Basic Commands

| Command | Function | Description |
|---------|----------|-------------|
| `/start` | Start Bot | Display main menu and function introduction |
| `/detect` | Address Detection | Enter address detection function directly |
| `/recovery` | Asset Recovery | Enter asset recovery function directly |

### Command Usage Examples

```
User: /start
Bot: 🤖 Welcome to Hyperliquid Recovery Bot!
     [Display main menu and function buttons]

User: /detect
Bot: 🔍 Please enter the Hyperliquid address to detect:
     [Wait for user to input address]

User: /recovery
Bot: 🛠️ Asset Recovery Function
     [Display recovery options and instructions]
```

## 🔍 Address Detection Function Details

### Function Features
- **Smart Recognition**: Automatically identify spot and perpetual contract assets
- **Real-time Data**: Get latest asset balance and price information
- **Risk Assessment**: Assess address risk level
- **Value Calculation**: Calculate total asset value (USD)

### Usage Process

#### 1. Start Detection
```
Click: 🔍 Address Detection
Or enter: /detect
```

#### 2. Input Address
```
Bot prompt: 🔍 Please enter the Hyperliquid address to detect:

Valid address formats:
✅ 0x1234567890123456789012345678901234567890
✅ 0xabcdefABCDEF1234567890123456789012345678

Invalid address formats:
❌ 1234567890123456789012345678901234567890 (missing 0x prefix)
❌ 0x12345 (insufficient length)
❌ 0xGHIJKL... (contains invalid characters)
```

#### 3. Detection Process
```
🔍 Detecting address assets...
⏳ Connecting to Hyperliquid API...
📊 Analyzing asset data...
🔒 Assessing risk level...
💰 Calculating asset value...
```

#### 4. Result Display
```
✅ Detection Complete

📍 Address: 0x1234...7890
🔍 Risk Level: High Risk
💰 Total Value: $1,234.56
📊 Asset Count: 3 types of assets

📋 Detailed Asset Information:
┌─────────────────────────────────┐
│ Spot Assets (Spot Account)      │
├─────────────────────────────────┤
│ USDC: 500.00 ($500.00)         │
│ ETH: 0.5 ($734.56)             │
│ BTC: 0.001 ($45.00)            │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│ Perpetual Contracts (Perp)     │
├─────────────────────────────────┤
│ No perpetual contract assets    │
└─────────────────────────────────┘

🛠️ Recoverable: Yes
💡 Suggestion: This address contains recoverable assets, recommend using recovery function
```

### Risk Level Description

| Level | Description | Recommendation |
|-------|-------------|----------------|
| 🟢 Low Risk | Address not flagged | Normal use |
| 🟡 Medium Risk | Address has minor risk flags | Operate cautiously |
| 🔴 High Risk | Address flagged as high risk | Recommend asset recovery |

## 🛠️ Asset Recovery Function Details

### Function Features
- **Automated Process**: Fully automated asset recovery process
- **Smart Conversion**: Automatically convert perpetual contract assets to spot assets
- **Safe Withdrawal**: Safely transfer assets to specified address
- **Transparent Fees**: Clearly display all fees and costs

### Recovery Process Details

#### 1. Start Recovery
```
Click: 🛠️ Asset Recovery
Or enter: /recovery
```

#### 2. Address Input
```
Bot: 🛠️ Asset Recovery Function

Please select operation method:
[Enter New Address] [Use Detected Address]

If choosing to enter new address:
🔍 Please enter the Hyperliquid address that needs asset recovery:
```

#### 3. Private Key Verification
```
Bot: 🔐 Please enter the private key for this address:

⚠️ Security Tips:
• Private key is only used for asset recovery operations
• Will be automatically cleaned after operation completion
• Please ensure input in secure environment

Private key format (without 0x prefix):
1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef
```

#### 4. Asset Analysis
```
🔍 Analyzing assets...
📊 Detected the following assets:

Spot Assets:
• USDC: 500.00 ($500.00)
• ETH: 0.5 ($734.56)

Perpetual Contract Assets:
• None

💰 Total Value: $1,234.56
🔄 Assets needing conversion: None
```

#### 5. Recovery Plan Confirmation
```
📋 Asset Recovery Plan

🎯 Recovery Target: Safely transfer all assets
💰 Total Asset Value: $1,234.56
🏦 Service Fee: $6.17 (0.5%)
💵 Actual Receipt: $1,228.39

📝 执行步骤:
1. ✅ 资产分析完成
2. 🔄 转换永续合约资产 (如有)
3. 🔄 提现现货资产
4. 🔄 收取服务费
5. 🔄 清理临时数据

⏱️ 预估时间: 2-5 分钟

确认执行恢复操作？
[确认恢复] [取消操作]
```

#### 6. 执行恢复
```
🚀 开始执行恢复...

步骤 1/4: 准备恢复环境
✅ 验证私钥和地址
✅ 检查网络连接
✅ 初始化恢复参数

步骤 2/4: 转换资产 (如需要)
🔄 正在转换永续合约资产...
✅ 转换完成

步骤 3/4: 提现资产
🔄 正在提现 USDC...
✅ USDC 提现完成
🔄 正在提现 ETH...
✅ ETH 提现完成

步骤 4/4: 收取服务费
🔄 正在收取服务费...
✅ 服务费收取完成

🎉 恢复完成！
```

#### 7. 恢复结果
```
✅ 资产恢复成功！

📊 恢复摘要:
┌─────────────────────────────────┐
│ 恢复详情                         │
├─────────────────────────────────┤
│ 源地址: 0x1234...7890           │
│ 目标地址: 0x5678...1234         │
│ 恢复时间: 2024-01-15 14:30:25   │
└─────────────────────────────────┘

💰 资产明细:
• USDC: 493.83 (已扣除服务费)
• ETH: 0.5

🧾 费用明细:
• 服务费: $6.17 (0.5%)
• 网络费: 已包含

🔗 交易记录:
• 交易哈希: 0xabcd...ef12
• 区块确认: 已确认

感谢使用 Hyperliquid Recovery Bot！
```

## 🔧 高级功能

### 批量地址检测
```
机器人: 🔍 批量地址检测 (开发中)

功能说明:
• 支持一次检测多个地址
• 生成汇总报告
• 导出检测结果

使用方法:
1. 选择批量检测模式
2. 输入多个地址 (每行一个)
3. 等待批量检测完成
4. 查看汇总结果
```

### 定时检测
```
机器人: ⏰ 定时检测 (开发中)

功能说明:
• 设置定时检测任务
• 资产变化通知
• 风险状态监控

使用方法:
1. 添加监控地址
2. 设置检测频率
3. 配置通知方式
4. 启动定时任务
```

## 📊 使用统计

### 个人统计
```
机器人: 📊 我的使用统计

📈 使用概况:
• 检测次数: 15 次
• 恢复次数: 3 次
• 恢复金额: $5,678.90
• 节省费用: $28.39

📅 最近活动:
• 最后检测: 2024-01-15 14:30
• 最后恢复: 2024-01-10 09:15

🏆 用户等级: 活跃用户
```

### 系统统计
```
机器人: 🌐 系统统计

📊 全局数据:
• 总检测次数: 10,234 次
• 总恢复次数: 1,567 次
• 总恢复金额: $2,345,678.90
• 活跃用户: 3,456 人

📈 今日数据:
• 检测次数: 234 次
• 恢复次数: 45 次
• 新用户: 67 人
```

## 🔔 通知设置

### 通知类型
- **检测完成通知**: 地址检测完成时通知
- **恢复进度通知**: 恢复过程中的进度更新
- **风险警告通知**: 发现高风险地址时警告
- **系统维护通知**: 系统维护和更新通知

### 通知配置
```
机器人: 🔔 通知设置

当前设置:
✅ 检测完成通知
✅ 恢复进度通知  
✅ 风险警告通知
❌ 系统维护通知

[修改设置] [恢复默认]
```

## 💬 反馈和支持

### 反馈功能
```
机器人: 💬 意见反馈

请选择反馈类型:
[功能建议] [问题报告] [使用体验] [其他]

或直接输入您的反馈内容...
```

### 获取帮助
```
机器人: 🆘 帮助中心

📚 文档资源:
• 快速开始指南
• 功能使用教程  
• 常见问题解答
• 安全使用指南

🔗 外部资源:
• 官方网站
• 技术支持
• 社区论坛
• 更新日志
```
