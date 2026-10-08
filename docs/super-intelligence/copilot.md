---
description: Ask Super Intelligence about a market or the order you are drafting. How answers are produced, what Copilot is given, the daily allowance, and what happens when it is paused.
---

# Copilot

Copilot is the part of Super Intelligence you can ask questions. It lives in two places: the **Super Intelligence** page (any market) and under **Risk Shield** on every trade page, where it also sees the order you are drafting.

## How an Answer Is Produced

1. **Hest's engine computes the numbers.** Your question is sent with a data block built from what the page shows: the market's price, 24h change and volume, open interest, hourly funding, maximum leverage, maintenance margin, the worst 1-hour candle of the week and the SI Score. On Hest Pools markets it adds spot, the 15-minute TWAP, the market's capacity and the open interest on each side. On a trade page it adds your draft order: side, leverage and size.
2. **Hest derives the answers that need arithmetic.** Before anything reaches the language model, Hest computes and labels: your liquidation distance and its Risk Shield verdict, the highest leverage with room to breathe, the verdict at the market's maximum leverage, which side pays funding and what the current rate costs over 24 hours, open interest against volume, and on Hest Pools markets the gap between spot and TWAP, the price a long and a short would get, the largest single position and the room left on each side.
3. **A language model writes the answer** under Hest's rules: numbers first, a one-line read, at most about 70 words, in the language you asked in. It may only use the numbers it was given and may not recalculate them. If something is not in the data, it says so instead of guessing.

The previous four messages of the conversation are included, so you can ask follow-up questions. A question can be up to 400 characters.

## What It Answers

* **Liquidation risk:** your liquidation distance against the worst candle of the week, the verdict, and a leverage that fits.
* **Funding and crowding:** which side pays funding, what it costs per day, and open interest against volume.
* **Hest Pools pricing:** spot against TWAP, which price your open and close would use, and how much the market can take on each side.
* **The score:** why the market has its SI Score, its strongest and weakest factor.
* **Your draft order:** on a trade page, the side, leverage and size you have entered.

The suggested questions under each chat are a good start: **What could liquidate me here this week?**, **Which side is crowded and who pays funding?**, **How does Hest price my fill on this pool?**, **How much can this market take on one side?**, and under Risk Shield **Is my order safe?**, **What leverage fits?**, **What could go wrong?**

## Daily Allowance

Answers cost real compute, so every signed-in account has a daily allowance. It resets at **midnight Pacific Time**.

| Account | Questions per day |
| --- | --- |
| Signed in | 5 |
| Traded $50+ today | 15 |
| Traded $500+ today | 30 |

* **What counts as trading volume:** the value of Hest Pools positions opened today plus the value of your Order Book fills today, both since midnight Pacific Time.
* **When it updates:** a higher allowance applies within a few minutes of the trade that reaches the threshold.
* **Where you see it:** the line under each chat shows how many questions are left today and what the next tier needs.
* **What does not count:** greetings and small talk do not use a question and do not reach the model.
* **Shared answers:** an identical question on the same market, in the same market state, within 5 minutes gets the same answer. It still counts as a question.

When you are not signed in, or when your allowance is used up, Copilot still answers with Hest's built-in risk reads, computed in your browser from the same numbers.

{% hint style="success" %}
Make each question count. Ask the hard ones: "What could liquidate me here this week?", "Is 3x reasonable on this pool right now?", "Which side is crowded and who pays funding?", "How does Hest price my fill on this pool?"
{% endhint %}

## Risk Reads, Not Price Calls

Copilot reads risk. It does not tell you where the price is going, does not tell you to buy or sell, and makes no promises. Each answer carries a mood for the Hest mascot (happy, neutral, worried or scared) that matches the risk it describes.

Copilot never asks for, accepts or repeats private keys or seed phrases. If you paste one, treat it as compromised and move your funds.

## When Copilot Is Paused

Copilot runs on a limited daily budget. If the budget for the day is used up, or the language model is unavailable, the chat shows **Copilot is paused** and switches to the built-in risk reads. It comes back by itself: after a provider error usually within about half an hour, and after a used-up budget at midnight Pacific Time. SI Score, Risk Shield, charts and trading are not affected.

{% hint style="info" %}
Copilot is information, not financial advice. It reads the market; the decision is yours.
{% endhint %}
