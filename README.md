# Kurulum
```
wget -q -O stride.sh https://api.rues.info/stride.sh && chmod +x stride.sh && sudo /bin/bash stride.sh
```
Kaynak: https://api.rues.info/

# Cüzdan Oluşturma
```
strided keys add CUZDANADI
```
Not: Mnemonic'i kaydedin.

# Test Tokeni Alma: https://discord.gg/98jCNJRP6S
discord-->stride-->poolparty-testnet-->token-faucet

# Sync Kontrol Etme
```
strided status 2>&1 | jq .SyncInfo
```
NOT: Validator oluşturmadan önce çıktının true yerine false olmasına dikkat edin.

# Validator Oluşturma
```
strided tx staking create-validator \
--amount=9900000ustrd \
--pubkey=$(strided tendermint show-validator) \
--moniker=VALIDATORISMI \
--chain-id=STRIDE-1 \
--commission-rate="0.10" \
--commission-max-rate="0.20" \
--commission-max-change-rate="0.1" \
--min-self-delegation="1" \
--fees=250ustrd \
--gas=200000 \
--from=CUZDANADI \
--website="" \
--details="KENDINIZITANITIN" \
-y
```

# Ek Komutlar
Logları Görüntüleme
```
journalctl -fu strided -o cat
```
Jailden Çıkma
```
strided tx slashing unjail --from=CUZDANADI --chain-id=STRIDE-1 --gas-prices=0.025ustrd -y
```
Cüzdanı Recover Etme
```
strided keys add CUZDANADI --recover
```
Cüzdan Listesi
```
strided keys list
```
# Stride Explorer: https://stride.explorers.guru/
