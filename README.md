# Immutable-Constant-Optimization
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract OptimizedConstants {
    uint256 public constant MAX_SUPPLY = 1_000_000 * 10 ** 18; // Gas free reads
    address public immutable OWNER; // Set once in constructor, cheap reads

    constructor(address _owner) {
        OWNER = _owner;
    }

    function isOwner(address caller) public view returns (bool) {
        return caller == OWNER;
    }
}
