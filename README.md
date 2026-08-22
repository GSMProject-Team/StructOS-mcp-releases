<div align="center">

# StructOS

### AI automation for structural engineers — right inside your CAD workflow

**LIRA-SAPR · Tekla Structures · AutoCAD**, driven from Claude Code, OpenAI Codex, or Cursor.

[**⬇ Download**](../../releases/latest) · [**🛒 Buy a license**](https://structos.lemonsqueezy.com) · [Store](https://structos.lemonsqueezy.com)

</div>

---

## What it does

StructOS is an MCP server that plugs your engineering software into an AI assistant, so you can
do hours of repetitive structural work with a single sentence:

- **Transfer whole models between LIRA-SAPR and Tekla** — columns, beams, slabs and grids, concrete
  *and* steel, with rolled profiles matched to the Tekla GOST catalogue.
- **Edit Tekla models from chat** — cut stair openings (проёмы) in slabs, build stair
  stringer↔truss connections, railings and finials — placed correctly in the model's coordinate
  system (requires Tekla Structures installed).
- **Read a live LIRA-SAPR model** over COM — elements, sections, materials, results, and load
  combinations (РСН / РСУ).
- **Generate reinforcement (КЖ) drawings and rebar specs** from LIRA results, to СП РК / ГОСТ.
- **Check steel connections in IDEA StatiCa** (CBFEM) — push joint forces from LIRA to an IDEA
  Unity Check, right from chat (requires IDEA StatiCa installed).
- **Read live Revit models** via pyRevit — elements, quantities and more (requires pyRevit installed).
- **Search your building-code library** — point it at your own СП РК / ГОСТ / Eurocode files.
- **Read DWG / DXF and IFC files** without opening the CAD application.

### Ask it things like

> *"Read the open LIRA model and copy the whole frame into Tekla."*
>
> *"Generate КЖ reinforcement drawings from the LIRA results."*
>
> *"What's the snow load per СП РК at 1000 m altitude?"*
>
> *"Check this beam-to-column joint in IDEA StatiCa and give me the Unity Check."*
>
> *"Read this DWG and list the column grid."*

## How it works

1. StructOS runs on **your** Windows machine, next to LIRA-SAPR / Tekla / AutoCAD.
2. You connect it to **your own** AI client (Claude Code, Codex, or Cursor) — you bring your own AI account.
3. Every tool runs locally against your open CAD software. Your models never leave your computer.

## Quick start

1. **[Buy a license](https://structos.lemonsqueezy.com)** — you get a key by email (one key = one computer).
2. **[Download `StructOS-win64.zip`](../../releases/latest)** and unzip it (e.g. to `C:\StructOS\`).
3. Open `StructOS/README.txt`, add StructOS to your AI client's config, and paste your license key.
4. Verify: run `structos-mcp.exe --checklicense` → you should see **`LICENSE OK`**.

## Requirements

- Windows 10/11 (64-bit)
- LIRA-SAPR 2024 · Tekla Structures 2021+ · AutoCAD — whichever you drive, installed
- An MCP-capable AI client with your own account (the AI is **not** included)

## Found a bug? Or a wrong number?

Both are worth reporting, and the second one especially — a tool that returns a plausible but wrong
force, area of reinforcement or profile is the kind of thing we cannot find without you.

**Easiest way — ask your assistant:**

> *"Отправь баг-репорт по этой ошибке."* · *"Send a bug report for that error."*

It calls `structos_report_bug`, which reads StructOS's own local log of tool calls, masks file
paths, your user name, e-mail and licence key, and shows you the result. Nothing is sent anywhere.
If you are happy with what you see, it opens a GitHub form with the technical fields already filled
in and **you** press Submit.

Your conversation is never read. The MCP protocol gives a server no access to it, and StructOS does
not reach around that — the log of its own tool calls is both more useful for debugging and none of
our business beyond that.

**Or file it by hand:** **[open an issue](../../issues/new/choose)** — there is a form for a crash,
one for a wrong engineering result, and one for a tool you wish existed.

Please paste text output rather than model files, and mask project or client names if they are
confidential.

## Keeping up to date

**From v0.1.5 on, StructOS updates itself.** You do not have to watch this page, and you never have
to change your config — the path your AI client points at stays exactly the same.

How it works: it checks the releases page about once a day, and when a new version is out it
downloads the zip, checks it against the checksum published with the release, and installs it **at
the end of a session** — the one moment nothing is running. Before the old version is removed, the
new one has to start and report its version; if it cannot, the update is rolled back and you keep
working on what you had.

Which version you are on:

```
structos-mcp.exe --version
```

**If you would rather decide yourself**, two environment variables:

| Variable | Effect |
| --- | --- |
| `STRUCTOS_AUTO_UPDATE=0` | Never install anything. New versions are only announced. |
| `STRUCTOS_PIN_VERSION=v0.1.5` | Stay on this exact version. |
| `STRUCTOS_NO_UPDATE_CHECK=1` | Do not contact GitHub at all. |

Pinning is worth knowing about if you are running an object through expert review and the numbers
must not move under you.

**What the check sends:** one anonymous request to GitHub for the public releases page — no model
data, no licence key, nothing identifying you or your projects. The checksum proves the download
arrived intact. It does not prove who built it: StructOS is not code-signed, so if that matters to
your IT policy, set `STRUCTOS_AUTO_UPDATE=0` and update by hand from the
**[releases page](../../releases/latest)**.

## Store & support

**[structos.lemonsqueezy.com](https://structos.lemonsqueezy.com)**

<sub>New capabilities are added continuously. This repository hosts the downloads only — no source code.</sub>
