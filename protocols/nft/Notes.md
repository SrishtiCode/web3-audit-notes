# nft protocols
 
Notes on vulnerabilities found in NFT marketplaces, minting contracts, and NFT-fi protocols.
 
Cross-reference entries here with the relevant `vuln-types/` file.
 
---
 
## protocol-specific things to always check
 
- [ ] Is the mint randomness manipulable by a miner or searcher?
- [ ] Can token IDs be predicted before reveal?
- [ ] Is royalty enforcement bypassable through wrapper contracts?
- [ ] Are signed offers replayable across different NFTs or collections?
- [ ] Is the floor price oracle manipulable for NFT-collateralized loans?
- [ ] Can a bid be accepted after the bidder's funds are withdrawn?
- [ ] Are there reentrancy risks in `safeTransferFrom` / `onERC721Received`?
- [ ] Can the owner lock NFTs inside the contract (DoS on transfers)?
 
---
 
## findings
 
<!-- format: link to your vuln-types entry + 1-line summary -->
 