# Ana-9211

`she/her` | computer science student | learning in public

![focus: security and systems](https://img.shields.io/badge/focus-security%20%26%20systems-8b5cf6?style=flat-square)

I like building things from scratch, then figuring out what I misunderstood along the way. Most of my projects begin as coursework and turn into deeper rabbit holes.

My current interests are cybersecurity, systems, and the space between a tool that technically works and a tool whose behavior I can actually explain.

## Building now

### [Laptop Guardian](https://github.com/Ana-9211/Laptop-Guardian)

A local-first Windows maintenance and audit tool: PowerShell agents, a zero-dependency Node bridge on 127.0.0.1, and a React dashboard. Safe Mode is on by default, fixes come from a closed catalog of typed actions, and each one is shown, confirmed, verified and logged.

**Checked on Linux:** type check, ESLint and an ASCII-only check are clean, the dashboard builds, and 177 of 181 Node tests pass (3 are skipped because they need Windows PowerShell, and 1 scheduler-polling test fails here, where PowerShell is absent). **Not yet checked:** the PowerShell/Pester suites, the installer, and CI on GitHub. The 1.1.0 line is unreleased.

## Selected work

### [MCP-Sentinel](https://github.com/Ana-9211/mcp-sentinel)

A Python and TypeScript/JavaScript security auditor for MCP servers: 8 static checks over 6 attack surfaces, scored HTML reports, and SARIF 2.1.0 output. A guard refuses non-loopback dynamic targets.

**Checked:** all 85 tests pass, Ruff is clean, it reports nothing on its own source or on either clean control fixture, and it flags the vulnerable fixtures I scanned (impl-flaws, ts-tool-injection, tool-poisoning). `--fail-on` returns a non-zero exit code. **Not checked here:** the Docker compose path (the dynamic tests start the fixtures as local processes instead).

### [CTF-trial-and-error](https://github.com/Ana-9211/CTF-trial-and-error)

Four self-designed challenges (web, crypto, forensics, reverse engineering), each with a fixture, a solver and a writeup.

**Checked:** I ran the RSA, forensics and reverse-engineering solvers and each recovered its flag. The VM flag is accepted by the shipped binary. For the SSRF challenge I confirmed the blocklist rejects the literal metadata IP but lets through its decimal, hex and octal forms, which resolve to 169.254.169.254. **Not checked:** the SSRF challenge end to end, since it needs Docker networking.

### [Sigma detection project](https://github.com/Ana-9211/sigma-detection-project)

16 Sigma rules tagged with MITRE ATT&CK techniques, with Splunk conversions and per-rule writeups.

**Checked:** `sigma check` reports 0 errors on all 16 rules (run with the two MITRE tag validators off because they need network access). The committed validation snapshots show 215 matches across 15 rules; the 16th (the Sysmon T1087 rule) matched nothing, which the writeup documents and a Security-log rule (T1087b) then fixed. The raw EVTX corpus isn't in the repo, so I couldn't rerun those snapshots.

## More projects

- [Online Bookstore](https://github.com/Ana-9211/Software-Engineering-Project-): a MERN course project with sprint docs and CI. The client lints, builds and passes its 23 tests. The server's MongoDB-backed tests could not run in my environment, so I have not confirmed them.
- [PES-VCS](https://github.com/Ana-9211/PES1UG24CS058-pes-vcs): a small Git-style version control system in C. The Phase 1 and 2 unit tests and the end-to-end commit sequence pass.
- [Swarm Health](https://github.com/Ana-9211/Swarm_Health): a linear-algebra swarm analyser. Rerunning the checker reproduced every number in its committed output, the FastAPI backend loads with 14 routes, and the frontend builds.
- [p2p_fun](https://github.com/Ana-9211/p2p_fun): a peer-to-peer swarm in Python (tracker, DHT, Merkle and crypto modules). It compiles, and its two scripts run and print a node ID and a tracker signature, but there is no assertion-based test suite yet.
- [OS-Jackfruit](https://github.com/Ana-9211/OS-Jackfruit): a small container runtime in C with a kernel memory monitor. The user-space supervisor and workloads compile; I could not build or load the kernel module here.
- [Attendance Planner](https://github.com/Ana-9211/attendance): a browser and Python attendance calculator. Testing found and fixed a startup bug that stopped the web version's saved state from loading.
- [Standalone HTML demos](https://github.com/Ana-9211/standalone-html-demos), [Password Analyzer](https://github.com/Ana-9211/Password-2.0) and [Password Chaos](https://github.com/Ana-9211/password): single-page tools that load in headless Chromium with no script errors.

### Earlier projects, not run here

[Wavelink](https://github.com/Ana-9211/music_streaming) (TCP/TLS audio streaming) and [Traffic Classifier](https://github.com/Ana-9211/traffic-classifier) (POX and Mininet) compile or parse cleanly, but need audio hardware or Mininet/POX, so I haven't run them. [Platformer](https://github.com/Ana-9211/Platformer) is a Unity project with scenes and assets but no scripts yet.

## Learning direction

Linux and Python fundamentals, networking, security fundamentals, ethical hacking, web application security, blue-team detection engineering, and deeper security research.

I am working through these topics deliberately, with checkpoints and working explanations instead of trying to speed-run them.

> A passing test is not enough if it is testing the wrong thing.

<sub>Last audited 2026-10-12 by running each project's tests and solvers. "Not checked" means my environment couldn't run it, not that it fails.</sub>
