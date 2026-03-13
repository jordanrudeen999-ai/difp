# Contributing to DIFP

Thank you for your interest in contributing to the Djowda Interconnected Food Protocol.

DIFP is a provisional open specification — v0.1 was published specifically to invite review, critique, and real-world implementation feedback before anything is locked down. Every contribution makes the protocol more useful to the people who need it most.

---

## Ways to contribute

### 1. Implement it and report back

The most valuable contribution right now is building a DIFP-conformant node and telling us where the spec is unclear, missing, or wrong.

- Port `geoToCellNumber` to your language and validate against the [test vectors](./test-vectors/grid.json)
- Stand up a presence store and expose the `/.well-known/difp/` endpoints
- Build the trade engine and run through the status lifecycle

When you have something working — even partially — open an [Implementation Report](../../issues/new?template=implementation_report.md). We want to know:
- What you built, in what language/stack
- What was clear in the spec
- What was ambiguous or missing
- Any decisions you had to make that the spec didn't cover

### 2. Review the specification

Read [SPEC.md](./SPEC.md) or the [web version](https://djowda.com/difp) and open a [Spec Feedback](../../issues/new?template=spec_feedback.md) issue for anything that is:

- Ambiguous or open to multiple interpretations
- Internally inconsistent
- Missing a case that needs to be covered
- Unnecessarily restrictive for legitimate use cases
- In conflict with an existing standard (GS1, W3C DID, RFC, etc.)

### 3. Contribute test vectors

If you port the grid algorithm to a new language, please contribute your test suite to `test-vectors/`. A pull request adding `test-vectors/grid_{language}.json` with your validation cases is always welcome.

### 4. Share use cases

If you represent an NGO, cooperative, government food agency, or research institution with a food coordination problem this protocol should address — open an issue with the `use-case` label. These shape the v0.2 roadmap directly.

---

## What we are NOT looking for right now

- Changes to the `geoToCellNumber` constants (CELL_SIZE_METERS, NUM_COLUMNS, NUM_ROWS). These are fixed by design — changing them breaks compatibility with every other implementation. If you have a strong argument for why they should change, open a discussion issue tagged `breaking-change` and make the case.
- New canonical component type codes. The 10 types in Section 2 are the canonical set. Custom types are supported via the extension mechanism — you don't need a PR for that.
- Transport-specific implementation details. The spec is intentionally transport-agnostic. Implementation guides for specific backends (Firebase, PostgreSQL, DynamoDB) belong in community wikis or separate repos, not the core spec.

---

## Pull request guidelines

For spec changes:

1. Open an issue first and discuss before writing a PR — spec changes affect all implementations
2. Reference the section number(s) you are modifying
3. Explain the problem the change solves and any tradeoffs
4. If your change affects the `geoToCellNumber` algorithm or the TradeMessage schema, it requires explicit sign-off from the Djowda Platform Team before merge

For everything else (README fixes, test vectors, typos, CONTRIBUTING updates):

1. Fork the repo
2. Create a branch: `git checkout -b fix/description-of-change`
3. Make your changes
4. Open a PR with a clear description

---

## Code of conduct

This project follows the [Contributor Covenant](https://www.contributor-covenant.org/version/2/1/code_of_conduct/) v2.1.

The short version: be direct, be kind, assume good faith. Critique the spec, not the person. We are all trying to make food coordination less broken.

---

## Questions?

Open a [Discussion](../../discussions) or email [sales@djowda.com](mailto:sales@djowda.com).
