
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



