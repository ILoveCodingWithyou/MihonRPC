MihonRPC — Event Protocol

1. Overview

MihonRPC uses an event-driven communication system between Mihon and the MihonRPC Companion.

Mihon acts as the event producer, while the companion receives and processes reading events.

The protocol should be lightweight, explicit and privacy-oriented.

2. Event Types

Event| Description
READING_STARTED| A reading session begins
PAGE_CHANGED| The current page changes
CHAPTER_CHANGED| The user opens another chapter
READING_PAUSED| Reading is temporarily paused
READING_RESUMED| Reading resumes
READING_STOPPED| The reading session ends
STATE_SYNC| Synchronizes the current reading state

3. Event Structure

Every event should follow a consistent structure.

{
  "protocol_version": 1,
  "event_id": "unique-event-id",
  "session_id": "unique-session-id",
  "event_type": "READING_STARTED",
  "timestamp": 1795360000,
  "data": {
    "manga_title": "Example Manga",
    "chapter_title": "Chapter 12",
    "author": "Example Author"
  }
}

Fields:

- "protocol_version": Protocol version.
- "event_id": Unique identifier for the event.
- "session_id": Identifier shared by events belonging to the same reading session.
- "event_type": Type of event.
- "timestamp": Event creation time.
- "data": Event-specific information.

The example values are illustrative only.

4. Event Behavior

READING_STARTED

Sent when the user starts reading a manga.

May include manga title, chapter information, author and cover reference.

PAGE_CHANGED

Sent when the reader moves to another page.

The companion should not publish page numbers to Discord by default.

CHAPTER_CHANGED

Sent when the current chapter changes.

Updates the manga and chapter information displayed by the companion.

READING_PAUSED

Sent when reading is temporarily suspended.

The companion should stop counting active reading time.

READING_RESUMED

Sent when reading resumes.

The companion may continue the existing session timer.

READING_STOPPED

Sent when the reading session ends.

The companion should clear the Rich Presence.

STATE_SYNC

Sent when the companion requests or needs the current reading state.

It allows the two components to recover synchronization after interruptions.

5. Session Management

- Every reading session has a unique session ID.
- Events belonging to the same session share that ID.
- Events should be processed in timestamp order where possible.
- Duplicate events should not cause duplicate state changes.
- A new session should invalidate the previous active session.
- The companion should handle missing or delayed events safely.

6. Privacy Rules

- Events must not contain Discord credentials.
- Page information must not be published by default.
- Sensitive manga metadata must be filtered before publication.
- Incognito mode must prevent manga details from reaching Discord.
- Only information necessary for the current session should be transmitted.

7. Communication

The initial design uses explicit Android inter-process communication between Mihon and the companion.

The exact Android mechanism is still to be evaluated.

Possible approaches include:

- Bound Android Service
- Explicit Broadcasts
- Messenger-based communication

The final choice must consider Android background execution restrictions, security and reliability.

8. Protocol Versioning

The protocol uses an explicit version field.

Changes to the event structure should preserve compatibility where possible.

Breaking changes require a protocol version update.

9. Current Status

Status: Proposed — not implemented.

The event protocol is subject to technical testing and refinement.