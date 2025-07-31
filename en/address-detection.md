# Address Detection Function

Address detection is one of the core functions of Hyperliquid Recovery Bot, helping users quickly understand the asset situation in Hyperliquid addresses.

## 🎯 功能概述

### 主要功能
- **智能资产识别**: 自动识别现货和永续合约资产
- **实时数据获取**: 使用 Hyperliquid 官方 API 获取最新数据
- **风险等级评估**: 评估地址的安全风险等级
- **价值计算**: 实时计算资产的 USD 价值
- **可恢复性判断**: 判断资产是否可以通过机器人恢复

### 支持的资产类型
- **现货资产 (Spot)**: USDC, ETH, BTC 等主流代币
- **永续合约 (Perp)**: 永续合约持仓和保证金
- **质押资产**: 质押在各种协议中的资产（部分支持）

## 🚀 使用方法

### 方法一：通过主菜单
1. 发送 `/start` 命令打开主菜单
2. 点击 **🔍 地址检测** 按钮
3. 输入要检测的 Hyperliquid 地址

### 方法二：直接命令
1. 发送 `/detect` 命令
2. 直接输入要检测的地址

### 方法三：快捷检测
如果您之前已经检测过地址，可以：
1. 在主菜单选择 **🔍 地址检测**
2. 选择 **使用历史地址**
3. 从列表中选择之前检测过的地址

## 📝 地址格式要求

### 有效地址格式
```
✅ 标准格式: 0x1234567890123456789012345678901234567890
✅ 大小写混合: 0xAbCdEf1234567890123456789012345678901234
✅ 全大写: 0X1234567890ABCDEF1234567890ABCDEF12345678
✅ 全小写: 0x1234567890abcdef1234567890abcdef12345678
```

### 无效地址格式
```
❌ 缺少前缀: 1234567890123456789012345678901234567890
❌ 长度不足: 0x12345
❌ 长度过长: 0x1234567890123456789012345678901234567890123
❌ 无效字符: 0x123456789012345678901234567890123456789G
❌ 空格字符: 0x1234 5678 9012 3456 7890 1234 5678 9012 3456 7890
```

### 地址验证
机器人会自动验证地址格式：
- **长度检查**: 必须是 42 个字符（包含 0x 前缀）
- **前缀检查**: 必须以 0x 或 0X 开头
- **字符检查**: 只能包含 0-9 和 a-f（或 A-F）字符
- **校验和验证**: 验证地址校验和（如果适用）

## 🔍 检测过程详解

### 1. 地址验证阶段
```
🔍 正在验证地址格式...
✅ 地址格式有效
✅ 长度检查通过
✅ 字符验证通过
```

### 2. 数据获取阶段
```
📡 连接 Hyperliquid API...
🔄 获取账户信息...
📊 查询现货资产...
📈 查询永续合约...
💰 获取价格数据...
```

### 3. 数据处理阶段
```
🧮 计算资产价值...
🔒 评估风险等级...
📋 生成检测报告...
✅ 检测完成
```

## 📊 检测结果解读

### 基本信息
```
📍 地址: 0x1234...7890
🔍 风险等级: 高风险
💰 总价值: $1,234.56
📊 资产种类: 3 种
🛠️ 可恢复: 是
⏰ 检测时间: 2024-01-15 14:30:25
```

### 现货资产详情
```
┌─────────────────────────────────┐
│ 现货资产 (Spot Account)          │
├─────────────────────────────────┤
│ USDC: 500.00 ($500.00)         │
│ ETH: 0.5 ($734.56)             │
│ BTC: 0.001 ($45.00)            │
│ DOGE: 1000 (价格未知)            │
└─────────────────────────────────┘

💡 说明:
• 显示代币符号和数量
• 括号内为 USD 价值
• "价格未知" 表示暂时无法获取价格信息
```

### 永续合约详情
```
┌─────────────────────────────────┐
│ 永续合约 (Perp Account)          │
├─────────────────────────────────┤
│ USDC 保证金: 200.00 ($200.00)   │
│ ETH-USD 持仓: 0.1 ETH           │
│ BTC-USD 持仓: 0.005 BTC         │
│ 未实现盈亏: +$15.50             │
└─────────────────────────────────┘

💡 说明:
• 显示保证金余额
• 显示各合约的持仓
• 显示未实现盈亏
```

### 风险等级说明

#### 🟢 低风险
- **描述**: 地址未被任何风险数据库标记
- **特征**: 正常的交易活动，无异常行为
- **建议**: 可以正常使用 Hyperliquid 前端
- **恢复需要**: 通常不需要使用恢复功能

#### 🟡 中等风险
- **描述**: 地址有轻微的风险标记
- **特征**: 可能有一些可疑的交易活动
- **建议**: 谨慎操作，监控账户状态
- **恢复需要**: 可能需要恢复功能

#### 🔴 高风险
- **Description**: Address flagged as high risk
- **Characteristics**: Cannot access Hyperliquid frontend interface
- **Recommendation**: Use recovery function immediately to transfer assets
- **Recovery Need**: Strongly recommend using recovery function

## 💡 Detection Result Analysis

### Recoverability Judgment
The bot determines if assets are recoverable based on the following factors:

1. **Asset Type**:
   - ✅ Spot assets: Usually recoverable
   - ✅ Perpetual contract margin: Recoverable
   - ⚠️ Active positions: Need to close positions first

2. **Asset Quantity**:
   - ✅ Quantity > 0: Recoverable
   - ❌ Quantity = 0: No need for recovery

3. **Network Status**:
   - ✅ Network normal: Recoverable
   - ❌ Network abnormal: Temporarily unable to recover

### Value Calculation Description
- **Real-time Price**: Use Hyperliquid API to get real-time prices
- **Price Source**: Mainly from Hyperliquid internal prices
- **Update Frequency**: Get latest prices for each detection
- **Missing Prices**: Some new tokens may temporarily have no price information

## 🔄 Re-detection

### When Re-detection is Needed
- **Asset Changes**: When address assets change
- **Price Updates**: When latest price information is needed
- **Risk Status**: Check if risk status has changed
- **Regular Monitoring**: Regularly monitor address status

### Re-detection Methods
1. **Quick Re-check**: Click **🔄 Re-detect** on detection result page
2. **Complete Re-check**: Re-enter address for complete detection
3. **Batch Re-check**: Batch re-detection for multiple addresses

## 📈 History Records

### Detection History
The bot saves your detection history:
```
📚 Detection History

Recent Detections:
1. 0x1234...7890 - 2024-01-15 14:30 (High Risk)
2. 0x5678...1234 - 2024-01-14 10:15 (低风险)  
3. 0x9abc...def0 - 2024-01-13 16:45 (中等风险)

[查看详情] [重新检测] [删除记录]
```

### 历史数据用途
- **快速重检**: 快速重新检测之前的地址
- **趋势分析**: 观察地址风险等级变化
- **资产监控**: 监控资产数量变化
- **恢复决策**: 帮助决定是否需要恢复

## ⚠️ 注意事项

### 检测限制
- **频率限制**: 每个用户每分钟最多检测 10 个地址
- **并发限制**: 同时只能进行 1 个检测任务
- **API 限制**: 受 Hyperliquid API 速率限制影响

### 数据准确性
- **实时性**: 数据可能有 1-2 分钟的延迟
- **价格波动**: 价格信息可能因市场波动而变化
- **网络状况**: 网络问题可能影响数据准确性

### 隐私保护
- **地址隐私**: 检测的地址信息会被临时存储
- **数据清理**: 定期清理过期的检测数据
- **匿名化**: 不会关联用户身份信息

## 🆘 常见问题

### Q: 检测失败怎么办？
A: 请检查：
1. 地址格式是否正确
2. 网络连接是否正常
3. 是否超过检测频率限制
4. 稍后重试或联系技术支持

### Q: 为什么某些资产没有价格？
A: 可能原因：
1. 新上线的代币暂无价格数据
2. 流动性较低的代币
3. 价格 API 暂时不可用
4. 代币已经下线或停止交易

### Q: 风险等级是如何判断的？
A: 基于多个因素：
1. 第三方风险数据库
2. 交易行为分析
3. 地址活动模式
4. 社区举报信息

### Q: 检测结果可以导出吗？
A: 目前支持：
1. 复制检测结果文本
2. 生成检测报告截图
3. 导出功能正在开发中
