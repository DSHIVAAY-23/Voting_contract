 instantiate  is to set up the data like constructor
Execute - is to write the data 
Query - is the to read the data
These are basics entrypoint for simple contract other then that 
We have 
Migrate - to migrate contract  data from contract  if you change versions
Reply - to wait for rply
Pseudo - used in governance contracts  allow governance to interact with the contract




.commands to run the wasmdd node.

./wasmd init wasmnode --chain-id=wasm_904-3 

./wasmd keys add bob --keyring-backend test  

./wasmd genesis add-genesis-account bob 10000000000000000000000000000000000token,10000000000000000000000000000000000stake --keyring-backend test

./wasmd genesis gentx bob 100000000000000000stake --keyring-backend test 

./wasmd genesis collect-gentxs 


To compile the contract


 cargo build --target wasm32-unknown-unknown --release


