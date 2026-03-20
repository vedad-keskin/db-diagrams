# db-diagrams

A personal collection of **database schema diagrams**—entity–relationship views, table layouts, and reference documentation for systems you work on. Use it as a single place to version diagrams alongside (or instead of) living only in wikis or design tools.

## Why this repo?

- **History**: See how schemas evolved with normal Git diffs (especially for text-based formats).
- **Sharing**: Clone or link diagrams in PRs, onboarding docs, or runbooks.
- **No lock-in**: Keep sources in open formats when possible so you are not tied to one vendor.

## Suggested layout

Organize however you like; one pattern that scales:

```text
db-diagrams/
├── README.md
├── <project-or-system>/
│   ├── README.md          # short context: env, owner, last reviewed
│   ├── schema.dbml        # or .mmd, .puml, source for your tool
│   └── exports/           # optional PNG/SVG snapshots for quick viewing on GitHub
└── _templates/            # optional: empty stubs for new systems
```

Name folders after **application or bounded context** (e.g. `billing`, `auth-service`) rather than only “database name,” unless one DB maps cleanly to one product.

## Formats that work well in Git

| Format | Typical use | Notes |
|--------|-------------|--------|
| **DBML** ([dbdiagram.io](https://dbdiagram.io)) | ER diagrams, quick iteration | Text-first; easy to diff |
| **Mermaid** `erDiagram` | Docs + GitHub preview | Renders in many Markdown viewers |
| **PlantUML** | Formal ERD / detailed models | Great for larger schemas |
| **SQL DDL** | Source of truth | Diagrams can be generated or kept in sync manually |

Pick one primary format per project and document it in that folder’s `README.md`.

## Conventions (optional)

- **Sensitive data**: Do not commit connection strings, real customer data, or production hostnames. Use placeholders in notes and samples.
- **Stale diagrams**: Add a “last verified” date or link to the migration/tooling that is authoritative when the diagram is illustrative only.
- **Exports**: If you commit binary images, also keep the **editable source** (DBML, Mermaid, etc.) so changes stay reproducible.

## Quick start

1. Create a folder for the system you are documenting.
2. Add a short `README.md` (what the database is for, who owns it, how diagrams are updated).
3. Commit your diagram source; optionally add rendered PNG/SVG under `exports/` for README embedding.

---

*Previously noted as diagrams for various IT projects—this README standardizes on **database** schema documentation; add UML or other diagram types in subfolders if you want everything in one place.*
