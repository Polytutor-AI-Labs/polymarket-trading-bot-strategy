# Security

This repository is a public showcase. It does not contain trading credentials, private keys, or production configuration. Keep it that way.

## Never share

Do not commit, paste, or send:

- seed phrases
- wallet private keys
- exchange or venue credentials
- unrestricted API credentials
- production environment files
- client account data

If a secret is exposed, treat it as compromised. Rotate it. Do not reuse it.

## Operational security

For any trading or research deployment you operate:

- Store secrets in environment variables or a secret manager, not in source control
- Use least-privilege credentials
- Separate trading wallets from treasury wallets where appropriate
- Harden VPS or server access
- Restrict SSH and disable password login where possible
- Rotate keys on a schedule and after staff or vendor changes
- Keep backups that do not include live private keys in plaintext
- Revoke credentials immediately after a suspected leak
- Review dependencies before they touch signing or order paths
- Sanitize logs so keys, seeds, and full account identifiers are not written to disk

## Vulnerability reporting

Do not open a public issue that includes secrets, private keys, or exploit details.

A dedicated security contact will be published after owner verification.
