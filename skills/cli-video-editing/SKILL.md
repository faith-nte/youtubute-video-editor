---
name: cli-video-editing
description: Edit existing videos from the command line, especially when a recording needs privacy redaction, clearer captions, scene transitions, or a shareable export.
---

# CLI video editing

Use this skill when asked to edit an existing recording or prepare it for sharing. Prefer command-line editing when requested. Start with the source and produce a separate export; keep the original available for recovery.

For a specific platform or project, first check whether a connected API, native CLI, or CLI-Hub adapter can access the source or project cleanly. Use the CLI-Hub discovery instructions when platform-specific tooling could materially help. Use FFmpeg and ffprobe for local media inspection, compositing, subtitles, transitions, encoding, and stream checks. Use a browser only when the requested source cannot be reached through an available CLI or API, and follow the user's choice if they request browser or command-line editing.

Inspect the full recording before deciding what to cut or conceal. Establish duration, resolution, frame rate, audio and subtitle streams; review scene changes and a contact sheet or representative frames; inspect the transcript when dialogue or caption edits matter. Pay extra attention to scene boundaries, tab switches, popovers, terminal flashes, and other short-lived screen content.

When privacy redaction is requested, identify direct and indirect identifiers in both picture and sound: names, company identity, email addresses, domains, account or case IDs, URLs, phone numbers, browser tabs and bookmarks, document or terminal content, file paths, notifications, and spoken identifiers. Review the whole timeline, including brief flashes. Preserve recognizable original application screens when they provide useful evidence; blur or redact identifying values in place so platform names, navigation, and the real workflow remain visible. Avoid replacing an entire sequence with reconstructed slides, which can make genuine screen-recorded evidence feel less credible. Use an opaque mask when text must be impossible to recover or when a blur would leave it legible. Replace a screen with a clearly labelled, anonymized example only when moving or dense private content cannot be safely redacted in place. If the recording has a separate presenter window, keep that layer visible while covering the screen recording; make sure the overlay does not expose content around its edges or during movement. If the presenter window moves, track it or replace the full screen area safely.

Keep the edit within the requested scope. Preserve narration, original timing, and useful content unless the user asks for cuts or restructuring. If an on-screen claim conflicts with verified evidence, use a brief, factual clarification rather than silently changing the story. Do not imply a result, policy, or timeline is guaranteed based on one example.

For captions, correct recognizable technical terms against the recording and context, retain the speaker's meaning, and keep lines readable and synchronized. Cover the full video, including the outro. Provide a separate SRT when useful; avoid leaving a raw subtitle stream in an export if it would duplicate or reveal text under burned-in captions. Use a consistent, legible style with sufficient contrast.

Use restrained transitions at actual scene changes. Short fades or dissolves should not interrupt speech or change the video duration. Preserve audio unless the requested edit requires a change. Keep FFmpeg filter timing explicit so each transition or overlay only affects its intended interval.

Before delivery, inspect representative frames from the finished export, especially immediately before, during, and after every privacy overlay and scene transition. Confirm the file decodes, duration and audio match the intended edit, captions reach the ending, and no original account material remains visible. Give the user the finished file and any requested caption file, and state what was changed in plain language.

For a detailed privacy sweep, read [references/privacy-review.md](references/privacy-review.md).
