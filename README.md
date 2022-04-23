# Steps to deploy to LocalTerra

1. Store smart contract to localterra

```bash 
terrad tx wasm store artifacts/cw721_test.wasm --from test1 --chain-id=localterra --gas=auto --fees=100000uluna --broadcast-mode=block
```
2. code_id = (n)  
note: n represents code_id generated upon storing 

3. instantiate 

```bash
{
	"name": "Kenny_NFT",
	"symbol": "KENNY",
	"minter": "terra1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8"
}
```
```bash
terrad tx wasm instantiate (n) '{"name":"Kenny_NFT","symbol":"KENNY","minter":"terra1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8"}' --from test1 --chain-id=localterra --fees=10000uluna --gas=auto --broadcast-mode=block
```


4. attributes

```bash
  - attributes:
    - key: creator
      value: terra1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8
    - key: admin
      value: ""
    - key: code_id
      value: "(n)"
    - key: contract_address
      value: terra1wgh6adn8geywx0v78zs9azrqtqdegufuegnwep
    type: instantiate_contract
```

5. minter
```bash
{
	"mint": 
	{
		"token_id": "Sword",
		"owner": "terra1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8",
		"token_uri": null,
		"extension": null
	}
}
```

```bash
terrad tx wasm execute terra1wgh6adn8geywx0v78zs9azrqtqdegufuegnwep '{"mint":{"token_id":"Sword","owner":"terra1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8","token_uri":null,"extension":null}}' --from test1 --chain-id=localterra --fees=1000000uluna --gas=auto --broadcast-mode=block
```

6. Contract and transactions can be found here:
- https://finder.terra.money/localterra/address/terra1wgh6adn8geywx0v78zs9azrqtqdegufuegnwep