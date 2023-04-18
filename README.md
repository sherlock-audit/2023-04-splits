
# [project name] contest details

- Join [Sherlock Discord](https://discord.gg/MABEWyASkp)
- Submit findings using the issue page in your private contest repo (label issues as med or high)
- [Read for more details](https://docs.sherlock.xyz/audits/watsons)


For more details:  https://www.notion.so/splits/Swapper-Audit-Overview-78ba6b86bb604e33942e5915c258ac62

# Q&A

### Q: On what chains are the smart contracts going to be deployed?
 just mainnet for now
___

### Q: Which ERC20 tokens do you expect will interact with the smart contracts? 
 ~any, although our provided oracle implementation only works with tokens handled by uniswap v3 (e.g. no rebasing or fee-on-transfer)
___

### Q: Which ERC721 tokens do you expect will interact with the smart contracts? 
 none
___

### Q: Which ERC777 tokens do you expect will interact with the smart contracts? 
 ~any, subject again to the above caveat re oracle / uni v3
___

### Q: Are there any FEE-ON-TRANSFER tokens interacting with the smart contracts?

 no
___

### Q: Are there any REBASING tokens interacting with the smart contracts?

 no
___

### Q: Are the admins of the protocols your contracts integrate with (if any) TRUSTED or RESTRICTED?
 don’t think there are any (uniswap v3 twap), but RESTRICTED
___

### Q: Is the admin/owner of the protocol/contracts TRUSTED or RESTRICTED?
 no protocol owner(s); oracle, swapper, & pass-through-wallet owners are TRUSTED
___

### Q: Are there any additional protocol roles? If yes, please explain in detail:
 no
___

### Q: Is the code/contract expected to comply with any EIPs? Are there specific assumptions around adhering to those EIPs that Watsons should be aware of?
 no
___

### Q: Please list any known issues/acceptable risks that should not result in a valid finding.
 user misconfiguration; swapper#flash callers are expected to be sophisticated (aka will check if a given txn reverts, will use flashbots rpc to avoid FR & owner-griefing, etc)
___

### Q: Please provide links to previous audits (if any).
 none
___

### Q: Are there any off-chain mechanisms or off-chain procedures for the protocol (keeper bots, input validation expectations, etc)?
 configuration of individual deployments is important but not in scope
___

### Q: In case of external protocol integrations, are the risks of external contracts pausing or executing an emergency withdrawal acceptable? If not, Watsons will submit issues related to these situations that can harm your protocol's functionality.
our understanding is uniswap v3’s twap is not pausable
___



# Audit scope


[splits-utils @ 0dd263bf6feb0bd26b054da3cf1bb742d0bfb13e](https://github.com/0xSplits/splits-utils/tree/0dd263bf6feb0bd26b054da3cf1bb742d0bfb13e)
- [splits-utils/src/AddressUtils.sol](splits-utils/src/AddressUtils.sol)
- [splits-utils/src/LibClone.sol](splits-utils/src/LibClone.sol)
- [splits-utils/src/LibRecipients.sol](splits-utils/src/LibRecipients.sol)
- [splits-utils/src/OwnableImpl.sol](splits-utils/src/OwnableImpl.sol)
- [splits-utils/src/PausableImpl.sol](splits-utils/src/PausableImpl.sol)
- [splits-utils/src/TokenUtils.sol](splits-utils/src/TokenUtils.sol)
- [splits-utils/src/WalletImpl.sol](splits-utils/src/WalletImpl.sol)

[splits-swapper @ 83ce1124767a097aac37d1cd162a9b27bbc48701](https://github.com/0xSplits/splits-swapper/tree/83ce1124767a097aac37d1cd162a9b27bbc48701)
- [splits-swapper/src/SwapperFactory.sol](splits-swapper/src/SwapperFactory.sol)
- [splits-swapper/src/SwapperImpl.sol](splits-swapper/src/SwapperImpl.sol)
- [splits-swapper/src/peripherals/SwapperCallbackValidation.sol](splits-swapper/src/peripherals/SwapperCallbackValidation.sol)

[splits-oracle @ f6628a116d8721289dad2c70d3e3aa14e4815d4e](https://github.com/0xSplits/splits-oracle/tree/f6628a116d8721289dad2c70d3e3aa14e4815d4e)
- [splits-oracle/src/OracleImpl.sol](splits-oracle/src/OracleImpl.sol)
- [splits-oracle/src/UniV3OracleFactory.sol](splits-oracle/src/UniV3OracleFactory.sol)
- [splits-oracle/src/UniV3OracleImpl.sol](splits-oracle/src/UniV3OracleImpl.sol)
- [splits-oracle/src/peripherals/OracleParams.sol](splits-oracle/src/peripherals/OracleParams.sol)
- [splits-oracle/src/utils/QuotePair.sol](splits-oracle/src/utils/QuotePair.sol)
- [splits-oracle/src/interfaces/IOracleFactory.sol](splits-oracle/src/interfaces/IOracleFactory.sol)

[splits-pass-through-wallet @ 203badc970b9bb2216cf2ae0e93dcb0a0de19151](https://github.com/0xSplits/splits-pass-through-wallet/tree/203badc970b9bb2216cf2ae0e93dcb0a0de19151)
- [splits-pass-through-wallet/src/PassThroughWalletFactory.sol](splits-pass-through-wallet/src/PassThroughWalletFactory.sol)
- [splits-pass-through-wallet/src/PassThroughWalletImpl.sol](splits-pass-through-wallet/src/PassThroughWalletImpl.sol)

[splits-diversifier @ bdb11a10d9f3aaf731adca09d6a0e05ab359e188](https://github.com/0xSplits/splits-diversifier/tree/bdb11a10d9f3aaf731adca09d6a0e05ab359e188)
- [splits-diversifier/src/DiversifierFactory.sol](splits-diversifier/src/DiversifierFactory.sol)


