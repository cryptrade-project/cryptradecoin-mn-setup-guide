CrypradeCoin(CRCO) Masternode  Setup Guide
=========================================

## Contents
- [About CRCO](#about-crco)
- [Introduction](#introduction)
- [Install Masternode on VPS](#install-masternode-on-vps)
- [Configuration of your local wallet](#configuration-of-your-local-wallet)
- [MN Collateral](#mn-collateral)

***

## About CRCO

![CryptradeCoin Banner](https://i.imgur.com/oM1aPBg.png)

Cryptrade is a decentralized cryptocurrency trading platform built on top of bitshares 2.0 which aims to provide traders with a secure and easy way to buy and sell cryptocurrencies and tokens online instantly.

CryptradeCoin(CRCO) is a private and anonymous cryptocurrency which is officially issued by Cryptrade. CRCO uses hybrid PoS+Masternode consensus to secure its blockchain and provides coin holders with full-time private and instant transactions by implementing swiftx and zerocoin protocol. Paying for the listing fees and trading fees in Cryptrade is the main use-case of CRCO coin.

***

## Introduction

This guide is for a single masternode, on a Ubuntu 14.04, 16.04 or 18.04 64bit server (VPS) running headless and will be controlled from the wallet on your **local computer (Control wallet or Local Wallet)**. The wallet on the the VPS will be referred to as the **Remote wallet**.

**Basic Requirements:**

1.  1,000 CRCO ( The collateral amount of CryptradeCoin is gradually increasing, learn more about this: [MN Collateral](#mn-collateral))
2.  A main computer (Your everyday computer) – This will run the control wallet, hold your collateral CRCOs and can be turned on and off without affecting the masternode.
3.  Masternode Server (VPS – The computer that will be on 24/7. We recommend [Vultr](https://www.vultr.com/?ref=7594415), [DigitalOcean](https://www.digitalocean.com/), [Linode](https://www.linode.com/?r=a21c6a221bdfbad108535fcd4a4898a732481648), [AWS](https://aws.amazon.com/) )
4.  A unique IP address for your VPS / Remote wallet

(For security reasons, you’re are going to need a different IP for each masternode you plan to host)

The basic reasoning for these requirements is that you get to keep your CRCO in your local wallet and host your masternode remotely, securely.

***

## Install Masternode on VPS

Login your VPS, and then copy/paste the following commands one by one with `Enter`. Our automatic masternode install script will help you install the masternode on your VPS. But plase make sure that your vps is running Ubuntu 14.04, 16.04 or 18.04 before you execute the following commands.

```shell
wget -q https://raw.githubusercontent.com/cryptrade-project/cryptradecoin-mn-install-script/master/install.sh
chmod u+x install.sh
./install.sh
```

***

## Configuration of Your Local Wallet

After the masternode is up and running on your vps, you need to configure your local wallet/control wallet. Below is the steps:

1. Open the CryptradeCoin Wallet on your local computer.
2. Go to `RECEIVE` tab and create a new address with a specific label, for example: **MN1**
3. Send 1000 CRCO to the address you just created in Step 2.
4. Wait for at least 15 confirmations.
5. Open `Tools` -> `Debug console - Console`.
6. Type the following command: `masternode outputs`.
7. Open `Tools` -> `Open Masternode Configuration File`. ***Add the following entry:***

```shell
Alias Address Privkey TxHash Output_index
```

```shell
Alias: The label you set in Step 2.
Address: VPS_IP:PORT  # the default port is 15600
Privkey: Masternode Private Key # Our automatic masternode install script will show you the masternode private key when finish the installation on the vps.
TxHash: First value from Step 6
Output index: Second value from Step 6
```
8. Save and close the file.
9. Go to `Masternode` Tab. ( ***If you tab is not shown, please enable it from: `Settings` -> `Options` -> `Wallet` -> `Show Masternodes Tab`*** )
10. Click `Update status` button to see your masternode. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
11. Choose the masternode you just created and click `Start alias` button.

***

## MN Collateral
<table>
<tr><th>Block Height</th><th>MN Collateral</th></tr>
<tr><td>1-450,000</td><td>1,000 CRCO</td></tr>
<tr><td>450,001-90,000</td><td>2,000 CRCO</td></tr>
<tr><td>90,001-135,000</td><td>4,000 CRCO</td></tr>
<tr><td>135,001-270,000</td><td>6,000 CRCO</td></tr>
<tr><td>270,001-540,000</td><td>8,000 CRCO</td></tr>
<tr><td>>=540,001</td><td>10,000 CRCO</td></tr>
</table>

***
