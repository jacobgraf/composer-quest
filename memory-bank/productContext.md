# Product Context

This file provides a high-level overview of the project and the expected product that will be created. Initially it is based upon projectBrief.md (if provided) and all other available project-related information in the working directory. This file is intended to be updated as the project evolves, and should be used to inform all other modes of the project's goals and context.
2025-07-29 12:07:49 - Initial Memory Bank creation for Composer Quest game project.

## Project Goal

Build a browser-based game for Laracon 2025 Game Jam called "Composer Quest: The Battle of the Packages". The game simulates a Laravel developer (Composer) managing package dependencies by accepting valid Laravel packages and rejecting fake/malicious ones within a 60-second time limit.

## Key Features

- **Core Gameplay**: Click ✅ to accept valid Laravel packages, ❌ to reject fake ones
- **Falling Package Mechanic**: Packages fall from top with real/fake Laravel package names
- **Scoring System**: Points for correct responses, penalties for mistakes
- **Time Pressure**: 60-second countdown timer
- **Dependency Conflicts**: Special events requiring quick "Resolve" button clicks
- **Audio Feedback**: Applause for correct, dissonant chords for wrong choices
- **Laravel Easter Eggs**: "Taylor Otwell approves!" messages on streaks
- **Local High Score**: localStorage-based leaderboard
- **Mobile & Desktop**: Responsive design using Tailwind CSS

## Overall Architecture

- **Single File Structure**: One index.html with embedded CSS/JS
- **Technology Stack**: Vanilla JavaScript, Tailwind CSS (CDN), plain HTML
- **Assets**: Local images (conductor, package delivery person), audio files
- **Hosting**: Laravel Cloud compatible, no build steps required
- **Game Data**: Hardcoded JSON array of real/fake Laravel packages
- **Styling**: Retro/pixel aesthetic with classical music theme
