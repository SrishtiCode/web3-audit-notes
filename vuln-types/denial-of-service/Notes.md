# denial of service

Vulnerabilities that allow an attacker (or accidental condition) to permanently or temporarily block core protocol functions.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what function was blocked, how, and what was the impact on users]

**root cause:**
[unbounded loop? external call that can revert? push payments? block gas limit?]

**vulnerable pattern:**
\`\`\`solidity
// paste simplified vulnerable snippet
\`\`\`

**fix:**
[how it was fixed — pull pattern, pagination, try/catch]

**my takeaway:**
[what you will look for in future audits]
```

---

## things to always check

- [ ] Are there loops over user-supplied or unbounded arrays?
- [ ] Does the protocol push ETH/tokens to users inside a loop? (use pull pattern)
- [ ] Can a failing external call revert the entire transaction?
- [ ] Can an attacker grief by sending small amounts to fill a list?
- [ ] Is there a blacklist/blocklist that can block a required call?
- [ ] Can a user leave dust that prevents clean state transitions?

---

## findings

<!-- add your entries below this line -->