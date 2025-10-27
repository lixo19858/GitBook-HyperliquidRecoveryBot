# Features

Hyperliquid Recovery Bot provides a complete asset detection and recovery solution, specifically designed to help users recover assets from flagged Hyperliquid addresses.

## 🔍 Address Detection Function

### What Can You Detect?

The bot can detect **4 types of assets**:

✅ **Spot Assets**
- USDC, ETH, BTC, and other tokens
- Shows balance and USD value

✅ **Perpetual Contracts**
- Open long/short positions
- Shows position size and value

✅ **Vault Assets**
- Assets deposited in vaults
- Shows lock-up status

✅ **Staked Assets**
- HYPE tokens staked to validators
- Shows staked amount and status

### What Information Do You Get?

After detection, you'll see:
- 💰 **Total Value**: Total worth of all your assets in USD
- 📊 **Asset List**: Detailed list of each asset with amounts
- 🔒 **Lock Status**: Which assets are locked and when they unlock
- ✅ **Recoverability**: Whether assets can be recovered

### Detection Result Example
```
✅ Detection Complete

📍 Address: 0x1234...7890
💰 Total Value: $1,234.56

📊 Assets Found:
[SPOT] USDC: 500.00 ($500.00)
[SPOT] ETH: 0.5 ($734.56)
[PERP] BTC-PERP: 0.001 BTC ($45.00)
[VAULT] USDC: 100.00 ($100.00) 🔒 Locked (3 days)
[STAKED] HYPE: 50.00 ($89.00)

🛠️ Recoverable: Yes
💡 Next Step: Click "Start Recovery" to begin
```

## 🛠️ Asset Recovery Function

### 7-Step Automated Process

The bot handles everything automatically:

**Step 1: Convert Spot Assets**
- Sells all non-USDC tokens to USDC

**Step 2: Transfer to Perpetual**
- Moves USDC to perpetual account

**Step 3: Close Positions**
- Closes all perpetual contract positions

**Step 4: Withdraw Vaults**
- Withdraws unlocked vault assets

**Step 5: Process Staking**
- Unstakes HYPE tokens (requires 1+7 days waiting)

**Step 6: Collect Fee**
- Deducts 0.5% service fee (min 1 USDC)

**Step 7: Final Withdrawal**
- Withdraws everything to your address

### What You Need to Provide

1. **Source Address**: The flagged address with assets
2. **Target Address**: Where you want to receive the funds
3. **Private Key**: To authorize the transactions (automatically deleted after use)

## 💰 Clear Fee Structure

### How Much Does It Cost?

**Service Fee**
- 0.5% of total asset value
- Minimum: 1 USDC

**Hyperliquid Withdrawal Fees**
- Service fee withdrawal: 1 USDC (to pay platform fee for service fee withdrawal)
- Final withdrawal: 1 USDC (to withdraw your assets to target address)
- Subtotal: 2 USDC

**Total Cost Calculation**
- Total Cost = Service Fee + 2 USDC

### Quick Examples

| Your Assets | Service Fee (0.5%) | Withdrawal Fees | Total Cost | You Receive |
|-------------|-------------------|-----------------|------------|-------------|
| $100 | $1 | $2 | **$3** | **$97** |
| $1,000 | $5 | $2 | **$7** | **$993** |
| $10,000 | $50 | $2 | **$52** | **$9,948** |

### What's Included?

✅ All asset conversions (ETH, BTC, etc. → USDC)
✅ All account transfers (Spot → Perpetual)
✅ All blockchain transaction fees
✅ Technical support

❌ No hidden fees
❌ No extra charges

### Why 2 Withdrawals?

1. **First Withdrawal**: Collect service fee to platform address (requires 1 USDC platform fee)
2. **Second Withdrawal**: Withdraw your assets to target address (requires 1 USDC platform fee)

💡 This is Hyperliquid platform's withdrawal mechanism - each withdrawal requires 1 USDC fee

## 🌐 Multilingual Support

The bot supports:
- 🇺🇸 **English**: Full English interface
- 🇨🇳 **中文**: Complete Chinese interface
- 🔄 **Auto-detect**: Automatically detects your language preference

## 🔒 Security Features

### Your Private Key is Safe

✅ **Never Saved**
- Only used during recovery
- Deleted immediately after completion
- Never stored in any database

✅ **Only for Signing**
- Used only to sign transactions
- Never sent to external servers
- All operations on official Hyperliquid network

✅ **You Can Verify**
- Every transaction has a hash
- Check on blockchain explorer
- Full transparency

### Safe Operations

✅ **Address Validation**
- Checks address format before operations
- Verifies private key matches address

✅ **Transaction Confirmation**
- Each step confirmed before proceeding
- Automatic retry on network failures

✅ **Error Handling**
- Graceful handling of failures
- Detailed error messages
- Support available if needed

---

These features ensure that Hyperliquid Recovery Bot provides you with a **safe, transparent, and efficient** asset recovery service.
