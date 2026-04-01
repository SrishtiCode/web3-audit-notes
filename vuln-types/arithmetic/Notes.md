# arithmetic

Overflow, underflow, precision loss, rounding errors, and incorrect calculations.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what calculation was wrong and what effect did it have]

**root cause:**
[overflow? division before multiplication? wrong decimals? unchecked block?]

**vulnerable pattern:**
\`\`\`solidity
// paste simplified vulnerable snippet
\`\`\`

**fix:**
[how it was fixed]

**my takeaway:**
[what you will look for in future audits]
```

---

## things to always check

- [ ] Is division done before multiplication anywhere? (precision loss)
- [ ] Are there `unchecked` blocks — what assumptions do they rely on?
- [ ] Are token decimals handled consistently (e.g. mixing 6-decimal USDC with 18-decimal tokens)?
- [ ] Does reward/share math use a scaling factor (1e18)?
- [ ] Can any counter underflow to wrap around?
- [ ] Are fee calculations rounding in the protocol's favor or the user's?

---

## findings

<!-- add your entries below this line -->