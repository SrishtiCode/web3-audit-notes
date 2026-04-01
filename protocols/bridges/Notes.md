# bridges
 
Notes on vulnerabilities found in cross-chain bridges (Wormhole, Ronin, Nomad, etc.).
 
Cross-reference entries here with the relevant `vuln-types/` file.
 
---
 
## protocol-specific things to always check
 
- [ ] Is the validator/guardian set properly decentralized and protected?
- [ ] Is message authenticity verified on the destination chain?
- [ ] Can messages be replayed on the same or different chains?
- [ ] Are withdrawal proofs correctly verified (not just checked for existence)?
- [ ] Is there a fraud-proof or challenge period for optimistic bridges?
- [ ] Is the bridge's admin key/multisig adequately secured?
- [ ] Are token decimals normalized correctly across chains?
- [ ] Can the bridge be drained by minting without locking on source chain?
 
---
 
## findings
 