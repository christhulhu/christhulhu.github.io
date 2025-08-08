---
title: "Semantic Versioning (SemVer)"
date: 2025-05-12
draft: false
tags: 
- versioning
- software-development
---

## Summary

**Semantic Versioning** (SemVer) is a versioning scheme for software that conveys meaning about the underlying changes through a structured version number format: `MAJOR.MINOR.PATCH`.

> Specification: <https://semver.org>

## Format

- **MAJOR**: Incompatible API changes
- **MINOR**: Backward-compatible new features
- **PATCH**: Backward-compatible bug fixes

## Rules

1. Start from `1.0.0` for production-ready projects.
2. Increment: 
   - MAJOR when breaking changes are introduced
   - MINOR when functionality is added in a backward-compatible way
   - PATCH when only bug fixes are introduced
3. Pre-release versions can be denoted with a hyphen, e.g. `1.0.0-alpha.1`
4. Build metadata can be appended with a plus, e.g. `1.0.0+20240512`

## Examples

| Version       | Meaning                                     |
|---------------|---------------------------------------------|
| `1.2.0`         | New features added, no breaking changes     |
| `2.0.0`         | Major change, breaks backward compatibility |
| `1.2.3`         | Minor bugfix only                           |
| `1.3.0-alpha.2` | Pre-release of next minor version           |

## Benefits

- Predictable upgrade paths
- Easier dependency management
- Clear communication between developers and users

## Criticism & Limitations

- Doesn’t cover internal or UI changes well
- Can be misused if rules aren’t followed strictly
- Sometimes overly rigid for rapid iteration cycles

## 