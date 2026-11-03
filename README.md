# adequate-footwear

Optional files and tools associated with AdequateFootwear's geocaches.

**Live site:** https://adequatefootwear.github.io/adequate-footwear/

None of these tools is needed to solve any cache. Everything required is on each cache page and in the field. The tools run entirely in the browser and send nothing anywhere.

## Tools

| Tool | Address | What it does |
|---|---|---|
| Read the Sign | https://adequatefootwear.github.io/adequate-footwear/read-the-sign/ | Decodes (line, word, character) sign puzzles, with adjustable counting rules and a trace of every triple. First built for GCAZ6T9. |
| Asymmetric Cryptosystems (folder) | https://adequatefootwear.github.io/adequate-footwear/asymmetric/ | Guided worksheets for public-key puzzles, one per cryptosystem. Named for the cryptosystem, not the cache, so solvers still work out which system a puzzle uses. |
| ↳ Symmetric and Asymmetric | https://adequatefootwear.github.io/adequate-footwear/asymmetric/symmetric-and-asymmetric/ | Lesson: classical ciphers (Caesar, Vigenère, Gronsfeld), the key-sharing problem, one-way functions, encryption versus key exchange, and the solver as Eve. |
| ↳ Modular Arithmetic Basics | https://adequatefootwear.github.io/adequate-footwear/asymmetric/modular-arithmetic/ | Interactive lesson: clock arithmetic, inverses, powers and generators, Fermat, Euler and φ, primes and factoring, square-and-multiply and extended Euclid, the CRT, square roots mod a prime, Pohlig–Hellman, a tiny RSA exercise, and Conway’s Doomsday rule. |
| ↳ From Letters to Numbers | https://adequatefootwear.github.io/adequate-footwear/asymmetric/letters-to-numbers/ | Lesson and converter: letter positions, character codes (ASCII and Unicode), hex bytes, coordinates as digits, lost leading zeros, and block alignment. |
| ↳ Diffie–Hellman | https://adequatefootwear.github.io/adequate-footwear/asymmetric/diffie-hellman/ | Factors p − 1, recovers either side’s secret by discrete log (Pohlig–Hellman, parallel Pollard rho), and rebuilds the shared secret, with a note that the message may still need a classical decryption. |
| ↳ ElGamal | https://adequatefootwear.github.io/adequate-footwear/asymmetric/elgamal/ | Finds the receiver’s x or the sender’s k by discrete log, rebuilds the shared secret, divides it out, and reads the message. |
| ↳ Goldwasser–Micali | https://adequatefootwear.github.io/adequate-footwear/asymmetric/goldwasser-micali/ | Factors n, checks the non-square x, turns each ciphertext number into a bit by Euler’s criterion, and reads the bits (8-, 7- or 5-bit). |
| ↳ Massey–Omura | https://adequatefootwear.github.io/adequate-footwear/asymmetric/massey-omura/ | Three-pass protocol: breaks Bob’s lock or Alice’s unlock by discrete log and recovers the message. |
| ↳ Okamoto–Uchiyama | https://adequatefootwear.github.io/adequate-footwear/asymmetric/okamoto-uchiyama/ | Factors n = p²q, checks h = gⁿ, applies L modulo p², and reads the message. |
| ↳ Paillier | https://adequatefootwear.github.io/adequate-footwear/asymmetric/paillier/ | Factors n, builds λ and μ, decrypts with the L function modulo n², and recovers the sender’s r as a check. |
| ↳ Rabin | https://adequatefootwear.github.io/adequate-footwear/asymmetric/rabin/ | Factors n, takes square roots modulo each prime (Euler shortcut or Tonelli–Shanks), combines them with the CRT, and reads the four candidates. |
| ↳ RSA | https://adequatefootwear.github.io/adequate-footwear/asymmetric/rsa/ | Factors n, builds φ(n) and d, decrypts, and reads the message (ASCII, A=1, hex), with plain-language checks for dropped digits and numbers in the wrong box. |
| ↳ Schmidt–Samoa | https://adequatefootwear.github.io/adequate-footwear/asymmetric/schmidt-samoa/ | Factors N = p²q, builds d = N⁻¹ mod lcm(p − 1, q − 1), and decrypts modulo pq. |
