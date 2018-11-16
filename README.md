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

This guide is for a single masternode, on a Ubuntu 14.04, 16.04 or 18.04 64bit server (VPS) running headless and will be controlled from the wallet on your **local computer (Control wallet)**. The wallet on the the VPS will be referred to as the **Remote wallet**.

**Basic Requirements:**

1.  1,000 CRCO ( The collateral amount of CryptradeCoin is gradually increasing, learn more about this: [MN Collateral](#mn-collateral))
2.  A main computer (Your everyday computer) – This will run the control wallet, hold your collateral CRCOs and can be turned on and off without affecting the masternode.
3.  Masternode Server (VPS – The computer that will be on 24/7. We recommend [Vultr](https://www.vultr.com/?ref=7594415), [DigitalOcean](https://www.digitalocean.com/), [Linode](https://www.linode.com/?r=a21c6a221bdfbad108535fcd4a4898a732481648), [AWS](https://aws.amazon.com/) )
4.  A unique IP address for your VPS / Remote wallet

(For security reasons, you’re are going to need a different IP for each masternode you plan to host)

The basic reasoning for these requirements is that you get to keep your CRCO in your local wallet and host your masternode remotely, securely.

## Install Masternode on VPS

Login your VPS, and then copy/paste the following commands one by one with `Enter`. Our automatic masternode install script will help you install the masternode on your VPS. But plase make sure that your vps is running Ubuntu 14.04, 16.04 or 18.04 before you execute the following commands.

```shell
wget -q https://raw.githubusercontent.com/cryptrade-project/cryptradecoin-mn-install-script/master/install.sh
chmod u+x install.sh
./install.sh
```

## Configuration of Your Local Wallet

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
