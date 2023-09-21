# Run a MBC Validator
## Setting up a node
1. Git clone https://github.com/navisharma007aus/validator-setup.git

2. Copy source form miner-setup to root folder
```
cp -r ValidatorSetup/miner-setup/MBC/root/
```
3. Create an Account

```
cd /root/MBC
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

    To stake MBC coin, all you should do is sending your MBC coin to the MBC Consensus contract address over the MBC network from the validator address.
    The MBC Consensus contract address: <MAINNET CONSENSUS ADDRESS>
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to MBC and send the MBC coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /MBC/nodes/validator/keys/MBC/UTC--xxxx
    /MBC/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
