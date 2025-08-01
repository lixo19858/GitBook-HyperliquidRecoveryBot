# Asset Recovery Function

Asset recovery is the core function of Hyperliquid Recovery Bot, helping users safely recover digital assets from Hyperliquid addresses.

## 🎯 Function Overview

### Recovery Principle
The bot helps users recover assets by directly calling Hyperliquid API to perform asset conversions, transfers, and withdrawals. This is particularly useful when users need to move assets from addresses that may have restricted access to the official frontend.

### Recovery Process
1. **Comprehensive Asset Analysis**: Systematic detection and valuation of all assets across spot, perpetual contract, vault, and staking accounts
2. **Spot Account Liquidation**: Execute market orders to convert all non-USDC assets in spot account to USDC, ensuring complete liquidation
3. **Inter-Account Consolidation**: Transfer all USDC holdings from spot account to perpetual contract account for centralized management
4. **Perpetual Contract Liquidation**: Close all open positions and convert remaining non-USDC assets in perp account to USDC
5. **Unified Withdrawal Execution**: Perform consolidated withdrawal of all USDC from perpetual contract account to Arbitrum network
6. **Automated Fee Settlement**: Seamless deduction of service fees during the withdrawal transaction

### Supported Asset Types
- **Spot Assets**: Direct conversion and withdrawal of spot account assets
- **Perpetual Contract Assets**: Close positions and transfer margin to spot
- **Vault Assets**: Withdrawal from Hyperliquid vaults (if supported)
- **Staked Assets**: Unstaking and recovery (if supported)

## 🚀 Usage Methods

### Starting Recovery Function
```
Method 1: Click 🛠️ Asset Recovery in main menu
Method 2: Send /recovery command
Method 3: Click [Start Recovery] on detection result page
Method 4: From wallet details page for imported wallets
```

### Complete Recovery Process

#### Step 1: Address Input
```
🛠️ Asset Recovery Function

Please enter the address you want to recover assets from:

💡 Tips:
• Use address from recent detection results
• Select from imported wallet list
• Enter new Hyperliquid address

[Enter Address] [Use Recent] [Select Wallet]
```

#### Step 2: Asset Analysis
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

#### Step 3: Private Key Input
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

[Enter Private Key] [Cancel]
```

#### Step 4: Private Key Verification
```
🔍 Verifying private key...

✅ Private key format valid
✅ Address match confirmed
✅ Account access verified

Proceeding with recovery execution...
```

#### Step 5: Recovery Execution
```
🚀 Executing systematic recovery plan...

Phase 1/4: Spot Account Liquidation
🔄 Liquidating ETH in spot account...
✅ ETH → USDC conversion: 0.5 ETH → 734.56 USDC
🔄 Liquidating BTC in spot account...
✅ BTC → USDC conversion: 0.001 BTC → 45.00 USDC
✅ Spot account fully liquidated: 1,279.56 USDC total

Phase 2/4: Inter-Account Consolidation
🔄 Transferring all USDC: Spot → Perp account...
✅ Transfer executed: 1,279.56 USDC moved to perp account

Phase 3/4: Perp Account Liquidation
🔄 Closing ETH-USD perpetual position...
✅ Position liquidated: +0.1 ETH realized profit
🔄 Converting realized ETH to USDC...
✅ Final conversion: 0.1 ETH → 147.12 USDC
✅ Perp account fully liquidated: 1,426.68 USDC total

Phase 4/4: Unified Withdrawal
🔄 Executing withdrawal to Arbitrum network...
💰 Service fee automatically deducted: 7.13 USDC (0.5%)
✅ Withdrawal completed: 1,419.55 USDC transferred

🎉 Recovery process completed successfully!
```

#### Step 6: Recovery Results
```
✅ Asset Recovery Successful!

📊 Recovery Summary:
┌─────────────────────────────────┐
│ Recovery Details                │
├─────────────────────────────────┤
│ Source Address: 0x1234...7890   │
│ Target Network: Arbitrum        │
│ Recovery Time: 2024-01-15 14:35 │
│ Duration: 4 min 23 sec          │
└─────────────────────────────────┘

💰 Asset Breakdown:
• Original Total: $1,495.06
• Service Fee: $7.48 (0.5%)
• Network Fees: Included
• Final Amount: $1,487.58

🔗 Transaction Hash:
0xabc123...def456 ✅ Confirmed

[View on Explorer] [Return to Menu]
```

## 💰 Fee Structure Details

### Service Fee Calculation
The service fee is calculated as a percentage of the total recovery value:

- **Rate**: 0.5% of total asset value
- **Minimum Fee**: $1.00 USDC
- **Maximum Fee**: $100,000,000 USDC (effectively no maximum)
- **Currency**: Fees collected in USDC only

### Fee Calculation Examples
```
Example 1: Recovery value $100
Service fee = max($100 × 0.5%, $1.00) = $1.00

Example 2: Recovery value $1,000
Service fee = $1,000 × 0.5% = $5.00

Example 3: Recovery value $10,000
Service fee = $10,000 × 0.5% = $50.00

Example 4: Recovery value $100,000
Service fee = $100,000 × 0.5% = $500.00
```

### What's Included in the Fee
- **Asset Conversion**: Converting non-USDC assets to USDC
- **Account Transfers**: Moving assets between spot and perp accounts
- **Withdrawal Processing**: Executing withdrawal to Arbitrum network
- **Network Fees**: All blockchain transaction costs included
- **Technical Support**: Bot operation and maintenance costs

### Fee Collection Process
1. **Calculation**: Fee calculated based on total detected asset value
2. **Deduction**: Automatically deducted during final withdrawal step
3. **Transparency**: Fee amount clearly shown before execution
4. **Single Payment**: One-time fee, no additional charges



## 🔒 Security Implementation

### Private Key Handling
The bot implements strict security measures for private key management:

```
🔐 Private Key Security:

1. Memory-Only Storage:
   • Private keys never written to disk
   • Stored only in memory during operation
   • Automatically cleared after completion

2. Encryption in Transit:
   • All API communications use HTTPS
   • Private keys encrypted when passed between functions
   • No logging of sensitive data

3. Minimal Exposure:
   • Private key used only for signing transactions
   • No unnecessary operations performed
   • Immediate cleanup after each step
```

### Operation Security
```
🛡️ Security Mechanisms:

1. Input Validation:
   • Address format verification using viem library
   • Private key format validation
   • Asset balance verification before operations

2. Transaction Safety:
   • Each operation confirmed before proceeding
   • Automatic retry on network failures
   • Rollback capability for failed operations

3. API Security:
   • Official Hyperliquid SDK used exclusively
   • Rate limiting respected
   • Error handling for all API calls
```

### Recovery Process Security
```
💎 Process Security:

1. Step-by-Step Execution:
   • Each recovery step executed independently
   • Progress tracked and logged
   • Failure isolation prevents cascade errors

2. Asset Protection:
   • Withdrawals only to Arbitrum network
   • Transaction hashes provided for verification
   • Complete audit trail maintained

3. Error Recovery:
   • Graceful handling of partial failures
   • Detailed error reporting
   • Manual intervention support when needed
```

## ⚠️ Important Notes

### Pre-Operation Requirements
1. **Stable Network**: Ensure reliable internet connection throughout the process
2. **Secure Environment**: Use the bot in a secure, private environment
3. **Private Key Access**: Have the correct private key ready for the source address
4. **Sufficient Time**: Allow 5-15 minutes for complete recovery process

### During Operation
1. **Stay Connected**: Keep Telegram app open and connected
2. **No Interference**: Avoid other operations on the same address
3. **Monitor Progress**: Watch for any error messages or requests for input
4. **Be Patient**: Some steps may take several minutes to complete

### Post-Operation Verification
1. **Check Transaction**: Verify the withdrawal transaction on Arbitrum explorer
2. **Confirm Receipt**: Check that funds arrived at the destination address
3. **Save Records**: Keep transaction hash for your records
4. **Clear Data**: Private key is automatically cleared from bot memory

## 🔧 Technical Implementation

### Recovery Algorithm
The bot follows a standardized recovery process:

```
📋 Professional Recovery Algorithm:

1. Multi-Account Asset Discovery:
   • Parallel query of spot, perp, vault, and staked accounts
   • Real-time USD valuation using market data
   • Comprehensive asset inventory and conversion mapping

2. Sequential Liquidation Strategy:
   • Phase A: Complete spot account liquidation (non-USDC → USDC)
   • Phase B: Spot-to-perp USDC consolidation transfer
   • Phase C: Complete perp account liquidation (non-USDC → USDC)
   • Phase D: Unified withdrawal execution

3. Risk-Managed Execution:
   • Market order execution with slippage protection
   • Transaction confirmation at each phase
   • Automatic retry mechanism for failed operations

4. Settlement and Finalization:
   • Proportional service fee calculation and deduction
   • Cross-chain withdrawal to Arbitrum network
   • Transaction hash verification and audit trail
```

### Supported Networks
- **Source**: Hyperliquid (mainnet or testnet)
- **Destination**: Arbitrum One (for mainnet) or Arbitrum Sepolia (for testnet)
- **Asset**: USDC only (all assets converted to USDC before withdrawal)

### Error Handling
- **Network Issues**: Automatic retry with exponential backoff
- **API Failures**: Graceful degradation and error reporting
- **Partial Failures**: Detailed status reporting for manual intervention
- **Transaction Failures**: Retry mechanism with user notification

## 🆘 Troubleshooting

### Common Issues and Solutions

#### Q: Private Key Verification Failed
```
❌ Possible Causes:
1. Invalid private key format
2. Private key doesn't match the address
3. Incorrect key length (not 64 hex characters)

✅ Solutions:
1. Ensure private key is 64 hexadecimal characters
2. Remove 0x prefix if present
3. Verify the private key corresponds to the correct address
4. Try importing the key into a wallet to verify it works
```

#### Q: Asset Conversion Failed
```
❌ Possible Causes:
1. Insufficient liquidity for the asset
2. Market volatility causing slippage
3. Hyperliquid API temporary issues

✅ Solutions:
1. Retry the operation after a few minutes
2. Check if the asset is actively traded
3. Contact support if the issue persists
```

#### Q: Withdrawal Transaction Failed
```
❌ Possible Causes:
1. Network congestion on Arbitrum
2. Insufficient balance for network fees
3. Temporary API connectivity issues

✅ Solutions:
1. Wait for network conditions to improve
2. Ensure sufficient USDC balance for fees
3. Retry the withdrawal operation
4. Check transaction status on Arbitrum explorer
```

#### Q: Recovery Process Stuck
```
❌ Possible Causes:
1. Network connectivity issues
2. Hyperliquid API rate limiting
3. Large transaction requiring more time

✅ Solutions:
1. Check your internet connection
2. Wait for the current step to complete (up to 5 minutes)
3. Do not close Telegram during the process
4. Contact support if stuck for more than 10 minutes
```

### Getting Help
If you encounter issues not covered above:

1. **Use Bot Feedback**: Send feedback through the bot's built-in feedback system
2. **Provide Details**: Include the address, error message, and time of the issue
3. **Transaction Hash**: If available, provide any transaction hashes
4. **Screenshots**: Screenshots of error messages can be helpful

### Recovery Limitations
- **Minimum Recovery**: $5.00 total value required
- **Supported Assets**: Only assets with available market prices
- **Network Dependency**: Requires both Hyperliquid and Arbitrum networks to be operational
- **API Availability**: Dependent on Hyperliquid API uptime
