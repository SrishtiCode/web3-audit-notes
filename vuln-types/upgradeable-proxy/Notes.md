# upgradeable proxy

Vulnerabilities in proxy patterns — storage collisions, uninitialized implementations, selfdestruct in logic contracts, broken upgrade authorization.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what proxy issue existed and what was the impact]

**root cause:**
[storage collision? missing initializer? selfdestruct? delegatecall to untrusted address?]

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

- [ ] Is the implementation contract initialized? (front-runnable initializer?)
- [ ] Does the implementation contain a `selfdestruct`? (destroys proxy state)
- [ ] Are storage slots EIP-1967 compliant to avoid collisions?
- [ ] Is the upgrade function protected by a timelock or multisig?
- [ ] Does the new implementation's storage layout match the old one?
- [ ] Is `initialize()` callable more than once? (missing `initializer` modifier)
- [ ] For UUPS: is `_authorizeUpgrade` properly protected?

---

## findings

<!-- add your entries below this line -->