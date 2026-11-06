# Diagrams — Student Success Assistant

These are simple diagrams to help a beginner see how the product works. They match the spec in `docs/03-spec.md`. No image files are used — the diagrams below are written in Mermaid text, which GitHub renders as a picture.

## 1. How it works

```mermaid
flowchart TD
    A["Notice, email, or LMS post"] --> B["AI extracts title, subject, and deadline"]
    B --> C["Student confirms every extraction"]
    C --> D["Save only the confirmed deadlines"]
    D --> E["Calculate attendance, showing the maths"]
    E --> F["Send one weekly digest: due, at risk, one action per risk"]
```

What this shows: the AI suggests, the student approves. Nothing is saved without confirmation, and every attendance figure shows how it was calculated.

## 2. User journey

```mermaid
flowchart TD
    A["Student gets notices in many different places"] --> B["Student confirms deadlines in one place"]
    B --> C["Student sees attendance percent and classes needed"]
    C --> D["Student gets an early weekly warning"]
    D --> E["Student acts before the deadline or the threshold"]
    E --> F["Student stays on track, with the advisor involved only with consent"]
```

What this shows: before the product, a missed notice could mean a missed deadline or an attendance shortfall found too late. After it, the student sees the risk early, while there is still time to act.

## 3. Eval and release flow

```mermaid
flowchart TD
    A["Build the 50-document test set"] --> B["Test extraction and attendance maths by hand"]
    B --> C{"Is deadline accuracy at least 98 percent, and attendance maths 100 percent?"}
    C -- No --> D["Fix the extraction rules"]
    D --> B
    C -- Yes --> E["Stage 1: you plus 3 students, 2 weeks, every extraction confirmed"]
    E --> F["Stage 2: 30-student cohort, advisor reviews warning accuracy weekly"]
    F --> G["Wider release only if warning precision is at least 90 percent"]
```

What this shows: a wrong deadline is a critical failure, so the product is tested hard first and released in stages. Wider release depends on real warning accuracy, not on a demo.
