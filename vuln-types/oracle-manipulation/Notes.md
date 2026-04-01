# oracle manipulation

Vulnerabilities where price or data feeds can be manipulated, leading to incorrect valuations, liquidations, or minting.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what oracle was used and how was it manipulated]

**root cause:**
[spot price? single-block TWAP? AMM reserve ratio? no staleness check?]

**vulnerable pattern:**
\`\`\`solidity
// paste simplified vulnerable snippet
\`\`\`

**fix:**
[how it was fixed — TWAP window, Chainlink, multi-source, circuit breaker]

**my takeaway:**
[what you will look for in future audits]
```

---

## things to always check

- [ ] Is the price derived from `reserve0/reserve1` of an AMM? (spot price — manipulable)
- [ ] Is there a TWAP? What is the window? (30min minimum is common)
- [ ] Is there a Chainlink staleness check (`updatedAt + heartbeat > block.timestamp`)?
- [ ] Is `get_virtual_price()` from Curve used in a reentrancy-susceptible context?
- [ ] Can a single large trade meaningfully move the price feed in one tx?
- [ ] Are there circuit breakers for extreme price deviations?

---

## findings

<!-- add your entries below this line -->