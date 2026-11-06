# DZShop — Payment FAQ

## Frequently Asked Questions (Payments)

### Q1: What payment methods do you accept?
**A:** We accept:
1. **CIB Bank Card** (debit cards from all Algerian banks).
2. **Edahabia** (Algérie Poste prepaid card).
3. **BaridiMob** (mobile payment from Algérie Poste).
4. **DZShop Wallet** (internal e-wallet).
5. **Cash on Delivery (COD)** (up to 50,000 DZD).
6. **Bank Transfer** (for orders above 100,000 DZD or B2B).
7. **Installment Plans** (3x, 6x, 12x — see Q5).

### Q2: What payment methods do you NOT accept?
**A:** We do **not** accept:
- ❌ PayPal (not supported in Algeria).
- ❌ International credit cards (Visa/Mastercard issued outside Algeria).
- ❌ Cryptocurrency (Bitcoin, Ethereum, etc.).
- ❌ Apple Pay / Google Pay.
- ❌ Western Union / MoneyGram.
- ❌ Cheques.

### Q3: Is it safe to pay online on DZShop?
**A:** Yes. We use:
- SSL/TLS encryption (256-bit).
- 3D Secure authentication for CIB and Edahabia.
- SATIM certification (Algerian interbank security).
- PCI DSS compliance (we never store full card numbers).
- Two-factor authentication for DZShop Wallet (orders above 10,000 DZD).

### Q4: What is the DZShop Wallet?
**A:** The DZShop Wallet is an internal e-wallet. Benefits:
- Faster checkout (no need to enter card details).
- 2% cashback on every purchase using the wallet.
- Maximum balance: 200,000 DZD.
- Top up with CIB, Edahabia, BaridiMob, or bank transfer.
- Refunds to wallet are processed in 24 hours (vs. 5–7 days for cards).

### Q5: Do you offer installment plans?
**A:** Yes, we offer 0% interest installment plans:
- **3x**: 3 monthly payments, for orders 10,000 – 100,000 DZD.
- **6x**: 6 monthly payments, for orders 30,000 – 300,000 DZD.
- **12x**: 12 monthly payments, for orders 50,000 – 500,000 DZD (CIB only).

See `payments/installment_plans.md` for full details.

### Q6: Why was my payment declined?
**A:** Common reasons:
1. Insufficient funds.
2. Incorrect card details.
3. Card expired.
4. Card blocked by your bank.
5. 3D Secure (OTP) authentication failed.
6. Transaction limit exceeded.
7. Network or bank server issue.
8. Fraud detection.

See `payments/failed_payment.md` for full troubleshooting.

### Q7: What is Cash on Delivery (COD)?
**A:** COD means you pay in cash when the order is delivered.
- Available in all 58 wilayas.
- Maximum order: 50,000 DZD.
- Additional fee: 200 DZD (handling).
- You must be present with the exact amount (couriers don't carry change).
- If absent 3 times, the order is cancelled.

### Q8: How do I pay with a bank transfer?
**A:** 
1. Place the order with "Bank Transfer" as payment method.
2. Receive an email with DZShop's bank details (RIB, SWIFT).
3. Make the transfer within 48 hours.
4. Send the transfer proof to `payments@dzshop.dz`.
5. Order is processed after payment confirmation (24–72 hours).

### Q9: Can I get a refund?
**A:** Yes, in these cases:
- Returned product (within 7 days).
- Cancelled order (before shipment).
- Defective or wrong product received.
- Duplicate charge.
- Pricing error.

Refund method = same as original payment. See `payments/refund_process.md` for details.

### Q10: How long does a refund take?
**A:** Refund timelines:
- **DZShop Wallet**: 24 hours.
- **CIB card**: 5–7 business days.
- **Edahabia**: 5–7 business days.
- **BaridiMob**: 5–7 business days.
- **COD**: 7–10 business days (bank transfer or wallet).
- **Bank Transfer**: 7–10 business days.
- **Installments**: 10–15 business days.

See `returns/refund_timeline.md` for full details.

### Q11: Can I pay in installments if I'm a new customer?
**A:** No. To use installments, you must:
- Have a DZShop account (verified).
- Have placed at least **1 previous order** with full payment.
- Have a CIB card (for all plans) or Edahabia (for 3x, 6x).

### Q12: What if my card is deducted but the order fails?
**A:** This is a "phantom charge". It will be automatically reversed within 24–72 hours. If not reversed, email `payments@dzshop.dz` with:
- Your bank statement showing the charge.
- The transaction date and amount.
- The error message you received.

We'll verify and process a refund within 5 business days.

### Q13: Can I use multiple payment methods for one order?
**A:** Partially:
- You can use **DZShop Wallet + another method** (e.g., wallet for partial amount + CIB for the rest).
- You cannot combine two cards or two installments.

### Q14: Do I get a receipt for my payment?
**A:** Yes. After every successful payment, you receive:
1. On-screen confirmation.
2. Email receipt (within 5 minutes).
3. SMS confirmation (within 10 minutes).
4. In-app notification.

The receipt includes order number, transaction ID, payment method, amount, date, and itemized list.

### Q15: How do I report a payment issue?
**A:** Contact our payments team:
- **Email**: payments@dzshop.dz (within 7 days).
- **Hotline**: 3030 (option 5).
- **WhatsApp**: +213 770 12 34 56.
- **Live Chat**: on website or app.

Provide:
- Order number.
- Transaction ID (if available).
- Description of the issue.
- Screenshots (if applicable).

Our team investigates within **48 hours**.

## Still Have Questions?

- **Hotline**: 3030
- **WhatsApp**: +213 770 12 34 56
- **Email**: payments@dzshop.dz
- **Live Chat**: on our website or app

## Last Updated

This document was last updated on **October 28, 2025**.
