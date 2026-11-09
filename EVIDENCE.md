# Evidence

## Backlog: HEARD 211 - Reordering takes as long as ordering from scratch

## Week 1: 
### Rail parity check

| Token | Figma value | `tokens.css` value | Agree? |
|---|---|---|---|
| --color-text-primary | #231F1C | --neutral-900 | Yes |
| --type-display-size | 32 | 32px | Yes |
| --space-inset-sm | 8 | 8px | Yes |
| --radius-sm | 6 | 6px | Yes |
| --target-min | 44 | 44px | Yes |
| --neutral-50 | #FAF9F7 | #FAF9F7 | Yes |
| --type-mono-size | 14px | 14px | Yes |
| --space-inset-lg | 24px | 24 px| Yes |
| --radius-full | 9999px | 9999px | Yes |
| --target-min env-high-glare | 56px | 56px | Yes |

### Density and Environment
#### Density:

| Axis | type/body | space/inset/md |
|---|---|---|
| Comfortable | 16px | 16px |
| Compact | 14px | 12px |
| Service | 24px | 24px |

#### Environment:

| Axis | Standard target/min | High-Glare target/min|
|---|---|---|
| Comfortable | 44px | 56px |
| Compact | 44px | 56px |
| Service | 44px | 56px |

#### Why is service type so much larger than comfortable? Why doesn't target/min get smaller at compact?
##### Service type is larger due to this being used in the fast-paced kitchen environment. Things need to be quick and easy to ready. Sometimes even from a distance. Target does not change with compact as the density changes the size of things on the screen, but it doesn't change the size of the fingers interacting.

### Components
#### Card: 
The card component has different variants but it packages together related sets of information, photos, meta data or it completes an action. 
#### Variants
- Basic: Holds a title and text.
- Card with Top Image: Places an image above the text.
- Card with Leading Image: Places an image leading or to the left of the text.
- Card with Metadata: Contains metadata such as pricing or prep time. 
- Card with Actions: Contains actions such as editing or removing an item.

States Handled: default, hover, focus, active, disabled, loading (skeleton)

States Not Handled: error

Rail Tokens: 
- Color: --text-primary, --text-secondary, --text-tertiary, --surface-raised, --border-strong, --text-link, --interactive-subtle, --surface-subtle, 
- Typography: --type-label-size, --type-label-line, --type-label-weight, --type-caption-size, --type-caption-line, --type-caption-weight, 
- Spacing: --space-inset-sm, --space-inset-md, --space-inline-md, --space-gap-sm, 
- Radius/Target: --radius-md, --radius-sm

 #### Input:
 The input component allows users to enter text into the field. 
 #### Variants
 - Single-line input with label and helper text: a single line text entry box with text to give direction.
 - Multi-line (text area) with character count: Ability to enter multiple lines of text and see how many characters are present in the box.

States: Default, hover, focused, filled, error, success, disabled

States Not Handled: Loading

Rail Tokens:
- Color: --surface-raised, --text-primary, --text-tertiary, --border-focus, --border-strong, --text-disabled, --surface-subtle, --border-subtle, --text-disabled, --border-error, --feedback-success, --text-error, --text-success
- Typography: --type-label-size, --type-label-line, --type-label-weight, --type-body-size, --type-body-line, --type-body-weight, --type-caption-size, --type-caption-line, 
- Spacing: --space-stack-sm, --space-inset-sm, --space-inset-md, 
- Radius/Target: --radius-sm, 

### 5-Task Script
1. You are eating at your favorite lunch spot and you want your go-to meal. Find your past order.
2. Using your order history, load your meal into your cart.
3. You decide you don't want the same side as the last time, but want to keep everything else the same. Modify this in your order.
4. When you go to your cart, you see the store is out of the drink you want. Correct this error.
5. Review everything looks good to go to checkout.
#### Revised script, kept the same for each participant
1. Find your past order. 
2. Using your order history, load your meal into your cart. 
3. Make the modifications to your reorder. 
4. When you go to your cart, review everything looks the same as the last order. 
5. Go to checkout.

---

## Sessions

### P1 — 2026-11-08, Design Review 2B: the evidence and the problem

**Consent:** Yes
**Setup:** Gave participants their role cards. \
**Amberley H.**
| Task | Completed? | Time | Stuck? | Quote |
|---|---|---|---|---|
| 1 | Y | 10:20p | No | |
| 2 | Y | 10:20p | No | "When I hit re order it doesn't show my Baja fish taco" |
| 3 | Y | 10:21p | No | "I added two of the carnitas since two of the al pastor were removed and I added two steak tacos for me since they are better than fish anyway" |
| 4 | Y | 10:24p | Irritation they had to go back to check that tacos were removed. | "irritated that my items weren't all added from the reorder because it was sold out after I hit back" |
| 5 | Y | 10:26p | No | Checkout was fine |

### Three moments worth quoting:
1. "If I was rushing and only fixed my partner's items, I wouldn't have got tacos"
2. "I didn't get stuck. Just irritated that my items weren't all added from the reorder because it was sold out after I hit back."
3. "When I hit re order it doesn't show my Baja fish tacos"
#### One thing that surprised me: The frustration was more from no notification the item out of stock was missing. 
#### How much did the role card carry? They were able to reason from it and understand what role they were taking in the situation.

**Emma B.**
| Task | Completed? | Time | Stuck? | Quote |
|---|---|---|---|---|
| 1 | Y | 10:20p | No | |
| 2 | Y | 10:21p | No | |
| 3 | Y | 10:21p | No | "I would add an add more food button, that would be easier" |
| 4 | Y | 10:22p | No | "Didn't realize the fish tacos weren't added. I would say if something isn’t available on a specific night, a message should show up in the cart stating it isn’t available. Or maybe be grayed out on the menu with a message." |
| 5 | Y | 10:22p | No | "Checking out was easy. I didn't mind the site." |

### Three moments worth quoting:
1. "Yeah if I were rushing I would have submitted and order without my tacos because I thought they were there."
2. "I would have finished. I honestly didn’t see anything wrong with the site."
3. "I would say if something isn’t available on a specific night, a message should show up in the cart stating it isn’t available. Or maybe be grayed out on the menu with a message."
#### One thing that surprised me: The user did not notice the baja fish tacos were missing until looking back at the role card and the previous order. 
#### How much did the role card carry? They reasoned with the role card in mind, but the role card did miss the specifics on what they were wanting to order for themselves. 

### Framed Problem:
Repeat guests who are reordering their same meal are met with a modified cart without any warning or notification. Both participants expressed frustration with not realizing their item was not in the cart and would have missed this in a hurry. One did not notice it wasn't added until after the fact, another noticed it was due to being out of stock, only when they went to add another item. The silent change violates usability heuristic #1: Visibility of System Status. This is due to failing to notify the users that their items were out of stock and not added to the cart. This ties into the 58% reorder completion rate. 

### Success Measure:
Users are no longer stuck checking their order to their past order to make sure everything was added, they would be immediately aware of unavailable items or price changes. This eliminates the user from having to cross-check their past order by going back and abandoning their cart due to time constraints. 
