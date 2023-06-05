# Voting_contract
COSM_WASM  CONTRACT
To start, we will go with three basic entry points:
instantiate which is called once per smart contract lifetime - you can think about it as a constructor or initializer of a contract.
execute for handling messages which are able to modify contract state - they are used to perform some actual actions.
query for handling messages requesting some information from a contract; unlike execute, they can never affect any contract state, and are used just like database queries.
use cosmwasm_std::{
    entry_point, Binary, Deps, DepsMut, Empty, Env, MessageInfo, Response, StdResult,
};

#[entry_point]
pub fn instantiate(
    _deps: DepsMut,
    _env: Env,
    _info: MessageInfo,
    _msg: Empty,
) -> StdResult<Response> {
    Ok(Response::new())
}
  
  
deps: DepsMut is a utility type for communicating with the outer world - it allows querying and updating the contract state, querying other contracts state, and gives access to an Api object with a couple of helper functions for dealing with CW addresses.
env: Env is an object representing the blockchains state when executing the message - the chain height and id, current timestamp, and the called contract address.
info: MessageInfo contains metainformation about the message which triggered an execution - an address that sends the message, and chain native tokens sent with the message.

  msg: Empty is the message triggering execution itself - for now, it is Empty type that represents {} JSON, but the type of this argument can be anything that is deserializable, and we will pass more complex types here in the future.


 #[entry_point]. Its purpose is to wrap the whole entry point to the form Wasm runtime understands.
It creates the raw Wasm entry point, calling the decorated function internally and doing all the magic required to build our high-level Rust arguments from arguments passed by Wasm runtime.








…
Firstly we make storage in state.rs
Then we move to msg.rs that how we communicate through the contract


 instantiate  is to set up the data like constructor
Execute - is to write the data 
Query - is the to read the data
These are basics entrypoint for simple contract other then that 
We have 
Migrate - to migrate contract  data from contract  if you change versions
Reply - to wait for rply
Pseudo - used in governance contracts  allow governance to interact with the contract


