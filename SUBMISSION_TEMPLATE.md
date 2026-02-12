# Submission: [Jakub Bilicki]

## Time Spent

Total time: **4 Hours** (approximate)

## Ticket Triage

### Tickets I Addressed

List the ticket numbers you worked on, in the order you addressed them:

1. **CFG-154**: [Missing equal sign in file pricing.ts, function getAppliedDiscountPercentage on line 95. Needs clarification on discount treshold.]
2. **CFG-145**: [The quick add feature is now available when pressing Ctrl + Enter.]
3. **CFG-142**: [Price was always rendered as $0.00 due to filtering by newest responses. Changed response filtering.]

### Tickets I Deprioritized

List tickets you intentionally skipped and why:

| Ticket  | Reason                 |
| ------- | ---------------------- |
| CFG-144| [As the CFG-145 ticket says, the key customer would like to see this feature, so removing it would go against the key customer's needs.] |
| CFG-146 | [Cosmetic changes, not important for application functionality.] |
| CFG-148 | [I couldn’t reproduce the bug.] |

### Tickets That Need Clarification

List any tickets where you couldn't proceed due to ambiguity:

| Ticket  | Question                  |
| ------- | ------------------------- |
| CFG-154 | [What is correct threshold for discount? Does 10% discount starts from 50 items or 51?] |
|CFG-
---

## Technical Write-Up

### Critical Issues Found

Describe the most important bugs you identified:

#### Issue 1: [Discount quantity now starts from 50 items]

**Ticket(s):** CFG-154

**What was the bug?**

[There was a missing equal sign in the if statement on line 95 in the pricing.ts file. The discount is now applied starting from 50 items, using logic similar to the 10-item discount.]

**How did you find it?**

[When setting items quantity to 50.]

**How did you fix it?**

[The order quantity must be equal to the minimum discount quantity for the discount to be applied.]

**Why this approach?**

[It's the easiest way to fix this.]

---

#### Issue 2: [The quick add feature is now available when pressing Ctrl + Enter.]

**Ticket(s):** CFG-145

**What was the bug?**

[Key customer want a shortcut for the quick add feature. It's now available for the demo.]

**How did you find it?**

[Button has missing shortcut event handler]

**How did you fix it?**

[Created a helper function handleQuickAddShortcut and assigned it to the onKeyDown property button.]

**Why this approach?**

[The function for the quick add shortcut is assigned to the button's onKeyDown property to avoid double invocations when adding items to the cart. Also this function was used]

---

#### Issue 3: [Price was always set to $0.00]

**Ticket(s):** CFG-142

**What was the bug?**

[Price was always set to $0.00, and adding an addon or changing the quantity didn’t increase the price.]

**How did you find it?**

[On render, the price was always set to $0.00, even though a quantity was already set. I found a way to render it by changing the if statement in UsePriceCalculation.ts on line 47.]

**How did you fix it?**

[I changed the if statement on line 47 in the usePriceCalculation.ts file. The if statement now checks whether the response has a timestamp.]

**Why this approach?**

[This isn’t perfect, but it works for now. Instead of checking if the response timestamp is greater than or equal to latestRequestRef.current, it should check if the response ID matches latestRequestRef.current ID.]
---

### Other Changes Made

Brief description of any other modifications:

- [Change 1]
- [Change 2]

---

## Code Quality Notes

### Things I Noticed But Didn't Fix

List any issues you noticed but intentionally left:

| Issue   | Why I Left It                                         |
| ------- | ----------------------------------------------------- |
| [Code has to be split into a separate component] | [Time-consuming, no time for now] |

### Potential Improvements for the Future

If you had more time, what would you improve?

1. [Improvement 1]
2. [Improvement 2]

---

## Questions for the Team

Questions you would ask in a real scenario:

1. [What is the correct treshold for discount?]
2. [Is the quick add feature crucial for our key client?]

---

## Assumptions Made

List any assumptions you made to proceed:

1. [Assumption 1]
2. [Assumption 2]

---

## Self-Assessment

### What went well?

[I’m happy that the application displays the correct price now. It needs polishing, but overall application functionality is working.]

### What was challenging?

[Working on a new codebase in such a short time frame was challenging.]

### What would you do differently with more time?

[I would find better ways for debugging in future work.]

---

## Additional Notes

Anything else you want us to know:

[I had a lot of fun working with this code. Thanks for the opportunity, and I hope to see you in the next stage of recruitment!]
