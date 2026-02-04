# TubeStamp

> Bookmark specific moments in YouTube videos.

TubeStamp is a personal bookmark manager that solves the problem of losing context in long YouTube videos. Instead of saving a whole video to a "Watch Later" list, TubeStamp lets you save the exact timestamp (e.g., 14:35) where the interesting content happens, add your own notes, and tag it for later reference.

## Tech Stack

- **Framework:** TanStack Start (React + SSR)
- **Database:** Drizzle ORM (SQLite)
- **Styling:** Tailwind CSS + shadcn/ui
- **Runtime:** Node.js / Bun

## Features

- **Smart Parsing:** Paste a YouTube link, and it automatically extracts the video ID and timestamp.
- **Timestamped Bookmarks:** Save clips starting at the exact second you want.
- **Embedded Player:** Watch your saved clips directly in the app without navigating away.
- **Tagging & Search:** Organize your library with tags and find clips instantly.
- **Notes:** Add context to why you saved the clip.

## Getting Started

1. **Clone the repository**
   ```bash
   git clone <repo-url>
   cd tubestamp
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or pnpm install
   ```

3. **Setup Environment**
   Copy `.env.example` to `.env` and configure your database URL.
   ```bash
   cp .env.example .env
   ```

4. **Initialize Database**
   ```bash
   npm run db:push
   ```

5. **Run Development Server**
   ```bash
   npm run dev
   ```

## Documentation

- [TASKLIST.md](./TASKLIST.md) - Track project progress
- [LEARNINGS.md](./LEARNINGS.md) - Developer notes and architectural decisions
- [.dev0/RULES.md](./.dev0/RULES.md) - AI coding guidelines