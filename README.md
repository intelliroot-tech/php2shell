# PHP2Shell Exposure Checker

A desktop toolkit (Windows, Linux) for finding and remediating
**CVE-2026-109618** / **CVE-2026-109619** ("PHP2Shell") — the October 2026
PHP engine vulnerabilities allowing unauthenticated RCE and memory
disclosure on unpatched PHP builds. Built by IntelliRoot.

**Scope: your own infrastructure only.** Every check is passive detection or
an explicitly user-confirmed remediation step — nothing here sends an
exploit payload. Each tab has an "i" info button explaining exactly what it
does and doesn't test.

## Tabs

- **Start Here** — guided wizard that routes you to the right tool based on
  what access you have.
- **Network Scan** — zero-payload PHP version fingerprinting across IP
  ranges, plus an opt-in exposed-`phpinfo()` check.
- **Code / Config Audit** — scans a local project for version pins and the
  two documented partial mitigations (`session.upload_progress`,
  `memory_limit`).
- **Remote Check & Upgrade (SSH)** — authoritative version/config check over
  SSH, with a guided, reviewed-before-running upgrade plan.
- **SFTP (Shared Hosting)** — same audit + mitigation for hosts where SSH
  has no shell (common on shared WordPress/Joomla hosting), via
  `.user.ini`/`.htaccess`.
- **Log Scan** — finds PHP/FPM crash signatures (direct evidence) and
  suspicious access-log patterns (not proof) for possible exploitation.

None of this patches the PHP engine itself — upgrading PHP is the only real
fix. The app's job is telling you accurately whether you need to, and
making that upgrade as easy as possible.

