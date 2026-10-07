# Connect a Wallet

Hest does not hold your keys. You connect a wallet, Hest asks for signatures, your funds stay in your control.

## Browser Wallets

Open [hest.si](https://hest.si) and click **Connect Wallet**. Every wallet extension installed in your browser is detected automatically and listed with its own icon and a `DETECTED` tag: MetaMask, Rabby, Phantom, Trust Wallet, Coinbase Wallet, Robinhood Wallet and any other EVM wallet.

1. Click the wallet you want to use.
2. Approve the connection in the wallet's own window.
3. Your address appears at the top right. Click it to see the full address, the network you are on, and a **Disconnect** button.

Switching accounts or networks inside the wallet updates Hest instantly.

## Mobile Wallets

* **Inside the wallet's browser**: open hest.si from the browser built into MetaMask, Trust or Rabby mobile. The wallet is detected like an extension.
* **Desktop site, phone wallet**: the **Mobile wallet (QR)** option in the connect dialog ships with the next build (WalletConnect).

## Email or Google Login

Coming with the next build. It creates a wallet for you behind the scenes so you can start without installing anything.

## Networks

Hest lives on **Robinhood Chain**, an Arbitrum Orbit chain, so any EVM wallet works. Deposits are in USDC. If your wallet is on another network when you deposit, Hest asks it to switch.

{% hint style="warning" %}
Hest will never ask for your seed phrase or private key, in the app, on Discord, on X or by email. Anyone asking for it is not Hest.
{% endhint %}
