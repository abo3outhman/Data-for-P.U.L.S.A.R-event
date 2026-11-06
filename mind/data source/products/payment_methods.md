# DZShop — Payment Methods (Payments Folder)

## Overview

This document is a quick reference for payment methods on DZShop. For the full product-level payment details, see `products/payment_methods.md`.

## Quick Comparison

| Method | Type | Processing | Fees | Limits |
|--------|------|-----------|------|--------|
| **CIB Card** | Online | Instant | Free | 500,000 DZD/transaction |
| **Edahabia** | Online | Instant | Free | 100,000 DZD/day |
| **BaridiMob** | Mobile | Instant | Free | 40,000 DZD/transaction |
| **DZShop Wallet** | Internal | Instant | Free | 200,000 DZD balance |
| **Cash on Delivery** | In-person | On delivery | +200 DZD handling | 50,000 DZD max |
| **Bank Transfer** | Manual | 24–72 hours | Bank fees apply | No limit |
| **Installments (3x)** | Recurring | First payment instant | 0% interest | 10,000–100,000 DZD |
| **Installments (6x)** | Recurring | First payment instant | 0% interest | 30,000–300,000 DZD |
| **Installments (12x)** | Recurring | First payment instant | 0% interest | 50,000–500,000 DZD |

## Choosing a Payment Method

### For Small Orders (< 5,000 DZD)
- ✅ DZShop Wallet (fastest)
- ✅ Edahabia
- ✅ BaridiMob
- ✅ Cash on Delivery

### For Medium Orders (5,000 – 50,000 DZD)
- ✅ CIB Card
- ✅ DZShop Wallet
- ✅ Cash on Delivery
- ✅ Installments 3x

### For Large Orders (> 50,000 DZD)
- ✅ CIB Card
- ✅ Bank Transfer
- ✅ Installments 6x or 12x
- ❌ Cash on Delivery (limit: 50,000 DZD)

### For B2B / Bulk Orders
- ✅ Bank Transfer (recommended)
- ✅ B2B Account (invoice billing)

## Payment Processing Flow

```
Customer selects payment → Enters details → Secured by 3D Secure
                                              ↓
                                    SATIM processes transaction
                                              ↓
                                          Success?
                                         /        \
                                       YES         NO
                                       ↓            ↓
                            Order confirmed    Error displayed
                            Email sent         Customer can retry
                            SMS sent
                            Order prepared for shipment
```

## Payment Statuses

| Status | Meaning |
|--------|---------|
| **Pending** | Payment initiated, awaiting confirmation |
| **Authorized** | Funds reserved on customer's card (not yet charged) |
| **Captured** | Funds charged successfully |
| **Failed** | Payment was declined |
| **Refunded** | Money returned to customer |
| **Partially Refunded** | Partial amount returned (for partial returns) |
| **Cancelled** | Payment cancelled before capture |

## Payment Receipts

Every payment generates a receipt containing:

- **Transaction ID**: Unique identifier (e.g., TRX-2025-0012345)
- **Order Number**: Linked order (e.g., DZ-2025-0012345)
- **Amount**: Total paid in DZD
- **Payment Method**: Method used
- **Date & Time**: When payment was processed
- **Status**: Captured, Failed, etc.

The receipt is sent via:
- Email (PDF attachment)
- SMS (link to view online)
- In-app (under "My Orders" → "Payment Details")

## Payment Security

DZShop uses the following security measures:

1. **SSL/TLS Encryption** — All payment pages are encrypted.
2. **3D Secure** — Verified by Visa and MasterCard SecureCode for CIB.
3. **SATIM Certification** — Algerian interbank security standard.
4. **PCI DSS Compliance** — We don't store full card numbers.
5. **Tokenization** — Card details are replaced with tokens.
6. **Fraud Detection** — AI-based system flags suspicious transactions.
7. **Two-Factor Authentication** — For DZShop Wallet transactions above 10,000 DZD.

## Last Updated

This document was last updated on **October 28, 2025**.
