
<h1>3. How to transfer ERC20 tokens through a Payment Channel </h1>

Raiden's Web Application makes transferring the tokens a breeze 

![Tranferring token UI](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/Screen%20Shot%202018-02-26%20at%204.39.37%20PM.png)

After hitting <b> SEND </b> You will immediately recieve a confirmation notification in the UI 

![Confirmation UI](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/Screen%20Shot%202018-02-26%20at%204.39.51%20PM.png) 

Your Channel balance will be updated in both partner Raiden node, you could check the successful payment message on console 
with `POST` API request

` INFO:raiden.network.protocol    MESSAGE RECEIVED node=00259b0d message_sender=0096c9ba echohash=05a20501 message=<SecretRequest [hashlock:10909024 amount:20 hash:b66de44c]
INFO:raiden.network.protocol    MESSAGE RECEIVED node=00259b0d message_sender=0096c9ba echohash=9ec8fe9e message=<RevealSecret [hashlock:10909024 hash:2b604921]>
INFO:raiden.api.rest    35.201.178.159 - - [2018-02-26 08:39:50] "POST /api/1/transfers/0xe6ce7a2b221bfd15b837217189d4db6a58772308/0x0096c9bad57df1ce7022268b3f62d839c23bd8
d1 HTTP/1.1" 200 374 0.145373 `

It's important to note that if there is a path in the network with enough capacity and the address sending the transfer holds enough tokens to transfer the amount in the payload, the transfer will go through. 

Previous:
* [2. How to Open, Close and Settle a Payment Channel](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/OpenChannel.md)

Next:
* [4. How to execute Atomic-Swap between two Raiden nodes](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/AtomicSwap.md)
