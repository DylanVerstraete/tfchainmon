# TFchain monitoring tool

## Installation

Installing rust:

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

## Config file

Config file be formatted like the following:

```yaml
- network:
  network_url: "wss://tfchain.dev.grid.tf:433"
  accounts:
    - name: Activation Service
      address: 5GNNdXSQJC5LxKv1s2zvhCwyWyCg1msGPanHCsSNbWyu2Z2n
    - name: Bridge
      address: 5Dfiaccytu741LE8KxqegrBeVKgmCKRHU7KEuamf3igxgGW9
    - name: Offchain worker
      address: 5GRiEUaZZxuS7J1VbCvmz9LRdgyMJR9mxPE9JzCZu45JyXTx
- network:
  network_url: "wss://tfchain.grid.tf:433"
  accounts:
    - name: Activation Service
      address: 5GNNdXSQJC5LxKv1s2zvhCwyWyCg1msGPanHCsSNbWyu2Z2n
```

Note: url should have a port, in case of `wss` it's 443 otherwise it could be `9944` or `80` depending on the settings of the websocket endpoint.

## Setting up a bot

Talk to `botfather` on telegram to create a new bot, once created you will get a `token`, save this for later.
Now add this bot to a group on telegram, now get the chat id for this group:

Go to: https://api.telegram.org/bot<BOT_TOKEN>/getUpdates

and find the corresponding chat group and extract the ID.

## Running

Default TFT Treshold is set to 10 TFT.

```
export TELEGRAM_BOT_TOKEN=token
export TELEGRAM_CHAT_ID=-1231231
export TFT_THRESHOLD=100
cargo run ./config.yaml
```