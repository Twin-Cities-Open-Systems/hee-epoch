# hee-epoch

The commit is the journal entry.

This repo is the running, real-time narrative record of TCOS's genesis
work -- root-of-trust infrastructure, governance, the decisions that only
get made once. Not a HEE consumer, not tied to HEE's own schema or
doctrine (see [human-execution-engine#207](https://github.com/Twin-Cities-Open-Systems/human-execution-engine/issues/207)
-- HEE stays free of TCOS-specific ties, deliberately). This repo lives
entirely on the TCOS side of that line.

Public on purpose. "Verified, not claimed" only means something if the
record is checkable by someone who wasn't in the room. Root-of-trust
ceremonies ([fleet-ops#102](https://github.com/Twin-Cities-Open-Systems/fleet-ops/issues/102))
get documented here -- inputs and hashes, never secrets. No private key
material, no raw payment credentials, no unredacted third-party PII ever
lands in this repo's history. If it's here, it was meant to be seen.

Described as "the first of many" -- root-DNS-shaped: a small, consistent,
public, authoritative pattern, not a one-off. The pattern itself isn't
locked yet -- this is instance one, proving the shape before it gets
extracted into something reusable.

---

**2026-08-16** -- First real commit. Tonight: `pve` got decommissioned
and rebuilt clean, `pve-resources.py` went from an SSH script to a fully
API-driven policy tool, a 2019 IANA PEN registration got found and its
fate decided (kept as "Crooked," TCOS gets its own), root/intermediate
key custody got designed before a single key exists, the fleet went from
six identities to two on purpose, GitHub Team got bought and branch
protection went from documentation to something actually enforced, and a
Mercury virtual card taught us in real time where the line between
"internal tooling" and "regulated financial identity" actually sits. Not
all of it went the way it was first pictured. All of it is real.
