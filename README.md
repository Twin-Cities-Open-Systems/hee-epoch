# hee-epoch

This repository is a verified component of the **Twin-Cities-Open-Systems (TCOS)** architecture.

* **Ecosystem Role:** [Insert the precise Purpose we defined in the master index]
* **Visibility Standard:** [Public | Private -> Public | Very Private]

---

## 🛠️ Global Alignment & Invariants

This codebase strictly adheres to the core engineering principles, scripting standards, and structural invariants mandated by the organization. 

* **Scripting Guardrails:** All userland scripts (`.sh`, `.py`, `.awk`) inside this repository enforce the portable shebang syntax and a mandatory 4-line metadata header block.
* **Terminology & Definitions:** Operational concepts, naming matrices, and architectural definitions match our centralized single source of truth.

For complete compliance blueprints, operational roadmaps, and the global architecture manifest, refer back directly to the primary [TCOS Command Center Config](../.github).

---

## 📜 Governance & Guidelines
Contributions, architectural proposals, and documentation changes inside this node must follow our organizational frameworks. Review our global guidelines in the centralized [TCOS Glossary](../.github/blob/main/profile/GLOSSARY.md).
=======
**2026-08-16, same day, correction**: the first commit's message said "0s
complete" -- wrong, and worth leaving visible rather than rewritten.
What's actually complete is that this journal now exists and has its
first entry. Genesis itself is not done: no PEN filed yet, no root/
intermediate keys generated, on-prem git not built, the actual #102
ceremony hasn't happened. "Verified, not claimed" applies to this repo's
own commits too -- caught here, not smoothed over.

---

**2026-09-03** -- The first keys exist. `owner-dogfood` (lxc 102) now holds
an ECDSA P-384 root and intermediate:

    CN=TCOS Fleet Root CA (dogfood)
      SHA256 78:6F:14:5B:C7:89:DD:1D:32:DA:0C:26:2C:1C:CA:C4:
             DE:BF:3E:92:1A:8F:5F:69:E7:63:E7:07:B9:09:24:74
      not after 2036-08-31, basicConstraints CA:TRUE pathlen:1

    CN=TCOS Fleet Issuing CA (dogfood)
      SHA256 8C:51:5D:94:60:17:22:39:EC:18:49:8E:93:0E:88:E8:
             10:C6:71:BA:2C:45:CC:E2:70:D5:5E:E6:01:1E:5C:7B
      not after 2031-09-02, basicConstraints CA:TRUE pathlen:0

`openssl verify` returns OK. Private keys are mode 600 and have not left
that container. Fingerprints and subjects are published here because they
are inputs, not secrets -- that is this repo's rule and this is the first
entry to actually exercise it.

**No ceremony was performed.** No air gap. No SLIP-39 share split, no
share holders, no witnesses. No CP/CPS, no recorded key ceremony. This was
the operator's explicit call and is recorded rather than implied: *"I do
not want to do a real 1 at a time usb blah. just a dogfood, good enough."*

The keys are cryptographically real. The ceremony is not. `(dogfood)` is
in both common names so the marker travels on the certificate itself and
not only in a provenance file someone might not read.

It is also, by design, **not a submission candidate**. Mozilla accepts
only roots generated within the prior five years, effective 2026-07-01, so
a root created now and applied for in 2033 is disqualified by its age
having done nothing wrong. The eventual public root gets generated last.
This is the working root and is meant to be replaced.

Two roles, not one: the intermediate issues and the root sits unused. A
root that signs leaf certificates daily is a root you cannot protect.

**This corrects the 2026-08-16 entry**, which said "no root/intermediate
keys generated." That is no longer true. Still true from that entry:
[fleet-ops#102](https://github.com/Twin-Cities-Open-Systems/fleet-ops/issues/102)
is open, and the real ceremony has not happened.

What is honestly still missing: no CRL, no OCSP, no revocation path of any
kind. No ACME automation, which CA/Browser Forum ballot SC-081v3 makes
necessary before 47-day certificates arrive in March 2029. And the key
material is not replicated -- it exists on one container, on one disk.

Also today: an anchor generator finally exists. `library/py/hee_hash/soa.py`
could only ever verify, so both existing SOA capsules were produced by
hand from a six-step written procedure. `hee trust anchor` now writes one,
calling the same library that verifies it, and independently recomputes
the existing capsule's stool hash `c37e3951..6ffa2cfc` from the same real
facts without reading it. The identity chain still has no anchor in
`owner-dogfood` itself -- the CA is there and nothing attests it yet.

