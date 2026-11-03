# adequate-footwear

Optional files and tools associated with AdequateFootwear's geocaches.

**Live site:** https://adequatefootwear.github.io/adequate-footwear/

None of these tools is needed to solve any cache. Everything required is on each cache page and in the field. The tools run entirely in the browser and send nothing anywhere.

## Tools

| Tool | Address | What it does |
|---|---|---|
| Read the Sign | https://adequatefootwear.github.io/adequate-footwear/read-the-sign/ | Decodes (line, word, character) sign puzzles, with adjustable counting rules and a trace of every triple. First built for GCAZ6T9. |
| Asymmetric Cryptosystems (folder) | https://adequatefootwear.github.io/adequate-footwear/asymmetric/ | Guided worksheets for public-key puzzles, one per cryptosystem. Named for the cryptosystem, not the cache, so solvers still work out which system a puzzle uses. |
| ↳ Diffie–Hellman | https://adequatefootwear.github.io/adequate-footwear/asymmetric/diffie-hellman/ | Factors p − 1, recovers either side’s secret by discrete log (Pohlig–Hellman, parallel Pollard rho), and rebuilds the shared secret, with a note that the message may still need a classical decryption. |
| ↳ ElGamal | https://adequatefootwear.github.io/adequate-footwear/asymmetric/elgamal/ | Finds the receiver’s x or the sender’s k by discrete log, rebuilds the shared secret, divides it out, and reads the message. |
| ↳ Rabin | https://adequatefootwear.github.io/adequate-footwear/asymmetric/rabin/ | Factors n, takes square roots modulo each prime (Euler shortcut or Tonelli–Shanks), combines them with the CRT, and reads the four candidates. |
| ↳ RSA | https://adequatefootwear.github.io/adequate-footwear/asymmetric/rsa/ | Factors n, builds φ(n) and d, decrypts, and reads the message (ASCII, A=1, hex), with plain-language checks for dropped digits and numbers in the wrong box. |
