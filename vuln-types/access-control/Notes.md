# access control

Vulnerabilities where critical functions lack proper authorization checks, or where roles/permissions are misconfigured.

---

## entry template

```
### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[what function was unprotected and what could an attacker do with it]

**root cause:**
[missing modifier? wrong role check? initializer unprotected? two-step ownership missing?]

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

- [ ] Is `initialize()` protected? Can it be front-run?
- [ ] Are all admin setters behind `onlyOwner` or role checks?
- [ ] Is ownership transfer two-step (propose + accept)?
- [ ] Are there functions with no modifier at all that change state?
- [ ] Does `selfdestruct` or `delegatecall` have access control?
- [ ] Are `DEFAULT_ADMIN_ROLE` and `PAUSER_ROLE` assigned correctly at deploy?

---

## findings

<!-- add your entries below this line -->