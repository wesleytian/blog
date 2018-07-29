---
title: "My Own Cryptocurrency"
date: 2018-03-15T00:14:49-04:00
showDate: true
draft: false
tags: ["blog","story"]
---

#### Summary:

* Cryptocurrency built in Selenium on the Ethereum blockchain.
* Blockchain @ Michigan Workshop.
* WesTCoin is currently private and the exchange rate is 1 WesTCoin ~ 1 Ethereum.

#### Why Did I Build This?
The Blockchain @ Michigan club at the University of Michigan was hosting a workshop to teach people how to create their own cryptocurrencies on the Ethereum blockchain. As as a former blockchain and cryptocurrency enthusiast, I couldn't turn down this great opportunity to attend this workshop.

#### How Did I Build This?
The coin was coded in Selenium and we used MetaMask to run the Ethereum dApp.

#### What Did I Learn From Building This?
However I did learn many things about the Ethereum ecosystem such as Ethereum gas, which is how you pay for operations on the Ethereum ecosystem. 

As with many other software projects, everything seems to be super straightforward to build in retrospect. Take this following function for example which transfers funds from one account address to another account address. Even without prior experience with Selenium or writing code for the blockchain, it was quite intuitive and easy to grasp. 

We first check that the transfer amount is nonnegative and that the `from` account has at least the transfer amount. Next, we just update the respective `from` account funds, `to` account funds, perform the tranfer, and finally return true.

---
    /// @notice send `_value` token to `_to` from `_from` on the condition it is approved by `_from`
    /// @param _from The address of the sender
    /// @param _to The address of the recipient
    /// @param _value The amount of token to be transferred
    /// @return Whether the transfer was successful or not
    function transferFrom(address _from, address _to, uint256 _value) returns (bool success) {
        if (balances[_from] >= _value && _value > 0 && allowed[_from][msg.sender] >= _value) {
            balances[_from] -= _value;
            balances[_to] += _value;
            allowed[_from][msg.sender] -= _value;
            Transfer(_from, _to, _value);
            return true;
        }
        return false;
	}

---


More info on how to replicate this project and create your own coin coming soon!

GitHub Repo: https://github.com/wesleytian/WesTCoin
