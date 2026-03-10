
## proof-bundle-format.md

```markdown
# Gravity Proof Bundle Format

This document describes the high-level structure of a Gravity Bitcoin proof bundle.

## Purpose

A Gravity proof bundle is a deterministic certification package generated from a Bitcoin transaction review workflow. Its purpose is to provide a portable verification package containing transaction evidence, analysis material, integrity hashes, and verification output.

## Bundle Objectives

A valid Gravity proof bundle should support:

- transaction reference identification
- artifact integrity checking
- structured analysis review
- independent third-party inspection
- reproducible verification steps

## Example Bundle Layout

```text
example-bundle/
├── artifact.json
├── analysis.json
├── hash_manifest.txt
└── verification_report.txt
