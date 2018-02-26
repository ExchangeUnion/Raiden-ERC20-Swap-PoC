<h1>2. How to open a Payment Channel </h1>

With two Raiden node running simultaneously, you can start the web application on both nodes in two different ports and open the channel through the User-Interface.


![OPENING THE CHANNEL](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/Screen%20Shot%202018-02-26%20at%2012.04.55%20PM.png)

* In *Partner Address* field, insert the address of the second raiden node running.
* In *Token* feild, insert the token that you intend to transfer.
* In *Deposit* feild, insert the amount of that token you want to deposit in the channnel
* In *Settle-Timeout* input the timelock after which you can settle the channel

After sucessfully opening the channel, you will see a new channel in the *Channel* tab:

![Channels](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/Screen%20Shot%202018-02-26%20at%204.00.57%20PM.png)

You can also check the channels through `GET /api/1/channels` request

`[
 {
  "state": "opened",
  "token_address": "0x706ffe280b3ab30719212a8b6f4a1b2ac00f0862",
  "channel_address": "0xca2a1d4ba29a0afcabf2899bde6f7ef420122948",
  "settle_timeout": 600,
  "reveal_timeout": 10,
  "partner_address": "0x00259b0d8acfc6e7177d30a93063c33e727f845e",
  "balance": 79940
 },
 {
  "state": "opened",
  "token_address": "0xe6ce7a2b221bfd15b837217189d4db6a58772308",
  "channel_address": "0x887e6a8f1ab580aad33e0a744f6ea55f29d275c2",
  "settle_timeout": 600,
  "reveal_timeout": 10,
  "partner_address": "0x00259b0d8acfc6e7177d30a93063c33e727f845e",
  "balance": 122
 }
]`

![Closing/Settling Channel](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/Screen%20Shot%202018-02-26%20at%205.14.58%20PM.png)

Closing and setting Channel can be done through the `close` endpoint OR through the WebUI, Once `close` has been called, the settle timeout period starts, During this period the counterparty of the node who closed the channel has to provide it's last recieved message. When the settlement timeout period is over, the channel can finally be settled through the webui or by sending `PATCH /api/channels/0x887e6a8f1ab580aad33e0a744f6ea55f29d275c2` 

with the payload:
` {
     "state":"settled"
  }
 `
 
Previous:
* [1. How to set up and Install Raiden Network](https://github.com/dopetard/Raiden-Test/blob/master/INSTALLATION.md)

Next:
* [3. How to transfer ERC20 tokens through a payment channel](https://github.com/dopetard/Raiden-ERC20-Atomic-Swap-POC-/blob/master/TransferTokens.md)
