# Hyperliquid Recovery Bot 用户指南

![Hyperliquid Recovery Bot](https://img.shields.io/badge/Hyperliquid-Recovery%20Bot-blue)
![Version](https://img.shields.io/badge/version-2.6.0-green)
![License](https://img.shields.io/badge/license-MIT-blue)
![Last Updated](https://img.shields.io/badge/last%20updated-2025--10-brightgreen)

## 🤖 什么是 Hyperliquid Recovery Bot？

Hyperliquid Recovery Bot 是一个专业的 Telegram 机器人，专为 Hyperliquid 用户设计，帮助您从被标记为高风险的地址中安全地恢复数字资产。

在 Hyperliquid 平台遇到地址被标记风险，资产无法正常操作？

## ⚠️ 标记地址提示

如果您的地址被Hyperliquid第三方筛选工具标记，系统将显示以下警告：

**English**: Your address has been flagged as high risk by a third-party screening tool. This frontend interface does not support connection to the Hyperliquid blockchain by high risk addresses. If you think this is an error, you can open a support ticket.

**中文**: 您的地址已被第三方筛选工具标记为高风险。此前端界面不支持高风险地址连接到Hyperliquid区块链。如果您认为这是一个错误，您可以开启一个支持票据。

**한국어**: 귀하의 주소가 제3자 검증 도구에 의해 고위험으로 표시되었습니다. 이 프론트엔드 인터페이스는 고위험 주소의 하이퍼리퀴드 블록체인 연결을 지원하지 않습니다. 오류라고 생각되는 경우, 지원 티켓을 열 수 있습니다.

**Français**: Votre adresse a été signalée comme à haut risque par un outil de filtrage tiers. Cette interface frontend ne prend pas en charge la connexion à la blockchain Hyperliquid par des adresses à haut risque. Si vous pensez qu'il s'agit d'une erreur, vous pouvez ouvrir un ticket de support.

当您的 Hyperliquid 地址被标记为高风险，无法通过官方前端界面进行操作时，本机器人可以帮助您：
- 检测地址中的所有资产
- 安全地恢复和转移资产
- 避免资产损失

## ✨ 主要功能

### 🔍 智能地址检测
- **4种资产类型**: 检测现货、永续、金库、质押资产
- **实时数据**: 显示最新余额和美元价值
- **锁定状态**: 查看哪些资产被锁定以及何时解锁
- **即时结果**: 几秒钟内获得完整资产概览

### 🛠️ 7步自动化恢复
- **全自动**: 只需提供私钥，机器人完成所有操作
- **全资产类型**: 处理现货、永续、金库、质押资产
- **智能处理**: 将所有资产转换为 USDC 并提现
- **进度跟踪**: 实时查看每个步骤的进度

### 💰 透明定价
- **服务费**: 0.5%（最低 1 USDC）
- **提现手续费**: 2 USDC（Hyperliquid 平台）
- **无隐藏费用**: 所有费用提前显示
- **示例**: 恢复 $1,000 → 您收到 $993

### 🌐 用户友好
- **中英双语**: 完整的中文和英文支持
- **简单步骤**: 易于遵循的流程
- **安全可靠**: 私钥从不保存

## 🚀 立即开始

### 第一步：访问机器人
点击链接直接访问：**[https://t.me/HyperliquidRecoveryBot](https://t.me/HyperliquidRecoveryBot)**

### 第二步：开始使用
1. 发送 `/start` 命令
2. 选择"地址检测"查看您的资产
3. 如需恢复，选择"资产恢复"功能

### 第三步：安全操作
- 在安全的环境下操作
- 仔细阅读每个步骤的提示
- 确认所有信息后再进行操作

## 💰 费用说明

- **地址检测**: 完全免费
- **服务费**: 总价值的 0.5%（最低 1 USDC）
- **Hyperliquid 提现手续费**:
  - 服务费提现: 1 USDC（用于支付服务费提现的平台手续费）
  - 最终提现: 1 USDC（提现您的资产到目标地址）
  - 小计: 2 USDC
- **总费用计算**: 服务费 + 2 USDC
- **费用示例**:
  - 恢复 $1,000 → 服务费 $5 + 提现费 $2 = 总费用 $7 → 您收到 $993
  - 恢复 $100 → 服务费 $1 + 提现费 $2 = 总费用 $3 → 您收到 $97

## 🔒 安全保障

- **私钥安全**: 从不保存，使用后自动删除
- **操作透明**: 每笔交易都有可验证的哈希
- **官方网络**: 所有操作在官方 Hyperliquid 区块链上
- **您掌控一切**: 在区块链浏览器上验证所有内容

## 📞 获取帮助

如果您在使用过程中遇到任何问题：

1. **查看指南**: 阅读本文档的详细使用指南
2. **常见问题**: 查看 [FAQ 页面](faq.md) 寻找答案
3. **联系支持**: 通过机器人内的反馈功能联系我们

## ⚠️ 重要提示

### 使用场景
- 本机器人仅用于帮助恢复被标记为高风险地址中的资产
- 请确保您了解相关风险并谨慎操作

### 私钥安全
- 私钥临时加密存储在内存中（不写入磁盘）
- 恢复完成后自动删除（最长保存30分钟）
- 建议在安全的网络环境下进行操作

### 资产去向
- **所有资产最终提现到 Arbitrum 网络**
- 请确保您的目标地址支持 Arbitrum 网络
- 可以使用与源地址相同的地址接收

### 最低恢复金额
- 总资产价值必须 **> $5.00** 才能恢复
- 低于此金额无法覆盖手续费成本

### 锁定资产限制
- **金库锁定期内的资产**: 无法提取，需等待解锁后再次运行恢复
- **质押资产**: 需要分阶段恢复（详见下方说明）

### 质押资产恢复流程（重要）

⚠️ **质押资产需要分3次运行恢复**（Hyperliquid 协议限制）:

**第一次运行**:
- 执行 undelegate 操作（解除委托）
- 资产进入 **1 天锁定期**

**1天后第二次运行**:
- 执行 withdraw 操作（提取到永续账户）
- 资产进入 **7 天锁定期**

**7天后第三次运行**:
- 资产完全解锁，可以正常提现

💡 **建议**: 如果您有质押资产，请记录好时间，按计划分3次运行恢复流程

---

**准备好开始了吗？** 点击 [快速开始指南](quick-start.md) 了解详细的使用步骤！
