# MADRE's Market · community modules

This is where modules that anyone builds with MADRE's SDK arrive to be published in the Market
(madre.run/mercado). Once published, it shows in every MADRE's Market with the «Community» label and
your name, and it updates itself when you publish a new version, without npm.

**It is curated.** MADRE's author reads every module and every new version before signing it. A
module runs inside MADRE with the permissions of whoever opens it, and the Market's modules update
themselves; that is why nothing is published without a person reading it.

## How to send yours

1. **Build it and try it** in your MADRE: with «Create your module» or by hand (`docs/SDK.md` in
   MADRE's repository).
2. **Send it.** In your module's card, «Send to the Market» checks it, leaves the two files in a
   folder and opens GitHub's page to upload them to `modulos/<id>/`: drag both in and press *Propose
   changes*; GitHub makes the fork and the pull request for you, no terminal. By hand:
   - fork this repository;
   - add `modulos/<id>/<id>.module.mjs` and `modulos/<id>/entrada.json`;
   - check it with `npx @jossuealcala/madre check-module --file modulos/<id>/<id>.module.mjs --entry modulos/<id>/entrada.json`;
   - open the pull request.
3. **The automatic check** loads your module, checks the entry and writes what it declares and what
   its code uses in the job's summary.
4. **The human review:** it is accepted, or changes are asked for in the same pull request.
5. **It is signed and published** on madre.run. You never need a key.

For a new version, open another pull request with a higher `version` and `changes`.

The fields of `entrada.json` are in LEEME.md (they are the same in both languages). By sending a
module you accept `TERMS.md`.
