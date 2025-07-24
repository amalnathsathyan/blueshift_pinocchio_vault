# Pinocchio Vault 🏦

A simple vault smart contract demonstration on Solana using **Pinocchio**, inspired by the [Blueshift Pinocchio Vault Challenge](https://learn.blueshift.gg/en/challenges/pinocchio-vault).

This program allows users to securely deposit and withdraw lamports using [Program Derived Addresses (PDAs)](https://docs.solana.com/developing/programming-model/calling-between-programs#program-derived-addresses-pdas) and Cross-Program Invocation (CPI). It is an educational project to get hands-on with account validation, instruction handling, and basic Solana DeFi building blocks in Rust.

> **Credits:**  
> Much of the logic, structure, and explanation here is based on the [Blueshift Pinocchio Vault Challenge](https://learn.blueshift.gg/en/challenges/pinocchio-vault).  
> Many thanks to the Blueshift team for this excellent resource!

---

## ✨ Features

- **Deposit**: Users create a vault (PDA) and deposit lamports, protected by strict account checks.
- **Withdraw**: Users can withdraw all lamports from their own vault, with the PDA signing for itself using seeds.
- **Security**: Only the vault creator (owner) can deposit and withdraw. No double deposits or unauthorized withdrawal.
- **CPI Usage**: Transfers leverage cross-program invocation to the System Program.

---

## 🚀 Installation

**Prerequisites:**

- [Rust](https://rustup.rs/)
- [Pinocchio](https://github.com/blueshift-gg/pinocchio) (Solana-like on-chain framework)

**Setup:**
