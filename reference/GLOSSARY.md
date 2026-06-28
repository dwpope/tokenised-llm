# Glossary — Tokenised LLM

The shared vocabulary for this course. Once a term is defined here, every lesson uses it
the same way. Linked from lessons.

- **Tokenised LLM** — an LLM system where the people who contributed knowledge are paid
  (in tokens or money) whenever someone else's query uses that knowledge. Two layers:
  *attribution* (who contributed to this answer?) and *settlement* (paying them).

- **Attribution** — determining which contributions were responsible for a given output,
  and how much. The hard part of a tokenised LLM.

- **Settlement / reward layer** — metering usage and splitting payment by attribution.
  The comparatively easy part (standard payments/smart-contract plumbing).

- **Baking (weights)** — folding knowledge into the model's parameters during training.
  Powerful, but blends every contribution together → attribution becomes approximate and
  expensive.

- **Retrieval (RAG)** — keeping knowledge as separate documents in a store and pulling the
  relevant pieces in at query time. The base model reasons; the store supplies knowledge.
  Because you *know which chunks were retrieved*, attribution is provable.

- **Bake ↔ Retrieve spectrum** — the core mental model. The more knowledge lives in
  retrievable, discrete units, the easier attribution is. The more it's baked into weights,
  the harder.

- **RAG** — Retrieval-Augmented Generation. The architecture underlying the retrieve end of
  the spectrum.

- **Influence functions** — a method to estimate how much a single training example affected
  a model's behaviour, without retraining. Approximate; assumption-laden at LLM scale.
  (e.g. TRAK.)

- **TRAK** — a scalable influence-function-style attribution method that approximates
  influence using a few model checkpoints. Still approximate.

- **Data Shapley** — a game-theory method (Shapley values) for *fairly* dividing credit
  among data contributors. Provably fair, but exact computation needs exhaustive retraining
  → intractable at scale; used via approximations.

- **LoRA adapter** — a small trainable module bolted onto a base model. Can be *owned* by a
  contributor, so activating it is attributable. (Modular-ownership approach.)

- **Mixture of Experts (MoE)** — architecture where a router sends each query to a subset of
  "expert" sub-networks. If experts are owned, routing becomes an attribution signal.

- **Proof of Contribution** — a contributor-supplied or protocol-defined function that scores
  how much/what quality a contribution adds (term used by Vana's DataDAOs).

- **Stake-weighting** — distributing rewards in proportion to how many tokens a participant
  has staked. The recurring failure mode: rewards track *stake*, not *contribution quality*
  (seen in both Bittensor and Vana).
