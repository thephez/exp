---
title: "Abandon Transaction"
excerpt: ""
category: "5be0bb0ab9b7dd006229a78a"
---

[block:callout]
{
  "type": "warning",
  "body": "Callout.",
  "title": "Example"
}
[/block]

## AbandonTransaction

*Added in Bitcoin Core 0.12.0*

The `abandontransaction` RPC marks an in-wallet transaction and all its in-wallet descendants as abandoned. This allows their inputs to be respent.

*Parameter #1---a transaction identifier (TXID)*

| Name | Type | Presence | Description |
| - | - | - |
| TXID | string (hex) | Required (exactly 1) | The TXID of the transaction that you want to abandon.  The TXID must be encoded as hex in RPC byte order

*Result---`null` on success*

| Name | Type | Presence | Description |
| - | - | - |
| `result` | null | Required (exactly 1) | JSON `null` when the transaction and all descendants were abandoned

*Example from Dash Core 0.12.2*

Abandons the transaction on your node.

[block:code]
{
  "codes": [
    {
      "code": "dash-cli abandontransaction \n fa3970c341c9f5de6ab13f128cbfec58d732e736a505fe32137ad551c799ecc4",
      "language": "text",
      "name": "RPC"
    },
    {
      "code": "dash-cli abandontransaction \n fa3970c341c9f5de6ab13f128cbfec58d732e736a505fe32137ad551c799ecc4",
      "language": "text"
    }
  ]
}
[/block]

```
dash-cli abandontransaction \
 fa3970c341c9f5de6ab13f128cbfec58d732e736a505fe32137ad551c799ecc4
```

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

```python
import requests

url = "https://dash.readme.io/api/v1/docs"

payload = "{\"title\":\"test0002\",\"type\":\"basic\",\"body\":\" test\",\"category\":\"documentation\"}"
headers = {
    'x-readme-version': "1",
    'content-type': "application/json",
    'authorization': "Basic abcd"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

Result (no output from `dash-cli` because result is set to `null`).

*See also*

* [SendRawTransaction][rpc sendrawtransaction]: {{summary_sendRawTransaction}}



[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Type",
    "h-2": "Presence",
    "h-3": "Description",
    "0-1": "string (hex)",
    "0-0": "TXID",
    "0-2": "Required (exactly 1)",
    "0-3": "The TXID of the transaction that you want to abandon.  The TXID must be encoded as hex in RPC byte order"
  },
  "cols": 4,
  "rows": 1
}
[/block]
