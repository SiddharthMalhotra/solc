# Introduction

This is an [Ethereum](https://www.ethereum.org) [Solidity](https://solidity.readthedocs.io/en/develop/#) compiler image, allowing you to compile contracts on any platform that supports Docker.

# Installation

Pull the image from [docker registry](https://hub.docker.com/r/mrhornsby/solc/):

> docker pull mrhornsby/solc:latest

(If you don't do this it will be done on demand when you execute the run command below).

Alternatively you can build the image locally:

> git clone https://github.com/mrhornsby/solc.git
> cd solc
> docker build --tag="&lt;your_tag_here&gt;"

# Quick start

To invoke the solidity compiler, solc, you can simply run the container:

> docker run mrhornsby/solc:latest

(**Note:** This will print the standard usage instructions)

To compile a contract you will need to mount a volume that contains your contract source files and where the output files can be written. Assuming you have a directory called *solidity* in your home directory that has a *contracts* and an *output* sub-directory:

> docker run -v ~/solidity:/solidity mrhornsby/solc:latest -o /solidity/output --abi --bin /solidity/contracts/&lt;yoursoliditycontract&gt;.sol

(**Note:** This will output both the [ABI](https://github.com/ethereum/wiki/wiki/Ethereum-Contract-ABI) and the contract binary in hex, feel free to select other options as required)
