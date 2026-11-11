# VERIFY.md

Every deployed address, transaction and sandbox id, **ids only, never secrets**.

## PayPal sandbox and live model runs (run by the owner)

Ids only, never secrets. These runs were made by hand on the owner's machine with their own sandbox app and model
keys. CI never makes them. The ids come from the slides in [`gallery/`](gallery/): rendered screenshots of terminal
output, not raw logs. **Not recorded** means no public source holds that id or date; it is not reconstructed or
guessed.

| Run | Date | What | Ids | Source |
|---|---|---|---|---|
| 1 | 1 Nov 2026 | LLM agent (Flovia `gpt-6-luna`) against the real PayPal **sandbox**: `create_order` 2.00 USD Allowed → sandbox buyer approval → `make sandbox-resume` → `get_order` re-check (APPROVED, pinned payee, same amount) → one capture, `COMPLETED` | agent run `faeccd82-e573-4b27-a080-230593a9946a`, sandbox order `3KP99367FE3669842` | [`gallery/05-capture-completed.png`](gallery/05-capture-completed.png), [`gallery/04-needs-your-ok.png`](gallery/04-needs-your-ok.png), [`DEVPOST.md`](DEVPOST.md) ("Accomplishments that we're proud of") |
| 2 | **not recorded** | LLM agent (Flovia `gpt-6-luna`) against the **mock** PayPal: 4.50 USD → `Needs your OK: NEEDS_OWNER_OK` | agent run `6eb467b0-4542-4c24-8bc4-e59525529599` | [`gallery/04-needs-your-ok.png`](gallery/04-needs-your-ok.png) |
| 3 | **not recorded** | An early live model run put the seller's name where a merchant id goes; the gate blocked it (**Blocked by your rule**) | run id **not recorded** | [`DEVPOST.md`](DEVPOST.md) ("Challenges we ran into": "A model trying to help") |
| 4 | **not recorded** | The same agent with Anthropic Claude Haiku (opt-in), with the spend cap in place | message id **not recorded** | [`DEVPOST.md`](DEVPOST.md) ("Accomplishments that we're proud of") |

The `PAYTO_MISMATCH` block for an injected payee is shown on the mock only: in the live runs the model ignored the
injected text.

## Testnet contracts (M4)

None yet.
