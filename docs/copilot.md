---
description: Ask Super Intelligence about a market or the order you are drafting. Daily allowance, what it answers, and what happens when it is paused.
---

# Copilot

Copilot is the part of Super Intelligence you can ask questions. It lives in two places: the **Super Intelligence** page (any market) and under **Risk Shield** on every trade page, where it also sees the order you are drafting.

## How It Works

Hest's engine computes the numbers first: price, funding, open interest, the worst 1-hour candle of the week, your liquidation distance, the SI Score factors and, on Hest Pools, the spot and TWAP prices and how much the market can still take. A language model then writes the answer under Hest's rules: short, numbers first, only from the data it was given. If something is not in the data, it says so instead of guessing.

## Daily Allowance

Answers cost real compute, so every account has a daily allowance. It resets at midnight Pacific Time.

| Account | Questions per day |
| --- | --- |
| Signed in | 5 |
| Traded $50+ today | 15 |
| Traded $500+ today | 30 |

Trading volume counts across Hest Pools and Order Book Markets. The number of questions left is shown under each chat. When you are not signed in, or when your allowance is used up, Copilot still answers with Hest's built-in risk reads, computed in your browser.

Greetings and small talk do not use a question and do not reach the model. Identical questions on the same market within a few minutes get the same answer.

{% hint style="success" %}
Make each question count. Ask the hard ones: "What could liquidate me here this week?", "Is 3x reasonable on this pool right now?", "Which side is crowded and who pays funding?", "How does Hest price my fill on this pool?"
{% endhint %}

## What It Answers

* **Liquidation risk**: your liquidation distance against the worst candle of the week, and a leverage that fits it.
* **Funding and crowding**: which side pays funding, and open interest against volume.
* **Hest Pools pricing**: spot against TWAP, which price your fill uses, and how much the market can take on each side.
* **The score**: why the market has its SI Score, its strongest and weakest factor.
* **Your draft order**: on a trade page, the side, leverage and size you have entered.

## Risk Reads, Not Price Calls

Copilot reads risk. It does not tell you where the price is going, and it does not tell you to buy or sell.

## When Copilot Is Paused

Copilot runs on a limited daily budget. If the budget is used up or the language model is unavailable, Copilot shows **Copilot is paused** and switches to the built-in risk reads until it is back, usually the next day. SI Score, Risk Shield, charts and trading are not affected.

{% hint style="info" %}
Copilot is information, not financial advice. It reads the market; the decision is yours.
{% endhint %}
