# logic errors

Business logic bugs — the code does what it says, but what it says is wrong. Incorrect state machines, wrong conditions, bad accounting.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what did the logic get wrong — what was the intended behavior vs actual behavior]

**root cause:**
[wrong condition? missing state update? incorrect formula? edge case not handled?]

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

- [ ] Fee-on-transfer tokens: is actual received balance checked (before/after pattern)?
- [ ] Rebasing tokens: does the protocol account for changing balances?
- [ ] ERC777 tokens: are there unexpected hooks being triggered?
- [ ] Is there a missing state update before an external call?
- [ ] Are there off-by-one errors in loops or array indexing?
- [ ] Does the protocol handle the case where `totalSupply == 0`?
- [ ] Can a user deposit 1 wei to manipulate share price (vault inflation attack)?

---

## findings

<!-- add your entries below this line -->