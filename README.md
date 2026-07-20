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

## Store & support

**[structos.lemonsqueezy.com](https://structos.lemonsqueezy.com)**

<sub>New capabilities are added continuously. This repository hosts the downloads only — no source code.</sub>
