# governance protocols
 
Notes on vulnerabilities found in on-chain governance systems (Compound Governor, OpenZeppelin Governor, etc.).
 
Cross-reference entries here with the relevant `vuln-types/` file.
 
---
 
## protocol-specific things to always check
 
- [ ] Can voting power be flash-loaned and used in the same block?
- [ ] Is a snapshot block used for voting power? Is it set correctly?
- [ ] Is the timelock delay sufficient to allow community response?
- [ ] Can a proposal be executed before the timelock expires?
- [ ] Is quorum calculated on current supply (manipulable) or fixed?
- [ ] Can the proposer cancel a passing proposal maliciously?
- [ ] Is the guardian/veto power adequately controlled?
- [ ] Can an attacker grief by spamming proposals to exhaust the queue?
 
---
 
## findings
 
<!-- format: link to your vuln-types entry + 1-line summary -->
 