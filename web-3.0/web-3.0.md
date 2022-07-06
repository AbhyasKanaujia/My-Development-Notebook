# Web 3.0

## What is Web 3.0?

Web 3.0 (Web3) is **the third generation of the evolution of web technologies**

## **What were web 1.0 and 2.0?**

Web 1.0 refers to tools for publishing static information that is “owned” and considered proprietary, fact checked and attributed. Those who had information are sharing it with those who want it. Web 2.0 applications are web pages that visitors can add to or change.

## Encryption

**Encryption is the method by which information is converted into secret code that hides the information's true meaning**. This is reversible, i.e., it can be decrypted and thus not good enough for Web 3.0. Instead, it uses hashing.

## Hashing

A hash function is any function that can be used to map data of arbitrary size to data of fixed size.

* No matter the size of the data, the **output is always of the same length**
* The same input always produces the **same output**.
* The output cannot be used to find the input.
* Small changes in the input causes significant change in the output
* Example Secure Hash Algorithm 2, 256 bit

## Block

A block is the smallest unit of a blockchain.

A block may contain the following elements:

1. **Block Number:** The Number of the block in the chain. Integer that starts at 1 and is increased by one for every new block.
2. **Nonce:** A number that is used to make a block valid. Its sole purpose is to be adjusted until the hash of the whole block has certain properties that make it “valid”.&#x20;
   1. For example, the hash should have 4 leading 0s is a required property of a valid hash. Changing the message randomly might help us reach such a hash, but this is not a viable solution. So change the nonce and the hash changes. Now keep changing the nonce until a valid hash is found.
3. **Data:** The actual data of the block. Can be anything!
4. **Previous block hash:** The hash of the previous block. For the first block in a chain, an arbitrary value like 00000000000… is used.
5. **Hash:** All previous elements appended together and then hashed.&#x20;

**Difficulty**

A block is considered “valid” if its hash has a certain form. For our example, we want the hash to start with a certain amount of zeroes. The higher the number of zeroes we want a hash to start with, the harder it will be to find a nonce that makes the hash of the block to look the way we want. This is what is called the difficulty.&#x20;

## Blockchain

Every block (except for the first) now has the hash of its predecessor in the "Prev" field.

If you change one block and it gets invalid, the whole chain from that block on will be invalid.

## Smart Contracts

Besides for data, code can also be stored in a blockchain. These are called **Smart Contracts.**

Smart contracts are simply programs stored on a blockchain that run when predetermined **-conditions** are met. They typically are used to **automate the execution of an agreement** so that all participants can be immediately certain of the outcome, without any intermediary’s involvement or time loss.&#x20;

## DApps

A decentralized application (DApps) is an application built on a decentralized network that combines a smart contract and a frontend user interface.&#x20;

## Pseudonymity

Pseudonymity is **the near-anonymous state in which a user has a consistent identifier that is not their real name: a pseudonym**. Like a discord username.

## Ethemrum

Ethereum is a decentralized, open-source blockchain with smart contract functionality.
