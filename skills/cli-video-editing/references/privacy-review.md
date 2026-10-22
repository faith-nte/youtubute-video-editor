# Privacy review for video edits

Use this reference when a user asks to anonymize a recording, redact company or account details, or prepare a screen recording for public sharing.

## Review the whole recording

Build a timeline of scenes and screen changes, not just a handful of attractive frames. Use a scene-change scan and sampled frames or contact sheets to find the main states, then inspect sensitive sections at short intervals and around every transition. A dropdown, tab preview, account switcher, toast, notification, or terminal output may be visible for only a fraction of a second. Check the start and end of every overlay against the actual frame timing.

Inspect the speech transcript and captions for spoken names, email addresses, domains, company names, account details, and other identifiers. Include metadata, title cards, lower thirds, subtitles, filenames, and output metadata in the review when relevant. If ASR is used, correct likely transcription mistakes and manually inspect the sensitive intervals; transcription alone does not prove that speech is anonymous.

## Choose the redaction method

- Use an opaque mask for values that must be hidden. Blur, pixelation, or a translucent shape may leave short text legible.
- Replace a sensitive screen with a clean, labelled summary when many values move or scroll. Use reserved example domains such as `example.com`; do not copy a live company's identifying detail into a replacement panel.
- Preserve a separate presenter camera layer when it is safe and useful. Composite it above the redaction surface and inspect its bounds so no strip of the original screen peeks around it.
- If the camera frame moves, track it or cover the entire screen instead of relying on a fixed hole in the mask.
- For spoken identifiers, redact the corresponding audio or replace the relevant narration/caption only when that fits the user's request. Keep the edit synchronized and disclose a substantive wording change.

## Verify the export

Review frames from the encoded output rather than relying only on the filter graph or source preview. Check several frames before and after each redaction interval, scene boundary, and briefly visible UI element. Decode the finished file and inspect its streams, duration, audio continuity, and captions. A full-screen replacement can be safer than a complex animated mask when the source UI changes too quickly to track reliably.
