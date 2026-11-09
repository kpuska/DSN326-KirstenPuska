# Decisions

## Backlog: HEARD 211 - Reordering takes as long as ordering from scratch

## 2026-10-30 — Backlog
- What I decided: I chose backlog HEARD 211
- Why: I chose this because I related to the reason but also it felt simple enough to really be able to focus on sharpening my skills with Figma and Github. Especially being newer to using Github.
- What I gave up: Choosing a more complex but rewarding topic
- What would change this: Nothing currently. 

## 5-Task Script Reasoning
1. You are eating at your favorite lunch spot and you want your go-to meal. Find your past order. 
2. Using your order history, load your meal into your cart.
3. You decide you don't want the same side as the last time, but want to keep everything else the same. Modify this in your order.
4. When you go to your cart, you see the store is out of the drink you want. Correct this error.
5. Review everything looks good to go to checkout.
### My reasoning behind these tasks are to get a clear picture of the users natural journey from opening the app to checkout of ordering a common meal.

## 2026-11-04 — Gaps - AI Conversation Log
- Tool: Bolt
- What for: Conversation with Dev Raman regarding gaps.
- Conversation:
- Me: Do you have the average order completion time for fresh orders vs reorders? Do you have the drop-off rates for fresh orders vs reorders as well?
- Dev: No on both, mostly.
Completion time: I don't have it. Never measured. No instrumentation for time-to-complete.
Drop-off by fresh vs reorder: I have a related pair but not what you're asking for. Overall checkout completion is 71%. Reorder completion is 58% — reorder gets tapped more, finished less. But I don't have a clean "fresh order completion" number separate from the 71% overall. The 71% includes reorders. So I can't hand you a fresh-vs-reorder drop-off comparison; I can only tell you reorder underperforms the average.
And neither breaks down by step. That's the thing I most want and don't have. If your design makes step-level drop-off measurable, put that in the handoff — it's worth something to me on its own.
Where to go if you need it: I'd ask Nate whether we log timestamps per checkout step. If we do, the number exists and nobody's pulled it. If we don't, it's a week of work and it's not on the Q4 list.

## 2026-11-08 - Gap Closures
### Three Gaps
### Gap #1 - The missing number
##### The Gap: 
The ticket claims that “reordering takes as long as ordering fresh.” However, the ticket does not provide any metrics for how long order entry takes for a fresh order versus a reorder. It also does not provide the drop-off rate difference between a fresh order and a reorder, but states reorders are “completed less often than a fresh order”. 
##### What I found: 
•	Overall order completion rate is 71%, and this includes both fresh and reorder data. \
•	Reorder completion rate is 58% \
•	No data on how long average order entry takes
##### Source: PM pack data, confirmed by Dev. 
##### What it changes:  I cannot go off data for when a user drops off in their reorder, so I will need to rely more on user testing to see when users drop off on their reorder. 
### Gap #2 – Solution disguised as a problem
##### What the ticket asks for: 
The ticket explains that the error is the reorder button just dumping the whole order into the cart and making reordering smarter.  
##### The problem underneath it: 
The problem is once the reorder is in the cart and errors with missing order components or being unable to do different customizations.
##### How I know they're different: 
A reorder is a simple click and should dump into the cart, whereas a smarter reorder allows for customization before finalizing and checking out.
##### Does the proposed solution address the real problem? 
Partly; consistent orders for reorder are what a customer wants. If available, it should be as simple as dumping it into the cart. However, the reordering does stand to be “smarter” as to be able to see or adjust if pricing, items, or ingredients have changed or are out of stock since the last order. 
### Gap #3 – Unstated Constraint
##### The constraint: 
The lack of user accounts and login requirements. We don’t ask for notification permission on someone’s first take-out order. 
##### Where I found it: HEARD-219 regarding constraints of group orders. 
##### Why the ticket doesn't mention it: Dev’s goal is to manage around all of the issues and maintain an accountless requirement. He wants the focus specifically on the order entry. 
##### What it rules out: The ability to save an item as a favorite on the account or anything related to notifications of out-of-stock or changed items. 
