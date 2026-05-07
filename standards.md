# Standards & API Reference

> Project: Screen Recording & Tutorial Builder · Generated: 2026-05-07

## Industry Standards & Specifications

### W3C Browser & Media Standards

**Screen Capture (W3C Working Draft)**
- URL: https://www.w3.org/TR/screen-capture/
- Defines `getDisplayMedia()` — the browser API used to capture a user's screen, application window, or browser tab as a video track. This is the foundational API for any browser-based screen recorder. The companion spec at https://w3c.github.io/mediacapture-screen-share/ covers ongoing extensions.

**Media Capture and Streams (W3C)**
- URL: https://w3c.github.io/mediacapture-main/
- Defines the `MediaStream`, `MediaStreamTrack`, and `MediaDevices` interfaces used to acquire camera and microphone input alongside screen captures. Essential for the webcam overlay and audio recording features common in all tools in this category.

**WebRTC 1.0: Real-Time Communication Between Browsers (W3C Recommendation)**
- URL: https://github.com/w3c/webrtc-pc
- Specifies peer-to-peer connection primitives. Relevant for real-time co-viewing, live streaming, and any collaborative synchronous feature (e.g., simultaneous editing during a recording session). The W3C WebRTC Working Group is chartered until September 2026.

**Media Source Extensions (MSE) (W3C)**
- URL: https://www.w3.org/TR/media-source-2/
- Enables JavaScript to feed byte streams to browser media codecs, underpinning adaptive bitrate streaming (DASH, HLS). Relevant for cloud-hosted video playback and progress-seeking without full file download.

**Web Video Text Tracks Format — WebVTT (W3C)**
- URL: https://www.w3.org/TR/webvtt1/
- The W3C standard for timed text tracks in `<video>` elements: captions, subtitles, chapter markers, and metadata cues. MIME type `text/vtt`. This is the primary delivery format for AI-generated captions in browser-based players. Source: https://github.com/w3c/webvtt

**Timed Text Markup Language — TTML2 (W3C Recommendation)**
- URL: https://www.w3.org/TR/2018/REC-ttml2-20181108/
- XML-based caption and subtitle standard used by Netflix, YouTube, Amazon Video, and broadcast workflows. TTML is the preferred interchange format between authoring and distribution systems; RFC 8759 (https://www.rfc-editor.org/rfc/rfc8759.html) defines its RTP payload encoding. Any tool exporting to broadcast or enterprise video platforms should support TTML export alongside WebVTT.

### eLearning & LMS Standards

**SCORM 2004 (4th Edition) — ADL / IMS**
- URL: https://scorm.com/scorm-explained/
- Sharable Content Object Reference Model: the most widely deployed LMS packaging and tracking standard. Defines a ZIP manifest, JavaScript runtime API, and data model for recording completion, score, and time-spent. Tools like Camtasia already export SCORM packages. Any tutorial builder targeting corporate training must support SCORM export.

**xAPI / Experience API (ADL)**
- URL: https://xapi.com/
- Successor to SCORM; sends structured "actor–verb–object" learning statements to a Learning Record Store (LRS), enabling tracking of informal learning, video watch events, and non-LMS contexts. Relevant for analytics features that measure viewer behaviour beyond a single course container.

**cmi5 (ADL / AICC)**
- URL: https://xapi.com/cmi5/
- xAPI Profile that bridges SCORM and xAPI: defines packaging (cmi5.xml manifest), launch, authorization, and reporting rules so LMSs can consume xAPI-tracked content. The specification is maintained at https://aicc.github.io/CMI-5_Spec_Current/. Suitable for modern LMS integrations that need both content packaging and granular activity tracking.

**IMS Learning Tools Interoperability (LTI) 1.3**
- URL: https://www.imsglobal.org/activity/learning-tools-interoperability
- Standard protocol for embedding external learning tools inside LMS course pages (Canvas, Moodle, Blackboard). A tutorial builder that can be embedded as an LTI tool gains distribution through every university and corporate LMS supporting LTI 1.3.

### Accessibility Standards

**Web Content Accessibility Guidelines (WCAG) 2.2 — W3C**
- URL: https://www.w3.org/TR/WCAG22/
- WCAG Level AA is now the US ADA Title II compliance baseline, with a first enforcement deadline of April 24, 2026 for public entities. Key obligations for video content: closed captions for all pre-recorded and live video (Success Criterion 1.2.2/1.2.4), audio descriptions (1.2.5), and transcripts for audio-only content. Any tutorial platform hosted by or used by US public-sector organisations must meet this requirement.

**IPTC Video Metadata Hub v1.4**
- URL: https://iptc.org/std/videometadatahub/userguide/
- The IPTC standard for structuring video metadata, with v1.4 adding dedicated accessibility properties: `altText` (short description for non-visual access) and `extendedDescription` (longer semantic context). Relevant for any platform that stores or exposes video metadata via API.

**audioMD / videoMD (Library of Congress)**
- URL: https://www.loc.gov/standards/amdvmd/
- XML schemas for technical metadata about audio and video digital objects. Used in archival and library contexts; relevant if the platform needs to interoperate with institutional repositories or government video archives.

### Security & Authentication Standards

**OAuth 2.0 (RFC 6749)**
- URL: https://www.rfc-editor.org/rfc/rfc6749
- Industry-standard authorization framework used by virtually every SaaS tool in this category (Loom, Scribe, Guidde) for API access delegation. Essential for building integrations with Slack, Notion, Confluence, and Jira.

**OpenID Connect (OIDC) 1.0**
- URL: https://openid.net/developers/how-connect-works/
- Authentication layer built on OAuth 2.0; provides ID tokens and SSO. Required for enterprise customers who log in via Okta, Azure AD, or Google Workspace SSO — already adopted by Glitter AI and Supademo. Full specification index: https://openid.net/developers/specs/

**GDPR (EU 2016/679)**
- URL: https://gdpr.eu/
- Screen recordings that capture EU residents' on-screen personal data (customer names, email threads, support tickets) are subject to GDPR. Core obligations: purpose limitation, data minimisation, right of erasure, encrypted storage, and Data Processing Agreements (DPAs) with SaaS providers. EDPB video surveillance guidelines: https://www.edpb.europa.eu/sites/default/files/files/file1/edpb_guidelines_201903_video_devices.pdf. Data-residency architecture is necessary but not sufficient for compliance.

**SOC 2 Type II (AICPA)**
- Not a formal ISO/IETF standard, but the de-facto enterprise security certification for SaaS. Scribe, Guidde, and Supademo all hold SOC 2 Type II. Any platform targeting enterprise customers or healthcare (HIPAA-aligned) will face procurement requirements for SOC 2 attestation.

### API Description & Interoperability Standards

**OpenAPI Specification 3.1 (OAS)**
- URL: https://www.openapis.org/
- The universal language for describing RESTful HTTP APIs. ScreenApp explicitly provides an OpenAPI specification and Postman collection for its recording API. Using OAS 3.1 for the project's own API enables auto-generated SDKs, interactive docs (Swagger UI), and validation tooling.

**Model Context Protocol (MCP) — Anthropic (November 2024)**
- URL: https://modelcontextprotocol.io/specification/2025-11-25
- Open protocol for connecting LLM agents to external tools and data sources via standardised tool/resource/prompt primitives. Supademo already ships an MCP server (https://docs.supademo.com/customize/mcp-server) enabling AI agents to update hotspot text, rewrite voiceovers, and generate trackable links at scale. An MCP server is a strong differentiator for an AI-native tutorial builder, enabling integration with Claude, ChatGPT, and Gemini agents.

---

## Similar Products — Developer Documentation & APIs

### Loom (Atlassian)
- **Description:** Leading async video messaging platform with screen + webcam recording, auto-transcription, AI summaries, and deep Atlassian integration.
- **API Documentation:** https://dev.loom.com/docs/record-sdk/getting-started
- **REST Endpoints:** Recordings, Folders, Tags, Comments CRUD; https://dev.loom.com/docs/record-sdk/details/api
- **SDKs/Libraries:** Record SDK (JavaScript); embed SDK for third-party sites
- **Developer Guide:** https://dev.loom.com/docs/record-sdk/getting-started
- **Standards:** REST/JSON
- **Authentication:** OAuth 2.0

### Descript
- **Description:** Transcript-first video editor with AI voice cloning, AI avatar presenters, and generative video creation from text prompts.
- **API Documentation:** https://docs.descriptapi.com/
- **Developer Guide (beta):** https://help.descript.com/hc/en-us/articles/43370311322509-Descript-API-beta
- **SDKs/Libraries:** HTTP REST (no official SDK); n8n and Zapier integration nodes; Descript MCP for Claude Code
- **Standards:** REST/JSON; rate-limited with `Retry-After` headers (429 responses)
- **Authentication:** Bearer token
- **Notes:** Lightweight import/export API; not a full editing API. Automation of Underlord AI edits is supported.

### Scribe (Scribe Labs)
- **Description:** Auto-workflow capture tool that generates annotated screenshot guides from observed browser and desktop activity.
- **API Documentation:** https://developer.scribelabs.ai/overview/introduction
- **Standards:** GraphQL (company data) + REST (PDF/Excel document sharing and JSON retrieval)
- **Authentication:** Token-based

### Guidde
- **Description:** AI-narrated video tutorial generator from workflow capture; 200+ voices in 50+ languages with enterprise privacy controls.
- **API Documentation:** No publicly documented developer API found; integrations primarily via native connectors (Slack, Jira, Notion, Zendesk) and embed code.
- **Standards:** Proprietary integration connectors
- **Notes:** Guidde does not appear to offer a public REST API as of May 2026. Integration is via their native connectors and embed URLs.

### ScreenApp
- **Description:** Browser-based screen recording with AI transcription and meeting bot; specialised for meeting capture and summary.
- **API Documentation:** https://screenapp.io/help/api-documentation
- **Developer Guide:** https://screenapp.io/features/meet-recording-api
- **REST Endpoints:** `POST /meetings/record`, `GET /recordings/{id}`, `GET /recordings/{id}/download`
- **SDKs/Libraries:** Open-source meeting bot: https://github.com/screenappai/meeting-bot
- **Standards:** REST/JSON; OpenAPI specification and Postman collection provided
- **Authentication:** Bearer token (`Authorization: Bearer <api_key>`)
- **Webhooks:** Real-time transcript and summary delivery via webhooks on processing completion

### Supademo
- **Description:** Interactive demo recorder with AI voiceovers, conditional branching, video hotspots, and MCP server for AI agent workflows.
- **API Documentation:** https://docs.supademo.com/admin-and-billing/integrations/data-and-api/developer-docs
- **MCP Server:** https://docs.supademo.com/customize/mcp-server
- **Standards:** REST/JSON; MCP (Model Context Protocol)
- **Authentication:** API key
- **Notes:** Supademo's MCP server is a notable differentiator — it allows AI agents to update hotspot text, rewrite voiceovers, replace steps, and generate trackable links in bulk without manual editing.

### Wistia
- **Description:** Professional video hosting with deep analytics (heatmaps, per-viewer engagement), live streaming, and in-player lead capture (Turnstile).
- **API Documentation:** https://docs.wistia.com/
- **Player API:** https://docs.wistia.com/docs/javascript-player-api
- **Aurora Embed API:** https://docs.wistia.com/docs/player-embed-api
- **SDKs/Libraries:** npm packages for React, Next.js, Angular embedding; Data API, Stats API, Upload API
- **Developer Guide:** https://support.wistia.com/en/collections/5604193-developer
- **Standards:** REST/JSON; Web Components; JavaScript Player API
- **Authentication:** OAuth 2.0 and API tokens

### OBS Studio
- **Description:** Free and open-source screen/audio recording and live streaming with scene composition; GPL-2.0 licensed.
- **API Documentation:** https://obsproject.com/kb/developer-guide
- **WebSocket Protocol:** https://github.com/obsproject/obs-websocket (bundled since OBS 28.0)
- **Protocol Spec:** https://github.com/obsproject/obs-websocket/blob/master/docs/generated/protocol.md
- **SDKs/Libraries:** `obs-websocket-js` (npm); `obsws-python` (PyPI); Dart, Go, Rust libraries available
- **Standards:** WebSocket (RFC 6455); JSON-RPC style protocol; default port 4455
- **Authentication:** Password-protected WebSocket (auto-generated on first load)
- **Notes:** OBS WebSocket enables full remote control of recording, scene switching, and streaming from external applications. Useful for headless or automated screen capture workflows.

---

## Notes

**Emerging and Evolving Areas**

- **MCP adoption in the tutorial space is nascent.** Supademo launched an MCP server in early 2026, but most competitors (Loom, Scribe, Guidde) have not. This is an active area with high differentiation potential.
- **WCAG 2.2 / ADA compliance deadlines are imminent.** The April 2026 and April 2027 enforcement deadlines for US public entities make accessible video output (captions, transcripts, audio descriptions) a compliance requirement, not just a feature.
- **cmi5 is gradually replacing SCORM in enterprise LMS integrations**, but SCORM 2004 remains more widely installed. Any LMS integration should support both for the next 3–5 years.
- **No ISO standard specifically covers screen recording or tutorial authoring.** The closest relevant ISO standards are ISO 24138:2024 (International Standard Content Code, for digital content identification) and general IT security frameworks (ISO 27001 for information security, relevant to data-residency and SOC 2 alignment).
- **Guidde's public API gap** is notable: unlike Loom, ScreenApp, Descript, and Supademo, Guidde does not appear to expose a documented public REST API. This limits enterprise automation workflows and may be a competitive vulnerability.
- **TTML vs. WebVTT**: WebVTT is the browser-native standard and simpler to implement; TTML is required for broadcast and some enterprise video platforms. A well-designed caption export system should support both.
