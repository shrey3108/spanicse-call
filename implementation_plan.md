# Implementation Plan - Premium AI Receptionist UI Upgrade

This plan upgrades the simple dental receptionist MVP into a premium, state-of-the-art dark-mode interface with glassmorphic elements and an interactive AI voice orb that reacts to volume inputs.

## User Review Required

> [!NOTE]
> The layout structure and functionalities (calling, transcripts, volume events, n8n webhook tools integration) will remain exactly the same, but the styling will be completely revamped to look premium and modern.

## Proposed Changes

### [Component Name] Frontend Styling & Layout

#### [MODIFY] [index.html](file:///c:/OneDriveTemp/Desktop/New%20folder%20(8)/index.html)
We will rewrite the `<style>` block and add minor decorative elements (like background blur glow blobs) to the HTML.

- **Theme**: Deep dark space theme (`#090d16` background) with cyan and indigo accents.
- **Glassmorphism**: `.card` will be a frosted glass panel using `backdrop-filter: blur(20px)` and semi-transparent borders.
- **AI Voice Orb**:
  - Rewrite `.call-btn` into a glowing circular AI Voice Orb.
  - Idle state: Indigo/purple breathing pulse animation.
  - Connecting state: High-frequency yellow-orange aura glow.
  - Active call state: Real-time dynamic scale transformation matching the Vapi `volume-level` value, with a vibrant green/cyan cyan glow.
- **Transcript**: Redesigned as clean, responsive chat bubbles floating above the glass.
- **Features Grid**: Translucent glass panels with hover translation and glow.

## Verification Plan

### Manual Verification
- Deploy/run the local server using `http://localhost:8080`.
- Verify the mobile responsive layout in desktop and mobile viewports.
- Click the AI Voice Orb to start a call; verify that the connection state and active speaking state show the dynamic pulsing animations.
