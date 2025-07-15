# VaultOS Build

**VaultOS** is a security-focused Linux distribution built on HumanityOS. It provides a locked-down environment with:

- **TPM-backed secure boot**: UEFI shim, GRUB, and kernel signed with user-managed keys.
- **Encrypted-rootfs**: Full disk encryption via dm-crypt/LUKS, with auto-unseal using the TPM at boot.
- **Immutable snapshots**: OverlayFS-based read-only root with snapshot rollbacks.
- **Sealed vault operations**: Automated sealing/unsealing of secrets in TPM NV storage.
- **Vault daemon**: A custom service (`vaultd`) that exposes secure storage APIs for higher-level apps.

## Key Components

| Component                 | Description                                                             |
|---------------------------|-------------------------------------------------------------------------|
| `secure-boot/`            | Shim and GRUB signing keys; scripts to generate and enroll certificates|
| `configs/*.cfg`           | Kernel fragments enabling TPM, dm-crypt, OverlayFS                      |
| `overlays/crypttab/`      | Default encrypted volume mappings                                       |
| `overlays/udev/99-tpm.rules` | Permissions for `/dev/tpm0` and `/dev/tpmrm0`                         |
| `scripts/generate_keys.sh`| Generate RSA keys & certificates for shim and GRUB                      |
| `scripts/seal_vault.sh`   | CLI wrapper for sealing/unsealing generic data into TPM NV indices      |
| `packages/*/vaultd`       | Packaging definitions for the vault daemon (DEB/RPM)                    |

## Getting Started

1. **Clone the VaultOS build repo**:
   ```bash
   git clone https://github.com/ZorroChainOfficial/VaultOS
   
   
   
   <!--
   
ZorroChain Core Protocol  
Copyright (c) 2025–present ZorroChain Foundation

Licensed under the Mozilla Public License, v. 2.0  
https://mozilla.org/MPL/2.0/
-->
