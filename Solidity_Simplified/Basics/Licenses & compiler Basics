# 📄 SPDX License Identifiers in Solidity (Simplified)

---

## 🔐 Why License Matters

When you open-source a smart contract, you’re giving others permission to read, reuse, or build upon your code — but only under certain legal terms. That’s where SPDX license identifiers come in.

---

## ✅ Syntax (Top of every `.sol` file)

```solidity
// SPDX-License-Identifier: MIT
```

This tells the compiler (and the world):

> "I’m open-sourcing this file under the MIT License."

---

## 📚 Common SPDX License Types

| SPDX Tag     | Meaning                                                                    |
| ------------ | -------------------------------------------------------------------------- |
| `MIT`        | Super permissive. You can use, copy, modify, distribute. Just give credit. |
| `GPL-3.0`    | Free to use, but **must open-source** derivative works.                    |
| `Apache-2.0` | Like MIT, but with added patent protection.                                |
| `UNLICENSED` | You are **not** allowing others to use or reuse the code.                  |
| `UNLICENSE`  | You are granting **all rights** to everyone — public domain.               |

> ⚠️ `UNLICENSED` ≠ `UNLICENSE` — Don’t get confused

---

## 📌 Best Practices

* Always add an SPDX license identifier in production contracts
* Place it at the very top of every `.sol` file
* Choose the license that fits the level of openness you want

---

## ✅ Example

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract HelloWorld {
    string public greet = "Hello, world!";
}
```

---

## 🧠 Compiler Notes

* The Solidity compiler does **not** validate the license — it just embeds it in bytecode metadata.
* SPDX tags are **machine-readable** — useful for automated tools, scanners, and legal audits.

---

## ⚙️ `pragma` in Solidity — Explained

The `pragma` keyword is like a compiler instruction. It tells the Solidity compiler to enable specific features or checks for that particular source file.

### 🔑 Key Points:

* `pragma` applies **only** to the file it's written in
* It does **not** affect imported files
* You must repeat it in every `.sol` file where it matters

---

## ✅ Most Common: Solidity Version Pragma

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;
```

This tells the compiler:

> "Compile this file using Solidity version 0.8.20 or compatible upward versions"

You can also specify a range:

```solidity
pragma solidity >=0.8.0 <0.9.0;
```

---

## ⚙️ Common `pragma` Directives

| Pragma                      | Purpose                                             |
| --------------------------- | --------------------------------------------------- |
| `abicoder v2`               | Enables ABI encoder v2 (default from Solidity 0.8+) |
| `experimental SMTChecker`   | Enables formal verification via SMT solver          |
| `experimental ABIEncoderV2` | Old encoder (⚠️ deprecated)                         |

---

## 🔄 `pragma abicoder v1` vs `v2`

Solidity smart contracts need to encode/decode data when calling functions or returning results — especially when structs, arrays, or nested types are involved.

You control which ABI encoder to use:

```solidity
pragma abicoder v2; // ✅ Recommended
pragma abicoder v1; // ❌ Legacy
```

* `v2` supports complex types, added safety checks
* `v1` is outdated and limited

---

## 🧪 Experimental Pragmas

Used to enable advanced or upcoming compiler features (not enabled by default).

### ✅ Syntax:

```solidity
pragma experimental SMTChecker;
```

Just like other pragmas, they're **file-local** — declare them where needed.

### 🔬 Supported Experimental Pragmas

#### 1. ❌ `ABIEncoderV2` (Deprecated)

```solidity
pragma experimental ABIEncoderV2;
```

* Legacy way to support nested arrays/structs
* Deprecated since Solidity 0.8.0
* Use `abicoder v2` instead

#### 2. 🧠 `SMTChecker` — Formal Verification

```solidity
pragma experimental SMTChecker;
```

* Enables static analysis via SMT solvers (e.g., Z3)
* Detects:

  * Integer overflows
  * Unreachable code
  * Failing asserts

### 🛠️ SMT Support

* Available in: Ubuntu PPA releases
* **Not available in**: Docker, Windows, or static Linux binaries
* With `solc-js`, enable via `smtCallback` (only with local SMT solver)

---

## 🔥 SMTChecker — Real Use Cases

* Useful in DeFi contracts
* Helps catch bugs before deployment
* Supports audit automation & logic verification

---

## ⚠️ Caution:

Experimental pragmas are for **advanced users** only. Use them if:

* You're running a compatible compiler
* You know what you're enabling
* You're writing critical, high-assurance contracts

---

## 🧪 TL;DR: Experimental Pragmas Overview

| Pragma         | Status                         | Use Case                         |
| -------------- | ------------------------------ | -------------------------------- |
| `ABIEncoderV2` | Deprecated (use `abicoder v2`) | Legacy encoder for nested types  |
| `SMTChecker`   | Still experimental             | Static bug checking & audit help |

---
