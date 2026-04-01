# cross-chain

Vulnerabilities in bridges, message passing, and multi-chain deployments — replay attacks, message spoofing, incorrect chain assumptions.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what cross-chain message or asset transfer was exploited and how]

**root cause:**
[missing sender validation? replay across chains? incorrect chainId check? finality assumption?]

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

- [ ] Is the source chain sender validated on the destination? (`msg.sender` = bridge contract, not original caller)
- [ ] Is `chainId` validated on receipt of a cross-chain message?
- [ ] Are messages replayable across chains or after re-orgs?
- [ ] Does the bridge assume instant finality on L2? (re-org risk)
- [ ] Are there differences in how `block.timestamp` or `block.number` behave across chains?
- [ ] Are address formats compatible? (EVM vs non-EVM)
- [ ] Is there a nonce or message ID to prevent duplicate processing?

---

## findings

<!-- add your entries below this line -->