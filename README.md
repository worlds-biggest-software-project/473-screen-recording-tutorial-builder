# Screen Recording & Tutorial Builder

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source platform that unifies screen recording, automated workflow documentation, and tutorial publishing into a single tool -- eliminating the need to juggle separate products for video messaging, step-by-step guides, and polished instructional content.

Software teams, customer success groups, and educators spend too much time stitching together fragmented tools to produce training material. One product records video, another captures screenshots into step-by-step guides, and yet another handles editing and publishing. Screen Recording & Tutorial Builder consolidates these workflows so that a single recording session can produce both a narrated video tutorial and an annotated screenshot guide, with AI handling transcription, captioning, voiceover, and privacy redaction automatically.

---

## Why Screen Recording & Tutorial Builder?

- **Fragmented tooling forces context-switching.** Loom handles async video messaging well but lacks process documentation. Scribe generates screenshot guides but cannot produce video. Teams end up paying for and maintaining both.
- **Incumbent pricing scales steeply.** Scribe Enterprise, Loom Business, and Camtasia subscriptions each run $12-33+/user/month. Organisations documenting processes at scale face significant per-seat costs across multiple products.
- **No self-hosted option exists.** Every major commercial solution (Loom, Scribe, Guidde, Descript, Tango) is SaaS-only. Enterprises in healthcare, government, and finance with strict data-residency requirements have no viable alternative.
- **Desktop application workflows are poorly served.** Scribe and Tango focus on browser-based capture. Documenting desktop software (Java GUIs, VB.NET applications, design tools) with automatic step detection remains a gap across the market.
- **Compliance and governance features are an afterthought.** Only Scribe offers formal approval workflows. Most tools lack audit trails, version control, and sign-off processes expected in regulated environments.

---

## Key Features

### Recording & Capture

- One-click screen and webcam recording with simultaneous audio capture (browser extension and desktop app)
- Auto-workflow capture for browser workflows: automatic step detection, screenshot extraction, and annotated guide generation
- Multi-modal recording: full screen, application window, or browser tab with optional webcam overlay
- Support for multiple recording quality options up to 4K

### AI-Powered Processing

- Automatic transcription with speaker identification and closed caption rendering
- AI voiceover synthesis in 50+ languages with multiple voice options
- Privacy-aware automatic PII detection and blur/redaction
- AI-generated video summaries and structured notes

### Editing & Annotation

- Transcript-based video editing: modify video by editing text, removing filler words and silences
- Annotation layer with arrows, shapes, spotlight effects, blur regions, and step-number overlays
- Advanced cursor emphasis, zoom-and-pan effects for tutorial focus
- Interactive elements: clickable hotspots and call-to-action overlays

### Collaboration & Governance

- Team workspace with folder-based organisation, brand kit (fonts, colours, logo watermark), and role-based permissions
- Approval workflows for formal content review and sign-off before publication
- Shareable links with viewer analytics: watch time, drop-off heatmaps, and engagement tracking
- Version control and comment review on recordings and guides

### Publishing & Integration

- Direct publishing to Confluence, Notion, Zendesk, and Jira
- Slack integration for sharing and notifications
- Embeddable player and guide widgets for help centres and knowledge bases
- SCORM/xAPI export for LMS integration
- Cloud hosting with responsive player for mobile viewing

---

## AI-Native Advantage

Where incumbents bolt AI onto existing workflows (auto-captioning, basic summaries), this project treats AI as a core architectural primitive. A single recording session feeds an AI pipeline that produces both a narrated video and a step-by-step screenshot guide simultaneously. AI-driven semantic step splitting infers logical process units (e.g., "log in" as one step across multiple clicks) rather than relying on raw click detection. Dynamic guide generation can ingest existing wiki pages or handbooks and auto-produce visual tutorials. Process optimisation analysis can review recorded workflows and flag redundant steps or common error points -- capabilities no current tool offers at scale.

---

## Tech Stack & Deployment

- **Deployment modes:** Self-hosted, cloud-hosted, and hybrid options. The self-hosted path targets enterprises with data-residency constraints (healthcare, government, finance) -- a gap no commercial incumbent fills.
- **Capture architecture:** Browser extension (Chrome) for web workflows plus a native desktop application (Windows, Mac, Linux) for full-screen and desktop application recording.
- **Open standards:** SCORM and xAPI for LMS interoperability. Standard embed protocols for knowledge-base integration.
- **Extensibility:** Plugin/API architecture for custom integrations and workflow automation.

---

## Market Context

The screen recording and tutorial creation market spans asynchronous video messaging, process documentation, and video tutorial production. Key incumbents include Loom (Atlassian), Scribe, Camtasia (TechSmith), Descript, and Guidde, all proprietary SaaS offerings priced at $12-33+/user/month for business tiers. Primary buyers are software engineering teams, customer success organisations, L&D departments, and educational institutions. High domain availability and high market demand (rated 4/10 complexity) make this an accessible entry point with strong differentiation through the unified video-plus-documentation approach and self-hosted deployment.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
