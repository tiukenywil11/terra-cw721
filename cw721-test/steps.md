1.

```bash 
terrad tx wasm store artifacts/cw721_test.wasm --from kenny --chain-id=localterra --gas=auto --fees=100000uluna --broadcast-mode=block
```

2. code_id = 4
   code_id = 3 for localterra

3. instantiate 

```bash
{
	"name": "Kenny_NFT",
	"symbol": "KENNY",
	"minter": "terra13885pj0s4sgv0dcpk6r2ftph750h8jlt88m0ej"
}
```
```bash
terrad tx wasm instantiate 4 '{"name":"Kenny_NFT","symbol":"KENNY","minter":"terra13885pj0s4sgv0dcpk6r2ftph750h8jlt88m0ej"}' --from kenny --chain-id=localterra --fees=10000uluna --gas=auto --broadcast-mode=block
```
3.1 Using locaterra account

```bash
{
	"name": "Kenny_NFT",
	"symbol": "KENNY",
	"minter": "terra1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8"
}
```
```bash
terrad tx wasm instantiate 3 '{"name":"Kenny_NFT","symbol":"KENNY","minter":"terra1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8"}' --from test1 --chain-id=localterra --fees=10000uluna --gas=auto --broadcast-mode=block
```


4. attributes
```bash
  - attributes:
    - key: creator
      value: terra1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8
    - key: admin
      value: ""
    - key: code_id
      value: "4"
    - key: contract_address
      value: terra13nkgqrfymug724h8pprpexqj9h629sa3ncw7sh
```

4.1
```bash
  - attributes:
    - key: creator
      value: terra1dcegyrekltswvyy0xy69ydgxn9x8x32zdtapd8
    - key: admin
      value: ""
    - key: code_id
      value: "3"
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
		"owner": "terra13885pj0s4sgv0dcpk6r2ftph750h8jlt88m0ej",
		"token_uri": null,
		"extension": null
	}
}
```

```bash
terrad tx wasm execute terra13nkgqrfymug724h8pprpexqj9h629sa3ncw7sh '{"mint":{"token_id":"Sword","owner":"terra13885pj0s4sgv0dcpk6r2ftph750h8jlt88m0ej","token_uri":null,"extension":null}}' --from kenny --chain-id=localterra --fees=1000000uluna --gas=auto --broadcast-mode=block
```

5.1
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