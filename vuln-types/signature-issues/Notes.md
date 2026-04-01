# signature issues

Vulnerabilities in signature verification — replay attacks, malleable signatures, missing fields, wrong signer checks.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what signed message was exploited and how]

**root cause:**
[missing chainId? missing nonce? ecrecover returns address(0)? signature malleability?]

**vulnerable pattern:**
\`\`\`solidity
// paste simplified vulnerable snippet
\`\`\`

**fix:**
[how it was fixed — EIP-712, nonce, chainId, OpenZeppelin ECDSA]

**my takeaway:**
[what you will look for in future audits]
```

---

## things to always check

- [ ] Is `chainId` included in the signed struct? (cross-chain replay)
- [ ] Is a `nonce` included and incremented after use? (same-chain replay)
- [ ] Is the return value of `ecrecover` checked against `address(0)`?
- [ ] Is OpenZeppelin's `ECDSA.recover` used instead of raw `ecrecover`?
- [ ] Does the domain separator include the contract address?
- [ ] Are signatures validated to be unused before executing the action?
- [ ] Is there a deadline/expiry on the signature?

---

## findings

<!-- add your entries below this line -->