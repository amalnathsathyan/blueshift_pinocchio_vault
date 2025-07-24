# 🏦 Pinocchio Vault on Solana

This project implements a simple **lamport vault** on Solana using [Pinocchio](https://learn.blueshift.gg/en/courses/introduction-to-pinocchio), a lightweight Solana-compatible framework.

Users can securely **deposit** and **withdraw** lamports (Solana’s smallest denomination) into a vault derived from their public key using a Program Derived Address (PDA). Only the original depositor can withdraw the funds.

> 💡 Built as part of the [Blueshift Pinocchio Vault Challenge](https://learn.blueshift.gg/en/challenges/pinocchio-vault)

---

## 🔧 Features

- 📥 **Deposit** lamports into a vault securely  
- 📤 **Withdraw** lamports back to the depositor  
- 🛡️ Enforces PDA ownership and vault uniqueness  
- 🔒 Rent-exempt checks for deposit safety  
- 🧠 Demonstrates PDA signing and CPI (Cross-Program Invocation)

---

## 🛠️ Installation & Setup

Make sure you have [Rust](https://www.rust-lang.org/tools/install) and the Pinocchio toolchain installed.

```bash
# Create a new cargo workspace
cargo new blueshift_vault --lib --edition 2021
cd blueshift_vault

# Add dependencies
cargo add pinocchio pinocchio-system
```

Update your `Cargo.toml` to support dynamic libraries:

```toml
[lib]
crate-type = ["lib", "cdylib"]
```

---

## 📁 Project Structure

All logic is implemented inside `lib.rs`, including:

- **Vault PDA Derivation**  
- **Deposit & Withdraw Instructions**  
- **Account Validation & Ownership Checks**

---

## 📤 Deposit Flow

- Validates the vault is empty (no double deposits)  
- Checks that deposit amount is non-zero and rent-exempt  
- Transfers lamports using a CPI to the system program  

---

## 📥 Withdraw Flow

- Ensures the vault contains lamports  
- Re-derives the PDA from the owner's pubkey  
- Vault signs the transfer using PDA signing via `invoke_signed`  

---

## 🧪 Build

To compile the program for Solana’s SBF (Sealevel BPF) format:

```bash
cargo build-sbf
```

This will generate a `.so` file in `target/deploy/`.

---

## 🏁 Taking the Challenge

Once built, go to the [Pinocchio Vault Challenge page](https://learn.blueshift.gg/en/challenges/pinocchio-vault/verify) and upload your `.so` file to test it and claim your on-chain NFT.

---

## 🙏 Credits

This project is based on the excellent guide by **[Blueshift](https://learn.blueshift.gg)**.  
Special thanks to their educational challenge:  
👉 [Pinocchio Vault Challenge](https://learn.blueshift.gg/en/challenges/pinocchio-vault)

---

## 📜 License

MIT License © 2025  
Built with ❤️ by [Your Name or GitHub handle]
