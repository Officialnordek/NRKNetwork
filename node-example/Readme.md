# Run a NRK Validator
## Setting up a node
1. Git clone https://github.com/Officialnordek/NRKNetwork.git

2. Copy source form node-example to root folder
```
cp -r NRKNetwork/node-example/NRK  /root/
```
3. Create an Account

```
cd /root/NRK
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake NRK coin, all you should do is sending your NRK coin to the NRK Consensus contract address over the NRK network from the validator address.
    The NRK Consensus contract address: 0x8db1436097E3d16DD366c138F6953Fb7ee9a96Ad
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to NRK and send the NRK coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /NRK/nodes/validator/keys/NRK/UTC--xxxx
    /NRK/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
