# ZK for Artists

---

## How Do You Prove an AI Model Is Actually Running?

Not just showing outputs. Proving which model, which version, which weights.

---

## How Do You Prove AI Training?

Verify datasets, training steps, and other inputs

---

## How Do Artists Prove Human Creative Input?

Distinguish human process from AI generation. Prove the artist's hand in the work.

---

## Enter Zero Knowledge

Technology that lets you prove all of this without revealing your underlying data.

---

## Use Cases of ZK

Reveal outputs without revealing inputs: voting results, identity verification, ownership proofs.

---

## What is ZK?

Verifiable, private computation. Prove calculations correct without showing the work.

---

## Succinctness

Small proof, fast verification. Even for massive computations.

---

## Confidentiality

Prove facts while keeping the underlying data completely secret.

---

## Leading zkVMs

SP1, RISC Zero, Jolt. Write Rust, get ZK proofs.

---

## Example - Fibonacci in Jolt

```rust
#[jolt::provable]
fn fib(n: u32) -> u128 {
    let mut a: u128 = 0;
    let mut b: u128 = 1;
    for _ in 1..n {
        let sum = a + b;
        a = b;
        b = sum;
    }
    b
}
```

---

## zkVM Trade-off

You get succinctness (small proofs) but NOT automatic confidentiality. Data is public by default.

---

## Usage Today

• Verifying TEE attestations
• Rollup bridges

---

## So Why Aren't zkVMs Everywhere?

1M-5M× overhead → 50K-10K× today → ~10× in 3-5 years.

---

## What Are TEEs?

Trusted hardware (Intel SGX, AMD SEV) that runs code in isolated enclaves with attestation.

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

