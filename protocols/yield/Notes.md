# yield / vault protocols
 
Notes on vulnerabilities found in yield aggregators, vaults, and farming protocols (Yearn, Beefy, etc.).
 
Cross-reference entries here with the relevant `vuln-types/` file.
 
---
 
## protocol-specific things to always check
 
- [ ] Is the first depositor vault inflation attack possible? (ERC4626 first deposit)
- [ ] Are share prices manipulable via donation?
- [ ] Is the harvest/compound function callable by anyone? (sandwich risk)
- [ ] Are rewards distributed correctly when users deposit mid-epoch?
- [ ] Is there a withdrawal fee that can be bypassed?
- [ ] Can a user sandwich a large harvest to steal yield?
- [ ] Does the vault correctly handle strategies that lose funds?
- [ ] Is emergency withdrawal working even when strategy is paused?
 
---
 
## findings
 
<!-- format: link to your vuln-types entry + 1-line summary -->
 