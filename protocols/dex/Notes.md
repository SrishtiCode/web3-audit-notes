# dex / amm protocols
 
Notes on vulnerabilities found in DEXs and AMMs (Uniswap, Curve, Balancer, etc.).
 
Cross-reference entries here with the relevant `vuln-types/` file.
 
---
 
## protocol-specific things to always check
 
- [ ] Is the swap slippage protected with a `minAmountOut` parameter?
- [ ] Is there a `deadline` parameter on swaps?
- [ ] Can the pool's reserves be manipulated within a single block?
- [ ] Are LP token prices calculated using spot reserves? (manipulable)
- [ ] Is the fee-on-transfer token case handled?
- [ ] Can liquidity be added/removed in the same tx as a price-sensitive action?
- [ ] Are price impact checks in place for large swaps?
- [ ] Does the router correctly handle native ETH vs WETH?
 
---
 
## findings
 
<!-- format: link to your vuln-types entry + 1-line summary -->
