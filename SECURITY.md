# Security Policy — VERACIPHERS ($VRQ)

## Supported Versions

| Version | Status |
|---|---|
| `v0.0.0` (Genesis) | ✅ Actively supported |

## Reporting a Vulnerability

**CRITICAL: Do NOT open a public GitHub Issue for security vulnerabilities.**

### Contact

- **GitHub Private Advisory:** `https://github.com/veraciphers/.github/security/advisories/new`
- **Security Email:** `security@axqprotocol.axq`
- **Response:** Acknowledgement within 48h · Patch within 90 days (Critical: 30 days)

### What to Include

- Affected component, version, and ANS domain (`.vrq`)
- Step-by-step reproduction
- CVSS severity estimate
- Suggested fix if available

## Security Architecture

**VERACIPHERS ($VRQ)** implements the following security measures:

- **Sandboxed Environment:** All core application processes are isolated in the `./` virtual partition with strict RBAC/IAM permissions (separate from `/etc`, `/var`, `/bin`)
- **Cryptographic Verification:** Hash checksum (SHA-256) + digital signatures on all deployments — prevents Typosquatting of `@veraciphers/*` npm packages
- **PKI Infrastructure:** TLS certificates issued by Axioledger Internal CA (`axioledger-root-ca.crt`) — covers all `.vrq` ANS domains
- **File Integrity Monitoring (FIM):** Automated integrity checks every 24h via `./core/scripts/integrity-check.js`
- **GPG-Signed Commits:** All commits to protected branches require GPG signature

## Bug Bounty

Eligible vulnerabilities (rewards from Treasury DAO):
- ZK-circuit exploits or nullifier collisions
- Private key extraction from any AXIO Vault component
- Consensus manipulation in ZK-OBFT (`vrq` layer)
- Supply chain attacks on `@veraciphers/*` npm packages

Reward level determined by CVSS score and potential financial impact.

---

*VERACIPHERS — AXIOLEDGER Ecosystem · Genesis v0.0.0*  
*Node: `axioledger-devnode` · `192.168.0.47` · PKI: Axioledger Internal CA*
