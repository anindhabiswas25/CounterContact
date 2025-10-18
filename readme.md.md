# 🧮 Counter Smart Contract

A simple **Solidity smart contract** that demonstrates how to store and
modify a number on-chain using basic **state variables**, **functions**,
and **transactions**.

------------------------------------------------------------------------

## 🚀 Overview

This smart contract allows anyone to **increment**, **decrement**, or
**read** a counter stored on the blockchain.

It's a perfect beginner project for learning how Solidity handles
**state**, **public variables**, and **gas-based function calls**.

------------------------------------------------------------------------

## 📜 Smart Contract Code

``` solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

/**
 * @title Counter
 * @dev A simple smart contract that allows incrementing and decrementing a count.
 */
contract Counter {
    /**
     * @dev The state variable 'count' is stored on the blockchain.
     * The 'public' keyword automatically creates a getter function for it.
     */
    uint256 public count;

    /**
     * @dev Increases the value of 'count' by 1.
     * This is a state-changing function and requires a transaction (and gas).
     */
    function increment() public {
        count += 1;
    }

    /**
     * @dev Decreases the value of 'count' by 1.
     * This will revert the transaction if 'count' is 0, preventing an underflow error,
     * because 'uint256' cannot be negative.
     */
    function decrement() public {
        require(count > 0, "Count cannot go below zero");
        count -= 1;
    }

    /**
     * @dev A view function to get the current value of the count.
     * Calling this function is free as it does not modify the state.
     * Note: A public getter is already created for 'count', but this is
     * included for explicit demonstration.
     */
    function get() public view returns (uint256) {
        return count;
    }
}
```

------------------------------------------------------------------------

## 🧠 Key Concepts Demonstrated

-   State variables and blockchain storage
-   Public visibility and automatic getters
-   Gas cost for state-changing functions
-   Safe increment/decrement operations
-   View functions (no gas cost for reads)

------------------------------------------------------------------------

## 🪙 Deployment Info

**Contact Address:** `0x4f8a0FF83CBD6D02566EaE08DEa7e7d9De556cA6`

------------------------------------------------------------------------

## 💡 How to Use

1.  Deploy the contract on Remix IDE (https://remix.ethereum.org)
2.  Click **Deploy** and open the deployed contract tab.
3.  Use:
    -   `increment()` → adds 1 to the count.
    -   `decrement()` → subtracts 1 (will fail if count is 0).
    -   `get()` → returns the current count.

------------------------------------------------------------------------

## 🌐 Author & Links

👤 **Developer:** Anindha Biswas\
🔗 **LinkedIn:** [Connect with
me](https://www.linkedin.com/in/anindhabiswas)\
📫 **Contact Address:** `0x4f8a0FF83CBD6D02566EaE08DEa7e7d9De556cA6`

------------------------------------------------------------------------

⭐ If you found this project useful, give it a like or share it on
LinkedIn!
