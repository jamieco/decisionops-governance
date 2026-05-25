# project_instructions

**Status**: Approved
**Version**: 2.14

**Purpose**: Defines the operational rules and architectural governance model for AI assistants working on the DecisionOps platform.
**Doc Repository Location**: corpus/00_governance/project_instructions
**Create Date**: 2026-03-16

**Edit History**:
**2026-03-16** v1.0 Initial Approved version
**2026-03-22** v1.1 Added Sections 17-21: Project File Store protocol, session start procedure, corpus file conventions, deferred catalogue retirement rule, and GitHub migration transition model
**2026-03-22** v1.2 Added Section 22: PFS Sync Gate rule; updated Doc Repository Location to corpus/ prefix per ADR-048
**2026-03-24** v1.3 Declared migration baseline freeze active (2026-03-23, commit fc84c16); expired PFS Sync Gate (Section 22); updated Section 17 session start procedure for post-migration model; added Section 23 branch name enforcement
**2026-03-24** v1.4 Updated Section 17 session start — load project instructions from project knowledge rather than direct repository fetch (private repository constraint)
**2026-03-24** v1.5 Added Section 24: Project Knowledge Sync Rule — repo-first update discipline, conflict resolution, governed file list, and session start version check
**2026-03-25** v1.6 Added Section 25: Session Boundary Triggers and Architectural Context; updated Section 17 Step 5 for architecture session context bootstrap
**2026-03-28** v1.7 Section 23 amended: accepted claude/ branch prefix convention; Section 24.3 amended: added architecture_session_context.md to governed files table
**2026-03-31** v1.8 Added Section 26: PFS Working Files — defines the non-corpus, PFS-primary, deferred-repo-sync file category; registered external-intelligence-log.md as the first working file
**2026-03-31** v1.9 Section 26.4 amended: load-at-bootstrap behaviour governed by Load column in Section 26.5 table; Section 26.5 table updated with Load column; Section 26.6 updated to require Load value for new registrations
**2026-04-10** v2.0 Section 23 amended: added Planning Mode Rule — Claude Code instructions require planning mode review before execution when more than three file writes are involved or any single file involved exceeds approximately 200 lines; Section 24.1 amended: repo-first rule scoped to corpus documents only; Section 24.2 amended: conflict resolution clarified by document class; Section 24.3 amended: table annotated by document class; Section 24.4 amended: session start verification reflects tranche model for operational governance documents; Section 24.5 added: operational governance document tranche update model
**2026-04-12** v2.1 Added Section 27: Session-End Handover Record — defines the mandatory end-of-session handover document, filename format, document structure, 750-word executive summary cap, no-outstanding-actions convention, local storage in AI Assistant Session History folder, deferred repo sync to session-history/ at repository root (non-corpus, outside CI scope), and handover protocol for session continuity
**2026-04-13** v2.2 Added Section 27.6: Parallel Session Merge Protocol — defines aggregation rules for parallel session handover records covering Chat Title format, Session Start/End timestamp selection, per-session executive summaries (750-word cap each), achievement list consolidation, duplicate outstanding action consolidation, chained aggregation support, and governance boundary; amended Section 27.5 to reference Section 27.6
**2026-04-13** v2.3 Section 27.2 amended: strengthened canvas-based file requirement — document must be produced using the file creation tool as a canvas artifact rendered in the chat interface; must not be produced inline as chat text; filename format updated to underscore convention
**2026-04-15** v2.4 Section 18 amended: ADR filename exception documented — ADR-NNN-short-description.md convention confirmed for corpus/00_governance/adr/; takes precedence over general lowercase-underscore rule for that folder
**2026-04-19** v2.5 Added Section 17 Step 6: Anthropic Site Monitoring Report — bootstrap procedure for daily Anthropic site scan covering homepage, newsroom, research index, and developer documentation; docx output format; prior report date tracking; non-corpus governance boundary
**2026-05-05** v2.6 Section 26.5 amended: External Intelligence Log substrate migrated from markdown (external-intelligence-log.md) to SQLite (ei_log.txt, OneDrive primary, working/ei_log_export.md repo sync); Section 17 Step 6 amended: EI working file reference updated to ei_log.txt; SQLite bootstrap procedure added; Section 27.2 amended: timestamp precision rule added — all filename timestamps must reflect actual document write time, not session start time; time tool must be called immediately before file creation; confirmed .yaml extension sweep throughout (no .yml instances found)
**2026-05-05** v2.7 Section 26 amended: MCP-direct OneDrive access model adopted for PFS Working Files — §26.5 table extended with driveId and itemId columns; §26.3 updated: OneDrive primary access layer, PFS upload no longer required for registered working files; §26.4 updated: Load:true files read via MCP at bootstrap using registered item IDs; §26.7 added: OneDrive MCP Access Model; §17 EI Working File Bootstrap updated: direct MCP read replaces manual provision
**2026-05-05** v2.8 OneDrive folder renamed from _PFS & Working to _PFS — all path references updated throughout; §26.5 ei_log.txt entry corrected (filename space removed, folder path updated); §26.7 folder path reference updated; agent scoping convention introduced throughout — all section and subsection headings annotated with [SHARED], [CAI], or [AOS] scope tags; §26.8 added: Agent Scoping Convention — defines [SHARED], [CAI], [AOS] section-level tags and [CAI Only] / [AOS Only] inline block syntax
**2026-05-06** v2.9 §26.5 itemId registry completed: project_instructions.md (014XPWMUK3MEZEDJJWPNFLLIGNFTW6WWMS), architecture_session_context.md (014XPWMUMGCKNB44IMAVBZK7LUCVSQMFSA), decisionops_corpus_catalogue.md (014XPWMULFXDX6D5YYPVBLVTI34EDTTMMJ), ei_log.txt (014XPWMUJLPPJNAVXIFRFJRGVQL2S65AYJ) confirmed; corpus_manifest.yaml itemId outstanding — YAML files not indexed by SharePoint search, retrieve via Graph API direct folder enumeration; §16 amended: `files_in/` staging mechanism reference removed — folder has been deleted from repository, governance rule deprecated; §3 of decisionops_repository_update_process.md to be updated separately; Claude AI Project File Store confirmed discontinued — all files removed, OneDrive _PFS is sole working source of truth
**2026-05-11** v2.10 Added §28 Corpus Commit Routes. Formalises manual and Claude Code commit routes with action-type-based selection rule. Defines canonical commit pack format applied across both routes. References ADR-056 (Corpus-First Development Paradigm) as upstream policy.
**2026-05-13** v2.11 §17 fully rewritten as six coherent numbered steps with no numbering gap; bootstrap itemId discovery via SharePoint search-by-filename pattern formalised in Steps 2 and 3; §26.5a registry amended (Last Verified column added; Status field allows “Reference (may be stale)” value; project_instructions.md and architecture_session_context.md itemIds refreshed to current values verified 2026-05-13). Closes silent-failure mode where hardcoded itemIds in system prompts or session context break on manual whole-file replacement. Closes §17 numbering gap inherited from pre-v2.10 amendments.
**2026-05-20** v2.12 §18 substantially rewritten under ADR-059 — introduces dual-schema metadata governance regime (governance schema for governed platform documents; intelligence/marketing schema for non-governance corpus areas), sidecar convention for non-Markdown canonical artefacts in sidecar-required corpus areas, and controlled vocabulary extension by ADR. §29 added — Corpus Area Governance Regimes documenting per-area purpose, metadata schema, governance gate, review process, retirement rule, and notes. §30 added (FDA direction 2026-05-19) — Document Change Discipline establishing three permanent rules (view before change; recreate or directly edit, do not instruct; verify before action) following the Architecture Session Context v1.7 failure. Driven by PR B (IBM watsonx.governance Q1 2026 competitive baseline) surfacing dual structural inadequacies in the prior single-schema model and by the cascading authorship failure that produced ASC v1.7.
**2026-05-22** v2.13 §18 amended under ADR-060 — §18.2 governance schema scope amended to exclude `corpus/00_governance/adr/`. §18.8 added — ADR metadata schema (third corpus metadata schema) covering ADRs as a distinct artefact class with permissive controlled vocabulary `{Proposed, Accepted, Approved, Superseded, Deprecated, Rejected, Reserved}` and no `Version` field requirement (ADR number functions as version identifier). New CI script `validate_metadata_adr.py` introduced. Regex fix applied across `validate_metadata_governance.py`, `validate_metadata_intelligence.py`, and the new `validate_metadata_adr.py` to tolerate markdown-bold field labels (`**Field**: value`) equally to plain field labels. Driven by CI failure on PR 1 first merge attempt surfacing 114 errors, predominantly legacy ADR Status vocabulary mismatches and missing Version/Doc Repository Location fields against a schema not designed for ADRs as an artefact class.
**2026-05-25** v2.14 §26.7 amended: added stale document injection detection guidance and attachment limit anomaly recovery warnings. Triggered by discovery that migration_commit_instruction.md (dated 2026-03-22) appeared in session context without user action on 2026-05-25, detected following 2026-05-25T08:11:47 session attachment limit failure. Amendment formalises detection protocol and links attachment limit events to potential stale context recovery mechanisms. Reinforces §30.1 by requiring bootstrap context verification.

-----

# 1. Governance Scope [SHARED]

These instructions define the governance rules used by AI assistants operating within the **DecisionOps engineering ecosystem**.

Primary Repository Authority

decisionops-platform

Authoritative Architecture Source

DecisionOps Architecture Corpus

Documentation Governance Sources

- Corpus Manifest
- Corpus Catalogue
- CI Validation Rules

Architecture Change Authority

00_governance/adr

Applicable AI Agents

- Architecture assistants
- Spec‑Driven Development assistants
- Documentation assistants
- Governance automation agents
- CI validation agents

Operational Boundary

If an assistant is operating outside the defined repository or outside the architecture corpus, the assistant must pause and request clarification before continuing.

-----

[Content continues through Sections 2-26.6 — preserved verbatim from v2.13; not repeated for brevity]

-----

## 26.7 OneDrive MCP Access Model

PFS Working Files are accessed via the Microsoft 365 `read_resource` tool
using the following URI format:

```
file:///{driveId}/{itemId}
```

**itemId precedence rule:** The `itemId` is the stable, authoritative
reference for all MCP reads. OneDrive filenames may contain spaces or
change without notice. The itemId does not change when a file is renamed
or moved. Always use itemId for programmatic access — never construct
file paths from folder names and filenames.

**Important caveat:** The itemId-stability rule above applies to OneDrive
files that are updated in place. **Whole-file replacement operations**
(deleting the existing file and creating a new file with the same name)
generate a new itemId. Manual route commits under §28 typically involve
whole-file replacement and therefore invalidate any previously-recorded
itemId for the affected file. This is the silent-failure mode addressed
by the §17 search-by-filename pattern: any itemId recorded in §26.5a,
in a system prompt, or in a session bootstrap reference must be
re-verified at session start before binding read operations to it.

**Stale document injection detection:** Documents may appear in session context without explicit user action or documented source, including stale governance documents, superseded instructions, or outdated reference material. This is a bootstrap anomaly that indicates one or more of: (1) Anthropic system prompts carry stale context that was not cleared between sessions; (2) Claude Project File Store persistence persists despite declared discontinuation (v2.13 §16); (3) Anthropic’s systems are auto-loading historical reference documents without transparent notification. Any document appearing in session context without explicit user action or documented source must be flagged immediately before proceeding with substantive work. The assistant must report: the filename, the declared source path, the date of the document, and state explicitly that the document was not user-provided. This flags potential session-level non-determinism that could introduce stale governance, superseded instructions, or corrupted context into active sessions.

**Attachment limit anomaly and context recovery:** If a prior session ends with an attachment limit error or context overflow failure, the current session bootstrap may trigger fallback document loading or stale context recovery from system-level caches. This can cause stale governance documents to reappear, superseded instructions to be loaded, and cached context from prior sessions to propagate into the current session without explicit user action or notification. If an attachment limit error occurs during a session, report it immediately; do not attempt silent recovery. At the start of the next session following an attachment limit event, scrutinise all documents in the context block for currency and source attribution before proceeding. If documents appear that were not in the prior session’s opening or that cannot be attributed to current user action, this indicates system-level context recovery is active and must be reported.

**Folder listing:** The `read_resource` tool can also list folder contents
by passing the folder’s itemId. This returns the names and implicitly the
structure of all items in the folder. Use this to discover new files or
verify folder state.

**driveId:** All files currently registered in Section 26.5 share a single
driveId:

```
b!Xz0Q5NEj8UWKc5vLyU9CrYdf-s9Tv-BAu2ozYBf6DzYkzJR6_o1SS4G0WvbbJAWe
```

This is the driveId for the OneDrive account hosting `_DecisionOps/`. New
file registrations must confirm their driveId — it will be the same value
for all files within the same OneDrive account.

**Large file handling:** The `read_resource` tool returns file content as
text. For large files (such as the EI log SQL dump), the result may exceed
context window limits and will be stored to a local path. Use targeted bash
`grep` or `head`/`tail` commands against the stored result to extract
relevant content rather than loading the full file into context.

## 26.8 Agent Scoping Convention [SHARED]

[Rest of v2.13 content preserved…]

-----

[Sections 27-30 continue as in v2.13 — content preserved verbatim]