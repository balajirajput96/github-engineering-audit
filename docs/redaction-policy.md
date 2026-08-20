# Redaction and Retention Policy

## Allowed records

The archive may record repository paths, branches, commit identifiers, workflow names, check conclusions, test commands at a category level, execution timestamps, tool availability, connector names, and approved scheduler metadata.

## Prohibited records

The archive must never store passwords, OAuth bearer values, API keys, tokens, session cookies, private keys, OTPs, raw shell-history lines, browser state, `.env` contents, Git credential helpers, or authentication database files.

## Validation before publication

Every generated report is scanned against a denylist for credential-related keys and common secret-bearing formats before it is committed. A failed redaction check blocks publication and records a non-sensitive failure category instead.

## Retention

Daily reports are versioned in Git. The continuity record retains the latest known state and references prior reports by path; it does not replicate their full contents. Historical repositories and worktrees are inventoried as metadata and are not copied into this archive.

