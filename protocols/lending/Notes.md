# lending protocols
 
Notes on vulnerabilities found specifically in lending/borrowing protocols (Aave, Compound, Euler, etc.).
 
Cross-reference entries here with the relevant `vuln-types/` file.
 
---
 
## protocol-specific things to always check
 
- [ ] Can collateral value be inflated before borrowing?
- [ ] Is the liquidation threshold correct and consistent with oracle precision?
- [ ] Can a borrower avoid liquidation by self-liquidating or donating collateral?
- [ ] Are interest accrual calculations correct across long time gaps?
- [ ] Is the health factor calculated with up-to-date oracle prices?
- [ ] Can a user borrow and repay in the same tx to avoid interest?
- [ ] Is bad debt socialized correctly when liquidation is unprofitable?
- [ ] Does the protocol handle paused/deprecated collateral assets safely?
 
---
 
## findings
 
<!-- format: link to your vuln-types entry + 1-line summary -->
 
<!-- example:
- [Euler — donation attack inflates collateral](../vuln-types/logic-errors/notes.md#euler-donation-attack) — attacker donated assets to inflate own collateral before borrowing
-->
 
