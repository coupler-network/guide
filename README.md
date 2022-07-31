# coupler.network Beta Usage Guide

[coupler.network](https://coupler.network) provides a REST API that lets users
integrate with the Lightning Network without having to worry about liquidity
management. You use a BTC transaction to deposit money into the service, and
call an HTTP endpoint to call invoices. Whenever you wish to, you can withdraw
the BTC funds from the service back into your wallet.

## Workflow

For experimenting with the API, use [swagger](https://api.coupler.network/v0/swagger).
Before using the API on mainnet, feel free to experiment on [testnet](https://testnet.coupler.network).

1. Generate a token using your [dashboard](https://coupler.network/dashboard).
2. Generate a deposit address using the `POST /deposits/addresses` endpoint.
3. Using your wallet, broadcast a BTC transaction to that address.
After the transaction is confirmed, the balance will show up on your dashboard.
4. Using your balance on coupler.network, you can now create and pay
BTC invoices.
    - To create a new invoice, use the `POST /invoices` endpoint.
    - To pay an existing invoice, use the `POST /payments` endpoint.
5. Whenever you wish, withdraw your balance back into your wallet using the
`POST /withdrawals` endpoint.

While you don't need to worry about liquidity management, there are API
limits. There are upper limits to the amounts you can send or receive at once,
as well as on a daily basis. You can see these on your dashboard. There are
also some API limits on querying data, but if you're using the API in an
ethical way, you should never run into these.

If you have any questions, please [open an ticket](https://github.com/coupler-network/guide/issues/new)
in this repository and we'll try to get back to you as soon as we can.
