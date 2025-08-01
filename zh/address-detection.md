# 地址检测功能

地址检测是 Hyperliquid Recovery Bot 的核心功能之一，帮助用户快速了解 Hyperliquid 地址中的资产情况。

## 🎯 功能概述

### 主要功能
- **实时资产检测**: 使用 Hyperliquid 官方 API 获取最新资产数据
- **多账户支持**: 检测现货、永续合约、金库和质押账户中的资产
- **USD 价值计算**: 使用市场价格实时计算资产的 USD 价值
- **风险等级评估**: 基于总资产价值的简单风险评估
- **恢复评估**: 判断资产是否达到最低恢复门槛

### 支持的资产类型
- **现货资产 (Spot)**: 现货账户中的 USDC、ETH、BTC 等代币
- **永续合约 (Perp)**: 永续合约账户中的保证金余额和持仓
- **金库资产 (Vault)**: 存入 Hyperliquid 金库的资产
- **质押资产 (Staked)**: 质押在各种协议中的资产

## 🚀 使用方法

### 方法一：通过主菜单
1. 发送 `/start` 命令打开主菜单
2. 点击 **🔍 地址检测** 按钮
3. 输入要检测的 Hyperliquid 地址

### 方法二：直接命令
1. 发送 `/detect` 命令
2. 直接输入要检测的地址

### 方法三：从钱包管理
如果您已导入钱包，可以：
1. 进入 **💼 钱包管理**
2. 选择钱包并点击 **查看详情**
3. 点击 **🔍 检测资产** 查看当前余额

## 📝 地址格式要求

### 有效地址格式
Hyperliquid 使用以太坊兼容地址：
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
机器人使用 viem 库自动验证地址格式：
- **长度检查**: 必须是 42 个字符（包含 0x 前缀）
- **前缀检查**: 必须以 0x 或 0X 开头
- **字符检查**: 只能包含 0-9 和 a-f（或 A-F）字符
- **校验和验证**: 验证以太坊地址校验和

## 🔍 检测过程详解

### 1. 地址验证阶段
```
🔍 正在验证地址格式...
✅ 地址格式有效（使用 viem 库）
✅ 长度检查通过（42 个字符）
✅ 校验和验证通过
```

### 2. 数据获取阶段
```
📡 连接 Hyperliquid API...
🔄 获取市场价格用于 USD 估值...
📊 查询现货账户状态...
📈 查询永续合约状态...
🏦 查询金库资产...
🔒 查询质押资产...
```

### 3. 数据处理阶段
```
🧮 使用市场价格计算 USD 价值...
📊 处理所有账户的资产余额...
🔒 基于总价值评估风险等级...
📋 生成检测报告...
✅ 检测完成
```

## 📊 检测结果解读

### 基本信息
```
📍 地址: 0x1234...7890
🔍 风险等级: 中等风险
💰 总价值: $1,234.56
📊 资产数量: 5 个资产
🛠️ 可恢复: 是（超过 $5.00 门槛）
⏰ 检测时间: 2024-01-15 14:30:25
```

### 资产显示格式
资产显示包含以下信息：
- **代币符号**: 资产的符号（如 USDC、ETH）
- **账户类型**: [SPOT]、[PERP]、[VAULT] 或 [STAKED]
- **余额**: 精确的代币数量
- **USD 价值**: 当前市场价值（如果价格可获取）

### 资产显示示例
```
💰 发现的资产:

[SPOT] USDC: 500.00 ($500.00)
[SPOT] ETH: 0.5 ($734.56)
[PERP] USDC: 200.00 ($200.00)
[VAULT] BTC: 0.001 ($45.00)
[STAKED] DOGE: 1000 (价格未知)

💡 说明:
• [SPOT] = 现货账户资产
• [PERP] = 永续合约账户资产
• [VAULT] = 金库存入资产
• [STAKED] = 质押资产
• "价格未知" = 市场价格暂时不可用
```

### 风险等级说明

风险等级基于总资产价值和资产数量计算：

#### 🟢 低风险
- **标准**: 总价值 < $1,000 且资产数量 ≤ 5
- **描述**: 小型投资组合，资产有限
- **特征**: 恢复操作复杂度较低
- **建议**: 适用标准恢复流程

#### 🟡 中等风险
- **标准**: 总价值 $1,000-$10,000 或资产数量 6-10
- **描述**: 中型投资组合，需要谨慎处理
- **特征**: 可能涉及多种资产类型和转换
- **建议**: 执行前仔细审查恢复计划

#### 🔴 高风险
- **标准**: 总价值 > $10,000 或资产数量 > 10
- **描述**: 大型投资组合，需要格外谨慎
- **特征**: 复杂恢复，多步骤操作，费用较高
- **建议**: 考虑分批恢复或寻求专业协助

## 💡 检测结果分析

### 可恢复性评估
机器人根据以下标准判断资产是否可恢复：

1. **最低价值门槛**:
   - ✅ 总价值 ≥ $5.00：视为可恢复
   - ❌ 总价值 < $5.00：低于最低门槛

2. **支持的资产类型**:
   - ✅ 现货资产：可恢复（转换为 USDC，转移到期货账户，然后提现）
   - ✅ 永续合约保证金：可恢复（平仓后从期货账户提现保证金）
   - ✅ 金库资产：可恢复（可能需要从金库提取）
   - ✅ 质押资产：可恢复（可能需要解除质押）

3. **技术可行性**:
   - ✅ 有效地址格式：所有操作的必要条件
   - ✅ API 可访问性：Hyperliquid API 必须响应
   - ✅ 网络状态：区块链网络必须正常运行

### USD 价值计算
- **价格来源**: Hyperliquid API 市场数据（`getAllMids()`）
- **更新频率**: 每次检测都获取实时价格
- **计算方法**: `代币余额 × 当前市场价格`
- **价格缺失**: 市场数据不可用时显示"价格未知"
- **精度**: 使用适当的小数位数显示价值

## 🔄 重新检测和更新

### 何时需要重新检测
- **资产变化**: 交易或转账后
- **价格更新**: 需要当前市场价格时
- **恢复规划**: 开始资产恢复操作前
- **投资组合监控**: 定期监控资产价值

### 重新检测方法
1. **从检测结果**: 点击 **🔄 重新检测** 按钮
2. **新检测**: 重新输入相同地址进行全新检测
3. **从钱包详情**: 对已导入钱包使用钱包管理界面



## ⚠️ 注意事项

### 技术限制
- **API 依赖**: 需要 Hyperliquid API 正常运行
- **网络要求**: 需要稳定的互联网连接
- **速率限制**: 受 Hyperliquid API 速率限制约束
- **测试网支持**: 可配置为测试网或主网

### 数据准确性
- **实时价格**: 每次检测都更新市场价格
- **余额精度**: 使用 Hyperliquid API 的完整精度
- **网络延迟**: 由于区块链确认时间可能有轻微延迟
- **价格可用性**: 某些新代币或低交易量代币可能缺少价格数据

### 安全考虑
- **只读操作**: 检测只读取数据，从不修改账户
- **无需私钥**: 地址检测不需要私钥
- **API 安全**: 使用官方 Hyperliquid API 端点
- **数据隐私**: 不永久存储敏感数据

## 🆘 常见问题

### Q: 检测失败怎么办？
A: 请检查以下项目：
1. **地址格式**: 确保是有效的以太坊格式地址（42 个字符，以 0x 开头）
2. **网络连接**: 验证稳定的互联网连接
3. **API 状态**: Hyperliquid API 可能暂时不可用
4. **重试**: 稍等片刻后重试，或联系支持如果问题持续

### Q: 为什么某些资产显示"价格未知"？
A: 可能原因：
1. **新代币**: 最近上线的代币可能还没有价格数据
2. **低流动性**: 交易量极低的代币
3. **API 问题**: Hyperliquid 价格 API 暂时不可用
4. **下线代币**: 不再活跃交易的代币

### Q: 风险等级是如何计算的？
A: 风险等级由以下因素决定：
1. **总投资组合价值**: 价值越高 = 风险类别越高
2. **资产数量**: 资产越多 = 复杂度增加
3. **简单算法**:
   - 低风险: < $1,000 且 ≤ 5 个资产
   - 中等风险: $1,000-$10,000 或 6-10 个资产
   - 高风险: > $10,000 或 > 10 个资产

### Q: "可恢复"是什么意思？
A: 如果满足以下条件，地址被视为可恢复：
1. **最低价值**: 总资产价值 ≥ $5.00
2. **支持的资产**: 包含现货、永续合约、金库或质押资产（均通过期货账户提现）
3. **技术访问**: 地址可通过 Hyperliquid API 访问

### Q: 可以多次检测同一地址吗？
A: 是的，您可以重新检测地址以：
1. **获取更新余额**: 交易或转账后
2. **刷新价格**: 获取当前市场价值
3. **监控变化**: 跟踪投资组合随时间的变化
4. **恢复前检查**: 恢复操作前验证资产
