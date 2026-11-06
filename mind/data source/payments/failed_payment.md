# DZShop — Failed Payments

## Overview

Payment failures can happen for various reasons. This guide helps you understand why a payment failed and how to fix it.

## Common Reasons for Payment Failure

### 1. Insufficient Funds

**Error Message**: "Transaction declined: insufficient funds"

**Cause**: Your card/account doesn't have enough balance.

**Solutions**:
- Check your account balance.
- Top up your card or account.
- Try a different payment method.
- Use a smaller order amount (split into two orders).

### 2. Incorrect Card Details

**Error Message**: "Invalid card number" or "Invalid CVV"

**Cause**: You entered wrong card number, expiry date, or CVV.

**Solutions**:
- Double-check the card number (16 digits, no spaces).
- Verify the expiry date (MM/YY format).
- Check the CVV (3 digits on the back of the card).
- Try entering the details again.

### 3. Card Expired

**Error Message**: "Card has expired"

**Cause**: Your card's expiry date has passed.

**Solutions**:
- Check the expiry date on your card.
- Contact your bank to renew the card.
- Use a different payment method.

### 4. Card Blocked

**Error Message**: "Card is blocked" or "Contact your bank"

**Cause**: Your bank has blocked the card (security, suspicious activity, etc.).

**Solutions**:
- Call your bank's customer service.
- Ask them to unblock the card for online transactions.
- Confirm that DZShop (or SATIM) is not on their blocked merchants list.

### 5. 3D Secure Authentication Failed

**Error Message**: "3D Secure authentication failed" or "OTP incorrect"

**Cause**: You entered the wrong One-Time Password (OTP) sent by your bank.

**Solutions**:
- Wait for a new OTP SMS.
- Enter the OTP within 5 minutes.
- Make sure you're entering the OTP for this transaction (not an old one).
- Contact your bank if you don't receive OTPs.

### 6. Transaction Limit Exceeded

**Error Message**: "Transaction amount exceeds limit"

**Cause**: The order amount exceeds your card's per-transaction limit.

**Solutions**:
- Check your card's limit with your bank.
- Use a different payment method with a higher limit.
- Split the order into smaller orders.
- For CIB cards: typical limit is 500,000 DZD/transaction.
- For Edahabia: typical limit is 100,000 DZD/day.

### 7. Network Issue

**Error Message**: "Connection timeout" or "Network error"

**Cause**: Internet connection problem between your device, the bank, and SATIM.

**Solutions**:
- Check your internet connection.
- Try again in a few minutes.
- Try a different network (Wi-Fi vs. mobile data).
- Try a different device or browser.

### 8. Bank Server Down

**Error Message**: "Bank server unavailable"

**Cause**: Your bank's servers are temporarily down.

**Solutions**:
- Wait 30 minutes and try again.
- Try a different payment method (different card or wallet).
- Check your bank's website or social media for outage announcements.

### 9. SATIM Service Issue

**Error Message**: "Payment processor unavailable"

**Cause**: SATIM (the Algerian interbank payment system) is experiencing issues.

**Solutions**:
- Wait 1 hour and try again.
- Check SATIM's status page (if available).
- Use Cash on Delivery instead.
- Use DZShop Wallet (if funded).

### 10. Fraud Detection

**Error Message**: "Transaction flagged for security review"

**Cause**: Our fraud detection system flagged your transaction as suspicious.

**Solutions**:
- Wait 24 hours (the system may auto-clear).
- Contact `security@dzshop.dz` with your order number.
- Verify your identity.
- Our team will review within 48 hours.

## What Happens After a Failed Payment?

When a payment fails:

1. **Order is NOT placed**: Your cart items remain.
2. **No charge**: Your card is not charged (or charge is reversed).
3. **Notification**: You see the error on screen.
4. **Retry option**: You can try a different payment method immediately.

> ✅ **Important**: If you received an error but the money was deducted from your account, this is a "phantom charge". It will be automatically reversed within 24–72 hours. If not, contact `payments@dzshop.dz`.

## How to Retry a Failed Payment

### Method 1: Same Order

1. After the failure, click **"Try Again"**.
2. Choose a different payment method.
3. Complete the payment.

### Method 2: New Order

1. Refresh the page.
2. Your cart items are still there.
3. Go to checkout again.
4. Choose a different payment method.

### Method 3: Contact Support

If you've tried multiple times and it still fails:

1. Contact our payments team:
   - Email: `payments@dzshop.dz`
   - Hotline: 3030 (option 5)
   - WhatsApp: +213 770 12 34 56
2. Provide:
   - Your email (or phone)
   - The error message you received
   - The payment method you tried
   - The order amount
3. Our team will investigate within 2 hours.

## Phantom Charges (Money Deducted but Order Not Placed)

Sometimes, the bank deducts the money but the order fails on our end:

### What to Do:

1. **Check your bank statement**:
   - Look for a "pending" or "authorized" charge from DZShop/SATIM.
2. **Wait 24–72 hours**:
   - Most phantom charges are automatically reversed.
3. **If not reversed after 72 hours**:
   - Email `payments@dzshop.dz` with:
     - Your bank statement showing the charge.
     - The transaction date and amount.
     - Your email/phone.
     - The error message you received.
   - We'll verify with SATIM and process a refund within 5 business days.

## Payment Failure Statistics

We track payment failures to improve our service:

| Reason | % of Failures |
|--------|---------------|
| Insufficient funds | 35% |
| Incorrect card details | 20% |
| 3D Secure/OTP issues | 15% |
| Card blocked by bank | 12% |
| Network issues | 8% |
| Bank server down | 5% |
| Transaction limit | 3% |
| Fraud detection | 2% |

## Preventing Payment Failures

✅ **DO:**
- Keep your card details handy and correct.
- Ensure sufficient funds before checkout.
- Update your card if it's about to expire.
- Use DZShop Wallet for faster checkout.
- Enable SMS notifications from your bank for OTPs.

❌ **DON'T:**
- Don't retry the same payment more than 3 times in 10 minutes (may trigger fraud detection).
- Don't use VPN during payment (may be flagged).
- Don't share your OTP with anyone.
- Don't save card details on shared computers.

## Last Updated

This document was last updated on **October 28, 2025**.
