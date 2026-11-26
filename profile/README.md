<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://deadhop.run/docs/mark-fog.svg">
  <img alt="deadhop mark: a dot, a dashed hop, and a box with a slot" src="https://deadhop.run/docs/mark.svg" width="88">
</picture>

# deadhop

**Dials out. Never listens.**

On-chain bitcoin payments from a service with no open port.

[Website](https://deadhop.run) · [Docs](https://deadhop.run/docs/) · [Try it on regtest](https://deadhop.run/docs/quickstart.html) · [Agent skills](https://deadhop.run/docs/skills.html)

</div>

deadhop runs next to your bitcoin node. It issues invoices, watches the chain and reports
payments, much as BTCPay Server does for simple invoicing. It never listens on a port:
customers and operators reach it only through Nostr relays, end-to-end encrypted, using
[ContextVM](https://contextvm.org) (MCP over Nostr). There is no IP address, HTTP endpoint or
login form to attack, and it holds only a watch-only key, so it cannot spend what it receives.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: light)" srcset="https://deadhop.run/shots/payments-overview-light.webp">
    <img alt="The operator Overview: privacy score 100, relays reached through a SOCKS5 proxy, the service running, and totals for payments, invoices and addresses" src="https://deadhop.run/shots/payments-overview.webp" width="70%">
  </picture>
  <img alt="A customer's invoice: 60,000 sats, a QR code, the address and Copy address" src="https://deadhop.run/shots/payments-checkout.webp" width="26%">
</p>
<p align="center"><sub>The operator's dashboard and a customer's invoice, on a test chain.</sub></p>

## Repositories

| | Repository | What it is |
| --- | --- | --- |
| **Run** | [stack](https://github.com/deadhop/stack) | Docker Compose for production, and the regtest stack for development. Start here. |
| | [server](https://github.com/deadhop/server) | The payment service, and the shared Rust crates |
| | [wallet](https://github.com/deadhop/wallet) | The optional sweeper: send, PayJoin or CoinJoin to your cold wallet |
| **Build** | [js](https://github.com/deadhop/js) | `@deadhop/client`, `react`, `solid`, `svelte`; the dashboard and the console |
| **Tools** | [lnaddr](https://github.com/deadhop/lnaddr) | A Lightning address for a node with no public address |
| | [relay](https://github.com/deadhop/relay) | A Nostr relay that carries one deadhop service's traffic and nothing else |
| **Docs** | [site](https://github.com/deadhop/site) | https://deadhop.run and every component's docs |
| | [brand](https://github.com/deadhop/brand) | Logo, icons, fonts and the brand guide |

## Get started

```sh
git clone https://github.com/deadhop/stack && cd stack
# write .env: your Electrum server, its certificate fingerprint, your Nostr key
docker compose up -d --build
```

[Your first real payment](https://deadhop.run/docs/first-payment.html) walks through it on your
own node. To add a pay button to an app:

```sh
npm install @deadhop/client @deadhop/react   # or @deadhop/solid, @deadhop/svelte
```

Working with a coding agent? Every repository ships skills for it:
`npx skills add deadhop/stack` ([all of them](https://deadhop.run/docs/skills.html)).

Everything is [MIT](https://github.com/deadhop/server/blob/main/LICENSE) licensed. Issues and
pull requests go to the repository the code lives in.
