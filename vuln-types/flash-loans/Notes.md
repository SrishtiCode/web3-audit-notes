# flash loans

Vulnerabilities exploitable by borrowing large uncollateralized amounts within a single transaction to manipulate state, prices, or governance.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what did the attacker borrow, what did they manipulate, what did they gain]

**root cause:**
[spot price oracle? same-block governance vote? no snapshot for voting power?]

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

- [ ] Can governance voting power be acquired and used in the same block?
- [ ] Does the protocol read a spot price that can be moved with a large borrow?
- [ ] Are liquidation prices fetched at call time (flashloanable)?
- [ ] Does the protocol have a `balanceOf` check that can be temporarily inflated?
- [ ] Is there any action that depends on token supply or ratio that a flashloan can distort?

---

## findings

<!-- add your entries below this line -->