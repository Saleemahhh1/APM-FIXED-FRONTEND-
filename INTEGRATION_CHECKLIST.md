# Contract integration checklist

Known notes from prior project discussion:
- Chain ID: 97 (BNB Testnet)
- APMToken: 0x97b619d007ac9fC06109b5162da22603ee316470
- MarketFactory: 0xd6a3cfd9653d88fd2a4efe7366bd0a19f74a70e9
- PredictionMarket deployment address was not independently confirmed in this build context.
- Factory calls recorded: createMarket(string,uint256,uint256), getAllMarkets(), getUserMarkets(address), resolveMarket(address,uint8), CREATION_FEE().
- PredictionMarket calls recorded: placeBet(uint256,uint256), claim(), setResult(uint8), getMarketStatus().
- YES=1; NO=2. Creation fee noted as 100 APM; default fee 200 BPS.

Before enabling writes:
1. Copy exact full ABI artifacts from the verified deployment build.
2. Verify addresses and chain ID against BNB Testnet explorer.
3. Check token decimals and approve flow.
4. Confirm the factory's createMarket argument meanings and payable/token fee behavior.
5. Confirm how a user position is queried and what claim() returns.
6. Confirm resolver authorization and status enum mapping.
7. Test all flows on testnet using small amounts.
8. Add VestingManager address + exact ABI; verify cap and cliff semantics.
