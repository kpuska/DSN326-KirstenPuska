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

## Design Review 3: Tradeoff Analysis 11-13-2026

| | Option #1: Alert Banner in Cart (Cheapest Option) | Option #2: Pre-Card Alert Pop-Up | Option #3: In-Cart Alert and Blocked Checkout |
| :--- | :--- | :--- | :--- |
| **What it is** | A top-of-cart alert advising in the cart that an item was removed from the reorder. The flow is still the same as it is presently. | A dialog box pop-up after clicking order again, that causes the user to acknowledge the unavailable item and choose a replacement from the menu themselves if they want before getting to the cart. | All items dumped in the cart as previously, but it separates the items that need reviewed or swapped before it allows you to checkout. |
| **Costs the user** | Easy to overlook if in a rush. Visual clutter. | More clicks and friction. A slower process of checking out. | Requires resolution of the issue before going to checkout. Limited swap options based on similar results. |
| **Costs the system** | **Small:** While `RAIL.md` does not have a specific banner component, this could be built using the existing `rail-card`. No changes to the cart structure. | **Small-Medium:** The dialog box component and the button components are already available. Just needs to filter the out of stock items for the prompt. | **Medium-Large:** The dialog box, buttons, and list-row options are already available to be used. However, this would require a new build logic system of swaps to choose from and validation to unlock the checkout feature. |
| **What it assumes** | It assumes the user will look at the banner before going to the next part of the checkout. | It assumes the user wants to be alerted before getting to the cart of the removed items. | It assumes the user wants to make all of their changes in the cart directly and that the blocked checkout forces the user to address the items that need removed or edited. |
| **What would kill it** | Testers ignoring the card and going through the cart as they did before, especially if they are rushed. | Users clicking out of the pop up without acknowledging what it was, just to get to the cart | Users abandoning their cart due to not being able to figure out how to advance to the checkout |

## Week 4 Direction 11-21-26
#### Choice: Option 3
I chose to move forward with option 3 after reviewing Marisol's memo this week. Marisol stated that this quarter we would be unable to make changes to the order history list due to being tied up with another project. Initially based on preference test, I was leaning towards options 2 as two of three users preferred it, one user preferred 3. My pivot to option 3 is based on the user test from week 2. P1 and P2 during the user test in week 2 expressed concerns with continuing through the cart without noticing the missing item, especially if rushing to get the order completed. Option 3 would keep these users in the cart and prevent them from continuing until completing the task.
#### What the data doesn't tell me:
The data does not answer if a rushing user would be able to successfully manage through the cart without abandoning their order. There is also no current data on why reorders are abandoned currently. 
#### What would have changed the decision:
What would have changed my decision away from option 3 would have been if users testing the design ran into issues understanding what item they needed to review or clicked on the greyed out checkout option. This would have shown there wasn't clear direction. 
#### What happens to the other two options?
Option 1: Alert Banner in Cart. This option is deferred. The in cart alert pop could be folding into option 3 at a later date. This is the cheapest build as we have all of the component currently. \
Option 2: Pre-Cart Alert. This option is deferred. Although the Order History is tied up this quarter, this may open up next quarter. 
#### Heard setting the direction touches:
This would affect any re-ordering settings. Restaurants could choose to have the blocked cart review toggled on or off. On the off state, this would act as it doesn't currently. 

## Marisol's Memo Reply:
Re: quick note before Friday
Good morning, Marisol, 
Quick clarifying question to start: When you say we cannot change the order history list this quarter, does this mean the order history list and any pre-cart banner interceptions tied to it are off the table? \
If I don’t hear back by Thursday, I will assume the pre-cart intercepts are locked due to the order history list and work on building inside the cart itself. Sticking to the cart flow will still help users catch missing items before checking out, and if that is off track, we can easily pivot the changes to pre-cart alerts.  \
I am counter-proposing option 3, the in-cart alert with blocked checkout. This defers options 1 and 2, which we can revisit later, especially if user testing shows the issue occurs before the cart. However, with this quarter’s constraints on editing the order history list, this plan keeps the ability for users to change out their items and continue to checkout. It uses components, such as cards we already have built, to keep down the cost. \
The trade-off: Blocking checkout until an unavailable or unreviewed item is resolved would reduce incomplete orders. However, it comes at the cost of adding an extra step and risking drop-offs for users in a rush. \
Reversibility: This could be completely reversed since the change doesn’t require any structural changes or altering the order history lists. Restaurants could even choose to toggle the checkout-blocking setting off if they choose. That matters because if reporting shows too much friction or points to a different spot in the flow, we can adjust or pull it back next quarter without the changes being locked in. 

### Week 4 Follow-ups:
In week 2's session, P1 did not see the item missing until it was loaded into the cart and P2 did not notice the missing item until they would have moved to checkout, but still in the cart. However, the current state after tapping reorder, dumps the reorder as is and omits missing items without warning. There isn't a current space after tap and before cart. \
With P1 noticing in the cart, but not liking they had to leave to cart to find a new item and P2 not noticing the missing item and moving toward checkout, I believe the in-cart alert/cart block won't add many extra steps but gives the user the ability to correct the order in cart. \
Currently there is no checkout-blocking togged in Heard today, this is a setting I am proposing to allow the restaurants more freedom to make this choice, especially if they are one that doesn't have edited or out of stock items typically.

### Week 4 Design Choices:
- In my week 4 design, in multiple instances I needed to detach the list-row instances in order to modify them for menu items. More of a workaround used was to remove the icon in the list-row with price, then rearrange the text so the title and price aligned with the description underneath. If the workaround was extended into it's own list-row state, it would cut down on needing to edit multiple items and help with consistency. The items already exist to do this.
- Another list-row work around I only had to use one or two times was adding an independent button to a list row item. This doesn't need to be added as a state as it was used less than 3 times overall. 
- Detached items: In the designs I detached instanced of the list-row in order to edit to add buttons or text that wasn't an option prior.
Primary Device Target: Phone at comfortable. This is due to many people ordering on the go from their phones. \
What differs: In the phone layout it features a 1 column scroll with sticky header and footer. In the desktop version, it has 2 different columns with the right column locked showing the total and next steps. This keeps the CTA visible while scrolling on the left side. 
