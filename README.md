![FYM05YzWAAA_7Sh](https://user-images.githubusercontent.com/91866065/181212921-f977d005-1800-4531-a17f-9a2052d0b729.jpg)
# Installation
```
wget -q -O stride.sh https://api.rues.info/stride.sh && chmod +x stride.sh && sudo /bin/bash stride.sh
```
![whitenigga2](https://user-images.githubusercontent.com/91866065/181213969-c5edace4-a264-48b8-a0ee-6e30750eb043.png)

Source: https://api.rues.info/

# Create Wallet
```
strided keys add WALLETNAME
```
* Save the Mnemonic

# Token Faucet: https://discord.gg/98jCNJRP6S
* Discord-->Stride-->Poolparty-testnet-->Token-faucet

# Sync
```
strided status 2>&1 | jq .SyncInfo
```
![github](https://user-images.githubusercontent.com/91866065/181214050-5667ff79-7227-41fd-b80a-cd1114f9b98a.png)
* "catching_up" must be false for creating validator

# Creating Validator
```
strided tx staking create-validator \
--amount=9900000ustrd \
--pubkey=$(strided tendermint show-validator) \
--moniker=MONIKERNAME \
--chain-id=STRIDE-TESTNET-2 \
--commission-rate="0.10" \
--commission-max-rate="0.20" \
--commission-max-change-rate="0.1" \
--min-self-delegation="1" \
--fees=250ustrd \
--gas=200000 \
--from=WALLETNAME \
--website="https://github.com/mulosbron" \
--details="" \
-y
```

# Commands
Logs
```
journalctl -fu strided -o cat
```
Unjail
```
strided tx slashing unjail --from=WALLETNAME --chain-id=STRIDE-TESTNET-2 --gas-prices=0.025ustrd -y
```
Recover Wallet
```
strided keys add WALLETNAME --recover
```
Wallet List
```
strided keys list
```
# Stride Explorer: https://stride.explorers.guru
