# LTI-CFGP — Prompts

**AI Assistant:** GitHub Copilot  
**Model:** Claude Sonnet 4.6

---

## Step 1 — Generate the Master Prompt

**Tool:** GitHub Copilot `/meta` slash command  
**Purpose:** Generate a high-quality master prompt that would produce the full system design document in a single response.

**Input given to `/meta`:**

> Act as a Senior Software Architect. I need a master prompt that instructs an AI to produce a complete system design document for LTI, a startup building a next-generation ATS (Applicant Tracking System) targeting small companies (under 50–100 employees). The document must cover: software description, main functions, Lean Canvas, 3 main use cases with Mermaid diagrams, data model with erDiagram, high-level system design with graph diagram, and a C4 component diagram for the Notification & Scheduling Service. All diagrams must use Mermaid. Output must be a single ready-to-save Markdown file named LTI-CFGP.md.

**Output:** The master prompt reproduced in Step 2 below.

---

## Step 2 — Generate the Full Document

**Tool:** GitHub Copilot (agent mode)  
**Model:** Claude Sonnet 4.6  
**Attached context file:** `plan.md`  
**Result:** All 7 artifacts generated in a single response, saved as `LTI-CFGP.md`.

**Prompt used:**

```
**Role:** Act as a Senior Software Architect with deep expertise in product design,
system architecture, and technical documentation, combined with strong product
management skills.

**Context:**
LTI is a startup building a next-generation ATS (Applicant Tracking System). Nothing
has been built yet. Market research concludes that the MVP targets small companies
(under 50–100 employees) and is built around three core feature pillars:

1. **One-Click Job Posting & Syndication** — Distribute job listings to multiple job
   boards (Indeed, LinkedIn) with one click; include a customizable branded career page.
2. **Visual Candidate Pipeline & Centralized Management** — A drag-and-drop Kanban
   board to track candidates; centralized database with basic resume parsing to
   automatically extract contact info and work history.
3. **Automated Communication & Interview Self-Scheduling** — Email templates and
   triggered status updates; self-service scheduling synced with Google Calendar and
   Outlook, eliminating back-and-forth email chains.

LTI's strategic differentiators over existing competitors (Greenhouse, Workable, Lever)
are: efficiency gains for HR departments, real-time collaboration between recruiters and
managers, aggressive automation of administrative tasks, and AI assistance across
recruiting workflows.

**Task:**
Produce a complete system design document for LTI's ATS MVP in a single Markdown file
named `LTI-CFGP.md`. The document must contain ALL seven artifacts below, in the exact
order listed, with no omissions.

---

### Artifact 1 — LTI Software Description
- Write 2–3 paragraphs describing the LTI ATS software.
- Clearly state the value proposition: what problem it solves, for whom, and why now.
- List at least 5 concrete competitive advantages vs. existing ATS solutions.
- Audience: Investors and potential customers.
- Tone: Persuasive, clear, business-oriented.

---

### Artifact 2 — Main Functions
- Provide a structured breakdown of main features, organized under the 3 core pillars.
- For each feature include: feature name, a 1–2 sentence description, and the primary
  user role that benefits from it (e.g., HR Admin, Recruiter, Hiring Manager, Candidate).
- Audience: Product team and stakeholders.
- Tone: Clear, structured, product-oriented.

---

### Artifact 3 — Lean Canvas
- Represent the Lean Canvas as a Markdown table with all 9 cells:
  Problem | Solution | Unique Value Proposition | Unfair Advantage |
  Customer Segments | Key Metrics | Channels | Cost Structure | Revenue Streams
- Every cell must be specific to LTI's ATS MVP — no generic placeholders.
- Audience: Founders, investors, business stakeholders.
- Tone: Strategic, concise, business-focused.

---

### Artifact 4 — 3 Main Use Cases
For each use case provide:
  a) A prose description covering: actors, preconditions, main flow (numbered steps),
     alternative flows, and postconditions.
  b) A Mermaid `flowchart TD` diagram representing the actors, decision points,
     and flow steps.

The three use cases must be:
1. Job Posting & Multi-Board Syndication (Actors: HR Admin, External Job Boards)
2. Candidate Pipeline Management (Actors: Recruiter, Hiring Manager, Candidate)
3. Automated Communication & Interview Self-Scheduling
   (Actors: Candidate, Recruiter, Calendar Service)

- Audience: Business analysts, developers, QA engineers.
- Tone: Precise, structured, use-case-specification style.

---

### Artifact 5 — Data Model
- Design a relational data model for the MVP.
- Minimum required entities: `Company`, `User`, `JobPosting`, `JobBoardSyndication`,
  `Candidate`, `Application`, `PipelineStage`, `Interview`, `EmailTemplate`,
  `ScheduledEvent`.
- For each entity list every attribute with its name and data type
  (e.g., `id: UUID`, `created_at: TIMESTAMP`, `status: ENUM`).
- Describe all relationships (one-to-many, many-to-many, etc.) with cardinality.
- Render the full model as a Mermaid `erDiagram`.
- Audience: Backend developers and database architects.
- Tone: Technical, precise, implementation-ready.

---

### Artifact 6 — High-Level System Design
- Write 2–3 paragraphs explaining: the overall architectural style chosen (e.g.,
  modular monolith, microservices), the main layers or services, and the rationale
  behind key technology decisions.
- Render the architecture as a Mermaid `graph TD` diagram showing all major components
  and their interactions: Frontend SPA, API Gateway, Core Backend Services (Job Service,
  Pipeline Service, Notification Service, Scheduling Service), Databases, and External
  Integrations (job boards, calendar APIs, email provider).
- Audience: Technical architects and senior engineers.
- Tone: Technical, reasoned, architecture-focused.

---

### Artifact 7 — C4 Diagram (Component Level)
- Select the **Notification & Scheduling Service** as the container to zoom into.
- Produce a C4 Component diagram using Mermaid's C4 notation (`C4Component`).
- The diagram must include: all internal components of the service, their
  responsibilities, relationships between them, and interactions with external systems
  (Calendar APIs, Email Provider, Database, API Gateway).
- Precede the diagram with a short paragraph explaining the component and justifying
  the design decisions (e.g., why components are separated as they are).
- Audience: Software developers working on this service.
- Tone: Highly technical, implementation-oriented.

---

**Constraints:**
- Write entirely in English.
- All diagrams must use Mermaid syntax. The sole exception is the Lean Canvas
  (Artifact 3), which must be a Markdown table.
- No placeholder text ("TBD", "lorem ipsum", "Example Co."): every section must be
  fully fleshed out with realistic, LTI-specific content.
- Output must be one continuous Markdown document. Do not add preambles, meta-commentary,
  or framing text such as "Here is your document". Start directly with the document title.
- Use this heading hierarchy strictly: `#` for the document title, `##` for each
  artifact heading, `###` for subsections within an artifact.
- Document title must be exactly: `# LTI ATS — System Design Document`

**Output Format:**
A single, complete, immediately usable `.md` document containing all 7 artifacts in
full detail, ready to be saved as `LTI-CFGP.md`.
```
