# exp

Misc stuff

``` bash
#!/bin/bash

echo -e "Please enter your name: "
read name
echo "Nice to meet you $name"
```

```bash
#!/bin/bash

echo -e "Please enter your name: "
read name
echo "Nice to meet you $name"
```


```json
{
  "domain": {
    "indices": [
      {
        "properties": [
          {
            "nameHash": "asc"
          }
        ],
        "unique": true
      },
      {
        "properties": [
          {
            "normalizedParentDomainName": "asc"
          },
          {
            "normalizedLabel": "asc"
          }
        ]
      },
      {
        "properties": [
          {
            "records.dashUniqueIdentityId": "asc"
          }
        ],
        "unique": true
      }
    ],
    "properties": {
      "nameHash": {
        "type": "string",
        "minLength": 68,
        "maxLength": 68,
        "pattern": "^[A-Fa-f0-9]+$",
        "description": "Double sha-256 multihash of the full domain name in a form of a hex string"
      },
      "label": {
        "type": "string",
        "pattern": "^((?!-)[a-zA-Z0-9-]{0,62}[a-zA-Z0-9])$",
        "maxLength": 63,
        "description": "Domain label. e.g. 'Bob'"
      },
      "normalizedLabel": {
        "type": "string",
        "pattern": "^((?!-)[a-z0-9-]{0,62}[a-z0-9])$",
        "maxLength": 63,
        "description": "Domain label in a lower case. e.g. 'bob'"
      },
      "normalizedParentDomainName": {
        "type": "string",
        "minLength": 0,
        "maxLength": 190,
        "description": "A full parent domain name in lower case. e.g. 'dash'"
      },
      "preorderSalt": {
        "type": "string",
        "minLength": 25,
        "maxLength": 34,
        "pattern": "^[123456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnopqrstuvwxyz]+$",
        "description": "Domain pre-order salt. Currently randomly generated base58 address string."
      },
      "records": {
        "type": "object",
        "properties": {
          "dashUniqueIdentityId": {
            "type": "string",
            "minLength": 42,
            "maxLength": 44,
            "pattern": "^[123456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnopqrstuvwxyz]+$",
            "description": "base58 encoded Identity ID string should be used to create a primary name for Identity"
          },
          "dashAliasIdentityId": {
            "type": "string",
            "minLength": 42,
            "maxLength": 44,
            "pattern": "^[123456789ABCDEFGHJKLMNPQRSTUVWXYZabcdefghijkmnopqrstuvwxyz]+$",
            "description": "base58 encoded Identity ID string should be used to create multiple alias names for Identity"
          }
        },
        "minProperties": 1,
        "maxProperties": 1,
        "additionalProperties": false
      }
    },
    "required": [
      "nameHash",
      "label",
      "normalizedLabel",
      "normalizedParentDomainName",
      "preorderSalt",
      "records"
    ],
    "additionalProperties": false
  },
  "preorder": {
    "indices": [
      {
        "properties": [
          {
            "saltedDomainHash": "asc"
          }
        ],
        "unique": true
      }
    ],
    "properties": {
      "saltedDomainHash": {
        "type": "string",
        "minLength": 68,
        "maxLength": 68,
        "pattern": "^[A-Fa-f0-9]+$",
        "description": "Double sha-256 multihash of the full domain name + salt in a form of a hex string"
      }
    },
    "required": [
      "saltedDomainHash"
    ],
    "additionalProperties": false
  }
}
```
