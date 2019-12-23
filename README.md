_**Kībōruto = "Key Vault" in Japanese**_

# Goal

Create a GPHWW(General Purpose Hardware Wallet) that is private, secure, incognito & portable. All while implementing Open Source Software

_End goal is to have an IMG that can be etched to a drive with all the necessary tools already on it_

## Implementation

You can install Samourai Wallet on an Android device that will always be offline to create a cold storage and still use the outside tools to watch/depost/withdraw. _The Samourai team is working on better solutions to offline storage via the app :)_

OR

A [TAILS](https://tails.boum.org/index.en.html) USB(s) with a suite of tools allowing you to interact with the Bitcoin blockchain. All while stressing privacy #1!

**Please read this to understand the security limitations of TAILS:**

Tails runs independently from the operating system installed on the computer. So, if the computer has only been compromised by software, running from inside your regular operating system (virus, trojan, etc.), then it is safe to use Tails. This is true as long as Tails itself has been installed using a **trusted** system.

If the computer has been compromised by someone having physical access to it and who installed untrusted pieces of hardware, then it might be unsafe to use Tails.

If the BIOS of the computer has been compromised, then it might also be unsafe to use Tails.

[TAILS Warnings](https://tails.boum.org/doc/about/warning/index.en.html)

**Hardware**

- Secure Desktop/Laptop
- 8GB+ USB Stick(s) 
- 4-5 Dice

**Setup**

- Download [TAILS OS](https://tails.boum.org/install/download/index.en.html)

- Flash to USB using [balenaEtcher](https://www.balena.io/etcher/)

- Initialize 

_When initializing the setup you must create a persistant encrypted volume. This will encrypt everything with LUKS_

Be sure to update, in Terminal: `sudo apt update` then `sudo apt dist-upgrade`

A great writeup on setting up TAILS w/cold storage:
[SovereignNode TAILS Guide](https://github.com/SovereignNode/tails-cold-storage/blob/master/tails-persistence.md)

Once you've initialized and setup one USB stick you can use this guide to create a duplicate
[Backup](https://tails.boum.org/doc/first_steps/persistence/copy/index.en.html)

## Tools

- [**Electrum**](https://github.com/spesmilo/electrum)

Backed by your own server, such as [electrs](https://github.com/romanz/electrs) via [RoninDojo](https://github.com/RoninDojo/RoninDojo) 

- [**Samourai Wallet**](https://github.com/Samourai-Wallet/samourai-wallet-android)

Using [Android Studio](https://developer.android.com/studio/) to emulate

- [**Whirlpool GUI**](https://github.com/Samourai-Wallet/Whirlpool) 

For private mixing. Perfeably backed by [Whirlpool CLI](https://github.com/Samourai-Wallet/whirlpool-gui), can be utalized via [RoninDojo](https://github.com/RoninDojo/RoninDojo) 

- [**Ian Coleman BIP39 Tool**](https://github.com/iancoleman/BIP39) 

Can be used to generate seeds offline

- [**EFF Random Passphrases**](https://www.eff.org/deeplinks/2016/07/new-wordlists-random-passphrases) 

Used to generate random passphrases

## Interacting w/Cold Storage

### Watching/Deposits

Tracking the PUB keys of your TAILS wallet(s) allows you to generate addresses to make deposits using these tools:

- [Sentinel](https://github.com/Samourai-Wallet/sentinel-android) 

- [Sentinel x](https://github.com/InvertedX/sentinelx)

### Whithdrawls

You **can** allow your TAILS to go online and send transactions that way. 

More securely you can broadcast the transaction separately. Using Samourai Wallet you can generate the hex of a transaction offline as a QR code. Scanning that QR with these tools will allow them to broadcast the transaction: 

- [Sentinel](https://github.com/Samourai-Wallet/sentinel-android) 

- [txTenna](https://github.com/MuleTools/txTenna)

_UTXOs will be **stale** and not updated on the offline wallet_

## Implementations of Backups

**Always keep a physical backup!!**

- Titanium/Stainless Steel plates **stamped!** Must be placed in **secure** location! 

A great option is [Coldbit](https://coldbit.com/) 

- Encrypted backup(s)

**Use strong passwords!!**

Such as is generated by Samourai Wallet. Using a storage medium of your choice

- TAILS OS on USB(s)

For greater protection and tamper evident. These USB(s) can be sealed in a vacuum bag, signed by yourself then placed in a fariday/fireproof bag in a secure location
