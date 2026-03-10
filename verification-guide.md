
## verification-guide.md

```markdown
# Gravity Verification Guide

This guide explains how a reviewer can inspect a Gravity Bitcoin proof bundle at a high level.

## Goal

The purpose of verification is to confirm that the bundle is internally consistent and that its included artifacts have not been altered.

## Basic Verification Steps

### 1. Inspect bundle contents

Confirm the expected files are present, such as:

- `artifact.json`
- `analysis.json`
- `hash_manifest.txt`
- `verification_report.txt`

### 2. Review the verification report

Read `verification_report.txt` for the stated outcome and summary of checks.

### 3. Check integrity hashes

Use a SHA-256 tool or equivalent to compute the hash of each included file and compare the results against `hash_manifest.txt`.

### 4. Review structured files

Inspect `artifact.json` and `analysis.json` to confirm they are logically consistent with one another.

Examples of consistency checks may include:

- same TXID reference
- same certification reference where applicable
- no obvious field mismatch between artifact and report
- no broken relation between analysis and manifest

### 5. Preserve the reviewed bundle

If the bundle is being used for audit, dispute, or recordkeeping purposes, preserve the original downloaded form and record the date/time of review.

## Verification Outcome Types

A reviewer may classify a bundle as:

- **Verified** — file integrity and internal consistency checks pass
- **Inconsistent** — fields or references conflict
- **Incomplete** — required files are missing
- **Tampered / Failed Integrity** — computed hashes do not match the manifest

## Minimal Command Example

Example SHA-256 workflow on Linux:

```bash
sha256sum artifact.json analysis.json verification_report.txt
