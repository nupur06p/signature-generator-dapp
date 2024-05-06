# Signature Generator Dapp

This project will help us understand how to verify a message signature on Ethereum. We will be using Ether.js for this project. Message signatures requires a message and an Ethereum private key to be generated. This can be used as a digital verification system for any application that requires a user to prove their identity.

In case of e-signing of documents or pdfs, this application can be utilized. The signature verification process does not require us to connect to Ethereum network as it requires a message, the wallet address (public key) and private key to generate the signature hash. The entire process happens off-chain and it has no gas costs. 

We will be understanding how a signature is generated and verified. We will be building a signature generation Dapp using React JS, using Ether.js we will be connecting to the front end such that it lets us connect to Metamask wallet to sign and verify messages. 

In this project, it is necessary to have Metamask. If we don't have it, then we cannot sign and verify the Dapp to the front end.

Libraries to be installed for this project
- Install Node.js
- Install Metamask wallet
- Install an IDE (using VS code in this project)
- Install Ether.js

The front-end interface will have four components:
- Connect Wallet button
- Sign Message component
- Verify Signature component
- Generated Signatures component

## Connect Wallet Button
The connect wallet function helps us get the addresses from Metamask.
This code is divided into four sections:

- connectWallet: It checks if the Metamask is installed and if yes, it returns the user's account address.
- getConnectedWallet: If the user is already connected to Metamask, this function will help us retrieve the connected addresses.
- walletConnectHandler: This function allows the Connect Wallet button to repsond to the user clicks and sets the wallet address such that the button has the correct address.
- addWalletListner: In case user switches accounts, this function helps to update the Connect Wallet button with the correct address.
- load: It handles the entire code we want to run after React has updated the DOM.

## Sign Message Component
This function takes the user message and pass it along to Metamask and await the user's signature. The timestamp when the message is signed by the user is captured. The timestamp, message, signature hash and signer address is returned as an object. This object is later passed as an array in the generated signature component.

## Verify Signature Component
This function takes the wallet address, message and signature hash. It checks whether they are valid using Ether.js recoverAddress function. It returns a Valid or Invalid response.

## Generated Signatures Component
This component displays the list of all signatures that was generated with timestamp, address and message field. 


