---
description: Examples for usage of the DeoGoldd API Wrapper.
---

# DeroGoldd

```python
from dego import DeroGoldd

daemon_host = 'localhost'
daemon_port = 6969
ssl = False

#Inilialization
derogoldd = DeroGoldd(host = daemon_host, port = daemon_port, ssl = ssl)

#getblockcount
response = derogoldd.get_block_count()
print(response)

#getblockhash
height = 123456
response = derogoldd.get_block_hash(height)
print(response)

#getblocktemplate
reserve_size = 200
wallet_address = 'dgxxxx...'

response = derogoldd.get_block_template(reserve_size, wallet_address)
print(response)

#submitblock
block_blob = '0100b...'
response = derogoldd.submit_block(block_blob)
print(response)

#getlastblockheader
response = derogoldd.get_last_block_header()
print(response)

#getblockheaderbyhash
hash = '30706...'
response = derogoldd.get_block_header_by_hash(hash)
print(response)

#getblockheaderbyheight
height = 123456
response = derogoldd.get_block_header_by_height(height)
print(response)

#getcurrencyid
response = derogoldd.get_currency_id()
print(response)

#getblocks
height = 500000
response = derogoldd.get_blocks(height)
print(response)

#getblock
hash = '980ff...'
response = derogoldd.get_block(hash)
print(response)

#gettransaction
hash = '702ad...'
response = derogoldd.get_transaction(hash)
print(response)

#gettransactionpool
response = derogoldd.get_transaction_pool()
print(response)
```
