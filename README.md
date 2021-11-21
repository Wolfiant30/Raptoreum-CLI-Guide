# Raptoreum CLI Guide

A basic guide to common usage for the CLI interface in the Raptoreum wallet.

The goal of this guide is show common commands with examples of managing your Raptoreum Core wallet in the command line interface.

## 1. Setup & Blockchain Sync

   1. Download the latest version of the wallet for your OS from:

      - https://github.com/Raptor3um/raptoreum/releases/latest
    
   2. Unpack the wallet from the achrive into any directory.

      - It is **highly** suggested, but no needed, to download the [bootstrap.zip](https://github.com/Raptor3um/raptoreum/releases/latest) located with the latest release download and extract it in your Raptoreum Core fold.

   3. Start the Raptoreum server:
      
      `raptoreumd -server`

[![SETUP](https://img.youtube.com/vi/DYYMSNIcO20/1.jpg)](https://youtu.be/DYYMSNIcO20)

   4. Wait for the server to complete syncronization.  
      **NOTE** This can take a while depending on how out of date the server is.

   - Check the status of the sync:
      
      `raptoreum-cli getblockchaininfo`

      - When the `"blocks"` height is close to the current height of the [blockchain](https://explorer.raptoreum.com/) and `"verificationprogress"` is to close `1`, your wallet is in sync.

[![BLOCKCHAIN SYNC](https://img.youtube.com/vi/hq49iBWM48I/1.jpg)](https://youtu.be/hq49iBWM48I)

## 2. Prepairing Wallet

- To create a receiving address: 
   
   `raptoreum-cli getnewaddress`

- An output similar to this `RJctR4QUAeFsgNpQN45mmF4tgrYrVE2jkH` will appear.

**NOTE** You can create as many recieving addresses as needed.

- To assign a label to the receiving address: 

   `raptoreum-cli setaccount "recieve address" "label"`

   - `recieve address` is the address that was created and `label` is what you want to call your `recieve address` for example "Mining Wallet".

- To check that the `label` matches the `recieve address`:
   
   `raptoreum-cli getaddressesbyaccount "label"`

[![WALLET ADDRESS](https://img.youtube.com/vi/o2Q8z7R6zic/1.jpg)](https://youtu.be/o2Q8z7R6zic)

## 3. Encrypting Wallet

Always encrypt your wallet and **DO NOT LOSE OR SHARE YOUR PASSWORD**.  Keep your information safe and secure.
   
`raptoreum-cli encryptwallet "password"`
   
   - `password` is a strong password consitating of numbers, upper and lower case characters and special characters such as: ! @ # $ % ^ & *

[![ENCRYPT](https://img.youtube.com/vi/UnfxYByIBYM/1.jpg)](https://youtu.be/UnfxYByIBYM)

- After you have encrypted your wallet, restart the Raptoreum server.
   
## 4. Change Encryption Password

- To change the encryption password:
 
   `raptoreum-cli walletpassphrasechange "current password" "new password"`
   
- `current password` is the current password and `new password` is the new password.

[![CHANGE PASSWORD](https://img.youtube.com/vi/pJcxfFpjng0/1.jpg)](https://youtu.be/pJcxfFpjng0)

## 5. How To Unlock and Lock an Encrypted Wallet

- To unlock the encrypted wallet:

   `raptoreum-cli walletpassphrase "password" time`
   
   - `time` is the amount of time the encrypted wallet is to remain unlocked in *seconds*.  During this time, operations can be completed.

[![UNLOCK](https://img.youtube.com/vi/O51mV53xiQg/1.jpg)](https://youtu.be/O51mV53xiQg)

- To lock the wallet:

   `raptoreum-cli walletlock`
   
[![LOCK](https://img.youtube.com/vi/tWx_JWQzs8w/1.jpg)](https://youtu.be/tWx_JWQzs8w)

## 6. Sending a Transaction

- To send RTM to an address:

   `raptoreum-cli sendtoaddress "ADDRESS" AMOUNT`
   
   - `ADDRESS` is the recepient recieve address.

   - `AMOUNT` is how much RTM that will be sent.

[![SEND TRANSACTION](https://img.youtube.com/vi/y1ijum8_nXs/1.jpg)](https://youtu.be/y1ijum8_nXs)
   
## 7. Broadcast or Rebroadcast a Transaction

- To rebroadcast an unconfirmed transaction:

   `raptoreum-cli resendwallettransactions`
  
  - This is generally not needed because the wallet periodically rebroadcasts automatically.

[![BROADCAST TRANSACTION](https://img.youtube.com/vi/1FrNYaK6hv4/1.jpg)](https://youtu.be/1FrNYaK6hv4)

## 8. Backup Wallet

- Make sure to backup your wallet periodically:

   `raptoreum-cli backupwallet "destination"`
   
   - `destination` is the directory you want your wallet backedup or you can leave it blank and the backup will be saved in the Raptoreum Core folder under "backups"

[![BROADCAST TRANSACTION](https://img.youtube.com/vi/7SeiSzl2aRk/1.jpg)](https://youtu.be/7SeiSzl2aRk)

## 9. Addition Help

- Any additional commands or explinations for commands can be found with the `help`
   
   `raptoreum-cli help`
   
   -  This will list all all available commands with options.

   `raptoreum-cli help "command"'
   
   - `command` is the command you are looking for more information.
