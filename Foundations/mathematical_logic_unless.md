# Mathematical Logic: Understanding "Unless" in Logical Expressions

> **Topic:** Translating English sentences into logical expressions, with a deep dive into the word "unless"
> **Reference:** Self-study notes

---

## The Original Problem

**Sentence:**
> *"You cannot ride the roller coaster if you are under 4 feet tall unless you are older than 16 years old."*

---

## Step 1: Define the Three Atomic Statements

| Variable | Meaning |
|----------|---------|
| **R** | You *can* ride the roller coaster |
| **T** | You are *under 4 feet* tall |
| **A** | You are *older than 16* years old |

---

## Step 2: Break the Sentence into Three Logical Pieces

**Statement 1 (The condition):**
> "You are under 4 feet tall" → **T**

**Statement 2 (The exception/override):**
> "You are older than 16 years old" → **A**

**Statement 3 (The conclusion):**
> "You cannot ride the roller coaster" → **¬R**

---

## Step 3: The Final Logical Expression

$$T \land \neg A \rightarrow \neg R$$

**Reading it back in plain English:**
> *"If you are under 4 feet tall AND you are NOT older than 16, then you cannot ride the roller coaster."*

---

## Deep Dive: Why is it AND (∧)?

### The "Unless" Problem

The word **"unless"** in English is tricky. Let's replace it with simpler words:

> **"Unless"** = **"except when"** = **"but not if"**

So the full sentence becomes:

> ❌ *"You cannot ride if you are under 4 feet tall"*
> ✅ **EXCEPT** when you are older than 16

So **"unless"** is not creating a new implication — it is **putting a condition on when the first rule applies.**

---

### A Real Life Analogy

Think of it like a club rule:

> *"You cannot enter if you are underage, unless you have a VIP pass"*

This does NOT mean two separate implications. It means:

```
The "cannot enter" rule ONLY fires when:
   → you ARE underage         ✅
   → you do NOT have VIP pass ✅
   Both together = banned
```

If you have the VIP pass, the rule is simply **switched off.**

---

### Think of it as a Gate

Imagine two security checks at the roller coaster:

```
Check 1: Are you under 4 feet?      → T
Check 2: Are you NOT older than 16? → ¬A

Only if BOTH checks are YES → You CANNOT ride (¬R)
```

If **either** condition fails, the ban lifts:
- If T is false → you're tall enough, ride freely ✅
- If ¬A is false (meaning A is true) → you're over 16, exception applies, ride freely ✅

---

### Why NOT OR?

If it were **OR**, the ban would trigger if **either** condition alone is met — meaning even a tall person over 16 could be banned, which contradicts the sentence. So OR doesn't fit here.

---

## The "Unless" Simple Rule

> **"X unless Y"** always means **"X AND NOT Y"**

| English | Logic |
|---------|-------|
| You cannot ride, if short, **unless** older than 16 | Cannot ride if short **AND NOT** older than 16 |
| `T unless A` | `T ∧ ¬A` |

The AND appears when the sentence has **two separate conditions** that must hold together to trigger the consequence.

---

## Bonus: The Contrapositive

When deriving `¬Q → P` is equivalent to `¬P → Q`, this is just the **contrapositive** rule.

### Contrapositive Rule

$$P \rightarrow Q \equiv \neg Q \rightarrow \neg P$$

They always have the **same truth value** — they are fully interchangeable.

### Applying It

Starting with:

$$\neg Q \rightarrow P$$

To find the contrapositive, **flip and negate both sides**:

| Original | Contrapositive |
|----------|---------------|
| `¬Q → P` | `¬P → ¬(¬Q)` |
| | `¬P → Q` ✅ |

Since **¬(¬Q) = Q**, we arrive at **¬P → Q**.

### In Plain Words (using our variables)

Let P = "cannot ride (¬R)" and Q = "older than 16 (A)"

| Expression | Meaning |
|------------|---------|
| `¬Q → P` | If you are **NOT older than 16**, then you **cannot ride** |
| `¬P → Q` | If you **can ride**, then you **must be older than 16** |

Both say **exactly the same thing**, just from a different angle.

---

## Advanced: "Unless" in P → Q

The claim is:

$$P \rightarrow Q \equiv Q \text{ unless } \neg P$$

### Verification

| Step | Expression |
|------|-----------|
| Start with | `Q unless ¬P` |
| Replace "unless" with "if not" | `Q, if not (¬P)` |
| "if not (¬P)" = "if P" | `if P → Q` |
| Which is just | `P → Q` ✅ |

### Why Doesn't "Unless" Mean AND here?

**"Unless" always means "if not."**

The AND came from the **specific sentence structure** in the roller coaster problem, not from "unless" itself.

| Sentence | Translation | Why |
|----------|------------|-----|
| *"Cannot ride if short, unless older than 16"* | `T ∧ ¬A → ¬R` | "Unless" cancelled the exception, leaving AND as the combined condition |
| *"Q unless ¬P"* | `¬(¬P) → Q` → `P → Q` | "Unless" simply means "if not ¬P" = "if P" |

---

## Summary: The Golden Rules

| Concept | Rule |
|---------|------|
| **Unless** | Always means **"if not"** |
| **"X unless Y"** | Translates to **X ∧ ¬Y** (AND appears when two conditions combine) |
| **Contrapositive** | `P → Q` ≡ `¬Q → ¬P` (flip and negate both sides) |
| **Double negation** | `¬(¬P)` = `P` |

> 💡 **Key Takeaway:** "Unless" is always "if not." The AND only appears when two conditions must hold simultaneously. When you see *"cannot do X if [condition], unless [exception]"*, the ban fires only when the condition is true AND the exception is absent — hence AND.

---
*Notes compiled from a tutoring session on propositional logic.*
