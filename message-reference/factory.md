---
description: >-
  This contract registers the relation between your token and others.It uses the
  pre-stored pair contract binary and instantiate it. So, you don’t have to
  execute pair contract additionally.
---

# Factory

### Transaction <a href="#transaction" id="transaction"></a>

#### Create pair <a href="#create-pair" id="create-pair"></a>

Instantiate pair from uploaded WASM binary. Please check [this document](https://app.gitbook.com/@usama-zeeyou/s/loop/\~/drafts/-MiV9TLqqmMLvhM7R-9J/how-to/creat-your-own-pair) in detail usage.

```
{
  "pair_code_id": "1",
  "token_code_id": "2",
  "init_hook": {
    "msg": "<base64_encoded_json_string>",
    "contract_addr": "<HumanAddr>"
  }
}
```

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



[Here](https://fcd.terra.dev/wasm/contracts/terra16hdjuvghcumu6prg22cdjl96ptuay6r0hc6yns/store?query\_msg={%22pairs%22:{}}) are first 30 pairs&#x20;

[Here](https://fcd.terra.dev/wasm/contracts/terra16hdjuvghcumu6prg22cdjl96ptuay6r0hc6yns/store?query\_msg={%22pairs%22:{%22start\_after%22:\[{%22token%22:{%22contract\_addr%22:%22terra14tl83xcwqjy0ken9peu4pjjuu755lrry2uy25r%22}},{%22native\_token%22:{%22denom%22:%22uluna%22}}]}}) are the pairs from 31 - 60 &#x20;
