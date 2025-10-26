# Asset Recovery Function

Asset recovery is the core function of Hyperliquid Recovery Bot, helping users safely recover digital assets from Hyperliquid addresses.

## 🎯 Function Overview

### What Does the Bot Do?
The bot automatically helps you recover all your assets from a Hyperliquid address by:
- Converting all your tokens to USDC
- Closing any open positions
- Withdrawing everything to your safe address

This is especially helpful when your address is flagged and you cannot access the official Hyperliquid interface.

### 7-Step Recovery Process

The bot follows a standardized 7-step process:

**Step 1: Convert Spot Assets**
- Sells all non-USDC tokens (ETH, BTC, etc.) in your spot account
- Converts everything to USDC

**Step 2: Transfer to Perpetual Account**
- Moves all USDC from spot account to perpetual account
- No fees for this internal transfer

**Step 3: Close Perpetual Positions**
- Closes all your open perpetual contract positions
- Converts to USDC

**Step 4: Withdraw Vault Assets**
- Withdraws assets from vaults (if you have any)
- Skips locked assets (you'll need to wait for unlock period)

**Step 5: Process Staked Assets**
- Unstakes your HYPE tokens (if you have any)
- Note: Requires 1 day + 7 days waiting period
- May need to run recovery multiple times

**Step 6: Collect Service Fee**
- Bot collects 0.5% service fee (minimum 1 USDC)

**Step 7: Final Withdrawal**
- Withdraws remaining USDC to your target address
- 1 USDC Hyperliquid platform fee

### Supported Asset Types

✅ **Spot Assets**
- USDC, ETH, BTC, and other tokens
- Automatically converted to USDC

✅ **Perpetual Contracts**
- Long/short positions
- Automatically closed and converted to USDC

✅ **Vault Assets**
- Assets deposited in vaults
- Withdrawn if not locked
- Skipped if in lock-up period

✅ **Staked Assets**
- HYPE tokens staked to validators
- Requires waiting period: 1 day (unstake) + 7 days (withdraw)
- May need to run recovery 2-3 times

## 🚀 Usage Methods

### Starting Recovery Function
```
Method 1: Click 🛠️ Asset Recovery in main menu
Method 2: Send /recovery command
Method 3: Click [Start Recovery] on detection result page
```

### Complete Recovery Process

#### Step 1: Enter Recovery Center
```
🔄 Asset Recovery Center

Intelligent asset recovery system providing secure and reliable asset retrieval services.

✨ Features:
• Automatic asset detection and analysis
• Secure recovery process execution
• Support for all Hyperliquid asset types

💡 How it works:
1. Enter the address to recover assets from
2. System analyzes available assets
3. Provide private key or mnemonic phrase for secure recovery
4. Automated recovery execution

Click the button below to start asset recovery

[🚀 Auto Recovery] [⬅️ Back]
```

#### Step 2: Input Address
After clicking "Auto Recovery", the system will prompt for address:
```
💬 Please enter the Hyperliquid address for recovery analysis:
```

#### Step 3: Asset Analysis
```
📊 Analyzing assets...

🔍 Detected assets:
• Spot Account: 3 assets ($750.00)
• Perp Account: 2 assets ($485.06)
• Total Value: $1,235.06

📋 Recovery Plan:
1. Liquidate all non-USDC assets in spot account → USDC
2. Consolidate all spot USDC → transfer to perp account
3. Liquidate all non-USDC assets in perp account → USDC
4. Execute unified withdrawal → all USDC to Arbitrum

💰 Service Fee: $6.18 (0.5%)
💵 Net Recovery: $1,228.88

[Continue] [Cancel]
```

#### Step 4: Private Key Input
```
🔐 Private Key Verification

Please enter the private key for this address:

⚠️ Security Notice:
• Private key is only used for recovery operations
• Automatically cleared from memory after completion
• Ensure you're in a secure environment
• Never share or screenshot your private key

Format: 64-character hexadecimal (with or without 0x prefix)
Example: 1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef

[Enter Private Key]
[Enter Mnemonic]
[Cancel]
```

**Note**: You can choose to use either a private key or mnemonic phrase for recovery.

**If you choose to enter mnemonic**:
```
📝 Enter Mnemonic

Please enter your mnemonic phrase to start the recovery process.

📝 Format Requirements:
• 12 or 24 words separated by spaces
• Example: word1 word2 word3 ... word12

⚠️ Security Tips:
• Ensure you are in a secure environment
• Never share or screenshot your mnemonic

Format: 12 or 24 words separated by spaces
Example: abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon about

[Enter Mnemonic]
[Cancel]
```

#### Step 5: Credential Verification
```
🔍 Verifying credentials...

✅ Credential format valid
✅ Address match confirmed
✅ Account access verified

Proceeding with recovery execution...
```

#### Step 6: Recovery Execution

**Example 1: Spot Assets Only**
```
🚀 Executing recovery plan...

Phase 1/3: Spot Account Liquidation
🔄 Converting ETH to USDC in spot account...
✅ ETH → USDC conversion: 0.5 ETH → 734.56 USDC
🔄 Converting BTC to USDC in spot account...
✅ BTC → USDC conversion: 0.001 BTC → 45.00 USDC
✅ Spot account liquidated: 1,279.56 USDC total

Phase 2/3: Transfer to Perp Account
🔄 Transferring all USDC: Spot → Perp account...
✅ Transfer completed: 1,279.56 USDC moved to perp account

Phase 3/3: Withdrawal
🔄 Withdrawing USDC from perp account to Arbitrum...
💰 Service fee deducted: 6.40 USDC (0.5%)
✅ Withdrawal completed: 1,273.16 USDC transferred

🎉 Recovery completed successfully!
```

**Example 2: Mixed Assets (Spot + Perp)**
```
🚀 Executing recovery plan...

Phase 1/4: Spot Account Liquidation
🔄 Converting ETH to USDC in spot account...
✅ ETH → USDC conversion: 0.3 ETH → 440.74 USDC
✅ Spot account liquidated: 940.74 USDC total

Phase 2/4: Transfer to Perp Account
🔄 Transferring all USDC: Spot → Perp account...
✅ Transfer completed: 940.74 USDC moved to perp account

Phase 3/4: Perp Account Liquidation
🔄 Closing ETH-USD perpetual position...
✅ Position closed: +0.2 ETH realized
🔄 Converting realized ETH to USDC...
✅ ETH → USDC conversion: 0.2 ETH → 294.12 USDC
✅ Perp account liquidated: 1,234.86 USDC total

Phase 4/4: Withdrawal
🔄 Withdrawing USDC from perp account to Arbitrum...
💰 Service fee deducted: 6.17 USDC (0.5%)
✅ Withdrawal completed: 1,228.69 USDC transferred

🎉 Recovery completed successfully!
```

#### Step 6: Recovery Results
```
✅ Asset Recovery Complete

📊 Execution Summary:
• Total Steps: 7
• Completed Steps: 7
• Recovered Amount: 1487.58 USDC
• Actual Fees: 9.48 USDC
- Service Fee: 7.48 USDC
- Withdrawal Fees: 2.00 USDC

[Return to Menu]
```

## 💰 Fee Structure

### How Much Does It Cost?

**Service Fee**
- **Rate**: 0.5% of your total asset value
- **Minimum**: 1 USDC
- **Calculation**: max(Total Value × 0.5%, 1 USDC)

**Withdrawal Fees** (Hyperliquid Platform)
- **Service Fee Withdrawal**: 1 USDC
- **Final Withdrawal**: 1 USDC
- **Total**: 2 USDC

### Complete Fee Examples

**Example 1: Recovering 100 USDC**
- Service Fee: 1 USDC (100 × 0.5% = 0.5, but minimum is 1 USDC)
- Withdrawal Fees: 2 USDC
- **You Receive**: 97 USDC

**Example 2: Recovering 1,000 USDC**
- Service Fee: 5 USDC (1,000 × 0.5%)
- Withdrawal Fees: 2 USDC
- **You Receive**: 993 USDC

**Example 3: Recovering 10,000 USDC**
- Service Fee: 50 USDC (10,000 × 0.5%)
- Withdrawal Fees: 2 USDC
- **You Receive**: 9,948 USDC

### Fee Breakdown

When you see the recovery plan, fees are shown like this:

```
💰 Fee Breakdown:
• Service Fee: 5.00 USDC (0.5% of total value)
• Withdrawal Fees: 2.00 USDC (Hyperliquid platform)
  - Service fee withdrawal: 1.00 USDC
  - Final withdrawal: 1.00 USDC
• Total Cost: 7.00 USDC

💵 You Will Receive: 993.00 USDC
```



## 🔒 Security & Safety

### Is My Private Key Safe?

**Yes! Here's how we protect it:**

✅ **Never Saved**
- Your private key is only used during recovery
- Not saved to any database or file
- Automatically deleted from memory after completion

✅ **Only Used for Signing**
- Only used to sign transactions on Hyperliquid
- Never sent to any external server
- All operations happen on official Hyperliquid network

✅ **You Stay in Control**
- You can verify all transactions on blockchain explorer
- Every transaction has a transaction hash
- You can see exactly where your funds go

### What Should I Do?

**Before Recovery:**
1. Make sure you're in a safe environment
2. Don't share your private key with anyone
3. Double-check the target address

**During Recovery:**
1. Keep Telegram open
2. Don't close the app
3. Wait for all steps to complete

**After Recovery:**
1. Check your target address received the funds
2. Verify the transaction hash on blockchain explorer
3. Your private key is automatically deleted

## ⏰ Special Cases

### Staked Assets (HYPE Tokens)

If you have staked HYPE tokens, the recovery process is different:

**Timeline:**
```
Day 0: First Run
↓ Bot unstakes your HYPE
↓ Wait 1 day
Day 1: Second Run
↓ Bot withdraws to spot account
↓ Wait 7 days
Day 8: Third Run
↓ Bot converts HYPE to USDC and withdraws
```

**Why Multiple Runs?**
- Hyperliquid requires 1 day waiting period after unstaking
- Then requires 7 days waiting period for withdrawal
- The bot will tell you when to run it again

**What You Need to Do:**
1. Run recovery first time → Wait 1 day
2. Run recovery second time → Wait 7 days
3. Run recovery third time → Complete!

### Vault Assets (Locked)

If your vault assets are locked:

**What Happens:**
- Bot checks if assets are locked
- Locked assets are skipped
- Bot tells you how many days until unlock

**What You Need to Do:**
1. Wait for lock-up period to end
2. Run recovery again after unlock
3. Bot will withdraw the vault assets

### Small Positions

**Good News:** The bot will try to close ALL positions, no matter how small!

Even if a position is worth only $0.05, the bot will attempt to close it. This ensures maximum recovery of your assets.

## ❓ Common Questions

### Q1: How long does recovery take?
**A:** Spot and perpetual assets are usually recovered quickly. If you have staked assets, add 1 day + 7 days waiting period.

### Q2: Can I cancel recovery after it starts?
**A:** No, once recovery starts, it cannot be cancelled. Please review the recovery plan carefully before confirming.

### Q3: What if recovery fails halfway?
**A:** You can run recovery again. The bot will detect the current state and continue from where it left off.

### Q4: Why do I need to run recovery multiple times for staked assets?
**A:** Hyperliquid requires waiting periods:
- 1 day after unstaking
- 7 days after withdrawal request
This is a platform requirement, not a bot limitation.

### Q5: What if my vault assets are locked?
**A:** The bot will skip locked assets and tell you when they unlock. Run recovery again after the lock-up period ends.

### Q6: Can I recover assets worth less than $5?
**A:** The bot will attempt to recover all assets, but very small amounts (under $5 total) may not be economical after fees.

### Q7: Where do my assets go?
**A:** All assets are converted to USDC and withdrawn to the target address you specify on the Arbitrum network.

### Q8: Is my private key safe?
**A:** Yes! Your private key is only used during recovery and is automatically deleted from memory after completion. It's never saved anywhere.

### Q9: What if I enter the wrong private key?
**A:** The bot will detect the mismatch and ask you to enter the correct private key. No operations will be performed with an incorrect key.

### Q10: Can I see proof of the transactions?
**A:** Yes! After recovery, you'll receive transaction hashes that you can verify on the Arbitrum blockchain explorer.

## 🆘 Need Help?

If you encounter any issues:

1. **Check FAQ**: Most common questions are answered above
2. **Contact Support**: Use the feedback function in the bot
3. **Provide Details**: Include your address and error message (never share your private key!)

---

**Ready to recover your assets?** Click [Quick Start Guide](quick-start.md) to begin!
