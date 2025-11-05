# ZK for Artists

---

## Use Cases of ZK

Reveal outputs without revealing inputs: voting results, identity verification, ownership proofs.

---

## What is ZK?

Verifiable, private computation—prove calculations correct without showing the work.

---

## Succinctness

Small proof, fast verification—even for massive computations.

---

## Confidentiality

Prove facts while keeping the underlying data completely secret.

---

## Leading zkVMs

SP1, RISC Zero, Jolt—write Rust, get ZK proofs.

---

## Example - Fibonacci in SP1

```rust
sp1_zkvm::entrypoint!(main);
pub fn main() {
    let n = sp1_zkvm::io::read::<u32>();
    let (mut a, mut b) = (0, 1);
    for _ in 0..n {
        (a, b) = (b, (a + b) % 7919);
    }
    sp1_zkvm::io::commit(&b);
}
```

---

## zkVM Trade-off

You get succinctness (small proofs) but NOT automatic confidentiality—data is public by default.

---

## Usage Today

• Verifying TEE attestations
• Rollup bridges

---

## So Why Aren't zkVMs Everywhere?

1M-5M× overhead → 50K-10K× today → ~10× in 3-5 years.

---

## TEEs vs zkVMs

TEEs: Pragmatic, native speed, weaker guarantees.
zkVMs: Mathematical proof, huge overhead, strongest guarantees.

---

## Verifiable AI

TEEs: Run full AI models at native speed.
zkVMs: Verifiable inference still impractical—too slow.

---

## The Path Forward

TEEs will deliver verifiable compute first; zkVMs will complement as performance improves.