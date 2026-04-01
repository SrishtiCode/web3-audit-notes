reentrancy
Vulnerabilities where an external call allows the callee to re-enter the calling contract before the first execution completes, leading to unexpected state.

### [title of finding]

- **source:** [solodit link or report name]
- **protocol:** [protocol name + type, e.g. "Euler Finance — lending"]
- **severity:** [critical / high / medium]
- **date read:** [YYYY-MM-DD]

**what happened:**
[1-2 sentences: what was the vulnerable function doing and what did the attacker do]

**root cause:**
[why the code was vulnerable — state update after external call? missing reentrancy guard?]

**vulnerable pattern:**
\`\`\`solidity
// paste the simplified vulnerable snippet here
\`\`\`

**fix:**
[what the protocol did to fix it — CEI pattern, ReentrancyGuard, etc.]

**my takeaway:**
[what you will look for in future audits because of this finding]

findings
<!-- add your entries below this line -->

read-only reentrancy via Curve LP price

source: https://solodit.xyz/issues/example
protocol: generic DeFi — vault
severity: high
date read: 2024-01-01

what happened:
A vault read Curve's virtual price inside a view function called during a callback. An attacker exploited the window between Curve's state update and the reentrancy lock to feed a stale price.
root cause:
View functions are not protected by reentrancy guards. The protocol assumed reads were safe mid-execution but the price oracle was manipulable in that window.
vulnerable pattern:
