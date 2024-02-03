# mini_starknet_project
Simple Version of Web3 Protocol and Apps built using cairo

## Mini-Ens
Lil-ens is just a very simple version of ens using cairo. To know more [ENS spec](https://eips.ethereum.org/EIPS/eip-137)


[Contract Source](https://github.com/Pelumi527/mini_ens/blob/main/src/lib.cairo)  • [Contract Test](https://github.com/Pelumi527/mini_ens/blob/main/tests/test_contract.cairo)

## Mini-FlashLoan
> A (Proof of Concept)-level flash loan implementation

lil flashloan allows contract implementing the `onFlashLoan(ERC20 token, uint256 amount, bytes data)` to temporarily receive any amount of ERC20 tokens by
calling the 
```cairo
      fn flashloan(
        ref self: TContractState,
        receiver: ContractAddress,
        token_address: ContractAddress,
        amount: u256,
        data: felt252
    );
```
 function the amount of tokens should be repaid (along with any fees) before the end of the transaction to prevent it from reverting.
    The Owner of the can set fee percentage by calling 
  ```cairo
        fn set_flash_fee(ref self: TContractState, token_address: ContractAddress, fee: u256)
  ```
    
  set supported token by calling 
  ```cairo
    fn set_support_token(
        ref self: TContractState, token_address: ContractAddress, isSupported: bool
    );
```
function and can withdraw the contract balance by calling 
```cairo
fn withdraw(ref self: TContractState, amount: u256, token_address: ContractAddress);
```
function.
    
[Contract Source](https://github.com/Pelumi527/mini_flashloan/blob/main/src/lib.cairo)  • [Contract Test](https://github.com/Pelumi527/mini_flashloan/blob/main/tests/test_contract.cairo)



## Contributing

Part of the motivation behind mini_starknet_project is to get better at Cairo. For this reason, I won't be accepting PRs that add new mini contracts, as I'd rather implement them myself.

That doesn't mean contributions aren't welcome tho! If you find a bug, gas optimisation, or there's something you'd have written differently, a PR will be very appreciated. New ideas for protocols/apps you'd like to see me try to build are also very welcome!
