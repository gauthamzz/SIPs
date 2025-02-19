---
sccp: 248
network: Ethereum
title: Update Atomic Exchange Fees / 1inch Integration
author: Kaleb (@kaleb-keny)
status: Implemented
created: 2022-11-22
proposal: >-
  https://snapshot.org/#/snxgov.eth/proposal/0x867b48633cdcdb427d9e98b51e0b2312bb136bc5363d9c230b7954ad52a2d884
type: Governance
---

<!--You can leave these HTML comments in your merged SCCP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new SCCPs. Note that an SCCP number will be assigned by an editor. When opening a pull request to submit your SCCP, please use an abbreviated title in the filename, `sccp-draft_title_abbrev.md`. The title should be 44 characters or less.-->

## Simple Summary

<!--"If you can't explain it simply, you don't understand it well enough." Provide a simplified and layman-accessible explanation of the SCCP.-->

Lower the atomic exchange fee on trades into sETH, with respect to the 1inch integration addresses specified in [SIP-288](https://sips.synthetix.io/sips/sip-288/), to 20 bp from 25 bp. 

## Abstract

<!--A short (~200 word) description of the variable change proposed.-->

The `atomicExchangeFee` is the fee applied on trades into a certain synth:

```
{'currencyKey': 'sETH',
 'dexPriceAggregator': '0x9645C7de2DBe8AAda01868cAa393cB7e5253268c' (uses 30 bp uni pool),
 'atomicMaxVolumePerBlock': 3m$,
 'atomicVolatilityUpdateThreshold': 10,
 'atomicExchangeFeeRate': 20 bp}
```

## Motivation

<!--The motivation is critical for SCCPs that want to update variables within Synthetix. It should clearly explain why the existing variable is not incentive aligned. SCCP submissions without sufficient motivation may be rejected outright.-->

The primary motivation is to boost the atomic exchange volume, taking into account protection against latency attacks via the curve slippage. 

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).