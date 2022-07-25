# StrideTestnetTurkish

![image](https://www.hizliresim.com/aihfkug)
# Kurulum:

```
wget -q -O stride.sh https://api.rues.info/stride.sh && chmod +x stride.sh && sudo /bin/bash stride.sh
```

# Cüzdan oluşturma:
```
strided keys add CUZDANADI
```

# Discordan test tokeni alma: https://discord.gg/4B4cbvCh

# Validator oluşturma:
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
--website="www.WEBSITENIZ.com" \
--details="KENDINIZITANITIN" \
-y
```

# Explorer kontrol: https://stride.explorers.guru/validator/stridevaloper1vm6wnmvxugqj8k6s6d2cktgctc550qaq53jyus

# Discorddan role-requestten rol de alabılırsınız.
