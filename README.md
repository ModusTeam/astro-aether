<div align="center">

# 🌑 Aether

**The Alchemy Engine for Astro Content.**
**Turn raw thoughts into Starlight.**

[![License: MIT](https://img.shields.io/badge/License-MIT-purple.svg)](LICENSE)
[![Status: Prototype](https://img.shields.io/badge/status-prototype-blue.svg)]()
[![Lua](https://img.shields.io/badge/Lua-5.5-blue.svg)]()
[![Astro](https://img.shields.io/badge/Astro-5.17-orange.svg)]()

</div>

---

## The Problem

Astro is amazing, but managing `src/content` can be friction-heavy.
You have to deal with strict YAML Frontmatter, complex folder structures, and manual date formatting.
When you have a sudden idea, you don't want to wrestle with syntax—you just want to write.

> **Friction kills creativity.**
> Aether removes the syntax barrier between your brain and your blog.

---

## What is Aether?

Aether is a lightning-fast content generator written in **Lua**.
It watches a folder of "raw" drafts (simple text files) and transmutes them into fully valid, type-safe **Astro Content Collections** (`.md` / `.mdx`).

It acts as a **pre-processor** for your Astro build pipeline.

---

### The Transformation

**Input (Draft)** `_drafts/lua-idea.txt`:
```text
@slug: magic-of-lua
@tags: dev, minimalism
@status: draft

# Why Lua?
Because it is fast, small, and beautiful...
```

**Output (Astro)** `src/content/blog/magic-of-lua.md`:
```astro
---
slug: "magic-of-lua"
title: "Why Lua?"
date: 2026-02-19T10:00:00Z
tags: 
  - "dev"
  - "minimalism"
draft: true
---

Because it is fast, small, and beautiful...
```

---

## Goals

* 🎯 Zero-Friction Writing: Use a minimalist syntax (`@key: value`) instead of YAML.
* 🎯 Astro-First: Specifically designed to populate Astro Content Collections.
* 🎯 Blazing Fast: Written in Lua. Parses hundreds of files in milliseconds.
* 🎯 Smart Defaults: Automatically infers titles (from first H1) and dates (from file creation) if missing.
* 🎯 Dependency-Free: No heavy `node_modules`. Just a single Lua script.

---

## Who Is It For?

| Audience | Use Case |
|---|---|
| Minimalists | Keep your writing folder clean, separate from code |
| Astro Developers | Automate the boring parts of content management |
| Obsidian Users | Easily adapt raw vault notes for the web |

---

## Tech Stack

* **Core Logic**: Lua 5.5 / LuaJIT (for raw speed and pattern matching).
* **FileSystem**: `LuaFileSystem` (lfs) for directory traversal.
* **Target**: Generates Markdown/MDX compatible with Astro Content Layer.

---

## Usage (Concept)

1. Install Lua (if you are on Linux/Mac, you likely already have it).
2. Clone Aether into your Astro project root (or as a submodule).
3. Run the transmutation:
```bash
# In your package.json
"scripts": {
  "transmute": "lua aether/src/main.lua",
  "dev": "npm run transmute && astro dev"
}
```

---

## Roadmap

* [ ] **Core Parser**: Implement regex-like patterns in Lua to parse `@headers`.
* [ ] **Smart Inference**: Auto-detect Title from the first `# Header`.
* [ ] **Draft Management**: Automatically exclude files marked `@draft` from production builds.
* [ ] **Obsidian Mode**: Support `[[WikiLinks]]` to standard Markdown link conversion.
* [ ] **Watch Mode**: Re-run transmutation instantly when a draft file changes.

---

## Contributing

This project is currently a personal prototype ("Pet Project").

---

## License

MIT © 2026 - see [LICENSE](LICENSE) for details.
