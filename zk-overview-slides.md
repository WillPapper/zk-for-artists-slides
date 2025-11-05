# ZK for Artists

---

## Slide 0: Use Cases of ZK

Reveal outputs without revealing inputs: voting results, identity verification, ownership proofs.

---

## Slide 1: What is ZK?

Verifiable, private computation—prove calculations correct without showing the work.

---

## Slide 2: Succinctness

Small proof, fast verification—even for massive computations.

---

## Slide 3: Confidentiality

Prove facts while keeping the underlying data completely secret.

---

## Slide 4: Leading zkVMs

SP1, RISC Zero, Jolt—write Rust, get ZK proofs.

---

## Slide 5: Example - Fibonacci in SP1

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

## Slide 6: zkVM Trade-off

You get succinctness (small proofs) but NOT automatic confidentiality—data is public by default.

---

## Slide 7: Usage Today

• Verifying TEE attestations
• Rollup bridges