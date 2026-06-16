# Doc Writing Core — Run Summary

**Date:** 2026-06-16
**Product:** payments
**Branch:** payments/callback-docs (worktree at ../payments-manual-callback)
**Intent:** payments-callback-docs-missing

---

## Changes made

### 1. `payments/en/developer-tools/callback.mdx` (new)

Created the English introduction page for callbacks. Explains what a callback is (a confirmation mechanism sent before Cobo executes a sensitive operation), how it differs from webhooks (webhooks notify after events; callbacks confirm before execution), that currently only Bulk Send triggers callbacks, and provides a 3-step overview (configure endpoint → implement handling → register at Cobo Portal).

### 2. `payments/cn/developer-tools/callback.mdx` (new)

Paired Chinese translation of the above.

### 3. `payments/en/developer-tools/set-up-callback-endpoint.mdx` (new)

Created the English setup guide covering: creating the endpoint server-side, the full callback request payload (all fields from `developer-site-waas2/.../callback_message.yaml`), signature verification (Ed25519 + SHA256), responding with `{"result":"ok"}` or `{"result":"deny"}`, registering the endpoint at Cobo Portal > Developer > Callbacks, and idempotency notes.

### 4. `payments/cn/developer-tools/set-up-callback-endpoint.mdx` (new)

Paired Chinese translation of the above.

### 5. `docs.json`

Added a `"Callbacks"` navigation group immediately after the existing `"Webhooks"` group in both the English version (versions[0]) and Chinese version (versions[1]) nav trees. Each group contains the two new callback pages.

### 6. `payments/en/guides/bulk-send.mdx`

Updated the "Smart contract mechanism for Bulk Send" section opening sentence to explain that Cobo sends a callback message for each smart contract operation and link to the new [Introduction to Callbacks](/payments/en/developer-tools/callback) page. Previously, this section mentioned "callback handler" without any link or explanation.

### 7. `payments/cn/guides/bulk-send.mdx`

Same update as above in Chinese, linking to [Callback 介绍](/payments/cn/developer-tools/callback).

### 8. `cobo-agents/docs/knowledge-base/payments-callback.md` (new, no worktree)

Created a domain knowledge entry for the workmate agent covering: callback concept and MFA nature, callback vs webhook comparison table, current trigger scope (Bulk Send only), full data structure table, response format, registration flow, and a note on user identity (developer/PSP, not "merchant").

---

## ⚠️ Pending confirmations

The following items could not be confirmed from code or spec and must be verified by the product team before treating the doc changes as authoritative. They do **not** appear in the published doc files.

### 1. Signature verification algorithm for callbacks

The setup guide documents the same Ed25519 + SHA256 + BIZ_TIMESTAMP/BIZ_RESP_SIGNATURE headers used for webhooks. This was inferred from the shared infrastructure (both use the WaaS2 developer system in `custody`), but there is no payments-callback-specific section in the spec that explicitly confirms the algorithm or header names for callbacks.

**Action needed:** Confirm with the payments backend team that callback requests use the same signature scheme as webhook events. If different, update `set-up-callback-endpoint.mdx` (EN and CN).

### 2. Response timeout (2 seconds)

The setup guide states a 2-second response timeout, mirroring the webhook guide. The `retry_callback_message.yaml` spec confirms up to 30 retries before `Failed`, but does not state the per-attempt timeout for payments callbacks specifically.

**Action needed:** Confirm the timeout value for payments callbacks with the backend team. Update the docs if different from 2 seconds.

---

## Build result

`mintlify validate` passed with no errors.
