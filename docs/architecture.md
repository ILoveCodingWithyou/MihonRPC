MihonRPC — Architecture

1. Overview

MihonRPC aims to integrate Discord Rich Presence into Mihon, an open-source manga reader for Android.

The project is designed around two main components:

- Mihon integration: Detects reading activity and provides manga information.
- Companion application: Receives reading events and manages Discord Rich Presence.

The architecture is experimental and subject to Discord SDK eligibility and technical verification.

2. System Architecture

+----------------------+
|        Mihon         |
|                      |
|  ReaderViewModel     |
|  Manga information   |
|  Chapter information|
+----------+-----------+
           |
           | Reading events
           v
+----------------------+
|   MihonRPC Bridge    |
|                      |
|  Event processing    |
|  Privacy filtering   |
|  State management    |
+----------+-----------+
           |
           | Explicit Android communication
           v
+----------------------+
|   MihonRPC Companion|
|                      |
|  Presence manager    |
|  Reading timer       |
|  User settings       |
+----------+-----------+
           |
           | Official integration,
           | subject to approval
           v
+----------------------+
|       Discord        |
|                      |
|   Rich Presence      |
+----------------------+

3. Reading Events

The integration should eventually support these events:

Event| Description
READING_STARTED| User starts reading
PAGE_CHANGED| Current page changes
CHAPTER_CHANGED| User changes chapter
READING_PAUSED| Reading is paused
READING_RESUMED| Reading resumes
READING_STOPPED| Reading session ends

4. Manga Information

The following information may be provided:

- Manga title
- Chapter title or number
- Author, if available
- Cover artwork, if available
- Reading duration

5. Privacy and Safety

Privacy must be a core design principle.

Planned protections:

- Incognito mode
- NSFW content filtering
- User-controlled presence visibility
- No collection of Discord user tokens
- No unnecessary personal data storage
- Clear presence when reading stops

6. Technology Stack

- Kotlin
- Android SDK
- Gradle
- Coroutines and Flow
- Discord Social SDK, subject to eligibility and compatibility verification

7. Development Principles

- Modular architecture
- Minimal changes to Mihon
- Explicit communication between components
- Privacy-first design
- Open-source development
- No undocumented Discord API usage

8. Current Status

Version: 0.0.1

Phase: Research and architecture preparation

No production Discord integration has been implemented yet.