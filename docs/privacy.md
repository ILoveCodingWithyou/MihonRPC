MihonRPC — Privacy

1. Privacy Principles

MihonRPC is designed around one core principle:

The user decides what information is shared.

Privacy must be considered from the beginning of development, not added as an afterthought.

2. Default Behavior

- Rich Presence should be disabled by default.
- No manga information should be shared until the user enables it.
- Reading history and library contents must never be shared.
- Users must be able to disable Rich Presence at any time.

3. Incognito Mode

When Incognito Mode is enabled:

- No manga details are sent to Discord.
- The current Rich Presence is cleared.
- Reading activity is not retained beyond what is necessary for the active session.

4. NSFW and Sensitive Content

MihonRPC should include a content-filtering system.

- Titles marked as NSFW or adult by Mihon's metadata should have their details hidden.
- Manga titles, chapters, authors and cover artwork should not be displayed for filtered content.
- Unknown or unclassified content should be handled conservatively.
- Content classification should rely on available metadata, not assumptions based only on manga titles.

5. User Controls

Users should be able to:

- Enable or disable Rich Presence.
- Enable or disable Incognito Mode.
- Hide sensitive content.
- Choose which information is displayed:
  - Manga title
  - Chapter
  - Author
  - Cover artwork
  - Reading duration
- Clear their current presence immediately.

6. Data Handling

MihonRPC aims to minimize data collection.

- No Discord user tokens or passwords.
- No collection of Discord account credentials.
- No upload of reading history to external servers.
- Reading events should be processed locally between Mihon and the companion application.
- Any persistent data storage must be documented and minimized.

7. Presence Lifecycle

Rich Presence should be cleared when:

- The user closes the reader.
- Incognito Mode is enabled.
- Rich Presence is disabled.
- The connection between Mihon and the companion application is interrupted.
- The reading session ends.

The application should also handle unexpected interruptions to prevent stale activity from remaining visible.

8. Transparency

Before release, MihonRPC must provide clear information about:

- What information is shared.
- When information is shared.
- Who may see the Discord activity, depending on Discord's privacy settings.
- How users can disable or clear their presence.

9. Project Status

Status: Planned — not implemented.

This document describes intended privacy behavior. It does not claim that these protections have already been implemented.