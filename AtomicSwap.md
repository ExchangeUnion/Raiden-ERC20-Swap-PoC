<h1>4. Atomic Swap </h1>

Just like with payments, it's incredibly easy to swap two ERC20 tokens between Raiden nodes using the WebUI. 


Firstly, let's look at the initial channel balances on both of our Raiden nodes:

![Raiden1](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/before1.png)

![Raiden2](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/before2.png)

Now, et's initiate a swap through the WebUI:

![SWAP](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/Screen%20Shot%202018-02-26%20at%204.55.40%20PM.png)

The role parts defines wheather the address sending the message is <b> Maker </b> or <b> Taker </b> The maker call must be carried out before the taker call can be carried out. In our case, Just pasting the "taker string" to the second Raiden node will autofill the UI. 

The swap `PUT` request can also be seen in the console:

`INFO:raiden.api.rest    35.201.178.159 - - [2018-02-26 08:57:37] "PUT /api/1/token_swaps/0x0096c9bad57df1ce7022268b3f62d839c23bd8d1/1337 HTTP/1.1" 201 142 100.0042
64 `

And the channel balances will be repectively updated

![after1](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/after1.png)
![after2](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/after2.png)

Previous:
* [3. How to transfer ERC20 tokens through a payment channel](TransferTokens.md)
