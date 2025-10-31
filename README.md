# 🌾 Kayu Farm — Mainnet Package for Solana Playground

This package is ready to **import directly into https://beta.solpg.io/** (Choose framework: **Anchor**).
After importing, set **Cluster: Mainnet Beta**, then click **Build & Deploy**.

## Initialize
After deployment, run `initialize_farm` with:
- reward_signer: your admin wallet (same as treasury or a separate signer)
- instant_ratio_bps: 7000
- vesting_ratio_bps: 3000
- vesting_secs: 259200   # 3 days
- invite_bps: [500,300,100,50,50]
- kayu_mint: FjPustc7ikQnzMfDHYEs7mkZaihwoJ6kiyAiQavW3ems
- reward_pool: <KAYU TokenAccount owned by state_signer PDA>
- burn_token: <KAYU TokenAccount owned by state_signer PDA>
- sol_treasury: 5T9wMdw4CCZinTJZCjT37QXHD4YQ1E2ShW8RUSDcvqek

## Notes
- Create reward_pool & burn_token using `spl-token create-account <KAYU_MINT>` (Mainnet)
- They must have **owner = state_signer PDA** (as required by program constraints).
- Claiming vesting is **manual** via `claim_vesting(vesting_id)` (linear release).

