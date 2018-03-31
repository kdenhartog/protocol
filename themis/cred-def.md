# Credential Definition

A credential definition associates an issuer and their public issuance
keys with a particular schema and revocation strategy. Credential
definitions are published on the ledger.

```json
{
  "schema_ref": "<schema id>",
  "primary": {
    "sig_type": "<primary credential signature scheme>",
    "verification_key": { <scheme-specific public key material> }
  },
  "revocation": {
    "sig_type": "<revocation signature scheme>",
    "verification_key": { <scheme-specific public key material> }
  }
}
```
<span style="color:yellow">TODO: Needs Issuer reference</span>

## Primary Credential Signature Schemes
This is the value of the "primary" element in a Credential Definition.

There is currently only one scheme in use today: CL.
###The "CL" Primary Credential Signature Scheme
```json
{
  "sig_type": "CL",
  "verification_key": {
    "rctxt": "<large integer>",
    "rms": "<large integer>",
    "n": "<large integer>",
    "s": "<large integer>",
    "r": {
      "<field1>": "<large integer>",
      "<field2>": "<large integer>",
      ...
    }
  }
}
```

## Revocation Signature Schemes
This is the value of the "revocation" element in a Credential Definition.

There is currently only one scheme in use today: CL(TODO).
###The "CL(TODO)" Revocation Signature Scheme
```json
{
  "sig_type": "(TODO: what do we all our revocation sig scheme?)",
  "verification_key": {
    "y": "<large random number in G2>",
    "pk": "<large random number in G1>",
    "h": "<large random number in G1>",
    "h0": "<large random number in G1>",
    "h1": "<large random number in G1>",
    "h2": "<large random number in G1>",
    "htilde": "<large random number in G1>",
    "hhat": "<large random number in G2>",
    "g": "<large random number in G1>",
    "gprime": "<large random number in G2>",
    "u": "<large random number in G2>",
    "qr": "<large number specifying the order of the pairing group>",
  }
}
```