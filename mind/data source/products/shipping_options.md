# DZShop — Shipping Options

## Overview

DZShop partners with the most reliable shipping companies in Algeria to deliver orders to all 58 wilayas. We offer multiple shipping options depending on the customer's location and urgency.

## Shipping Partners

### 1. Yalidine Express

| Field | Details |
|-------|---------|
| **Type** | Express delivery |
| **Coverage** | All 58 wilayas |
| **Delivery Time** | 24–72 hours |
| **Stop Desk** | Available in 45 wilayas |
| **Home Delivery** | Available in all wilayas |
| **Tracking** | Yes (real-time) |

> Yalidine is our **default shipping partner** for most orders outside Algiers.

### 2. Maystro Delivery

| Field | Details |
|-------|---------|
| **Type** | Standard delivery |
| **Coverage** | 41 wilayas |
| **Delivery Time** | 48–96 hours |
| **Stop Desk** | Available in 30 wilayas |
| **Home Delivery** | Available in 41 wilayas |
| **Tracking** | Yes (real-time) |

> Maystro is used for orders with non-urgent items or large packages.

### 3. Algérie Télécom (EPRESSO)

| Field | Details |
|-------|---------|
| **Type** | Postal service |
| **Coverage** | All 58 wilayas + remote areas |
| **Delivery Time** | 5–10 business days |
| **Stop Desk** | Post offices in all communes |
| **Home Delivery** | Limited (postman delivery) |
| **Tracking** | Yes (limited, daily updates) |

> Algérie Télécom is used for:
> - Remote areas not covered by Yalidine/Maystro
> - Small packages (under 1 kg)
> - Budget deliveries

### 4. DZShop Express (Internal Service)

| Field | Details |
|-------|---------|
| **Type** | Same-day delivery |
| **Coverage** | Algiers only (wilaya 16) |
| **Delivery Time** | Within 4 hours (orders before 14:00) |
| **Home Delivery** | Yes |
| **Tracking** | Yes (real-time GPS) |
| **Cost** | 600 DZD flat rate |

> DZShop Express is only available in Algiers. See the `same_day_delivery.md` file in the `shipping/` folder for full details.

## Shipping Options at Checkout

When placing an order, customers can choose from:

| Option | Partner | Delivery Time | Cost |
|--------|---------|---------------|------|
| **Express (Same Day)** | DZShop Express | 4 hours | 600 DZD |
| **Express (24h)** | Yalidine | 24 hours | Calculated by weight & destination |
| **Standard (48–72h)** | Yalidine | 2–3 days | Calculated by weight & destination |
| **Economy (4–6 days)** | Maystro | 4–6 days | Cheaper than Standard |
| **Budget (5–10 days)** | Algérie Télécom | 5–10 days | Cheapest option |
| **Click & Collect** | DZShop stores | 4 hours (if ordered before 14:00) | Free |

## Stop Desk vs. Home Delivery

### Stop Desk
- Customer picks up the package from a partner location.
- Available in most cities.
- Cheaper than home delivery.
- Customer has 7 days to pick up (after SMS notification).

### Home Delivery
- Delivery agent brings the package to the customer's address.
- Available in cities and many rural areas.
- More expensive than Stop Desk.
- Customer must be present at the time of delivery.

## Shipping Restrictions

### Products with Special Shipping Requirements

| Product Type | Restriction |
|--------------|-------------|
| **Large appliances** (fridges, washing machines) | Home delivery only, Maystro or specialized transport |
| **Furniture** | Home delivery only, Maystro or specialized transport |
| **Fragile items** (glass, TVs) | Special packaging (+200 DZD) |
| **Lithium batteries** (laptops, phones) | Cannot be shipped by air (only road) |
| **Perfumes** | Cannot be shipped by air (only road) |
| **Groceries** | Algiers only, DZShop Express |

### Geographic Restrictions

- **Tamanrasset, Djanet, In Salah**: Only Algérie Télécom (5–10 days, higher cost).
- **Border areas**: May require additional security screening (1–2 extra days).
- **Military zones**: Not served.

## Shipping Costs

Shipping costs are calculated based on:
1. **Weight** of the package (in kg)
2. **Destination wilaya**
3. **Shipping option** (Express, Standard, Economy, Budget)
4. **Delivery type** (Stop Desk vs. Home Delivery)

For the full shipping fees table, see the `delivery_fees.md` file in the `shipping/` folder.

## Tracking Your Order

All orders come with **free tracking**. Customers can track their order by:

1. Logging into their DZShop account → "My Orders" → "Track"
2. Using the tracking link in the email/SMS sent when the order is shipped
3. Calling our hotline **3030** and providing the order number
4. Sending a WhatsApp message to +213 770 12 34 56 with the order number

For more details, see the `track_order.md` file in the `orders/` folder.

## Delivery Confirmation

A delivery is considered successful when:

1. The customer (or someone authorized) signs the delivery receipt.
2. The customer pays the amount due (for COD orders).
3. The package is handed over in good condition.

> ⚠️ **Important:** Customers must check the package condition before signing. Once signed, claims for damaged products are not accepted (the customer must refuse delivery and contact us immediately).

## Missed Deliveries

If the customer is absent at the time of delivery:

1. **First attempt**: The delivery agent leaves a notice and tries again the next day.
2. **Second attempt**: Another notice is left.
3. **Third attempt**: The order is returned to the nearest Stop Desk for pickup (7 days).
4. **After 7 days at Stop Desk**: The order is returned to DZShop and cancelled. A refund is processed (5–10 business days).

## Last Updated

This document was last updated on **October 28, 2025**.
