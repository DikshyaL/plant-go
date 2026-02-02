
Perfect! Here's a **clean `README.md`** just for using **Cargo** to build and run your Solana program, without any Anchor references:

````markdown
# Iodex - Solana Project

Iodex is a Solana-based decentralized application (dApp) written in Rust. This project demonstrates building, deploying, and interacting with Solana programs (smart contracts) using the Solana CLI and Cargo.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Building the Program](#building-the-program)
- [Deploying the Program](#deploying-the-program)
- [Running the Program](#running-the-program)
- [Testing](#testing)
- [Project Structure](#project-structure)
- [Troubleshooting](#troubleshooting)

---

## Prerequisites

Before you begin, make sure you have the following installed:

- Rust (latest stable)
  ```bash
  curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
  rustup update
````

* Solana CLI (v1.14+ recommended)

  ```bash
  sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
  solana --version
  ```
* Node.js and npm (if integrating with frontend)
* Git

---

## Installation

Clone this repository:

```bash
git clone https://github.com/your-username/iodex.git
cd iodex
```

Set your Solana CLI to devnet for testing:

```bash
solana config set --url https://api.devnet.solana.com
```

Generate a keypair (if you don’t have one):

```bash
solana-keygen new --outfile ~/.config/solana/id.json
```

Check your balance (you can request test SOL from the faucet):

```bash
solana airdrop 2
solana balance
```

---

## Building the Program

Compile your Solana program to the **SBF (Solana Bytecode Format)** using Cargo:

```bash
cargo build-sbf
# or for release build
cargo build-sbf --release
```

Compiled artifacts will be placed in:

```
target/deploy/
```

---

## Deploying the Program

Deploy your program to the Solana cluster:

```bash
solana program deploy target/deploy/iodex.so
```

This will output a **program ID**, which is needed to interact with your program.

---

## Running the Program

You can interact with your program using Solana CLI commands or custom scripts. Example:

```bash
solana program show <PROGRAM_ID>
solana program close <PROGRAM_ID> --recipient <YOUR_WALLET>
```

For writing your own scripts, you can use Rust or JavaScript/TypeScript with `@solana/web3.js` to send transactions to your program.

---

## Testing

Run Rust unit tests:

```bash
cargo test
```

This will run all your unit and integration tests locally.

---

## Project Structure

```
iodex/
├─ Cargo.toml           # Rust dependencies
├─ src/
│  └─ lib.rs           # Solana program code
├─ target/deploy/       # Compiled SBF program
├─ tests/               # Unit / integration tests
└─ README.md
```

* `src/lib.rs`: Main program logic
* `tests/`: Rust integration tests
* `target/deploy/`: Output of SBF compilation

---

## Troubleshooting

* **`build-sbf` not recognized**: Make sure you run `cargo build-sbf`, not `solana build-sbf`.
* **Insufficient SOL**: Request more from devnet faucet.
* **Version mismatch**: Ensure Solana CLI and Rust are up-to-date.
* **Program ID mismatch**: Use the correct deployed program ID when interacting.

---

## References

* [Solana Docs](https://docs.solana.com/)
* [Rust for Solana](https://docs.rs/solana-program/latest/solana_program/)

---

Made with ❤️ by Sabin Ranabhat

```

---

If you want, I can **also add a small “How to run a transaction script” section** that shows how to call your program after deploying, purely using Cargo + Rust. It makes the README fully runnable.  

Do you want me to do that?
```
``
