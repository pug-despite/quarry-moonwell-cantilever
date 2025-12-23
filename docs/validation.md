# Quarry Moonwell Cantilever — Validation Notes

Maintenance notes covering testnet validation, explorer verification, and dependency hygiene.

---

## Testnet Validation (Base Sepolia)

Before merging or releasing:

- [ ] App boots on Base Sepolia with no console errors
- [ ] Read-only probes succeed (balances / token metadata / allowances)
- [ ] RPC fallback works (temporarily switch to a fallback endpoint)
- [ ] Network selection logic uses config (no duplicated constants)

Recommended approach:
- Use `scripts/sample-inputs.json` for repeated runs to keep validation consistent.

---

## Explorer Verification

- [ ] Base Mainnet explorer URLs point to `https://basescan.org`
- [ ] Base Sepolia explorer URLs point to `https://sepolia.basescan.org`
- [ ] Transaction links open on the correct explorer for the selected chain
- [ ] Chain IDs match network config (`8453` mainnet, `84532` sepolia)

---

## Dependency Hygiene

Keep dependencies minimal and aligned with the **Base ecosystem**:

- [ ] New deps are justified (wallet / AA / RPC / UI)
- [ ] Avoid multiple libs that solve the same problem
- [ ] Remove unused packages after refactors
- [ ] Confirm versions remain compatible with TypeScript + build tooling
- [ ] No direct forks without documentation

---

## Safe Defaults

- Mainnet is the default network unless the feature explicitly targets testnet
- Prefer **public Base RPC** endpoints and small fallback lists
- Never commit secrets (keys, tokens, private RPC URLs)

---

_Last updated: initial scaffold_
