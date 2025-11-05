# ZK for Artists

### Glitch Artist Residency - November 5th, 2025

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

## Zero Knowledge Cryptography

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

## Privacy

Prove facts while keeping the underlying data completely secret.

---

## Leading zkVMs

SP1, RISC Zero, Jolt. Write Rust, get ZK proofs.

---

## Example - Fibonacci in Jolt (Guest)

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

## Generating the Proof (Host)

```rust
fn main() {
    // Compile and preprocess the program
    let program = guest::compile_fib("/tmp/targets");
    let prover = guest::build_prover_fib(program, preprocessing);

    // Generate proof for fib(50)
    let (output, proof, io) = prover(50);

    // Verify the proof
    let is_valid = verifier(50, output, io, proof);
    println!("Valid: {is_valid}");
}
```

---

## Plot Twist: zkVMs Aren't Zero-Knowledge Yet

You get succinctness (small proofs) but NOT automatic privacy. Data is public by default.

---

## Usage Today

• Verifying complex signatures
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
