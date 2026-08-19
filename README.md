# DriverLens

> **Understand why Windows chose your driver.**

You installed a newer driver by hand, Windows did not apply it, and it never told you why.
DriverLens answers two questions against the real data on your machine:

1. **which** of the installed driver packages is actually in use;
2. **why the others are not** — including the one you just tried to install.

Filter by a term you actually know (the INF name, a version, the vendor) and you get the
explanation of Windows' choice next to **the raw data it is derived from**: the rank value, the ID
that matched, the position in the list. Windows publishes no rationale — the sentence is a
deterministic rendering of exact values, and you must be able to verify it.

DriverLens also lists **what was installed or attempted recently**, read from `setupapi.dev.log`,
and links each operation back to its package.

> **The user interface is in Italian.**

## Download

**[DriverLens-portatile.zip](https://github.com/aikabox/DriverLens/releases/latest/download/DriverLens-portatile.zip)** — always the latest version.

Extract the folder anywhere, including a USB stick, and run `DriverLens.exe`. There is no installer
and no setup step. The three program files must stay together in the same folder.

**Requirements:** Windows 10 or 11. It uses the .NET Framework 4.8 already included in both. It does
not request administrator rights.

## It does not modify the system

The program **contains no declaration capable of installing, uninstalling or modifying a driver**,
no system file, no registry key, no Driver Store package. What is not declared cannot be called,
not even by a defect. It runs **without administrator rights** — the second barrier.

The only write it can perform is **exporting a package**, at your request, into a folder you pick.

## First run: what Windows will show you

The executable is **not code-signed**, so Windows treats it as an unknown program:

- **"Windows protected your PC"** — click *More info*, then *Run anyway*.
- If the extracted files do not start, right-click the downloaded **zip** → *Properties* → tick
  *Unblock* → *OK*, then extract again. Windows marks files that come from the internet.

## Verify what you downloaded

Compare the archive against the hash published on the release page:

```powershell
Get-FileHash DriverLens-portatile.zip
```

Version 1.0.0 — SHA-256: `67DF1E749479E97AABB3981B4467E6B9E923F232FB49A003769C2B6C5946AF03`

The source code is not published at this time.
