# Vib Tools Documentation (`@vibdocs`)

**Official public documentation repositories for [Vib Tools](https://vib.tools/) products.**

This GitHub organization hosts clean, standalone documentation repositories—containing only user guides, setup manuals, and configuration metadata—so end users, teams, and contributors can read, search, or suggest documentation improvements in one place without digging through application source code.

> **Looking to read the docs instead?**
> Visit the live documentation portals for formatted navigation, instant search, and light/dark reading modes:
>
> - **End-User Portal:** [docs.vib.tools](https://docs.vib.tools/) — Setup guides, desktop app manuals, workflows, and troubleshooting.
> - **Developer Portal:** [developer.vibtools.io](https://developer.vibtools.io/) — Open-source tools, APIs, SDKs, CLI references, and self-hosting guides.

---

## Quick Navigation

| What you need | Where to go | Notes |
| :--- | :--- | :--- |
| **Product user guides & setup manuals** | [docs.vib.tools](https://docs.vib.tools/) | Fast static portal with sidebar navigation and full-text search (`Ctrl+K`) |
| **Developer & self-hosting reference** | [developer.vibtools.io](https://developer.vibtools.io/) | Technical guides for open-source Vib Tools software |
| **Docs-only product repositories** | [github.com/vibdocs](https://github.com/vibdocs) | Public `docs/` + `.vibtools/` files for Vib Tools apps |
| **Open-source code repositories** | [github.com/vibtoolshq](https://github.com/vibtoolshq) | Public source code, engines, and developer tooling |
| **Official website & app directory** | [vib.tools](https://vib.tools/) | Product overview, releases, and company links |

---

## Why `@vibdocs` Exists

Vib Tools separates product documentation into two GitHub organizations based on repository access:

| Organization | Purpose | Repository Contents | Target Portal |
| :--- | :--- | :--- | :--- |
| **[`@vibdocs`](https://github.com/vibdocs)** | Public documentation repositories for commercial and desktop products | Only `docs/` Markdown files and `.vibtools/` metadata | [docs.vib.tools](https://docs.vib.tools/) |
| **[`@vibtoolshq`](https://github.com/vibtoolshq)** | Open-source software and developer tools | Full source code alongside `.vibtools/` and `docs/` | [developer.vibtools.io](https://developer.vibtools.io/) & [docs.vib.tools](https://docs.vib.tools/) |

Every repository inside `@vibdocs` stays focused purely on documentation—making it simple to review changes, open typos or clarity pull requests, and sync updates automatically to the live portal.

---

## Featured Documentation Repositories

| Repository | Category | Description | Live Docs |
| :--- | :--- | :--- | :--- |
| **[`vibdocs/CalGrid`](https://github.com/vibdocs/CalGrid)** | Desktop Apps | Windows user guide for CalGrid: installation, Google Calendar invitations, workspaces, templates, and troubleshooting. | [docs.vib.tools/calgrid](https://docs.vib.tools/calgrid/) |

*Additional product guides hosted across Vib Tools portals (such as **ReadBox** custom-domain email & team inboxes) are synced automatically from [`@vibtoolshq`](https://github.com/vibtoolshq).*

---

## Reader Features on `docs.vib.tools`

Everything published from `@vibdocs` repositories is automatically built into a fast static site with reader-friendly features:

- **Instant Search (`Ctrl+K` / `Cmd+K`):** Search across all products or filter results to the product you are currently reading, or link directly with `/?q=<term>`.
- **Shareable Light & Dark Mode URLs:** Open any guide directly in your preferred appearance by appending `?theme=light` or `?theme=dark` to any documentation URL (for example, `https://docs.vib.tools/calgrid/getting-started/?theme=light`). Your choice carries across pages automatically.
- **Direct Edit Links:** Every article includes an **Edit this page on GitHub** link at the bottom that opens the exact source Markdown file inside `@vibdocs`.
- **Clean URLs & Table of Contents:** Automatic left-hand chapter navigation, right-hand `On This Page` heading tracker, and Previous/Next step buttons.
- **Plain-Text & AI-Ready Exports:**
  - Portal index: [`/llms.txt`](https://docs.vib.tools/llms.txt)
  - Full portal corpus: [`/llms-full.txt`](https://docs.vib.tools/llms-full.txt)
  - Per-product bundle: `https://docs.vib.tools/<product>/llms.txt`
  - Individual Markdown page: Append `.md` to any page route (for example, `/calgrid/getting-started.md`)

---

## How Repositories Here Are Structured

Every documentation repository in `@vibdocs` follows a compact, predictable layout so our automated build pipeline can sync updates cleanly:

```text
<product-repo>/
├── .vibtools/
│   ├── docs.config.json        # Portal routing, title, category, version & docsPath metadata
│   └── logo.png                # Optional product icon (PNG, SVG, WebP, or AVIF; max 2 MB)
└── docs/
    ├── index.md                # Required root overview page for the product
    ├── getting-started/
    │   ├── index.md            # Sets the collapsible folder title & section overview
    │   └── installation.md
    └── guides/
        └── ...
```

### Configuration & Authoring Standards

1. **Canonical `.vibtools/docs.config.json` Schema:**
   All repositories validate against the published Draft 2020-12 JSON Schema at [`docs.vib.tools/schemas/vibtools-docs.schema.json`](https://docs.vib.tools/schemas/vibtools-docs.schema.json).
2. **Portal Targeting (`docsType`):**
   Repositories declare `"users"` (`docs.vib.tools`), `"developer"` (`developer.vibtools.io`), or `"both"` (using separate `targets.users` and `targets.developer` paths and metadata).
3. **Clean Authoring Conventions:**
   - Every `docs/` root requires an `index.md` (or `README.md`).
   - Ordering uses explicit frontmatter `order`, numeric prefixes (`01-setup.md`), or relative link order inside parent `index.md` files.
   - Internal `.md` links are automatically rewritten to clean portal routes during builds.
   - Unpublished pages marked with `draft: true` in frontmatter are automatically excluded from public routes, search, and AI exports.

---

## Contributing to Vib Tools Docs

Community fixes—from spelling corrections and clearer step-by-step screenshots to updated troubleshooting notes—are welcome across all `@vibdocs` repositories:

1. **Find the page:** On [docs.vib.tools](https://docs.vib.tools/), scroll to the bottom of any guide and select **Edit this page on GitHub** (or locate the file under `docs/` in the corresponding repository).
2. **Keep edits clear and user-focused:** Write concise, accurate steps matching the current product UI and behavior.
3. **Preview links as relative `.md` paths:** Link sibling pages with standard Markdown paths (e.g., `[Installation](./installation.md)`) so both GitHub browsing and the web portal resolve them accurately.
4. **Open a Pull Request:** Describe what changed and which version or platform it applies to. Maintainers review and merge updates cleanly, which triggers automatic portal rebuilds.

---

## Support, Contact & Security

If you need help with a Vib Tools product, spot an issue in the documentation, or want to report a security concern privately:

| Channel | Destination | Use for |
| :--- | :--- | :--- |
| **Product & Technical Support** | [support@vibtools.io](mailto:support@vibtools.io) | App support, setup help, documentation issues, and private security disclosures |
| **General Inquiries** | [hello@vibtools.io](mailto:hello@vibtools.io) | General questions, partnerships, and company communication |
| **Phone / WhatsApp** | `+880 1795-470603` | Direct support line (`GMT+6` / `Asia/Dhaka`) |
| **Head Office** | `5660 Kochakata, Nageswari, Kurigram, Rangpur, Bangladesh` | Vib Tools HQ |

> **Security Note:** Please do not post sensitive account details, credentials, or security vulnerabilities in public GitHub issues. Send private reports directly to **[support@vibtools.io](mailto:support@vibtools.io)**.

### Official Links

- **Website:** [vib.tools](https://vib.tools/)
- **User Docs:** [docs.vib.tools](https://docs.vib.tools/)
- **Developer Docs:** [developer.vibtools.io](https://developer.vibtools.io/)
- **GitHub (Docs):** [@vibdocs](https://github.com/vibdocs)
- **GitHub (Code):** [@vibtoolshq](https://github.com/vibtoolshq)
- **GitLab:** [gitlab.com/vibtools](https://gitlab.com/vibtools)
- **Brand Assets:** [vibtools-brand-assets](https://github.com/vibtoolshq/vibtools-brand-assets)
- **Social:** [X (@vibtools)](https://x.com/vibtools) · [Facebook](https://www.facebook.com/vib.tools) · [Instagram](https://www.instagram.com/vib.tools/) · [Reddit](https://www.reddit.com/user/VibTools/) · [TikTok](https://www.tiktok.com/@vibtools)

---

<sub>© 2026 Vib Tools · All documentation in `@vibdocs` is maintained by Vib Tools.</sub>
