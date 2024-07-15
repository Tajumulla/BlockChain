
# Simple Blockchain Implementation in Java

This project is a simple implementation of a blockchain using Java, designed to demonstrate the fundamental concepts of blockchain technology, including block creation, hashing, and mining.

## Table of Contents

- [Introduction](#introduction)
- [Components](#components)
  - [Block.java](#blockjava)
  - [NewCoin.java](#newcoinjava)
  - [StringUtil.java](#stringutiljava)
- [How It Works](#how-it-works)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Key Concepts](#key-concepts)
- [Enhancements](#enhancements)
- [License](#license)

## Introduction

This project provides a basic implementation of a blockchain in Java. It includes core functionalities such as block creation, mining, and validation. The project is intended for educational purposes to help understand the workings of blockchain technology.

## Components

### Block.java

The `Block` class represents an individual block in the blockchain.

- **Attributes**:
  - `hash`: The hash of the current block.
  - `previousHash`: The hash of the previous block.
  - `data`: The data stored in the block.
  - `timeStamp`: The timestamp when the block was created.
  - `nonce`: A counter used in the mining process.
- **Methods**:
  - `calculateHash()`: Computes the SHA-256 hash of the block.
  - `mineBlock(int difficulty)`: Mines the block by finding a hash that meets the difficulty requirement.

### NewCoin.java

The `NewCoin` class manages the blockchain and contains the main application logic.

- **Attributes**:
  - `blockchain`: An array list of `Block` objects representing the chain.
  - `difficulty`: The difficulty level for mining new blocks.
- **Methods**:
  - `isChainValid()`: Validates the integrity of the blockchain.
  - `main(String[] args)`: Creates, mines, and validates blocks, and prints the blockchain in JSON format.

### StringUtil.java

The `StringUtil` class provides utility functions, particularly for hashing.

- **Methods**:
  - `applySha256(String input)`: Applies the SHA-256 hashing algorithm to a string and returns the resulting hash.

## How It Works

1. **Block Creation**:
   - A block is created with specific data and the hash of the previous block. The current block’s hash is calculated using its data, previous hash, timestamp, and a nonce.

2. **Mining**:
   - The `mineBlock` method adjusts the nonce and recalculates the block’s hash until it meets the difficulty requirement (a certain number of leading zeros).

3. **Blockchain Management**:
   - The `NewCoin` class maintains an array list of blocks and provides functionality to add new blocks, mine them, and validate the entire chain’s integrity.

4. **Validation**:
   - The `isChainValid` method checks each block’s hash against its calculated hash and ensures the `previousHash` field matches the previous block's hash, maintaining the chain’s consistency and immutability.

## Getting Started

### Prerequisites

- Java Development Kit (JDK) 8 or later.
- A code editor or IDE such as IntelliJ IDEA or Eclipse.

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/your-repository-name.git
   ```
2. Navigate to the project directory:
   ```sh
   cd your-repository-name
   ```

## Usage

1. Compile the Java files:
   ```sh
   javac *.java
   ```
2. Run the main class:
   ```sh
   java NewCoin
   ```

## Key Concepts

- **Hashing**: Ensures data integrity by producing a unique hash for each block.
- **Proof of Work (Mining)**: Demonstrates the computational effort required to add a new block to the blockchain.
- **Chain Validation**: Ensures the blockchain’s integrity by verifying each block’s hash and its link to the previous block.

## Enhancements

While this project effectively demonstrates basic blockchain concepts, real-world blockchains include additional features such as:

- Transaction handling
- Digital signatures
- More complex consensus algorithms
- Enhanced security measures

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to modify any section according to your specific details and requirements.
