---
description: >-
  This contract registers the relation between your token and others.It uses the
  pre-stored pair contract binary and instantiate it. So, you don’t have to
  execute pair contract additionally.
---

# Factory

### Query <a href="#query" id="query"></a>

#### Config <a href="#config" id="config"></a>

```
{
    "config": {}
}
```

#### Pair <a href="#pair" id="pair"></a>

```
{
    "pair": {
        "asset_infos": [
            {
                "token": {
                    "contract_addr": "<HumanAddr>"
                }
            },
            {
                "native_token": {
                    "denom": "uluna"
                }
            }
        ]
    }
}
```

#### Pairs <a href="#pairs" id="pairs"></a>

```
{
    "pairs": {
        "start_after": [ //optional
            {
                "token": {
                    "contract_addr": "<HumanAddr>"
                }
            },
            {
                "native_token": {
                    "denom": "uluna"
                }
            }
        ],
        "limit": 10 //optional, default=10, max=30
    }
}
```

[Here](https://fcd.terra.dev/wasm/contracts/terra16hdjuvghcumu6prg22cdjl96ptuay6r0hc6yns/store?query\_msg=%7B%22pairs%22:%7B%22limit%22:30%7D%7D) are first 30 pairs

[Here](https://fcd.terra.dev/wasm/contracts/terra16hdjuvghcumu6prg22cdjl96ptuay6r0hc6yns/store?query\_msg=%7B%22pairs%22:%7B%22start\_after%22:\[%7B%22token%22:%7B%22contract\_addr%22:%22terra1mj4rkdr2l5cvse8089z45mlp5dxx0hrjy5ts94%22%7D%7D,%7B%22native\_token%22:%7B%22denom%22:%22uusd%22%7D%7D],%22limit%22:30%7D%7D) are the pairs from 31 - 60
