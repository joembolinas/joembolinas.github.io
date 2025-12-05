---
title: Academic Journey Portfolio - Project Specification Document
version: 1.3
date_created: 2025-12-03
last_updated: 2025-12-05
owner: Portfolio Owner
tags: [architecture, design, infrastructure, github-pages, static-site]
---

This specification defines the architecture for the Academic Journey Portfolio, a static, Jekyll-compatible site on GitHub Pages. It documents requirements, constraints, and interfaces for clear, repeatable, AI-assisted development and maintenance.

## 1. Purpose & Scope

### 1.1 Purpose

Define a static portfolio system that organizes academic content (projects, reflections, assignments, achievements) into markdown pages, rendered via GitHub Pages/Jekyll, with term-based navigation and simple client-side interactivity.

**Intended Audience:** AI code generation systems, developers, system architects, maintainers

**Assumptions:**

- GitHub Pages availability; Student Dev Pack not required but permitted
- Consistent source directory structures per term
- Quarterly updates aligned with term completion
- Static site only; no backend

### 1.2 Objectives

| Obj. ID | Objective                           | Measurable Goal                                        |
| ------- | ----------------------------------- | ------------------------------------------------------ |
| OBJ-001 | Publish a static academic portfolio | Site live at `https://joembolinas.github.io/`          |
| OBJ-002 | Term-based organization             | New term added within 1 hour of content creation       |
| OBJ-003 | Content validity                    | 100% required front matter validated pre-merge         |
| OBJ-004 | Performance                         | Lighthouse Performance ≥ 90 on main/subject pages      |
| OBJ-005 | Accessibility                       | WCAG 2.1 AA automated checks pass (no blocking issues) |

### 1.3 Project Scope

**In Scope:**

- Static pages (Markdown/HTML) rendered by Jekyll on GitHub Pages
- Term- and subject-based navigation (e.g., `subject1/week1..12`, `subject2/output1..12`)
- Basic client-side interactivity (expand/collapse, filters) using vanilla JS
- Optional lightweight analytics (privacy-friendly) if desired

**Out of Scope:**

- Authentication, roles, personalization
- Custom backend services/databases
- Commenting systems, UGC submissions
- Real-time features (chat/live collab)
- Payments/monetization
- Collection of sensitive personal data
- Heavy analytics requiring tracking cookies

## 2. Definitions

- **GitHub Pages:** Static site hosting by GitHub
- **MCP:** Model Context Protocol (VS Code integration)
- **CI/CD:** Continuous Integration/Deployment (GitHub Actions)
- **SSG:** Static Site Generator (Jekyll-compatible)
- **Component:** Reusable UI element (Markdown → HTML via layout)
- **Term:** Academic term
- **Content Source:** Markdown files with YAML front matter from term folders
- **Deployment Target:** `joembolinas/joembolinas.github.io` (main branch)

## 3. Requirements, Constraints & Guidelines

### 3.1 Functional Requirements

| Req. ID | Name                    | Requirement Description                                               |
| ------- | ----------------------- | --------------------------------------------------------------------- |
| FR-001  | Home Page               | System MUST provide a landing page linking to all subjects/terms.     |
| FR-002  | Subject Index           | System MUST list subject subpages (weeks/outputs) per subject.        |
| FR-003  | Term Organization       | System MUST group content by term for chronological navigation.       |
| FR-004  | Content Rendering       | System MUST render Markdown with YAML front matter to HTML via Jekyll.|
| FR-005  | Front Matter Validation | System MUST validate required front matter fields before publish.     |
| FR-006  | Navigation Integrity    | System MUST ensure internal links resolve (no broken internal links). |
| FR-007  | Expandable Content      | System MUST support expandable sections/cards via client-side JS.     |
| FR-008  | Asset Handling          | System MUST serve static assets (CSS/JS/images) from the repo.        |
| FR-009  | Multi-Repo Intake       | System SHOULD allow importing content from additional repos (copy-in).|
| FR-010  | Accessibility Hooks     | System MUST provide semantic HTML structure and ARIA where applicable.|

### 3.2 Non-Functional Requirements

#### Performance

| Req. ID | Name            | Requirement Description                                   |
| ------- | --------------- | --------------------------------------------------------- |
| NFR-001 | Load Time       | System MUST load above-the-fold content ≤1.5s on 3G test. |
| NFR-002 | Page Weight     | System MUST keep page weight ≤2MB per page.               |
| NFR-003 | Lighthouse Perf | System MUST achieve Lighthouse Performance ≥ 90.          |
| NFR-004 | Caching         | System SHOULD leverage browser caching for static assets. |

#### Security

| Req. ID | Name           | Requirement Description                                           |
| ------- | -------------- | ----------------------------------------------------------------- |
| NFR-005 | Content Safety | System MUST NOT collect sensitive PII beyond owner contact.       |
| NFR-006 | Dependencies   | System SHOULD avoid remote scripts except trusted CDNs; pin versions. |
| NFR-007 | HTTPS          | System MUST use HTTPS (GitHub Pages-managed cert).                |

#### Scalability

| Req. ID | Name             | Requirement Description                                                        |
| ------- | ---------------- | ------------------------------------------------------------------------------ |
| NFR-999 | Content Capacity | System MUST scale to ≥1,000 markdown files + assets without manual reconfig.  |

### 3.3 Constraints

| ID      | Constraint                                                                    |
| ------- | ----------------------------------------------------------------------------- |
| CON-001 | MUST remain GitHub Pages–compatible (safe Jekyll; no custom plugins).         |
| CON-002 | MUST deploy from `main` branch root (or configured Pages branch).             |
| CON-003 | MUST avoid server-side code; static only.                                     |
| CON-004 | MUST keep optional JS lightweight; no heavy SPA routing required.             |

### 3.4 Guidelines

| ID      | Guideline                                                                      |
| ------- | ------------------------------------------------------------------------------ |
| GUD-001 | Prefer AI-assisted development (GitHub Copilot) with clear prompts.            |
| GUD-002 | Use semantic HTML5 and accessible patterns.                                    |
| GUD-003 | Automate checks (links, lint) where feasible in CI.                            |
| GUD-004 | Document content transformation processes and metadata requirements.           |
| GUD-005 | Keep navigation simple and shallow; avoid deep nesting where possible.         |
| GUD-006 | Use relative URLs (`relative_url` filter) for portability.                     |

### 3.5 Architectural Patterns

| ID      | Pattern                                                          |
| ------- | ---------------------------------------------------------------- |
| PAT-001 | Use Jekyll (Pages-safe) for Markdown-to-HTML rendering.          |
| PAT-002 | Content-first design (Markdown + layouts).                       |
| PAT-003 | Separation of concerns (content, presentation, behavior).        |
| PAT-004 | Declarative config over imperative code.                         |
| PAT-005 | Atomic design for components (cards, lists, nav).                |

## 4. Interfaces & Data Contracts

### Content Source Interface

**Input Directory Structure (example):**

```text
sample/
├── projects/
│   └── project-name/
│       ├── README.md
│       ├── documentation/
│       └── assets/
├── reflections/
│   └── reflection-YYYY-MM-DD.md
├── assignments/
│   └── subject-assignment-name.md
└── achievements/
    └── achievement-name.md
```

**Content File Metadata Schema (YAML front matter):**

```yaml
---
title: string (required)
date: YYYY-MM-DD (required)
category: [string] (required) # ["academic","reflection","extracurricular","achievement"]
skills: [string] (optional)
tags: [string] (optional)
term: string (required)       # "T3-AY2025"
type: string (required)       # ["project","reflection","assignment","achievement"]
---
```

### Component Interface

Logical schema for content cards:

```javascript
{
  "componentName": "ContentCard",
  "props": {
    "title": "string",
    "content": "markdown|string",
    "metadata": {
      "date": "YYYY-MM-DD",
      "category": ["string"],
      "skills": ["string"],
      "tags": ["string"],
      "term": "string"
    },
    "expandable": true,
    "defaultExpanded": false
  }
}
```

### Deployment Configuration

**GitHub Pages / Jekyll `_config.yml`:**

```yaml
title: string
description: string
baseurl: ""
url: "https://joembolinas.github.io"
theme: minima
plugins: []        # none; keep Pages-safe
exclude: ["node_modules", "vendor"]
include: []
markdown: kramdown
permalink: pretty
```

**(Optional) GitHub Actions Workflow skeleton:**

> Not required for Pages-native Jekyll, but can be added for validation tasks.

```yaml
name: Validate
on:
  push: { branches: [main] }
  pull_request: { branches: [main] }
jobs:
  lint-and-validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Link check (optional)
        run: echo "Add link checker or markdown lint here"
```

### Navigation Data Contract

```json
{
  "navigation": [
    {
      "label": "Home",
      "path": "/",
      "children": []
    },
    {
      "label": "Subject 1",
      "path": "/subject1/",
      "children": [
        { "label": "Week 1", "path": "/subject1/week1/", "metadata": { "term": "Tn", "category": "academic" } }
      ]
    },
    {
      "label": "Subject 2",
      "path": "/subject2/",
      "children": [
        { "label": "Output 1", "path": "/subject2/output1/", "metadata": { "term": "Tn", "category": "academic" } }
      ]
    }
  ]
}
```

## 5. Acceptance Criteria

- **AC-001**: Given valid front matter, When content is processed, Then content is included in the build successfully.
- **AC-002**: Given missing required front matter fields, When validation runs, Then build/validation fails with clear error message.
- **AC-003**: Given content organized by term, When navigation renders, Then term grouping is visible with chronological ordering within term.
- **AC-004**: Given category/skill filters are implemented, When user applies filter, Then only matching content is displayed.
- **AC-005**: Given expand/collapse controls, When user interacts via keyboard, Then controls are accessible and maintain ARIA state.
- **AC-006**: Given a push to `main` branch, When GitHub Pages builds, Then site is live with updated content.
- **AC-007**: Given automated accessibility checks, When run against the site, Then WCAG 2.1 AA compliance is achieved (no blocking issues).
- **AC-008**: Given mobile viewport (≥320px), When page loads, Then layout is readable without horizontal scroll.
- **AC-009**: Given link validation runs, When internal links are checked, Then all return 200–299; external links warn but are non-blocking.
- **AC-010**: Given content copied from another repo, When added to the project, Then no config changes are required.
- **AC-011**: Given Lighthouse audit runs, When key pages are tested, Then Performance score ≥ 90.

## 6. Test Automation Strategy

- **Test Levels**: Lint/validate markdown & links; (optional) HTML validation if run locally
- **Frameworks**: markdownlint, link checker (e.g., lychee) — optional in CI
- **Test Data Management**: Sample fixtures for front matter validation
- **CI/CD Integration**: Optional GitHub Actions for lint/link checks; Pages native build handles Jekyll
- **Coverage Requirements**: Not applicable (no backend); focus on validation completeness
- **Performance Testing**: Lighthouse audits on key pages

## 7. Rationale & Context

- **GitHub-centric workflow**: Versioned content, PR review, Pages hosting provides a seamless development experience
- **AI-assisted development**: Faster authoring with consistent patterns using GitHub Copilot
- **Static only**: Simplicity, security, zero infrastructure cost; client-side interactivity sufficient for portfolio needs

## 8. Dependencies & External Integrations

### External Systems

- **EXT-001**: GitHub - Repository hosting, PR/issues management
- **EXT-002**: GitHub Pages - Static site hosting with HTTPS

### Third-Party Services

- **SVC-001**: Google Lighthouse - Performance and accessibility audits (optional)

### Infrastructure Dependencies

- **INF-001**: Git (≥2.x) - Version control
- **INF-002**: Node.js (≥18.x) - Local linting/validation (optional)

### Technology Platform Dependencies

- **PLT-001**: GitHub Actions - Optional CI for validation tasks
- **PLT-002**: Jekyll - Pages-safe default static site generator

## 9. Examples & Edge Cases

### Missing Required Front Matter

```yaml
# Invalid - missing required fields
---
title: My Project
---
```

**Expected behavior:** Exclude from build/fail validation with clear error message.

### Overlapping Dates

When multiple content items share the same date, apply secondary sort by title to stabilize ordering.

### Special Characters in Filenames

Slugify filenames for URLs:

- Input: `My Project (Final).md`
- Output URL: `/my-project-final/`

### Large Files

Files exceeding 10MB trigger a warning; recommend optimization (compression, external hosting).

### Empty Term Directory

Display: "No content available for this term."

## 10. Validation Criteria

- Front matter required fields present; dates in ISO 8601 format
- Internal links resolve; external links warned if broken
- Images accessible with alt text; reasonable dimensions
- HTML/CSS validity (if checked locally)
- Accessibility: headings ordered, contrast meets AA, keyboard access for interactive elements
- Performance: page weight ≤2MB; critical render ≤1.5s on 3G; assets minified where applicable

## 11. Related Specifications / Further Reading

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [WCAG 2.1 Quick Reference](https://www.w3.org/WAI/WCAG21/quickref/)
- [Markdown Guide](https://www.markdownguide.org/)
- [YAML Specification](https://yaml.org/spec/1.2/spec.html)
- [JAMstack](https://jamstack.org/)

## 12. Target Users & Personas

| Persona              | Description                                                                  |
| -------------------- | ---------------------------------------------------------------------------- |
| Portfolio Owner      | Student who adds/updates term content; ensures accessibility and link integrity |
| Recruiter/Employer   | Skims highlights; filters by skill/term; expects fast load                   |
| Instructor/Reviewer  | Verifies artifacts and accessibility; checks organization                    |
| General Visitor      | Seeks quick understanding of background and achievements                     |

## 13. User Stories & Use Cases

- **US-001**: As a Portfolio Owner, I want to add new term content so that my portfolio stays current. CI (if present) validates; Pages publishes automatically.
- **US-002**: As a Recruiter, I want to filter by skill (if implemented) so that I can view top relevant items quickly.
- **US-003**: As an Instructor, I want to check front matter and accessibility so that validation passes before merge.
- **US-004**: As a Visitor, I want to expand a card to read details so that I can learn more about specific projects; controls are accessible and responsive.

---

*v1.3 | For Revision | Last Updated: Dec 05 2025 - 15:30*
