# CW20 Token

### Transaction <a href="#transaction" id="transaction"></a>

#### Transfer <a href="#transfer" id="transfer"></a>

Transfer token from the sender user to the recipient.

```
{
    "transfer": {
        "recipient": "<HumanAddr>",
        "amount": 123123,
    }
}
```

#### Burn <a href="#burn" id="burn"></a>

Burn tokens from total supply.

```
{
    "burn": {
        "amount": 123123
    }
}
```

#### &#x20;Send <a href="#send" id="send"></a>

Work same as transfer but it sends token to contract, not user address.\
&#x20;And, it triggers given message in `msg`. The given message should be executable on recipient contract.

`msg` is base64-endcoded JSON string.

```
{
    "send": {
        "contract": "<HumanAddr>",
        "amount": 123123,
        "msg": "1234erwfaffaesfaef="
    }
}
```

#### Mint <a href="#mint" id="mint"></a>

It produces token and transfer to given recipient.

```
{
    "mint": {
        "recipient": "<HumanAddr>",
        "amount": 123123
    }
}
```

#### Increase/Decrease allowance <a href="#increasedecrease-allowance" id="increasedecrease-allowance"></a>

It increases / decreases allowance of withdrawable token from the executor.\
&#x20;After execution, user token can be transferred by spender’s contract method execution, not only `transfer`.

And it expires on the given time point.

```
{
    "increase_allowance": {
        "spender": "<HumanAddr>",
        "amount": 123123,
        "expires": {
            "at_height": 123123,
            // or
            "at_time": 123123,
            // or
            "never": {}
        }
    }
}
```

```
{
    "decrease_allowance": {
        "spender": "<HumanAddr>",
        "amount": 123123,
        "expires": {
            "at_height": 123123,
            // or
            "at_time": 123123,
            // or
            "never": {}
        }
    }
}
```

#### Transfer from / send from <a href="#transfer-from--send-from" id="transfer-from--send-from"></a>

It transfers token from owner to recipient, which not owner nor recipeint are not the contract executor. Before execution, the allowance should be increased.

```
{
    "transfer_from": {
        "owner": "<HumanAddr>",
        "recipient": "<HumanAddr>",
        "amount": 123123,
    }
}
```

```
{
    "send_from": {
        "owner": "<HumanAddr>",
        "recipient": "<HumanAddr>",
        "amount": 123123,
        "msg": "<base64_encoded_json_message>"
    }
}

```

#### &#x20;Burn from <a href="#burn-from" id="burn-from"></a>

Burns token from token supply, whose owner is not same as the contract executor.

```
{
    "burn_from": {
        "owner": "<HumanAddr>",
        "amount": 123123
    }
}
```

### Query <a href="#query" id="query"></a>

#### Get balance <a href="#get-balance" id="get-balance"></a>

Check the balance of the given address

```
{
    "balance": {
        "address": "<HumanAddr>"
    }
}
```

#### &#x20;Token info <a href="#token-info" id="token-info"></a>

Check metadata of the contract.

&#x20;It check:

* Name
* Decimals
* Total supply
* Other useful information

```
{
    "token_info": {}
}
```

#### Get minter <a href="#get-minter" id="get-minter"></a>

```
{
    "minter": {}
}
```

#### Get allowance <a href="#get-allowance" id="get-allowance"></a>

Get allowance list of the given owner & spender.

```
{
    "allowance": {
        "owner": "<HumanAddr>",
        "spender": "<HumanAddr>"
    }
}
```

#### Get all allowance <a href="#get-all-allowance" id="get-all-allowance"></a>

Get list of all allowance of the token.

```
{
    "all_allowances": {
        "owner": "<HumanAddr>",
        "start_after": "<HumanAddr>", // optional
        "limit": 1 // optional
    }
}
```

#### &#x20;Accounts list that have the token <a href="#accounts-list-that-have-the-token" id="accounts-list-that-have-the-token"></a>

Get all accounts list of the token holder.

```
{
    "all_accounts": {
        "start_after": "<HumanAddr>", // optional
        "limit": 1 // optional
    }
}
```
