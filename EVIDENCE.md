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

States Not Handled: error, 

Rail Tokens: 
- Color: --text-primary, --text-secondary, --text-tertiary, --surface-raised, --border-strong, --text-link, --interactive-subtle, --surface-subtle, 
- Typography: --type-label-size, --type-label-line, --type-label-weight, --type-caption-size, --type-caption-line, --type-caption-weight, 
- Spacing: --space-inset-sm, --space-inset-md, --space-inline-md, --space-gap-sm, 
- Radius/Target: --radius-md, --radius-sm


---

## Sessions

### P1 — YYYY-MM-DD, round [1/2]

**Consent:** 
**Setup:** 
**Task 1:** 
**Task 2:** 
