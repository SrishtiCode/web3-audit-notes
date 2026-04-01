# frontrunning / MEV

Vulnerabilities where a miner or searcher can observe a pending transaction and insert their own transaction ahead of it to profit or cause harm.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what transaction was visible in the mempool and how was it exploited]

**root cause:**
[no slippage protection? approve+transferFrom pattern? predictable randomness? public reveal?]

**vulnerable pattern:**
\`\`\`solidity
// paste simplified vulnerable snippet
\`\`\`

**fix:**
[how it was fixed — commit-reveal, private mempool, slippage param, deadline]

**my takeaway:**
[what you will look for in future audits]
```

---

## things to always check

- [ ] Is there a `minAmountOut` / slippage param on swaps?
- [ ] Is `approve(spender, amount)` used? (increaseAllowance is safer)
- [ ] Is there a `deadline` param on time-sensitive operations?
- [ ] Does the protocol use `block.timestamp` or `blockhash` for randomness?
- [ ] Is there a commit-reveal scheme where the reveal is frontrunnable?
- [ ] Are NFT mints predictable (token ID or rarity calculable before mint)?

---

## findings

<!-- add your entries below this line -->