---
description: Examples for usage of the wallet-api wrapper.
---

# Wallet-API

```python
from dego import WalletAPI

password = 'mysupersecretpassword'
rpc_host = 'localhost'
rpc_port = 1337
ssl = False

#Inilialization
wallet_api = WalletAPI(key = password, host = rpc_host, port = rpc_port, ssl = False)

#open_wallet
file = 'wallet.dego'
passwd = 'yourpassword'

wallet_api.open_wallet(file, passwd)

#import_wallet_key
file = 'wallet.dego'
passwd = 'yourpassword'
view_key = '493f522e1f46b5c07f753ed28dc2db9da5f571f28c2fa54f4c9a0a7941b09d0b'
spend_key = '5c703d9bde0b7cd5ff3e19ea826a44066534661a7322c85e854e73f06e49cd06'

wallet_api.import_wallet_key(file, passwd, view_key, spend_key)

#import_wallet_seed
file = 'wallet.dego'
passwd = 'yourpassword'
mnemonic_seed = 'cynical waveform sixteen husband zebra ritual vexed jaws eccentric jewels toenail having nabbing wept nozzle grunt tipsy flying pegs feel upright lower racetrack sapling sapling'

wallet_api.import_wallet_seed(file, passwd, mnemonic_seed)

#import_wallet_view
file = 'wallet.dego'
passwd = 'yourpassword'
view_key = '493f522e1f46b5c07f753ed28dc2db9da5f571f28c2fa54f4c9a0a7941b09d0b'
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'

wallet_api.import_wallet_view(file, passwd, view_key, addr)

#create_wallet
file = 'wallet.dego'
passwd = 'yourpassword'

wallet_api.create_wallet(file, passwd)

#delete_wallet

wallet_api.delete_wallet()

#addresses
addr = wallet-api.addresses()

print(addr)

#delete_address
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'

wallet_api.delete_address(addr)

#primary address
addr = wallet_api.primary_address()

print(addr)

#create_address    
addr_details = wallet_api.create_address()

print(addr_details)

#import_address
spend_key = '5c703d9bde0b7cd5ff3e19ea826a44066534661a7322c85e854e73f06e49cd06'

wallet_api.import_address(spend_key, 300000)

#import_address_view
public_spend_key = '5c703d9bde0b7cd5ff3e19ea826a44066534661a7322c85e854e73f06e49cd06'

wallet_api.import_address_view(public_spend_key, 300000)

#integrated_address
payment_id = '38a8224a4c8bc5f060555cf9e89551dcd0cbb1c587a52b63e98f71280c362ee4'
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'

integrated_addr = wallet_api.integrated_address(payment_id, addr)
print(integrated_addr)

#get_node
node_details = wallet_api.get_node()

print(node_details)

#set_node
daemon_host = 'localhost'
daemon_port = 6969

wallet_api.set_node(daemon_host, daemon_port)

#wallet_keys
keys = wallet_api.wallet_keys()

print(keys)

#address_keys
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'

keys = wallet_api.address_keys(addr)
print(keys)

#mnemonic
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'

mnemonic_seed = wallet_api.mnemonic(addr)
print(mnemonic_seed)

#transactions
response = wallet_api.transactions()

print(response) 

#transaction_details
hash = '396e2a782c9ce9993982c6f93e305b05306d0e5794f57157fbac78581443c55f'

response = wallet_api.transaction_details(hash)
print(response)

#unconfirmed_transactions
response = wallet_api.transaction_details()

print(response)

#unconfirmed_address
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'

response = wallet_api.unconfirmed_address(addr)
print(response)

#transactions_height
start = 300000
end = 1000000  #optional

response = wallet_api.transactions_height(start, end)

#transactions_height_address
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'
start = 300000
end = 1000000

response = wallet_api.transactions_height_address(addr, start, end)
print(response)

#send_basic
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'
amt = 1234567
pay_id = '38a8224a4c8bc5f060555cf9e89551dcd0cbb1c587a52b63e98f71280c362ee4'

response = wallet_api.send_basic(addr, amt, pay_id)
print(response)

#prepare_basic
amt = 1234567

response = wallet_api.prepare_basic(addr, amt, pay_id)
print(response)

#send_advanced
dest = [
    {
      "address": "dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD",
      "amount": 1234000
    },
    {
      "address": "dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDkLfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD",
      "amount": 5000000
    }
  ]
source_addr = ['dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD']
change_addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'

response = wallet_api.send_advanced(destination = dest, source_addresses = source_addr, change_address = change_addr)
print(response)

#prepare_advanced
dest = [
    {
      "address": "dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD",
      "amount": 1234000
    },
    {
      "address": "dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD",
      "amount": 5000000
    }
  ]
source_addr = ['dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD']

response = wallet_api.prepare_advanced(destination = dest, source_addresses = source_addr)
print(response)

#send_prepared
hash = '396e2a782c9ce9993982c6f93e305b05306d0e5794f57157fbac78581443c55f'

response = wallet_api.send_prepared(hash)
print(response)

#cancel_prepared
hash = '396e2a782c9ce9993982c6f93e305b05306d0e5794f57157fbac78581443c55f'

wallet_api.cancel_prepared(hash)

#send_fusion_basic
response = wallet_api.send_fusion_basic()
print(response)

#send_fusion_advanced
opt = 20000

response = wallet_api.send_fusion_advnaced(optimize_target = opt)
print(response)

#transactions_private_key
hash = '396e2a782c9ce9993982c6f93e305b05306d0e5794f57157fbac78581443c55f'

response = wallet_api.transactions_private_key(hash)
print(response)

#wallet_balance
response = wallet_api.balance()

print(response)

#address_balance
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'

response = wallet_api.address_balance(addr)
print(response)

#balances
response = wallet_api.balances()

print(response)

#save
wallet_api.save()

#export
file = 'wallet.json'

wallet_api.export(file)

#reset
height = 300000

wallet_api.reset(height)

#validate
addr = 'dg51XbaPvkmVSyC1sK1NDfBdiPkMBMmlZY1WjFRdxreDLkDpPfW23aBZTgzDeap9voh2vQTXxCyNJbi3A1TgvXQE1CKrtXdJD'

response = wallet_api.validate(addr)
print(response)

#status
response = wallet_api.status()

print(response)
```

