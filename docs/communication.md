MihonRPC — Android Communication

1. Overview

MihonRPC uses Android inter-process communication (IPC) to exchange reading events between Mihon and the MihonRPC Companion.

The communication system must be secure, reliable and compatible with modern Android versions.

2. Proposed Architecture

The proposed communication architecture consists of:

- Mihon event producer
- MihonRPC Bridge
- MihonRPC Companion Service
- Companion event processor

3. Communication Technology

The proposed implementation uses:

- Android Bound Service
- Android Messenger
- Message-based event delivery

Messenger will provide a structured communication channel between the two applications.

This approach is a proposal and must be validated through implementation and testing.

4. Message Flow

1. Mihon detects a reading event.
2. The MihonRPC Bridge processes the event.
3. Privacy filters are applied.
4. The event is sent to the companion.
5. The companion validates and processes the message.
6. The Presence Manager updates Discord when appropriate.

5. Connection Lifecycle

The companion should:

- Detect when Mihon connects.
- Handle unexpected disconnections.
- Request the current state after reconnection.
- Avoid processing duplicate events.
- Clear stale presence when the reading session ends.

6. Security

- Use explicit Android components.
- Restrict access to authorized applications.
- Validate incoming messages.
- Never transmit Discord credentials.
- Minimize transmitted information.
- Avoid exporting components unnecessarily.

The final implementation must verify Android IPC permissions and application identity.

7. Alternative Technologies

The following alternatives have been considered:

- BroadcastReceiver
- Direct Bound Service communication
- Messenger-based communication

The proposed initial approach is Bound Service with Messenger.

8. Current Status

Status: Proposed — not implemented.

The final IPC implementation is subject to compatibility and security testing.