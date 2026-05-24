---
tags:
  - concept
  - security
---
Security models are **ways to ensure the CIA triad of a system.**
# Bell-LaPadula
This model focuses on **security levels**.
The Bell-LaPadula model aims to **achieve confidentiality through three rules:**
- **Simple Security Property**: Someone on a lower level can't read information from a higher level
- **Star Security Property**: Someone on a higher level can't write information to lower levels, preventing information disclosure
- **Discretionary-Security Property**: Access matrix for read/write operations. Every user has its own write and read access to every resource.
This model was **not designed to handle file-sharing**.
# Biba Integrity
The Biba model aims to **achieve integrity with two main rules**:
- **Simple Integrity Property**: A higher integrity subject should not read from a lower integrity one
- **Star Integrity Property**: A lower integrity subject should not write to a higher integrity one
This contrasts the Bell-LaPadula model strongly, since the Biba model is focused on integrity, not confidentiality.
# Clark-Wilson
The Clark-Wilson model also aims to **achieve integrity through the following concepts**:
- **Constrained Data Item (CDI)**: Data types whose integrity we want to preserve
- **Unconstrained Data Item (UDI)**: All data types that aren't CDIs, like user and system input
- **Transformation Prodecudres (TPs)**: Programmed operations, like read/write, that should maintain the integrity of CDIs
- **Integrity Verification Procedures (IVPs)**: Procedures that check and ensure the validity of CDIs
# Other Models
There are a few other security models, including but not limited to:
- Brewer and Nash
- Goguen-Meseguer
- Sutherland
- Graham-Denning
- Harrison-Ruzzo-Ullman
# Resources