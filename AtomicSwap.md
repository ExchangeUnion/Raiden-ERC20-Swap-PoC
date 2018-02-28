<h1>4. Atomic Swap </h1>

Just like with payments, it's incredibly easy to swap two ERC20 tokens between Raiden nodes using the WebUI. 


Firstly, let's look at the initial channel balances on both of our Raiden nodes:

The channel on the first Raiden node has 60 BET tokens balance (highlighted in green)

![Raiden1](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/before1.gif)

The channel on the second Raiden node has a custom token balance of 142 (highlighted in green)

![Raiden2](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/before2.gif)

Now, let's initiate a swap through the WebUI:

![SWAP](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/Screen%20Shot%202018-02-26%20at%204.55.40%20PM.png)

The role parts define whether the address sending the message is <b> Maker </b> or <b> Taker </b> The maker call must be carried out before the taker call can be carried out. In our case, just pasting the "taker string" to the second Raiden node will autofill the UI. 

The swap `PUT` request can also be seen in the console:

` "PUT /api/1/token_swaps/0x0096c9bad57df1ce7022268b3f62d839c23bd8d1/1337 HTTP/1.1" 201 142 100.0042
64 `

And, evidently, the respective channel balances are updated

The channel on first Raiden node shows 560 BET token balance

![after1](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/after1.gif)

The channel on the second Raiden node shows a balance of 942 custom tokens

![after2](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/after2.gif)

Previous:
* [3. How to transfer ERC20 tokens through a payment channel](TransferTokens.md)
