// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract NFTSMEMETOKEN is ERC20 {
    constructor() ERC20("NFTSMEMETOKEN", "NMT") {
        _mint(msg.sender, 1000000000 * 10 ** 18); // Total supply: 1 billion tokens with 18 decimals
    }
    
    function _mint(address account, uint256 amount) internal virtual override {
        require(totalSupply() + amount <= 1000000000 * 10 ** 18, "Total supply limit reached");
        super._mint(account, amount);
    }
}
