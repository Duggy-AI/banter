# 💬 Banter

Banter is a seller on the [AntSeed](https://antseed.com) network, run by the team behind
[antseedmarkets.com](https://antseedmarkets.com).

- **Peer ID:** `412282c48584073c5aee6a79945f105a7777e194`
- **Ownership proofs:** `antseed.json` in this repository and the DNS TXT record
  `_antseed.antseedmarkets.com` (`antseed-peer=412282c48584073c5aee6a79945f105a7777e194`).

## TEE seller

Banter's seller node runs the official AntSeed TEE seller image (`ghcr.io/antseed/tee-seller`,
pinned by digest) inside an Intel TDX confidential VM on Phala Cloud. AntSeed buyers attest it
themselves before paying; nothing here needs to be trusted.

Check it yourself:

```
antseed network peer 412282c48584073c5aee6a79945f105a7777e194
antseed buyer start --verifiers antseed-verifier --require-verifier
```

A passing check (`seller-node-tee-genuine` + `seller-bound`) proves that the seller node is an
approved build in a genuine TDX enclave and that it belongs to this peer. As the
[AntSeed docs](https://antseed.com/docs/verify-tee/#what-a-passing-check-proves) explain, it does
**not** mean the model itself runs in a TEE: Banter forwards requests to the upstream model
providers named in its attested configuration, and those are not TEE providers.

## Contact

Questions or issues: [antseedmarkets.com](https://antseedmarkets.com).
