
# Introduction 
Although traditional blockchain transactions offer many advantages, the overall process often comes with many burdens when used in the context of small, frequent payments. Repeated payments can become costly and inefficient due to the associated transaction fees as well as the slow processing times. Micropayment channels have become a feasible and efficient way to remedy these drawbacks. Through a micropayment channel, individuals can carry out multiple transactions without having to make multiple commits on a blockchain, minimizing the cost for the entire process while making it faster. With the current limitations of existing micropayment channels, we propose to create a user-friendly system for individuals to send small repeated payments to trusted parties.
 <br>

![dsc capstone graphic for website small](https://github.com/medhaupadhyay/Micropayment-Channel-Public-Website/assets/81603081/e9d535fd-2630-4b0e-b98a-140bcd0ba705)
<br>

# How it Works 
<details>
<summary> Creating a New Channel </summary>
<br>
• Launch index.html and styles.css locally on your computer <br>
• Login with MetaMask and connect your account <br>
• Under ”Create New Channel”, enter your MetaMask address as the ”Sender Wallet Address” <br>
• Enter the ”Receiver Wallet Address”; this is the account you will be sending Ethereum to <br>
• Click "Deploy Contract" <br>
• Check your MetaMask account and click on the transaction that just occurred <br>
• Click "View on Etherscan" and copy the contract address; keep this for your records <br>
</details>

<details>
<summary>Logging a New Channel</summary>
<br>
• Enter the contract address of the newly created contract under ”Log a New Channel” <br>
• Click ”Submit” <br>

</details>




<details>
<summary>How do I dropdown?</summary>
<br>
This is how you dropdown.
</details>

<br> *Logging Payments on an Existing Channel* <br>
• Under ”Log Payments on an Existing Channel”, enter the contract address <br>
• Input the amount of Ethereum you would like to send to the receiver <br>
• Click ”Log Payment” <br>
• Save the unique signature that is generated <br>

<details>
<summary>How do I dropdown?</summary>
<br>
This is how you dropdown.
</details>
<br>*Closing a Channel* <br>
• Note: this action is irreversible <br>
• Enter the contract address under ”Close Channel” <br>
• Enter the most recently generated signature <br>
• Click ”Close Channel” <br>
• The receiver should receive the Ethereum once the transaction goes through <br>

# Methods
*Connecting to MetaMask* <br>
Users will be provided a field where they can input their address as well as the receiver's address to connect to MetaMask and begin the transaction process. This was implemented through the integration of Solidity smart contracts (converted to bytecode) and JavaScript, which were used to build the functionalities of the front-end interface. The smart contract acts as the MetaMask connection, while the program written in JavaScript executes the entire process from start to finish. <br>
<br>*Opening a New Payment Channel Through Interface* <br>
Like the Connecting to MetaMask feature, opening a new payment channel involves the integration of Solidity and JavaScript. The smart contract will initiate the transaction history between the sender and receiver, and open a payment channel between the two parties. (Note: The user will not have to worry about the "contract address", as it will be stored and implemented in the back-end.) Once the addresses are verified as existing addresses, the sender will be permitted to enter an amount that they wish to send to the recipient. A unique signature will be generated and the sender will be expected to store and save this signature for future reference or when the parties wish to close the current channel. Once the payment channel is open, the sender can send more transactions -- which will be logged off-chain -- as long as needed or until the channel has been closed. <br>
<br>*Logging Payments Off-Chain* <br>
This feature was implemented using key-value pairs in local storage. Each contract address serves as a key and the amount that the sender owes the receiver is the value. When a new channel is logged, the contract address is registered in local storage with a value of zero. When a new payment is logged, the existing value is increased by the given amount. The new total amount owed is set as the value for that contract key. This value is then displayed to the user in a pop up message, so they are aware of how much they owe the receiver and that the payment was logged. <br>
Since the total amount due is updated as the information comes in, closing the channel simply involves transferring the recorded dues from the sender to the receiver. <br>
<br>*Closing a Payment Channel Through Interface* <br>
The final feature, closing the payment channel, integrates the smart contract, which includes a function that allows the user to close the current payment channel. The user will be prompted with a message ensuring that they are ready to close the channel. If the user permits, the user must provide the unique signature that was generated when opening the channel. The channel will officially close, and this action cannot be reversed. Once the payment channel closes, all transactions made from start to end will tally and be sent to the receiver in whole. <br>

# Conclusion
Our channel emphasizes transparency by encouraging users to verify and publish the contract code on Etherscan. MetaMask integration ensures secure transaction confirmation. Users can interact with the micropayment channel on the Ethereum testnet and use it to sent testnet Ethereum to trusted users. <br>
In essence, this method is a user-friendly guide for experimenting with micropayment channels on the Ethereum test network. With further testing, this framework can be expanded to be deployed on the Ethereum blockchain and be used for real transactions among trusted parties.
