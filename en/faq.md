# Frequently Asked Questions

![Version](https://img.shields.io/badge/version-2.6.0-green)
![Last Updated](https://img.shields.io/badge/last%20updated-2025--01-brightgreen)

This document collects the most common questions and detailed answers that users encounter when using Hyperliquid Recovery Bot.

## 🤖 Bot Basic Questions

### Q: What is Hyperliquid Recovery Bot?
**A:** Hyperliquid Recovery Bot is a professional Telegram bot designed specifically for Hyperliquid ecosystem users to help users safely recover digital assets from addresses flagged as high-risk.

### Q: Is the bot free to use?
**A:** Address detection is completely FREE. Asset recovery services charge:
- **Service Fee**: 0.5% of total asset value (minimum 1 USDC)
- **Withdrawal Fees**: 2 USDC (Hyperliquid platform)
- **Example**: Recover $1,000 → Pay $7 → Get $993

### Q: How to confirm this is the official bot?
**A:** Please ensure you access the bot using the official link:
- **Official Address**: https://t.me/HyperliquidRecoveryBot
- **Username**: @HyperliquidRecoveryBot
- **Verification**: Check the bot's function menu and interface features

### Q: What languages does the bot support?
**A:** Currently supports:
- **Chinese**: Complete Simplified Chinese support
- **English**: Full English language support

### Q: What are the bot's operating hours?
**A:** The bot runs continuously and can be used at any time. However, it is recommended to perform important operations when network conditions are good.

## 🔍 Address Detection Questions

### Q: What address formats are supported?
**A:** Supports standard Hyperliquid address formats:
- **Length**: 42 characters (including 0x prefix)
- **Format**: 0x + 40 hexadecimal characters
- **Example**: 0x1234567890123456789012345678901234567890

### Q: How long does detection take?
**A:** Usually completed within a few seconds to a few minutes, depending on:
- Network conditions
- Hyperliquid API response speed
- Number and complexity of assets in the address

### Q: Is the detected asset information accurate?
**A:** Yes, the bot uses Hyperliquid official API to get real-time data, which is accurate and reliable. However, please note:
- Price information may have 1-2 minutes delay
- Some new tokens may temporarily have no price information
- Network congestion may affect data updates

### Q: Why do some assets not display prices?
**A:** Possible reasons:
- Newly listed tokens have no price data yet
- Low liquidity tokens
- Price API temporarily unavailable
- Token has been delisted or stopped trading

### Q: Can multiple addresses be detected?
**A:** Currently supports single address detection. Batch detection function is under development.

### Q: How long is detection history saved?
**A:** Detection history is saved for 30 days, after which it will be automatically cleaned to protect user privacy.

## 🛠️ Asset Recovery Questions

### Q: What asset types can be recovered?
**A:** The bot can recover 4 types of assets:
- ✅ **Spot Assets**: USDC, ETH, BTC, and other tokens
- ✅ **Perpetual Contracts**: Long/short positions
- ✅ **Vault Assets**: Assets deposited in vaults (if not locked)
- ✅ **Staked Assets**: HYPE tokens staked to validators (requires waiting period)

### Q: When is asset recovery needed?
**A:** When your address is flagged as high-risk and:
- Cannot access Hyperliquid frontend interface
- Frontend displays "address restricted" message
- Cannot perform normal trading operations
- Assets are "frozen" and cannot be operated

### Q: How long does the recovery process take?
**A:** Spot and perpetual assets are usually recovered quickly. For staked assets:
- **First run**: Unstake HYPE (wait 1 day)
- **Second run**: Withdraw to perpetual account (wait 7 days)
- **Third run**: Convert to USDC and withdraw

### Q: Can the recovery process be cancelled?
**A:** Once confirmed to start recovery operation, it cannot be cancelled. Therefore, please carefully check all information before confirmation.

### Q: Is the private key secure?
**A:** Yes, your private key is completely safe:
- ✅ Never saved to any database
- ✅ Only used during recovery
- ✅ Automatically deleted after completion
- ✅ Only used to sign transactions on official Hyperliquid network

### Q: What if I have staked HYPE tokens?
**A:** Staked assets require multiple runs:
- **Day 0**: Bot unstakes your HYPE (wait 1 day)
- **Day 1**: Bot withdraws to perpetual account (wait 7 days)
- **Day 8**: Bot converts to USDC and withdraws
- The bot will tell you when to run again

### Q: What if my vault assets are locked?
**A:** The bot will skip locked vault assets:
- Wait for the lock period to end
- Then run recovery again to withdraw them

### Q: Can I specify withdrawal to a specific address?
**A:** Yes, you can specify any Arbitrum address as the target address.

### Q: What to do if recovery fails?
**A:** The bot will automatically retry on network failures. If it continues to fail:
1. Check your internet connection
2. Verify private key is correct
3. Check error message
4. Contact support if needed

## 💰 Fee Related Questions

### Q: How much does recovery cost?
**A:** Total cost = Service Fee + Withdrawal Fees
- **Service Fee**: 0.5% of total asset value (minimum 1 USDC)
- **Withdrawal Fees**: 2 USDC (Hyperliquid platform charges)

**Examples**:
| Your Assets | Service Fee | Withdrawal Fees | Total Cost | You Receive |
|-------------|-------------|-----------------|------------|-------------|
| $100 | $1 | $2 | $3 | $97 |
| $1,000 | $5 | $2 | $7 | $993 |
| $10,000 | $50 | $2 | $52 | $9,948 |

### Q: What does the service fee include?
**A:** Service fee includes:
- All asset conversions (ETH, BTC, etc. → USDC)
- All account transfers (Spot → Perpetual)
- All blockchain transaction fees
- Technical support

### Q: When is the service fee charged?
**A:** Service fee is automatically deducted during the final withdrawal step. No fees are charged if recovery fails.

### Q: Why are there withdrawal fees?
**A:** Hyperliquid platform charges 1 USDC per withdrawal. The bot makes 2 withdrawals:
1. First withdrawal: Collect service fee (1 USDC)
2. Second withdrawal: Send your assets (1 USDC)
Total: 2 USDC withdrawal fees

## 🔒 Security Related Questions

### Q: How to ensure operation security?
**A:** Please follow these security recommendations:
- Operate in secure devices and network environments
- Do not enter private keys in public places
- Carefully verify each operation step
- Clean related traces after operation completion

### Q: Will private keys be saved?
**A:** No. Private keys are only temporarily used during the recovery process and will be immediately cleaned after operation completion, without any form of persistent storage.

### Q: How to prevent fraud?
**A:** Please note:
- Only use the official bot @HyperliquidRecoveryBot
- Do not enter private keys elsewhere
- Official will never actively ask you to provide private keys
- Be wary of false promises and unreasonable profit guarantees

### Q: What to do if suspicious activity is found?
**A:** If any suspicious activity is found:
1. Stop operation immediately
2. Screenshot and save evidence (excluding sensitive information)

## 🔧 Technical Questions

### Q: Why does address validation fail?
**A:** Possible reasons:
- Incorrect address format (missing 0x prefix or wrong length)
- Contains invalid characters
- Extra spaces or characters included during copy-paste
- Not a valid Ethereum address format

### Q: Why does private key validation fail?
**A:** Possible reasons:
- Incorrect private key format (includes 0x prefix)
- Incorrect private key length (should be 64 hexadecimal characters)
- Private key does not match address
- Extra characters included during input

### Q: How to handle network errors?
**A:** When encountering network errors:
1. Check if network connection is stable
2. Try switching to a more stable network
3. Wait a few minutes and retry

### Q: What to do if API calls fail?
**A:** API call failures may be due to:
- Hyperliquid API temporarily unavailable
- Network connection issues
- Request frequency too high
- Recommend retrying later

## 📱 User Experience Questions

### Q: Can it be used on mobile phones?
**A:** Yes, the bot fully supports mobile use. Recommendations:
- Use the latest version of Telegram app
- Ensure stable mobile network connection
- Operate in secure environment

### Q: What to do if interface display is abnormal?
**A:** If interface display is abnormal:
1. Try restarting Telegram app
2. Send /start command to reinitialize
3. Check if Telegram app is the latest version

### Q: What to do if operation response is slow?
**A:** Slow operation response may be due to:
- Unstable network connection
- High Telegram server load
- Slow Hyperliquid API response
- Recommend operating when network conditions are good



## 🆘 Emergency Situations

### Q: What to do if errors occur during recovery process?
**A:** If errors occur during recovery process:
1. Don't panic, record error information
2. Check if network connection is normal
3. Check if some operations have been completed

### Q: What to do if assets don't reach target address?
**A:** If assets don't reach target address:
1. Check transaction hash status in blockchain explorer
2. Confirm if target address is correct
3. Wait for more block confirmations



## 📊 Other Questions

### Q: Can I view historical operation records?
**A:** Yes, you can view:
- Address detection history
- Asset recovery records
- Transaction hashes and times
- Operation results and status

### Q: Will the bot be updated regularly?
**A:** Yes, we will update the bot regularly:
- Fix known issues
- Add new features
- Improve user experience
- Enhance security

### Q: Are there tutorials or videos available?
**A:** Currently provides:
- Detailed text tutorials
- Illustrated user guides
- Frequently asked questions
- Video tutorials are in production

---

## 💬 Have Other Questions?

If your question is not answered here, please:

1. **View Other Documentation**:
   - [Quick Start](quick-start.md)
   - [Bot Usage Guide](bot-usage.md)



3. **Community Support**:
   - Join user discussion groups
   - View community discussions
   - Share usage experiences

**Remember**: We are committed to providing you with the best service and support!
