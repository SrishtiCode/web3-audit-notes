# web3-audit-notes
 
Personal knowledge base for Web3 security research. Notes are written after reading audit reports on [Solodit](https://solodit.xyz), [Code4rena](https://code4rena.com), [Sherlock](https://audits.sherlock.xyz), and other sources.
 
## structure
 
```
web3-audit-notes/
├── vuln-types/              # notes organized by vulnerability class
│   ├── reentrancy/
│   ├── access-control/
│   ├── arithmetic/
│   ├── oracle-manipulation/
│   ├── flash-loans/
│   ├── logic-errors/
│   ├── frontrunning/
│   ├── denial-of-service/
│   ├── signature-issues/
│   ├── upgradeable-proxy/
│   └── cross-chain/
├── protocols/               # notes organized by protocol type
│   ├── lending/
│   ├── dex/
│   ├── bridges/
│   ├── yield/
│   ├── nft/
│   └── governance/
└── resources/               # useful links, tools, checklists
```
 
## how to use
 
1. Read a report on Solodit or any audit platform
2. Find the relevant `vuln-types/` file for the bug class
3. Add a new entry using the template at the top of that file
4. Also cross-reference in the relevant `protocols/` file if applicable
5. Commit and push
 
## quick links
 
| category | file |
|---|---|
| Reentrancy | [vuln-types/reentrancy/notes.md](vuln-types/reentrancy/notes.md) |
| Access Control | [vuln-types/access-control/notes.md](vuln-types/access-control/notes.md) |
| Arithmetic | [vuln-types/arithmetic/notes.md](vuln-types/arithmetic/notes.md) |
| Oracle Manipulation | [vuln-types/oracle-manipulation/notes.md](vuln-types/oracle-manipulation/notes.md) |
| Flash Loans | [vuln-types/flash-loans/notes.md](vuln-types/flash-loans/notes.md) |
| Logic Errors | [vuln-types/logic-errors/notes.md](vuln-types/logic-errors/notes.md) |
| Frontrunning / MEV | [vuln-types/frontrunning/notes.md](vuln-types/frontrunning/notes.md) |
| Denial of Service | [vuln-types/denial-of-service/notes.md](vuln-types/denial-of-service/notes.md) |
| Signature Issues | [vuln-types/signature-issues/notes.md](vuln-types/signature-issues/notes.md) |
| Upgradeable Proxy | [vuln-types/upgradeable-proxy/notes.md](vuln-types/upgradeable-proxy/notes.md) |
| Cross-chain | [vuln-types/cross-chain/notes.md](vuln-types/cross-chain/notes.md) |
 
