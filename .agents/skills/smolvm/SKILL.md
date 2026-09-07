---
name: smolvm
description: Use when the user mentions `smolvm`, asks to run a command in a smolvm microVM, manage smolvm machines, write a Smolfile, package a workload, or use the smolvm HTTP API. Run `smolvm --help` first to inspect the CLI's current capabilities and guidance.
---

# smolvm

When this skill is triggered, first run:

```bash
smolvm --help
```

Use the current CLI help as the source of truth before proposing or executing smolvm commands. For a specific command's flags or behaviour, also run its subcommand help, for example:

```bash
smolvm machine --help
smolvm machine run --help
smolvm pack --help
```

## Safety defaults

- Do not enable networking unless the workload needs it; `smolvm` networking is off by default.
- Use `machine run` for disposable work and named `machine create` / `start` / `exec` for work that must persist.
- Prefer `--ssh-agent` over copying private keys into a VM.
- Pass secrets using `--secret-env` or `--secret-file`; never put their values in a Smolfile, shell history, or command output.
- Confirm before creating, starting, stopping, deleting, or modifying a persistent named machine unless the user explicitly requested the action.
