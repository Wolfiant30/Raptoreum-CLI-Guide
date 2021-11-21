# Raptoreum CLI Guide

A guide to common usage for the CLI interface in the Raptoreum wallet.

The goal of this guide is show common commands with examples of managing your Raptoreum Core wallet in the command line interface.

## 1. Setup & Blockchain Sync

   1. Download the latest version of the wallet for your OS from

      - https://github.com/Raptor3um/raptoreum/releases/latest
    
   2. Unpack the wallet from the achrive into any directory.

      - I would **highly** suggest to download the [bootstrap.zip](https://github.com/Raptor3um/raptoreum/releases/latest) located with the latest release download.

   3. Start your Raptoreum Core server `raptoreumd -server`

[![SETUP](https://img.youtube.com/vi/DYYMSNIcO20/1.jpg)](https://youtu.be/DYYMSNIcO20)

   4. Wait for the server to complete syncronization.  This can take a while depending on how out of date the server is.

   - You can check the status of the sync with `raptoreum-cli getblockchaininfo`

      - When the `"blocks"` height is close to the current height of the [blockchain](https://explorer.raptoreum.com/) and `"verificationprogress"` is to close `1`, your wallet is in sync.

[![BLOCKCHAIN SYNC](https://img.youtube.com/vi/hq49iBWM48I/1.jpg)](https://youtu.be/hq49iBWM48I)

## 2. Prepairing Your Wallet

- To create a receiving address: 
   `raptoreum-cli getnewaddress`

- An output similar to this `RJctR4QUAeFsgNpQN45mmF4tgrYrVE2jkH` will appear.

- You can create as many recieving addresses as you want.

- To assign a label to your receiving address: `raptoreum-cli setaccount "wallet address" "label"`

   - `wallet address` is the address you created and `label` is what you want to call your wallet for example "Mining Wallet".

- To check to make sure you `label` matches your address
   
   `raptoreum-cli getaddressesbyaccount "label"`

[![WALLET ADDRESS](https://img.youtube.com/vi/o2Q8z7R6zic/1.jpg)](https://youtu.be/o2Q8z7R6zic)

## 3. Encrypting Your Wallet

Always encrypt your wallet and **DO NOT LOSE YOUR PASSWORD**.  Keep your information safe and secure.
   
`raptoreum-cli encryptwallet "password"`
   
   - `password` is a strong password consitating of numbers, upper and lower case characters and special characters such as: ! @ # $ % ^ & *

[![ENCRYPT](https://img.youtube.com/vi/UnfxYByIBYM/1.jpg)](https://youtu.be/UnfxYByIBYM)

- After you have encrypted your wallet, restart your Raptoreum Core server.
   
## 4. Change Your Encryption Password

- To change your password:
 
   `raptoreum-cli walletpassphrasechange "oldpassword" "newpassword"`
   
- `oldpassword` is your current password and `newpassword` is your new password.

[![CHANGE PASSWORD](https://img.youtube.com/vi/pJcxfFpjng0/1.jpg)](https://youtu.be/pJcxfFpjng0)

## 5. How To Lock and Unlocked an Encrypted Wallet

- To unlock your newly encrypteds wallet:

   `raptoreum-cli walletpassphrase "password" time`
   
   - `time` is the amount of time you want your encrypted wallet to remain unlocked in **seconds**.  During this time can complete any other commands.

[![UNLOCK](https://img.youtube.com/vi/O51mV53xiQg/1.jpg)](https://youtu.be/O51mV53xiQg)

- To lock your wallet:

   `raptoreum-cli walletlock`
   
[![LOCK](https://img.youtube.com/vi/tWx_JWQzs8w/1.jpg)](https://youtu.be/tWx_JWQzs8w)

## 6. Sending a Transaction

- To send RTM from your wallet to an address:

   `raptoreum-cli sendtoaddress "ADDRESS" AMOUNT`
   
   - `ADDRESS` is the recepient recieve address.

   - `AMOUNT` is how much RTM you want to send to that address.

[![SEND TRANSACTION](https://img.youtube.com/vi/y1ijum8_nXs/1.jpg)](https://youtu.be/y1ijum8_nXs)
   
## 7. Sending and Signing a Raw Transaction

Lorem Ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

<!-- add image here-->

## 8. Resending a Stuck Transaction

Lorem Ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

<!-- add image here-->

## 9. Broadcast or Rebroadcast a Transaction
- To rebroadcast an unconfirmed transaction:

   `raptoreum-cli resendwallettransactions`
  
  - This is generally not needed because the wallet periodically rebroadcasts automatically.

[![BROADCAST TRANSACTION](https://img.youtube.com/vi/1FrNYaK6hv4/1.jpg)](https://youtu.be/1FrNYaK6hv4)
